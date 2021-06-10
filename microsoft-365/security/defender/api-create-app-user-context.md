---
title: Создание приложения для доступа Microsoft 365 API Defender от имени пользователя
description: Узнайте, как Microsoft 365 API Defender от имени пользователя.
keywords: доступ от имени пользователя, api, приложения, пользователя, маркера доступа, маркера,
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
ms.openlocfilehash: bffe38ff5dc4c11ed25519c86081e24ff1191e94
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076702"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>Создание приложения для доступа Microsoft 365 API Defender от имени пользователя

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

На этой странице описывается создание приложения для получения программного доступа к Microsoft 365 Defender от имени одного пользователя.

Если вам необходим программный доступ к Microsoft 365 Defender без определенного пользователя (например, если вы пишете фоновое приложение или daemon), см. в раздел Создание приложения для доступа Microsoft 365 [Defender](api-create-app-web.md)без пользователя . Если вам необходимо предоставить доступ нескольким клиентам, например, если вы обслуживаете крупную организацию или группу клиентов, см. в статью Создание приложения с партнерским доступом к API [Microsoft 365 Defender.](api-partner-access.md) Если вы не уверены, какой доступ вам нужен, см. [в этой ленте Начало](api-access.md)работы.

Microsoft 365 Defender предоставляет большую часть своих данных и действий с помощью набора программных API. Эти API помогают автоматизировать рабочий процесс и использовать возможности Microsoft 365 Defender. Этот доступ к API требует проверки подлинности OAuth2.0. Дополнительные сведения см. [в тексте OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

В общем, для использования этих API необходимо предпринять следующие действия:

- Создание приложения Azure Active Directory Azure AD.
- Получение маркера доступа с помощью этого приложения.
- Используйте маркер для доступа к API Microsoft 365 Defender.

В этой статье объясняется, как:

- Создание приложения Azure AD
- Получите маркер доступа к Microsoft 365 Defender
- Проверка маркера

> [!NOTE]
> При доступе Microsoft 365 API Defender от имени пользователя вам потребуется правильные разрешения приложения и разрешения пользователей.

> [!TIP]
> Если у вас есть разрешение на выполнение действия на портале, у вас есть разрешение на выполнение действия в API.

## <a name="create-an-app"></a>Создать приложение

1. Во входе [в Azure](https://portal.azure.com) в качестве пользователя с **ролью глобального администратора.**

2. Перейдите **к Azure Active Directory**  >  **регистрации Приложений** Новая  >  **регистрация**.

   ![Изображение Microsoft Azure и навигации для регистрации приложений](../../media/atp-azure-new-app2.png)

3. В форме выберите имя приложения и введите следующую информацию для URI перенаправления, а затем **зарегистрируйтесь.**

   ![Изображение окна создания приложения](../../media/nativeapp-create2.PNG)

   - **Тип приложения:** Общедоступный клиент
   - **Перенаправление URI:**https://portal.azure.com

4. На странице приложения выберите **API Permissions** Add permission API, которые моя организация использует  >    >   >, **введите** Защита от угроз (Майкрософт) и выберите **Защита от угроз (Майкрософт)**. Теперь приложение может получить доступ к Microsoft 365 Defender.

   > [!TIP]
   > *Защита от угроз (Майкрософт)* является прежним именем Microsoft 365 Defender и не будет отображаться в исходном списке. Чтобы увидеть его, необходимо приступить к написанию его имени в текстовом окне.

   ![Изображение выбора разрешений API](../../media/apis-in-my-org-tab.PNG)

   - Выберите **делегирование разрешений.** Выберите соответствующие разрешения для сценария **(например, Incident.Read),** а затем **добавьте разрешения.**

   ![Изображение доступа к API и выбора API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > Необходимо выбрать соответствующие разрешения для сценария. *Чтение всех инцидентов* — это только пример. Чтобы определить, какое разрешение вам нужно, обратите внимание на раздел **Разрешения** в API, который вы хотите вызвать.
    >
    > Например, для [запуска расширенных запросов](api-advanced-hunting.md)выберите разрешение "Запуск расширенных запросов"; чтобы [изолировать устройство,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)выберите разрешение "Изолировать машину".

5. Выберите **согласие администратора Гранта**. Каждый раз, когда вы добавляете разрешение, необходимо выбрать согласие администратора **Гранта,** чтобы оно вступает в силу.

   ![Изображение разрешений гранта](../../media/grant-consent-delegated.PNG)

6. Запись ID приложения и ID клиента в безопасном месте. Они перечислены в статье **Обзор на** странице приложения.

   ![Изображение созданного id приложения](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>Получение токена доступа

Дополнительные сведения о маркерах Azure Active Directory см. в руководстве [Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

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

1. Скопируйте и вклейте маркер [в JWT,](https://jwt.ms) чтобы расшифровать его.
1. Убедитесь, что *утверждение ролей* в расшифроваемом маркере содержит нужные разрешения.

На следующем изображении можно увидеть расшифровав маркер, приобретенный из приложения, с разрешениями и ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` разрешениями:

![Изображение проверки маркеров](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Используйте маркер для доступа к API Microsoft 365 Defender

1. Выберите API, который вы хотите использовать (инциденты или расширенный поиск). Дополнительные сведения см. в [Microsoft 365 API Defender.](api-supported.md)
2. В http-запросе, который вы отправляете, задайте загон авторизации , Bearer является схемой авторизации, а маркер - `"Bearer" <token>` проверенным маркером.  
3. Срок действия маркера истекает в течение одного часа. За это время вы можете отправить несколько запросов с одним маркером.

В следующем примере показано, как отправить запрос для получения списка инцидентов **с C#**.

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Связанные статьи

- [Microsoft 365 Обзор API defender](api-overview.md)
- [Доступ к API Microsoft 365 Defender](api-access.md)
- [Создание приложения "Hello world"](api-hello-world.md)
- [Создание приложения для доступа Microsoft 365 Defender без пользователя](api-create-app-web.md)
- [Создание приложения с несколькими партнерами-партнерами для доступа Microsoft 365 API Defender](api-partner-access.md)
- [Узнайте о ограничениях API и лицензировании](api-terms.md)
- [Понимание кодов ошибок](api-error-codes.md)
- [Авторизация OAuth 2.0 для входов пользователей и доступа к API](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)