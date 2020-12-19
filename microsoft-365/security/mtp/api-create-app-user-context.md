---
title: Создание приложения для доступа к API Microsoft 365 Defender от имени пользователя
description: Узнайте, как получить доступ к API Microsoft 365 Defender от имени пользователя.
keywords: доступ от имени пользователя, API, приложения, пользователя, маркер доступа, маркер,
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f1c0caea9ff7810f79026c789241a4f250ec5303
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719420"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>Создание приложения для доступа к API Microsoft 365 Defender от имени пользователя

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

На этой странице описывается создание приложения для получения программного доступа к Защитнику Microsoft 365 от имени одного пользователя.

Если вам нужен программный доступ к Microsoft 365 Defender без определенного пользователя (например, если вы пишете фоновое приложение или программу-программу), см. статью "Создание приложения для доступа к [Microsoft 365 Defender](api-create-app-web.md)без пользователя". Если вам нужно предоставить доступ нескольким клиентам (например, если вы обслуживаете крупную организацию или группу клиентов), см. статью "Создание приложения с партнерским доступом к API Защитника [Microsoft 365".](api-partner-access.md) Если вы не знаете, какой тип доступа вам нужен, см. ["Начало работы".](api-access.md)

Защитник Microsoft 365 предоставляет большую часть своих данных и действий с помощью набора программных API. Эти API помогают автоматизировать процессы и использовать возможности Защитника Microsoft 365. Для доступа к этому API требуется проверка подлинности OAuth2.0. Дополнительные сведения см. в потоке кода авторизации [OAuth 2.0.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

Как правило, для использования этих API необходимо сделать следующее:

- Создайте приложение Azure Active Directory (Azure AD).
- Получение маркера доступа с помощью этого приложения.
- Используйте маркер для доступа к API Защитника Microsoft 365.

В этой статье объясняется, как:

- Создание приложения Azure AD
- Получите маркер доступа к Защитнику Microsoft 365
- Проверка маркера

> [!NOTE]
> При доступе к API Microsoft 365 Defender от имени пользователя необходимы правильные разрешения приложения и разрешения пользователя.

> [!TIP]
> Если у вас есть разрешение на выполнение действия на портале, у вас есть разрешение на выполнение действия в API.

## <a name="create-an-app"></a>Создать приложение

1. Во sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.

2. Перейдите к регистрации нового приложения **Azure Active Directory.**  >    >  

   ![Изображение Microsoft Azure и переход к регистрации приложений](../../media/atp-azure-new-app2.png)

3. В форме выберите имя приложения и введите следующие сведения для URI перенаправления, а затем выберите **"Регистрация".**

   ![Изображение окна "Создание приложения"](../../media/nativeapp-create2.PNG)

   - **Тип приложения:** Общедоступный клиент
   - **URI перенаправления:**https://portal.azure.com

4. На странице приложения выберите API "Разрешения для добавления разрешений" **API,** которые моя организация использует >, введите "Защита от угроз (Майкрософт)" и выберите "Защита от  >    >   **угроз (Майкрософт)".**  Теперь ваше приложение может получить доступ к Microsoft 365 Defender.

   > [!TIP]
   > *Защита от угроз (Майкрософт)* — это прежнее имя Защитника Microsoft 365, которое не будет отображаться в исходном списке. Чтобы увидеть, как оно появляется, необходимо начать писать его имя в текстовом поле.

   ![Изображение выбора разрешений API](../../media/apis-in-my-org-tab.PNG)

   - Choose **Delegated permissions**. Выберите соответствующие разрешения для сценария **(например, Incident.Read),** а затем выберите **"Добавить разрешения".**

   ![Изображение доступа к API и выбора API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > Необходимо выбрать соответствующие разрешения для сценария. *Прочитать все инциденты* можно только в качестве примера. Чтобы определить необходимые разрешения, обратитесь к разделу **"Разрешения"** в API, который требуется вызвать.
    >
    > Например, чтобы выполнить [расширенные запросы,](api-advanced-hunting.md)выберите разрешение "Выполнение расширенных запросов"; чтобы [изолировать устройство,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)выберите разрешение "Изолировать компьютер".

5. Выберите **"Предоставить согласие администратора".** При каждом добавлении разрешения  необходимо выбрать разрешение администратора, чтобы оно вступает в силу.

   ![Изображение разрешения на предоставление](../../media/grant-consent-delegated.PNG)

6. Зафиксировать свой ИД приложения и ид клиента в надежном месте. Они перечислены в списке **"Обзор"** на странице приложения.

   ![Изображение созданного ид приложения](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>Получение токена доступа

Дополнительные сведения о маркерах Azure Active Directory см. в руководстве [по Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="get-an-access-token-using-powershell"></a>Получить маркер доступа с помощью PowerShell

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $cleintId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a>Проверка маркера

1. Скопируйте и в paste маркер в [JWT,](https://jwt.ms) чтобы декодировать его.
1. Убедитесь, что *утверждение ролей* внутри раскодирования маркера содержит нужные разрешения.

На следующем изображении можно увидеть раскодный маркер, полученный из приложения, с ```Incidents.Read.All``` разрешениями ```Incidents.ReadWrite.All``` и ```AdvancedHunting.Read.All``` разрешениями:

![Изображение проверки маркера](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Использование маркера для доступа к API Защитника Microsoft 365

1. Выберите нужный API (инциденты или расширенный поиск). Дополнительные сведения [см. в поддерживаемых API Microsoft 365 Defender.](api-supported.md)
2. В http-запросе, который вы будете отправлять, задайте для загона авторизации `"Bearer" <token>` *,Bearer* является схемой авторизации, а маркер является вашим проверенным  маркером.
3. Срок действия маркера истекает в течение одного часа. За это время можно отправить несколько запросов с одним маркером.

В следующем примере показано, как отправить запрос, чтобы получить список инцидентов с **помощью C#**.

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Статьи по теме

- [Обзор API Microsoft 365 Defender](api-overview.md)
- [Доступ к API Microsoft 365 Defender](api-access.md)
- [Создание приложения "Hello world"](api-hello-world.md)
- [Создание приложения для доступа к Защитнику Microsoft 365 без пользователя](api-create-app-web.md)
- [Создание приложения с мультиязычным доступом партнеров к API Защитника Microsoft 365](api-partner-access.md)
- [Узнайте об ограничениях API и лицензировании](api-terms.md)
- [Коды ошибок](api-error-codes.md)
- [Авторизация OAuth 2.0 для доступа к API и входу пользователя](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
