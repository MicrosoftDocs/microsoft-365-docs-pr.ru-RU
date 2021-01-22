---
title: Hello World для REST API Защитника Microsoft 365
description: Узнайте, как создать приложение и использовать маркер для доступа к API Microsoft 365 Defender
keywords: приложение, маркер, доступ, aad, приложение, регистрация приложения, powershell, сценарий, глобальный администратор, разрешение, Защитник Microsoft 365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 66afa27d0fa7a092d3f9e9ed6c3b6abc6020cb8d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928382"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Hello World для REST API Защитника Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="get-incidents-using-a-simple-powershell-script"></a>Получить инциденты с помощью простого сценария PowerShell

Этот проект должен занять от 5 до 10 минут. В этот раз оценка включает регистрацию приложения и применение кода из примера сценария PowerShell.

### <a name="register-an-app-in-azure-active-directory"></a>Регистрация приложения в Azure Active Directory

1. Во sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.

2. Перейдите к регистрации нового приложения **Azure Active Directory.**  >    >  

   ![Изображение Microsoft Azure и переход к регистрации приложений](../../media/atp-azure-new-app2.png)

3. В форме регистрации выберите имя приложения, а затем выберите **"Регистрация".** Выбор URI перенаправления необязателен. Для выполнения этого примера он не потребуется.

4. На странице приложения выберите "API Разрешения для добавления разрешений" **API,** которые моя организация использует >, введите "Защита от угроз (Майкрософт)" и выберите "Защита от  >    >   **угроз (Майкрософт)".**  Теперь ваше приложение может получить доступ к Microsoft 365 Defender.

   > [!TIP]
   > *Защита от угроз (Майкрософт)* — это прежнее имя Защитника Microsoft 365, которое не будет отображаться в исходном списке. Чтобы увидеть, как оно появляется, необходимо начать писать его имя в текстовом поле.
   ![Изображение выбора разрешений API](../../media/apis-in-my-org-tab.PNG)

   - Выберите **разрешения приложения**  >  **Incident.Read.All** и выберите **"Добавить разрешения".**

   ![Изображение доступа к API и выбора API](../../media/request-api-permissions.PNG)

5. Выберите **"Предоставить согласие администратора".** При каждом добавлении разрешения  необходимо выбрать разрешение администратора, чтобы оно вступает в силу.

    ![Изображение разрешения на предоставление](../../media/grant-consent.PNG)

6. Добавьте секрет в приложение. Select **Certificates & secrets,** add a description to the secret, then select **Add**.

    > [!TIP]
    > После выбора **"Добавить"** выберите **"Скопировать сгенерированную секретную копию".** После этого вы не сможете получить значение секрета.

    ![Изображение создания ключа приложения](../../media/webapp-create-key2.png)

7. Зафиксировать свой ИД приложения и ид клиента в надежном месте. Они перечислены в списке **"Обзор"** на странице приложения.

   ![Изображение созданного ид приложения](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>Получите маркер с помощью приложения и используйте его для доступа к API

Дополнительные сведения о маркерах Azure Active Directory см. в руководстве [по Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

> [!IMPORTANT]
> Несмотря на то, что в примере в этом демонстрационных приложениях  рекомендуется в целях тестирования в paste in your secret value, никогда не следует жестко кодировать секреты в приложение, запущенное в производственной версии. Третья сторона может использовать ваш секрет для доступа к ресурсам. Вы можете обеспечить безопасность секретов приложения с помощью [Azure Key Vault.](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates) Практический пример того, как можно защитить приложение, см. в под управлением секретов в серверных приложениях [с помощью Azure Key Vault.](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)

1. Скопируйте сценарий ниже и в paste его в избранный текстовый редактор. Сохраните как **Get-Token.ps1**. Вы также можете запустить код в is-is в PowerShell ISE, но вам следует сохранить его, так как нам потребуется запустить его снова, когда мы будем использовать сценарий получения инцидентов в следующем разделе.

    Этот сценарий создает маркер и сохраняет его в рабочей папке под именем *Latest-token.txt.*

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

1. Скопируйте и в paste маркер, полученный в [JWT,](https://jwt.ms) чтобы декодировать его.
1. *JWT* означает *веб-маркер JSON.* Раскодированный маркер будет содержать ряд элементов или утверждений в формате JSON. Убедитесь, что *утверждение ролей* внутри раскодирования маркера содержит нужные разрешения.

    На следующем изображении можно увидеть раскодный маркер, полученный из приложения, с ```Incidents.Read.All``` разрешениями ```Incidents.ReadWrite.All``` и ```AdvancedHunting.Read.All``` разрешениями:

    ![Изображение jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>Получить список последних инцидентов

Сценарий ниже **будет** использоватьGet-Token.ps1для доступа к API. Затем он извлекает список инцидентов, которые были в последний раз обновлены в течение последних 48 часов, и сохраняет список в JSON-файле.

> [!IMPORTANT]
> Сохраните этот сценарий в той же папке, в **Get-Token.ps1.**

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

Все готово! Вы успешно выполнили:

- Создано и зарегистрировано приложение.
- Предоставлено разрешение для этого приложения на чтение оповещений.
- Подключен к API.
- Использовал сценарий PowerShell для возврата инцидентов, обновленных за последние 48 часов.

## <a name="related-articles"></a>Статьи по теме

- [Обзор API Microsoft 365 Defender](api-overview.md)
- [Доступ к API Microsoft 365 Defender](api-access.md)
- [Создание приложения для доступа к Microsoft 365 Defender без пользователя](api-create-app-web.md)
- [Создание приложения для доступа к API Microsoft 365 Defender от имени пользователя](api-create-app-user-context.md)
- [Создание приложения с мультиязычным доступом партнеров к API Microsoft 365 Defender](api-partner-access.md)
- [Управление секретами в серверных приложениях с помощью Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Авторизация OAuth 2.0 для доступа пользователя к API и входу в нее](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
