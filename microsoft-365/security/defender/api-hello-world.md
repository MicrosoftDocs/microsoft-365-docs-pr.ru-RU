---
title: Hello World for Microsoft 365 Defender REST API
description: Узнайте, как создать приложение и использовать маркер для доступа к API Защитника Microsoft 365
keywords: app, token, access, aad, app, application registration, powershell, script, global administrator, permission, Microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ffdcf91da6b5def7d63e5fdb8ff51ddbdb1ec550
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072757"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Hello World for Microsoft 365 Defender REST API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

## <a name="get-incidents-using-a-simple-powershell-script"></a>Получать инциденты с помощью простого сценария PowerShell

На завершение этого проекта должно пройти от 5 до 10 минут. Эта оценка времени включает регистрацию приложения и применение кода из сценария образца PowerShell.

### <a name="register-an-app-in-azure-active-directory"></a>Регистрация приложения в Azure Active Directory

1. Во входе [в Azure](https://portal.azure.com) в качестве пользователя с **ролью глобального администратора.**

2. Перейдите к **регистрации приложений Azure Active**  >  **Directory**  >  **.**

   ![Изображение Microsoft Azure и навигация для регистрации приложений](../../media/atp-azure-new-app2.png)

3. В форме регистрации выберите имя приложения, а затем выберите **Register**. Выбор URI перенаправления необязателен. Для завершения этого примера не потребуется один пример.

4. На странице приложения выберите **API Permissions Add**  >  **permission**  >  **API,** которые моя организация использует >, введите Microsoft Threat Protection и выберите **Microsoft Threat Protection**. Теперь ваше приложение может получить доступ к Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* — это прежнее имя защитника Microsoft 365, которое не будет отображаться в исходном списке. Чтобы увидеть его, необходимо приступить к написанию его имени в текстовом окне.
   ![Изображение выбора разрешений API](../../media/apis-in-my-org-tab.PNG)

   - Выберите **разрешения приложения**  >  **Incident.Read.All** и добавьте **разрешения.**

   ![Изображение доступа к API и выбора API](../../media/request-api-permissions.PNG)

5. Выберите **согласие администратора Гранта**. Каждый раз, когда вы добавляете разрешение, необходимо выбрать согласие администратора **Гранта,** чтобы оно вступает в силу.

    ![Изображение разрешений гранта](../../media/grant-consent.PNG)

6. Добавьте секрет в приложение. Выберите **сертификаты &,** добавьте описание в секрет, а затем **добавьте**.

    > [!TIP]
    > После выбора **Добавить** выберите **скопируйте сгенерированную секретную ценность.** Вы не сможете получить секретное значение после того, как вы уйдете.

    ![Изображение ключа создания приложения](../../media/webapp-create-key2.png)

7. Запись ID приложения и ID клиента в безопасном месте. Они перечислены в статье **Обзор на** странице приложения.

   ![Изображение созданного id приложения](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>Получите маркер с помощью приложения и используйте маркер для доступа к API

Дополнительные сведения о маркерах Azure Active Directory см. в руководстве [Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

> [!IMPORTANT]
> Хотя в примере в этом демо-приложении рекомендуется вклеить  секретное значение для целей тестирования, никогда не следует секретов жесткого кода в приложение, запущенное в производстве. Третья сторона может использовать ваш секрет для доступа к ресурсам. Вы можете помочь сохранить секреты вашего приложения в безопасности с помощью [Хранилища ключей Azure.](/azure/key-vault/general/about-keys-secrets-certificates) Пример того, как защитить приложение, см. в примере Управление секретами в серверных приложениях [с помощью хранилища ключей Azure.](/learn/modules/manage-secrets-with-azure-key-vault/)

1. Скопируйте сценарий ниже и вклейте его в любимый текстовый редактор. Сохраните как **Get-Token.ps1**. Вы также можете запустить код как есть в ISE PowerShell, но его следует сохранить, так как нам потребуется выполнить его снова, когда мы используем сценарий для получения инцидентов в следующем разделе.

    Этот скрипт будет создавать маркер и сохранять его в рабочей папке под именем *Latest-token.txt*.

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

    $resourceAppIdUri = 'https://api.security.microsoft.com'
    $oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"
    $authBody = [Ordered] @{
      resource = $resourceAppIdUri
      client_id = $clientId
      client_secret = $appSecret
      grant_type = 'client_credentials'
    }
    $authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
    $token = $authResponse.access_token
    Out-File -FilePath "./Latest-token.txt" -InputObject $token
    return $token
    ```

#### <a name="validate-the-token"></a>Проверка маркера

1. Скопируйте и вклейте маркер, полученный в [JWT,](https://jwt.ms) чтобы расшифровать его.
1. *JWT* — это *веб-маркер JSON.* Декодированный маркер будет содержать ряд элементов или утверждений в формате JSON. Убедитесь, что *утверждение ролей* в расшифроваемом маркере содержит нужные разрешения.

    На следующем изображении можно увидеть расшифровав маркер, приобретенный из приложения, с разрешениями и ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` разрешениями:

    ![Изображение jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>Получить список последних инцидентов

Сценарий ниже будет использовать **Get-Token.ps1** для доступа к API. Затем он извлекает список инцидентов, которые были обновлены в течение последних 48 часов, и сохраняет список в качестве JSON-файла.

> [!IMPORTANT]
> Сохраните этот скрипт в той же папке, что и **Get-Token.ps1.**

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

Все готово! Вы успешно:

- Создано и зарегистрировано приложение.
- Предоставлено разрешение для этого приложения на чтение оповещений.
- Подключение к API.
- Для возврата инцидентов, обновленных за последние 48 часов, используется скрипт PowerShell.

## <a name="related-articles"></a>Связанные статьи

- [Обзор API защитника Microsoft 365](api-overview.md)
- [Доступ к API защитника Microsoft 365](api-access.md)
- [Создание приложения для доступа к Microsoft 365 Defender без пользователя](api-create-app-web.md)
- [Создание приложения для доступа к API Защитника Microsoft 365 от имени пользователя](api-create-app-user-context.md)
- [Создание приложения с несколькими партнерами-партнерами для API Защитника Microsoft 365](api-partner-access.md)
- [Управление секретами в приложениях сервера с помощью хранилища ключей Azure](/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2.0 Авторизация для входов пользователей и доступа к API](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)