---
title: GDPR для SharePoint Server
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: Узнайте, как обеспечить соблюдение требований GDPR в локальном развертывании SharePoint Server.
ms.openlocfilehash: 6da9d635506eafc2b976cf6a87f68370f40e327a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37089490"
---
# <a name="gdpr-for-sharepoint-server"></a>GDPR для SharePoint Server

Ниже перечислены рекомендуемые меры по обеспечению безопасности персональных данных.

-   Классифицируйте свои данные, используя Azure Information Protection.

-   Запускайте SharePoint Server в конфигурации с наименьшими привилегиями. Дополнительную информацию см. в статьях [Планирование администрирования с минимальными правами в SharePoint Server](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/plan-for-least-privileged-administration) и [Безопасность SharePoint Server](https://docs.microsoft.com/ru-RU/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server).

-   [Включите на серверах шифрование BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server).

## <a name="user-generated-content"></a>Контент, создаваемый пользователями

Основной рекомендуемый подход для контента, создаваемого пользователями и содержащегося на сайтах и в библиотеках SharePoint Server:

-   Используйте Azure Information Protection для пометки конфиденциальных данных.

-   Используйте [поиск SharePoint Server](https://docs.microsoft.com/SharePoint/search/search) и [обнаружение электронных данных](https://docs.microsoft.com/SharePoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server) для извлечения конфиденциальных данных.

Рекомендуемый подход для общих папок, а также сайтов и библиотек SharePoint включает следующие действия:

1.  **[Установите и настройте сканер Azure Information Protection.](https://docs.microsoft.com/ru-RU/azure/information-protection/rms-client/client-admin-guide-install#options-to-install-the-azure-information-protection-client-for-users)**

    -   Выберите необходимые типы конфиденциальных данных.

    -   Укажите необходимые сайты SharePoint.

2.  **Выполните цикл обнаружения.**

    -   Запустите сканер в режиме обнаружения и проверьте обнаруженные данные.

    -   При необходимости оптимизируйте условия и типы конфиденциальной информации.

    -   Оцените ожидаемое воздействие автоматического применения меток.

3.  **Запустите сканер Azure Information Protection для применения меток к соответствующим документам**.

4.  **Для защиты:**

    a. Настройте правила защиты от потери данных в Exchange, чтобы защитить документы с нужной меткой.

    b. Используйте разрешения, чтобы ограничить доступ к файлам.

    c. Используйте защиту IRM для библиотек в SharePoint.

5.  **Интегрируйте журналы Windows Server с помощью средства SIEM для мониторинга.**

    a. Используйте центр поиска или обнаружение электронных данных, чтобы найти персональные данные по запросу субъектов данных.

Применяя метки к конфиденциальным данным, убедитесь, что используемые метки не имеют защиты. Защита включает шифрование, из-за которого службы не могут найти конфиденциальные данные в файлах.

Дополнительные сведения об использовании сканера Azure Information Protection для поиска и пометки персональных данных см. в [наборе средств для обнаружения данных GDPR (Майкрософт)](http://aka.ms/gdprpartners) (http://aka.ms/gdprpartners).

Сведения о настройке сканера в соответствии с условиями и использовании типов конфиденциальной информации для защиты от потери данных (DLP) в Office 365 см. в статье [Как настроить условия для автоматической и рекомендуемой классификации с помощью Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Обратите внимание, что новые типы конфиденциальной информации Office 365 не сразу станут доступны для использования в сканере. Кроме того, в нем невозможно использовать пользовательские типы конфиденциальной информации.

## <a name="removing-personal-information-from-office-files"></a>Удаление личных сведений из файлов Office

Удаление личных сведений (таких как метаданные или комментарии в документе Word) из файлов Office, хранящихся в библиотеке документов SharePoint, необходимо выполнять вручную. Выполните следующие действия:

1.  Скачайте копию документа с сервера SharePoint Server на локальный диск.

2.  Удалите документ из библиотеки документов SharePoint.

3.  Выполните действия, описанные в статье [Удаление скрытых и персональных данных при проверке документов](https://support.office.com/article/356B7B5D-77AF-44FE-A07F-9AA4D085966F).

4.  Отправьте документ обратно в библиотеку документов SharePoint.

## <a name="telemetry-and-log-files"></a>Телеметрия и файлы журналов

### <a name="uls-logs"></a>Журналы ULS

Журналы ULS (единая служба ведения журналов) и журналы использования в SharePoint Server помогают отслеживать различные функции системы и могут содержать информацию о пользователе. Журналы ULS и журналы использования — это текстовые файлы, в которых можно искать информацию, используя различные поисковые средства. [Командлет Merge-SPLogFile PowerShell](https://docs.microsoft.com/ru-RU/powershell/module/sharepoint-server/merge-splogfile) позволяет возвращать записи из журналов ULS на нескольких серверах в ферме.

В политиках хранения журнала рекомендуется указать минимальное значение, необходимое для бизнес-целей. Сведения о настройке ведения журнала в SharePoint Server см. в статье [Настройка журнала ведения диагностики в SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).

Обратите внимание, что некоторые события системы также регистрируются в журнале событий Windows.

### <a name="usage-database"></a>База данных использования

База данных использования SharePoint Server (имя по умолчанию WSS_Logging) содержит часть информации, находящейся в журналах ULS. Максимальный срок хранения данных в этой базе данных составляет 30 дней. Рекомендуем настроить минимальный срок хранения, подходящий для вашей организации. Дополнительную информацию см. в статье [Настройка журнала ведения диагностики в SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).

## <a name="personal-information-and-search"></a>Персональные данные и поиск

Журнал поисковых запросов и записи об использовании содержат ссылки на имена пользователей.

### <a name="query-history-and-favorite-queries"></a>Журнал запросов и избранные запросы

В SharePoint Server срок действия журналов запросов и избранных запросов автоматически истекает через 365 дней. Если пользователь покидает вашу организацию, вы можете удалить ссылки на имя пользователя из журнала запросов, следуя приведенным ниже инструкциям.

Следующие SQL-запросы применяются к SharePoint Server и позволяют:

-   Экспортировать журнал запросов или избранные запросы пользователя.

-   Удалять ссылки на имена пользователей в журнале запросов.

#### <a name="export-a-users-queries-since-a-specific-date"></a>Экспорт запросов пользователя начиная с определенной даты 

Используйте следующую процедуру, чтобы экспортировать запросы, выполненные пользователем @UserName начиная с @StartTime, из таблиц журнала запросов Link Store.

```sql
[In dbo].[LinkStore_<ID>]:
CREATE PROCEDURE proc_MSS_GetQueryTermsForUser 
( 
    @UserName nvarchar(256), 
    @StartTime datetime 
) 
AS 
BEGIN 
    SET NOCOUNT ON; 
    SELECT searchTime, queryString 
    FROM 
        dbo.MSSQLogPageImpressionQuery 
    WITH 
        (NOLOCK) 
    WHERE 
        userName = @UserName AND 
        searchTime > @StartTime 
END 
GO 
```

#### <a name="export-a-users-queries-from-the-past-100-days"></a>Экспорт запросов пользователя за последние 100 дней

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetQueryTermsForUser '0#.w|domain\username', @FROMDATE 
```

#### <a name="export-a-users-favorite-queries"></a>Экспорт избранных запросов пользователя

Выполните указанные ниже действия, чтобы экспортировать избранные запросы пользователя, выполненные пользователем @UserName начиная с <DateTime>, из таблиц личных результатов базы данных администрирования поиска.

```sql
In [dbo].[Search_<ID>]:
CREATE PROCEDURE proc_MSS_GetPersonalFavoriteQueries 
( 
    @UserName nvarchar(256), 
    @SearchTime datetime 
) 
AS 
BEGIN 
    SET NOCOUNT ON; 
    SELECT max(queries.SearchTime) as SearchTime, 
           max(queries.querystring) as queryString, 
           max(url.url) as URL 
    FROM MSSQLogOwner owners WITH(NOLOCK) 
    JOIN MSSQLogPersonalResults results WITH(NOLOCK) on owners.OwnerId = results.OwnerId 
    JOIN MSSQLogUrl url WITH(NOLOCK) on results.ClickedUrlId = url.urlId 
    JOIN MSSQLogPersonalQueries queries WITH(NOLOCK) on results.OwnerId = queries.OwnerId 
    WHERE queries.SearchTime > @SearchTime 
        AND queries.UserName = @UserName 
        GROUP BY queries.QueryString,url.url 
END 
GO 
```

#### <a name="export-a-users-favorite-queries-from-the-past-100-days"></a>Экспорт избранных запросов пользователя за последние 100 дней 

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetPersonalFavoriteQueries '0#.w|domain\username', @FROMDATE 
```

#### <a name="remove-references-to-user-names-that-are-more-than-x-days-old"></a>Удаление ссылок на имена пользователей, которые старше X дней

Используйте следующую процедуру, чтобы удалить ссылки на *все* имена пользователей, которые старше @Days, из таблиц журнала запросов Links Store. Процедура удаляет прошлые ссылки, пока не будет достигнуто время @LastCleanupTime.

```sql
In [dbo].[LinksStore_<ID>]:  
CREATE PROCEDURE proc_MSS_QLog_Cleanup_Users 
( 
    @LastCleanupTime datetime, 
    @Days int 
) 
AS 
BEGIN 
    DECLARE @TooOld datetime 
    SET @TooOld = DATEADD(day, -@Days, GETUTCDATE()) 
    DECLARE @FromLast datetime 
    SET @FromLast = DATEADD(day, -@Days, @LastCleanupTime) 
    BEGIN TRANSACTION 
         UPDATE MSSQLogPageImpressionQuery 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld 
    UPDATE MSSQLogO14PageClick 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld 
    COMMIT TRANSACTION 
END 
GO 
```

#### <a name="remove-references-to-a-specific-user-name-thats-more-than-x-days-old"></a>Удаление ссылок на определенное имя пользователя, которые старше X дней

Используйте следующую процедуру, чтобы удалить ссылки на *определенное* имя пользователя из таблиц журнала запросов Links Store, где ссылки старше @Days. Процедура удаляет прошлые ссылки, пока не будет достигнуто время @LastCleanupTime.

```sql
In [dbo].[LinksStore_<ID>]:
CREATE PROCEDURE proc_MSS_QLog_Cleanup_Users 
( 
    @UserName nvarchar(256),
    @LastCleanupTime datetime, 
    @Days int 
) 
AS 
BEGIN 
    DECLARE @TooOld datetime 
    SET @TooOld = DATEADD(day, -@Days, GETUTCDATE()) 
    DECLARE @FromLast datetime 
    SET @FromLast = DATEADD(day, -@Days, @LastCleanupTime) 
    BEGIN TRANSACTION 
         UPDATE MSSQLogPageImpressionQuery 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld AND userName = @UserName
    UPDATE MSSQLogO14PageClick 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld AND userName = @UserName
    COMMIT TRANSACTION 
END 
GO 
```

#### <a name="remove-references-to-all-user-names-in-the-query-history-from-a-date-and-up-to-the-past-30-days"></a>Удаление ссылок на все имена пользователей в журнале запросов за последние несколько (до 30) дней начиная с определенной даты

```sql
EXECUTE proc_MSS_QLog_Cleanup_Users '1-1-2017', 30 
```

### <a name="delete-usage-records"></a>Удаление записей об использовании

SharePoint Server автоматически удаляет записи об использовании через 3 года. Вы можете вручную удалить такие записи с помощью описанной ниже процедуры:

Чтобы удалить все записи об использовании, связанные с удаленными документами: 

1.  Убедитесь, что у вас установлено последнее обновление SharePoint. 

2.  Запустите командную консоль SharePoint.

3.  Остановите аналитику использования и очистите ее данные: 

    ```powershell
    $tj = Get-SPTimerJob -Type Microsoft.Office.Server.Search.Analytics.UsageAnalyticsJobDefinition 
    $tj.DisableTimerjobSchedule()
    $tj.StopAnalysis() 
    $tj.ClearAnalysis() 
    $tj.EnableTimerjobSchedule()
    ```

4.  Подождите, пока аналитика не запустится снова (может потребоваться до 24 часов). 

5.  При следующем запуске аналитики все записи из базы данных отчетов аналитики будут записаны в дамп. Выполнение полного дампа большой базы данных с множеством записей может занять некоторое время.

6.  Подождите 10 дней. Аналитика запускается ежедневно, и записи, связанные с удаленными документами, будут удалены после 10-го запуска. Если удаляемых записей очень много, этот запуск может занять больше времени, чем обычно. 

### <a name="personal-information-and-search-in-sharepoint-server-2010"></a>Персональные данные и поиск в SharePoint Server 2010

#### <a name="fast-search-server-2010-for-sharepoint"></a>FAST Search Server 2010 для SharePoint 

Помимо индекса, надстройка FAST Search Server 2010 также хранит файлы в промежуточном формате, называемом FixML. Файлы FiXML регулярно сжимаются (по умолчанию каждую ночь с 3:00 до 5:00). При сжатии из этих файлов автоматически исключаются удаленные файлы. Чтобы обеспечить своевременное удаление информации, принадлежащей удаленным пользователям или документам, убедитесь, что функция сжатия всегда включена.

### <a name="hybrid-search"></a>Гибридный поиск 

Рекомендуемые действия для решений гибридного поиска аналогичны действиям для поиска в SharePoint Server или SharePoint Online. Существует два решения гибридного поиска:

**Решение для облачного гибридного поиска.** Вы вносите весь просканированный контент, в том числе локальный, в индекс поиска Office 365. Когда пользователи запрашивают информацию в индексе поиска Office 365, они получают результат из локального контента и контента Office 365. При удалении документов из среды SharePoint Server они также удаляются из индекса поиска Office 365. Чтобы лучше понять, как GDPR влияет на гибридную среду, [ознакомьтесь с информацией о решении для облачного гибридного поиска](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint) и [взаимодействии поисковых компонентов и баз данных в облачном гибридном поиске](https://docs.microsoft.com/sharepoint/hybrid/plan-cloud-hybrid-search-for-sharepoint).

**Решение для гибридного федеративного поиска.** Вы используете индексы как из SharePoint Server, так и из Office 365. Службы поиска SharePoint Server и SharePoint Online могут отправлять запросы к индексу поиска в другой среде и возвращать федеративные результаты. Когда пользователи выполняют поиск в центре поиска, результаты поступают из поисковых индексов как в SharePoint Server, так и в Office 365. Чтобы лучше понять, как GDPR влияет на гибридную среду, [ознакомьтесь с информацией о решении для гибридного федеративного поиска](https://docs.microsoft.com/sharepoint/hybrid/learn-about-hybrid-federated-search-for-sharepoint).

## <a name="on-prem-to-cloud-migrations"></a>Перенос локальных данных в облако

При переносе данных из SharePoint Server в SharePoint Online в течение определенного времени данные могут дублироваться. Если у вас есть данные, которые необходимо удалить в середине переноса, рекомендуем сначала выполнить перенос, а затем удалить их из обоих расположений. Вы можете запросить данные для экспорта из любого расположения.

## <a name="user-profile-data"></a>Данные профиля пользователя

Служба профилей пользователей позволяет импортировать данные профилей из различных внешних источников. Запросы и обновления таких данных профиля пользователя должны обрабатываться в системах, управляющих этими данными. Если вы обновляете внешние системы, не забудьте повторно синхронизировать профили пользователей в SharePoint Server.

Выполните следующие действия, чтобы удалить персональные данные пользователя из его профиля в SharePoint Server:

1.  Удалите информацию о пользователе из внешних систем, которые предоставляют данные для профиля в SharePoint Server. Если вы используете синхронизацию службы каталогов, пользователя необходимо удалить из локальной среды Active Directory.

2.  Запустите [синхронизацию профилей](https://docs.microsoft.com/sharepoint/administration/start-profile-synchronization-manually) на SharePoint Server.

3.  Удалите профиль с сервера SharePoint Server. После этого SharePoint Server полностью удалит этот профиль из базы данных профилей пользователей в течение 30 дней. Страница профиля и персональный сайт пользователя будут удалены.

После удаления профиля в семействах веб-сайтов, которые посещал этот пользователь, по-прежнему может оставаться некоторая информация (например, ИД пользователя). Чтобы удалить эти данные из определенного семейства веб-сайтов, воспользуйтесь CSOM. Пример сценария представлен ниже:

```powershell
$username = "<admin@company.sharepoint.com>"
$password = "password"
$url = "<https://site.sharepoint.com>"
$securePassword = ConvertTo-SecureString $Password -AsPlainText -Force

# the path here may need to change if you used e.g. C:Lib.
Add-Type -Path "c:\Program Files\Common Files\microsoft shared\Web Server Extensions\16ISAPIMicrosoft.SharePoint.Client.dll"
Add-Type -Path "c:\Program Files\Common Files\microsoft shared\Web Server Extensions\16ISAPIMicrosoft.SharePoint.Client.Runtime.dll"

# connect/authenticate to SharePoint Online and get ClientContext object.
$clientContext = New-Object Microsoft.SharePoint.Client.ClientContext($url)
$credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($username, $securePassword)
$clientContext.Credentials = $credentials
if (!$clientContext.ServerObjectIsNull.Value)
{
    Write-Host "Connected to SharePoint Online site: '$Url'" -ForegroundColor Green
}

# Get user
$user = $clientContext.Web.SiteUsers.GetByLoginName("i:0#.f|membership|user@company.sharepoint.com")

# Redact user
$user.Email = "Redacted"
$user.Title = "Redacted"
$user.Update()
$clientContext.Load($user)
$clientContext.ExecuteQuery()

# Get users
$users = $clientContext.Web.SiteUsers

# Remove user from site
$users.RemoveById($user.Id)
$clientContext.Load($users)
$clientContext.ExecuteQuery()
```
