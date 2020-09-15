---
title: Создание приложения для доступа к защите от угроз Майкрософт без пользователя
description: Узнайте, как создать приложение для доступа к защите от угроз Майкрософт без пользователя
keywords: приложение, доступ, API, создание
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
ms.openlocfilehash: be637bab97083cb857e3983dd9b82290590c1302
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650502"
---
# <a name="create-an-app-to-access-microsoft-threat-protection-without-a-user"></a>Создание приложения для доступа к защите от угроз Майкрософт без пользователя

**Область применения:**
- Защита от угроз (Майкрософт)

>[!IMPORTANT] 
>Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

На этой странице описано, как создать приложение для получения программного доступа к защите от угроз Майкрософт без участия пользователя. Если вам необходим программный доступ к защите от угроз Майкрософт от имени пользователя, обратитесь [к разделу Получение доступа с помощью контекста пользователя](api-create-app-user-context.md). Если вы не знаете, какой необходим доступ, ознакомьтесь со [статьей начало работы](api-access.md).

Защита от угроз Майкрософт предоставляет множество своих данных и действий через набор программных интерфейсов API. Эти API помогут вам автоматизировать рабочие процессы и внедрять их на основе возможностей защиты от угроз Майкрософт. Для доступа к API требуется проверка подлинности OAuth 2.0. Для получения дополнительных сведений см [код авторизации OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

В общем случае необходимо выполнить следующие действия, чтобы использовать API:
- Создайте приложение Azure Active Directory (Azure AD).
- Получение маркера доступа с помощью этого приложения.
- Используйте маркер для доступа к API защиты от угроз Майкрософт.

В этой статье объясняется, как создать приложение Azure AD, получить маркер доступа для защиты от угроз Майкрософт и проверить маркер.

## <a name="create-an-app"></a>Создание приложения

1. Войдите в [Azure](https://portal.azure.com) с помощью пользователя с ролью **глобального администратора** .

2. Перейдите к разделу Регистрация приложений **Azure Active Directory**с  >  **App registrations**  >  **новой регистрацией**. 

   ![Изображение Microsoft Azure и переход к регистрации приложения](../../media/atp-azure-new-app2.png)

3. В форме регистрации выберите имя приложения и нажмите кнопку **зарегистрировать**.

4. Чтобы разрешить приложению доступ к защите от угроз Майкрософт и назначить ей разрешения, на странице приложения выберите **разрешения API**  >  **Добавление**разрешений  >  **API "Моя организация использует** >", введите **Microsoft Threat protection**, а затем выберите **Microsoft Threat protection**.

   > [!NOTE]
   > Защита от угроз Майкрософт не отображается в исходном списке. Чтобы отобразить его имя, необходимо сначала начать его ввод в текстовое поле.

   ![Изображение доступа к API и выбора API](../../media/apis-in-my-org-tab.PNG)

   - Выберите **разрешения приложений** > выберите соответствующие разрешения для вашего сценария, например, " **инцидент. Read. ALL**", а затем выберите **Добавить разрешения**.

   ![Изображение доступа к API и выбора API](../../media/request-api-permissions.PNG)

    >[!NOTE]
    >Необходимо выбрать соответствующие разрешения для вашего сценария, например, **"читать все инциденты"** — только пример. Чтобы определить, какое разрешение необходимо, просмотрите раздел **разрешения** в API, который вы хотите вызвать.

5. Выберите **согласие Grant**.

     > [!NOTE]
     > Каждый раз, когда вы добавляете разрешение, необходимо выбрать разрешение **Grant Grant** , чтобы новое разрешение вступило в силу.

    ![Изображение разрешений GRANT](../../media/grant-consent.PNG)

6. Чтобы добавить секрет в приложение, выберите **сертификаты & секреты**, добавьте описание к секрету, а затем нажмите кнопку **Добавить**.

    > [!NOTE]
    > После того как вы нажмите кнопку **Добавить**, выберите **Копировать созданное секретное значение**. После выхода вы не сможете получить это значение.

    ![Изображение ключа "создать приложение"](../../media/webapp-create-key2.png)

7. Запишите идентификатор своего приложения и идентификатор клиента. На странице приложения перейдите в раздел **Overview (обзор** ) и скопируйте приведенный ниже пример.

   ![Изображение идентификатора созданного приложения](../../media/app-and-tenant-ids.png)

8. **Только для партнеров Майкрософт по защите от угроз**. [Следуйте инструкциям в этой статье](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access). Настройте приложение для нескольких клиентов (доступно во всех клиентах после согласия). Это **необходимо** для сторонних приложений (например, при создании приложения, предназначенного для запуска в клиенте с несколькими клиентами). Это **не требуется** , если вы создаете службу, которую нужно запустить только в своем клиенте (например, если вы создаете приложение для собственного использования, которое будет работать только с собственными данными). Чтобы настроить приложение для поддержки нескольких клиентов:

    - Перейдите к разделу **Проверка подлинности**и добавьте в https://portal.azure.com качестве **URI перенаправления**.

    - В нижней части страницы в разделе **Поддерживаемые типы учетных записей**выберите **учетные записи в любом** согласии приложения каталога организации для приложения с несколькими клиентами.

    Приложение должно быть утверждено в каждом клиенте, где вы планируете его использовать. Это связано с тем, что ваше приложение взаимодействует с защитой от угроз Майкрософт от имени клиента.

    Вы (или ваш клиент, если вы пишете стороннее приложение), должны выбрать ссылку согласие и одобрить ваше приложение. Разрешение следует выполнять у пользователя с правами администратора в Active Directory.

    Ссылка на согласие выглядит следующим образом: 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    Где 00000000-0000-0000-0000-000000000000 заменяется ИДЕНТИФИКАТОРом приложения.


**Договорились!** Вы успешно зарегистрировали приложение! В примерах ниже показано, как для получения и проверки маркера.

## <a name="get-an-access-token"></a>Получение токена доступа

Более подробную информацию о маркерах Azure AD можно узнать в [руководстве по Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

### <a name="use-powershell"></a>Использование PowerShell

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="use-c"></a>Используйте C#:

Приведенный ниже код был протестирован с использованием NuGet Microsoft. IdentityModel. Clients. ActiveDirectory 3.19.8.

1. Создайте новое консольное приложение.
1. Установите NuGet [Microsoft. IdentityModel. Clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).
1. Добавьте следующие компоненты:

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Скопируйте и вставьте следующий код в свое приложение (не забудьте обновить три переменные: ```tenantId, appId, appSecret``` ):

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a>Использование Python 

```
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```
### <a name="use-curl"></a>Использование фигурного скобки

> [!NOTE]
> В приведенной ниже процедуре предполагается, что на компьютере уже установлена функция "фигурное" для Windows.

1. Откройте командную строку и присвойте CLIENT_ID ИДЕНТИФИКАТОРу приложения Azure.
1. Задайте для CLIENT_SECRET секрета приложения Azure.
1. Присвойте TENANT_ID ИДЕНТИФИКАТОРу клиента Azure, который хочет использовать ваше приложение для доступа к защите от угроз Майкрософт.
1. Выполните следующую команду:

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Вы получите ответ в следующей форме:

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Проверка маркера

Убедитесь, что вы получили правильный маркер:

1. Скопируйте и вставьте маркер, полученный на предыдущем шаге, в [JWT](https://jwt.ms) , чтобы его можно было декодировать.
1. Проверка наличия утверждения "роли" с нужными разрешениями
1. На следующем рисунке показан Раскодированный маркер, полученный из приложения с ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` разрешениями:

![Изображение проверки маркера](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a>Использование маркера для доступа к API защиты от угроз Майкрософт

1. Выберите API, который хотите использовать. Дополнительные сведения [см.](api-supported.md)

2. Задайте заголовок Authorization в HTTP-запросе, отправляемом пользователю "Bearer {token}" (Bearer является схемой авторизации).

3. Срок действия маркера равен одному часу. Можно отправить больше одного запроса с одним и тем же маркером.

Ниже приведен пример отправки запроса на получение списка инцидентов, **использующих C#**: 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a>Статьи по теме
- [Доступ к API защиты от угроз Майкрософт](api-access.md)
- [Доступ к защите от угроз Майкрософт с помощью контекста приложения](api-create-app-web.md)
- [Доступ к защите от угроз Майкрософт с помощью контекста пользователя](api-create-app-user-context.md)
