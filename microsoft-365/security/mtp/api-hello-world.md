---
title: Hello World для REST API для защиты от угроз Майкрософт
description: Узнайте, как создать приложение и использовать маркер для доступа к API Microsoft Threat protection
keywords: приложение, маркер, доступ, AAD, App, регистрация приложений, PowerShell, сценарий, глобальный администратор, разрешение
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
ms.openlocfilehash: d9aafc43fb08d9e8b3a427805ba58490afee6297
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650499"
---
# <a name="hello-world-for-microsoft-threat-protection-rest-api"></a>Hello World для REST API для защиты от угроз Майкрософт 

**Область применения:**
- Защита от угроз (Майкрософт)

>[!IMPORTANT] 
>Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="get-incidents-using-a-simple-powershell-script"></a>Получение инцидентов с помощью простого скрипта PowerShell

### <a name="how-long-it-takes-to-go-through-this-example"></a>Сколько времени потребуется проделать через этот пример?
Выполнение выполняется в течение 5 минут в два этапа:
- Регистрация приложения
- Примеры: требуется только копирование и вставка короткого скрипта PowerShell

### <a name="do-i-need-a-permission-to-connect"></a>Требуется ли разрешение на подключение?
Для этапа регистрации приложений необходимо иметь роль **глобального администратора** в клиенте Azure Active Directory (Azure AD).

### <a name="step-1---create-an-app-in-azure-active-directory"></a>Шаг 1: создание приложения в Azure Active Directory

1. Войдите в [Azure](https://portal.azure.com) с помощью учетной записи **глобального администратора** .

2. Перейдите к разделу Регистрация приложений **Azure Active Directory**с  >  **App registrations**  >  **новой регистрацией**. 

   ![Изображение Microsoft Azure и переход к регистрации приложения](../../media/atp-azure-new-app2.png)

3. В форме регистрации выберите имя приложения и нажмите кнопку **зарегистрировать**.

4. Разрешите приложению получать доступ к пакету Office Defender ATP и назначить ему разрешение " **чтение всех происшествий** ":

   - На странице приложения выберите **разрешения API**  >  **Добавление разрешений**  >  **интерфейсы API для моей организации используется** > введите **Microsoft Threat protection** и выберите **защиту от угроз Майкрософт**.

   >[!NOTE]
   >Защита от угроз Майкрософт не отображается в исходном списке. Чтобы отобразить его имя, необходимо сначала начать его ввод в текстовое поле.

   ![Изображение доступа к API и выбора API](../../media/apis-in-my-org-tab.PNG)

   - Выберите **разрешения для приложений**  >  **происшествие инцидент. Read. ALL** > SELECT for **Permissions Permissions**

   ![Изображение доступа к API и выбора API](../../media/request-api-permissions.PNG)

   >[!IMPORTANT]
   >Необходимо выбрать соответствующие разрешения. 

     Например,

     - Чтобы определить, какое разрешение необходимо, просмотрите раздел **разрешения** в API, который вы хотите вызвать.

5. Выбор **предоставления согласия администратора**

    - >[!NOTE]
      > Каждый раз, когда вы добавляете разрешение, для вступления в силу нового разрешения необходимо выбрать разрешение на **предоставление** разрешения.

    ![Изображение разрешений GRANT](../../media/grant-consent.PNG)

6. Добавьте секрет в приложение.

    - Выберите **сертификаты & секреты**, добавьте описание к секрету и нажмите кнопку **Добавить**.

    >[!IMPORTANT]
    > После нажатия кнопки **Добавить** **скопируйте созданное значение секрета**. Вы не сможете получить его после выхода из!

    ![Изображение ключа "создать приложение"](../../media/webapp-create-key2.png)

7. Запишите идентификатор своего приложения и идентификатор клиента:

   - На странице приложения перейдите в раздел **Overview (обзор** ) и скопируйте следующее:

   ![Изображение идентификатора созданного приложения](../../media/app-and-tenant-ids.png)


Договорились! Вы успешно зарегистрировали приложение.

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>Шаг 2. Получите маркер с помощью приложения и используйте этот маркер для доступа к API.

-   Скопируйте приведенный ниже скрипт в PowerShell ISE или в текстовый редактор и сохраните его как "**Get-Token.ps1**".
-   При выполнении этого скрипта будет создан маркер, который будет сохранен в рабочей папке под именем "**Latest-token.txt**".

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

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

-   Проверка санити:<br>
Запустите сценарий.<br>
В браузере перейдите по адресу: https://jwt.ms/ <br>
Скопируйте маркер (содержимое файла Latest-token.txt).<br>
Вставьте в верхнее поле.<br>
Найдите раздел "роли". Найдите ```Incidents.Read.All``` роль.<br>
Ниже приведен пример из приложения с ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` разрешениями и разрешениями.

![Jwt.ms изображений](../../media/api-jwt-ms.png)

### <a name="lets-get-the-incidents"></a>Позволяет получить инциденты!

-   Приведенный ниже скрипт будет использовать **Get-Token.ps1** для доступа к API и будет получать последние обновленные происшествия за последние 48 часов.
-   Сохраните этот скрипт в той же папке, в которой вы сохранили предыдущий **Get-Token.ps1**сценария. 
-   Сценарий — файл JSON с данными в той же папке, что и скрипты.

```
# Returns Incidents last updated in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Incidents from the last 48 hours. Make sure you have incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# The URL contains the type of query and the time filter we created above
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results. 
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"     

Out-File -FilePath $outputJsonPath -InputObject $incidents 
```

Все готово. Вы только что успешно:
-   Создано, зарегистрировано и приложение
-   Разрешение на чтение оповещений для этого приложения
-   Подключен API
-   Использование скрипта PowerShell для возврата инцидентов, созданных за прошедшие 48 часов



## <a name="related-topic"></a>Связанная тема
- [Доступ к API защиты от угроз Майкрософт](api-access.md)
- [Доступ к защите от угроз Майкрософт с помощью контекста приложения](api-create-app-web.md)
- [Доступ к защите от угроз Майкрософт с помощью контекста пользователя](api-create-app-user-context.md)
