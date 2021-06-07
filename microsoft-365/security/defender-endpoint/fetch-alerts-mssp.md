---
title: Извлечение оповещений клиента MSSP
description: Узнайте, как получать оповещения от клиента-клиента
keywords: поставщик управляемых служб безопасности, mssp, настройка, интеграция
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 456507533265bc085adc1008f3264e123569a6ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770773"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a>Извлечение оповещений клиента MSSP

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
>Это действие будет принимать msSP.


Существует два способа получения оповещений:
- Использование метода SIEM
- Использование API

## <a name="fetch-alerts-into-your-siem"></a>Извлечение оповещений в SIEM

Для получения оповещений в системе SIEM необходимо предпринять следующие действия:

Шаг 1. Создание сторонних приложений

Шаг 2. Получить доступ и обновить маркеры от клиента клиента
 
Шаг 3: разрешить приложение на Центр безопасности в Microsoft Defender
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a>Шаг 1. Создание приложения в Azure Active Directory (Azure AD)
 
Необходимо создать приложение и предоставить ему разрешения на получение оповещений от клиента клиента Microsoft Defender для клиента Endpoint.

1. Во входе на [портал Azure AD](https://aad.portal.azure.com/).

2. Выберите **Azure Active Directory**  >  **регистрации приложений.**
 
3. Нажмите **кнопку Новая регистрация**.

4. Укажите следующие значения:

    - Имя: \<Tenant_name\> соединителем SIEM MSSP (замените Tenant_name на имя отображения клиента)
 
    - Поддерживаемые типы учетных записей. Учетная запись только в этом организационном каталоге 
    - Перенаправление URI: Выберите Веб и введите `https://<domain_name>/SiemMsspConnector` (замените <domain_name> на имя клиента)

5. Нажмите **Зарегистрировать**. Приложение отображается в списке собственных приложений.

6. Выберите приложение, а затем щелкните **Обзор**.

7. Скопируйте значение из поля ID приложения **(клиента)** в безопасное место, это потребуется на следующем шаге.

8. Выберите **& сертификата в** новой панели приложений.

9. Нажмите **кнопку Новый секрет клиента**.

    - Описание. Введите описание ключа.
    - Истекает срок действия: выберите **в 1 год**

 
10. Нажмите **кнопку Добавить,** скопируйте значение секрета клиента в безопасное место, это потребуется на следующем шаге.
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a>Шаг 2. Получить доступ и обновить маркеры от клиента клиента
В этом разделе вы можете узнать, как использовать сценарий PowerShell для получения маркеров от клиента. Этот скрипт использует приложение на предыдущем этапе для получения доступа и обновления маркеров с помощью кода авторизации OAuth Flow.

После предоставления учетных данных необходимо предоставить согласие на приложение, чтобы приложение было задано в клиенте клиента.


1. Создайте новую папку и назови ее: `MsspTokensAcquisition` .

2. Скачайте [модуль LoginBrowser.psm1](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) и сохраните его в `MsspTokensAcquisition` папке.

    >[!NOTE]
    >В строке 30 замените `authorzationUrl` `authorizationUrl` .

3. Создайте файл со следующим содержимым и сохраните его с именем `MsspTokensAcquisition.ps1` в папке:
    ```
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " -----------------------------------  TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " -----------------------------------  REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken 
    ```
4. Откройте командную подсказку PowerShell повышенной мощности в `MsspTokensAcquisition` папке.

5. Выполните следующую команду: `Set-ExecutionPolicy -ExecutionPolicy Bypass`

6. Введите следующие команды: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`
 
    - \<client_id\>Замените **ID приложения (клиента),** который вы получили на предыдущем шаге.
    - Замените \<app_key\> секрет **клиента,** созданный на предыдущем этапе.
    - Замените \<customer_tenant_id\> с клиентом **tenant ID**. 
 

7. Вам будет предложено предоставить учетные данные и согласие. Игнорировать перенаправление страницы.

8. В окне PowerShell вы получите маркер доступа и маркер обновления. Сохраните маркер обновления, чтобы настроить соединитель SIEM. 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a>Шаг 3. Разрешить применение в Центр безопасности в Microsoft Defender
Необходимо разрешить приложение, созданное в Центр безопасности в Microsoft Defender.
 
Чтобы разрешить приложение, необходимо иметь разрешение **на** управление настройками системы портала. В противном случае необходимо попросить клиента разрешить приложение для вас.

1. Перейдите `https://securitycenter.windows.com?tid=<customer_tenant_id>` к \<customer_tenant_id\> (замените его ИД клиента.

2. Щелкните **Параметры**  >  **SIEM**. 

3. Выберите **вкладку MSSP.**

4. Введите **ID приложения** с первого шага и ваш **ID клиента**.

5. Нажмите **кнопку Авторизировать приложение**. 

 
Теперь можно скачать соответствующий файл конфигурации для SIEM и подключиться к API Defender для конечной точки. Дополнительные сведения см. в дополнительных сведениях о том, как вывести [оповещения в инструменты SIEM.](configure-siem.md)
 

- В файле свойств конфигурации ArcSight / Splunk Authentication Properties напишите ключ приложения вручную, задав секретное значение.
- Вместо приобретения маркера обновления на портале используйте скрипт предыдущего шага, чтобы приобрести маркер обновления (или приобрести его другими средствами).

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a>Извлечение оповещений клиента MSSP с помощью API
 
Сведения о том, как получать оповещения с помощью API REST, см. в руб. в руб. [Pull alerts using REST API.](pull-alerts-using-rest-api.md)


## <a name="see-also"></a>См. также
- [Предоставление MSSP доступа к порталу](grant-mssp-access.md)
- [Получение доступа к порталу клиентов MSSP](access-mssp-portal.md)
- [Настройка уведомлений оповещений](configure-mssp-notifications.md)
