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
# <a name="gdpr-for-sharepoint-server"></a><span data-ttu-id="8fa5a-103">GDPR для SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="8fa5a-103">GDPR for SharePoint Server</span></span>

<span data-ttu-id="8fa5a-104">Ниже перечислены рекомендуемые меры по обеспечению безопасности персональных данных.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-104">As part of safeguarding personal information, we recommend the following:</span></span>

-   <span data-ttu-id="8fa5a-105">Классифицируйте свои данные, используя Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-105">Classify your data, using Azure Information Protection.</span></span>

-   <span data-ttu-id="8fa5a-p101">Запускайте SharePoint Server в конфигурации с наименьшими привилегиями. Дополнительную информацию см. в статьях [Планирование администрирования с минимальными правами в SharePoint Server](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/plan-for-least-privileged-administration) и [Безопасность SharePoint Server](https://docs.microsoft.com/ru-RU/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server).</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p101">Run SharePoint Server in a least-privileged configuration. See [Plan for least-privileged administration in SharePoint Server](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/plan-for-least-privileged-administration) and [Security for SharePoint Server](https://docs.microsoft.com/ru-RU/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server) for more information.</span></span>

-   <span data-ttu-id="8fa5a-108">[Включите на серверах шифрование BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="8fa5a-108">[Enable BitLocker encryption on your servers](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server).</span></span>

## <a name="user-generated-content"></a><span data-ttu-id="8fa5a-109">Контент, создаваемый пользователями</span><span class="sxs-lookup"><span data-stu-id="8fa5a-109">User Generated content</span></span>

<span data-ttu-id="8fa5a-110">Основной рекомендуемый подход для контента, создаваемого пользователями и содержащегося на сайтах и в библиотеках SharePoint Server:</span><span class="sxs-lookup"><span data-stu-id="8fa5a-110">The basic recommended approach for user generated content contained in SharePoint Server sites and libraries is:</span></span>

-   <span data-ttu-id="8fa5a-111">Используйте Azure Information Protection для пометки конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-111">Use Azure Information Protection to label sensitive data.</span></span>

-   <span data-ttu-id="8fa5a-112">Используйте [поиск SharePoint Server](https://docs.microsoft.com/SharePoint/search/search) и [обнаружение электронных данных](https://docs.microsoft.com/SharePoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server) для извлечения конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-112">Use [SharePoint Server search](https://docs.microsoft.com/SharePoint/search/search) and [eDiscovery](https://docs.microsoft.com/SharePoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server) to retrieve sensitive data.</span></span>

<span data-ttu-id="8fa5a-113">Рекомендуемый подход для общих папок, а также сайтов и библиотек SharePoint включает следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8fa5a-113">The recommended approach for files shares and SharePoint sites and libraries includes these steps:</span></span>

1.  <span data-ttu-id="8fa5a-114">**[Установите и настройте сканер Azure Information Protection.](https://docs.microsoft.com/ru-RU/azure/information-protection/rms-client/client-admin-guide-install#options-to-install-the-azure-information-protection-client-for-users)**</span><span class="sxs-lookup"><span data-stu-id="8fa5a-114">**[Install and configure Azure Information Protection scanner.](https://docs.microsoft.com/ru-RU/azure/information-protection/rms-client/client-admin-guide-install#options-to-install-the-azure-information-protection-client-for-users)**</span></span>

    -   <span data-ttu-id="8fa5a-115">Выберите необходимые типы конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-115">Decide which sensitive data types to use.</span></span>

    -   <span data-ttu-id="8fa5a-116">Укажите необходимые сайты SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-116">Specify which SharePoint sites to use.</span></span>

2.  <span data-ttu-id="8fa5a-117">**Выполните цикл обнаружения.**</span><span class="sxs-lookup"><span data-stu-id="8fa5a-117">**Complete a discovery cycle.**</span></span>

    -   <span data-ttu-id="8fa5a-118">Запустите сканер в режиме обнаружения и проверьте обнаруженные данные.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-118">Run the scanner in discovery mode and validate the findings.</span></span>

    -   <span data-ttu-id="8fa5a-119">При необходимости оптимизируйте условия и типы конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-119">If needed, optimize the conditions and sensitive information types.</span></span>

    -   <span data-ttu-id="8fa5a-120">Оцените ожидаемое воздействие автоматического применения меток.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-120">Assess the expected impact of automatically applying labels.</span></span>

3.  <span data-ttu-id="8fa5a-121">**Запустите сканер Azure Information Protection для применения меток к соответствующим документам**.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-121">**Run the Azure Information Protection scanner to apply labels to qualifying documents**.</span></span>

4.  <span data-ttu-id="8fa5a-122">**Для защиты:**</span><span class="sxs-lookup"><span data-stu-id="8fa5a-122">**For protection:**</span></span>

    <span data-ttu-id="8fa5a-p102">a. Настройте правила защиты от потери данных в Exchange, чтобы защитить документы с нужной меткой.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p102">a.  Configure Exchange data loss prevention rules to protect documents with the desired label.</span></span>

    <span data-ttu-id="8fa5a-p103">b. Используйте разрешения, чтобы ограничить доступ к файлам.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p103">b.  Be sure permissions to limit who can access files.</span></span>

    <span data-ttu-id="8fa5a-p104">c. Используйте защиту IRM для библиотек в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p104">c.  For SharePoint, use IRM-protection for libraries.</span></span>

5.  <span data-ttu-id="8fa5a-129">**Интегрируйте журналы Windows Server с помощью средства SIEM для мониторинга.**</span><span class="sxs-lookup"><span data-stu-id="8fa5a-129">**For monitoring, integrate Windows Server logs with a SIEM tool.**</span></span>

    <span data-ttu-id="8fa5a-p105">a. Используйте центр поиска или обнаружение электронных данных, чтобы найти персональные данные по запросу субъектов данных.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p105">a.  To find personal data for data subject requests, use Search Center or eDiscovery.</span></span>

<span data-ttu-id="8fa5a-p106">Применяя метки к конфиденциальным данным, убедитесь, что используемые метки не имеют защиты. Защита включает шифрование, из-за которого службы не могут найти конфиденциальные данные в файлах.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p106">When applying labels to sensitive data, be sure to use a label that is not configured with protection. Protection includes encryption which prevents services from detecting sensitive data in the files.</span></span>

<span data-ttu-id="8fa5a-134">Дополнительные сведения об использовании сканера Azure Information Protection для поиска и пометки персональных данных см. в [наборе средств для обнаружения данных GDPR (Майкрософт)](http://aka.ms/gdprpartners) (http://aka.ms/gdprpartners).</span><span class="sxs-lookup"><span data-stu-id="8fa5a-134">For more information on using Azure Information Protection scanner to find and label personal data, see the [Microsoft GDPR Data Discovery Toolkit](http://aka.ms/gdprpartners) (http://aka.ms/gdprpartners).</span></span>

<span data-ttu-id="8fa5a-p107">Сведения о настройке сканера в соответствии с условиями и использовании типов конфиденциальной информации для защиты от потери данных (DLP) в Office 365 см. в статье [Как настроить условия для автоматической и рекомендуемой классификации с помощью Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Обратите внимание, что новые типы конфиденциальной информации Office 365 не сразу станут доступны для использования в сканере. Кроме того, в нем невозможно использовать пользовательские типы конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p107">For information on configuring the scanner for conditions and using the Office 365 data loss prevention (DLP) sensitive information types, see [How to configure conditions for automatic and recommended classification for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Note that new Office 365 sensitive information types will not be immediately available to use with the scanner and custom sensitive information types cannot be used with the scanner.</span></span>

## <a name="removing-personal-information-from-office-files"></a><span data-ttu-id="8fa5a-137">Удаление личных сведений из файлов Office</span><span class="sxs-lookup"><span data-stu-id="8fa5a-137">Removing personal information from Office files</span></span>

<span data-ttu-id="8fa5a-p108">Удаление личных сведений (таких как метаданные или комментарии в документе Word) из файлов Office, хранящихся в библиотеке документов SharePoint, необходимо выполнять вручную. Выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p108">Removing personal information (such as metadata or comments in a Word document) from Office files that are stored in a SharePoint document library must be done manually. Follow these steps:</span></span>

1.  <span data-ttu-id="8fa5a-140">Скачайте копию документа с сервера SharePoint Server на локальный диск.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-140">Download a copy of the document from SharePoint Server to your local disk.</span></span>

2.  <span data-ttu-id="8fa5a-141">Удалите документ из библиотеки документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-141">Delete the document from the SharePoint document library.</span></span>

3.  <span data-ttu-id="8fa5a-142">Выполните действия, описанные в статье [Удаление скрытых и персональных данных при проверке документов](https://support.office.com/article/356B7B5D-77AF-44FE-A07F-9AA4D085966F).</span><span class="sxs-lookup"><span data-stu-id="8fa5a-142">Follow the steps in [Remove hidden data and personal information by inspecting documents](https://support.office.com/article/356B7B5D-77AF-44FE-A07F-9AA4D085966F).</span></span>

4.  <span data-ttu-id="8fa5a-143">Отправьте документ обратно в библиотеку документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-143">Upload the document back to the SharePoint document library.</span></span>

## <a name="telemetry-and-log-files"></a><span data-ttu-id="8fa5a-144">Телеметрия и файлы журналов</span><span class="sxs-lookup"><span data-stu-id="8fa5a-144">Telemetry and log files</span></span>

### <a name="uls-logs"></a><span data-ttu-id="8fa5a-145">Журналы ULS</span><span class="sxs-lookup"><span data-stu-id="8fa5a-145">ULS Logs</span></span>

<span data-ttu-id="8fa5a-p109">Журналы ULS (единая служба ведения журналов) и журналы использования в SharePoint Server помогают отслеживать различные функции системы и могут содержать информацию о пользователе. Журналы ULS и журналы использования — это текстовые файлы, в которых можно искать информацию, используя различные поисковые средства. [Командлет Merge-SPLogFile PowerShell](https://docs.microsoft.com/ru-RU/powershell/module/sharepoint-server/merge-splogfile) позволяет возвращать записи из журналов ULS на нескольких серверах в ферме.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p109">Unified Logging Service (ULS) and Usage logging in SharePoint Server track a variety of system functions and can contain user information. ULS logs and usage logs are text files and can be searched using a variety of searching tools. The [Merge-SPLogFile PowerShell cmdlet](https://docs.microsoft.com/ru-RU/powershell/module/sharepoint-server/merge-splogfile) provides a way to return records from the ULS logs on multiple servers in a farm.</span></span>

<span data-ttu-id="8fa5a-p110">В политиках хранения журнала рекомендуется указать минимальное значение, необходимое для бизнес-целей. Сведения о настройке ведения журнала в SharePoint Server см. в статье [Настройка журнала ведения диагностики в SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p110">Consider setting log retention policies to the minimum value needed for your business purposes. For information about configuring logging in SharePoint Server, see [Configure diagnostic logging in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span></span>

<span data-ttu-id="8fa5a-151">Обратите внимание, что некоторые события системы также регистрируются в журнале событий Windows.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-151">Note that some system events are also logged to the Windows Event Log.</span></span>

### <a name="usage-database"></a><span data-ttu-id="8fa5a-152">База данных использования</span><span class="sxs-lookup"><span data-stu-id="8fa5a-152">Usage Database</span></span>

<span data-ttu-id="8fa5a-p111">База данных использования SharePoint Server (имя по умолчанию WSS_Logging) содержит часть информации, находящейся в журналах ULS. Максимальный срок хранения данных в этой базе данных составляет 30 дней. Рекомендуем настроить минимальный срок хранения, подходящий для вашей организации. Дополнительную информацию см. в статье [Настройка журнала ведения диагностики в SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p111">The SharePoint Server Usage database (default name WSS_Logging) contains a subset of the information found in the ULS logs. The maximum retention of data in this database is 30 days. We recommend that you configure it for the shortest duration allowable by your business needs. For more information, see [Configure diagnostic logging in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span></span>

## <a name="personal-information-and-search"></a><span data-ttu-id="8fa5a-157">Персональные данные и поиск</span><span class="sxs-lookup"><span data-stu-id="8fa5a-157">Personal information and search</span></span>

<span data-ttu-id="8fa5a-158">Журнал поисковых запросов и записи об использовании содержат ссылки на имена пользователей.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-158">The search query history and usage records contain references to user names.</span></span>

### <a name="query-history-and-favorite-queries"></a><span data-ttu-id="8fa5a-159">Журнал запросов и избранные запросы</span><span class="sxs-lookup"><span data-stu-id="8fa5a-159">Query history and favorite queries</span></span>

<span data-ttu-id="8fa5a-p112">В SharePoint Server срок действия журналов запросов и избранных запросов автоматически истекает через 365 дней. Если пользователь покидает вашу организацию, вы можете удалить ссылки на имя пользователя из журнала запросов, следуя приведенным ниже инструкциям.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p112">In SharePoint Server, query histories and ‘favorite’ queries automatically expire after 365 days. If a user leaves your organization, it is possible to remove references to a user's name from the query history using the steps below.</span></span>

<span data-ttu-id="8fa5a-162">Следующие SQL-запросы применяются к SharePoint Server и позволяют:</span><span class="sxs-lookup"><span data-stu-id="8fa5a-162">The following SQL queries apply to SharePoint Server and make it possible to:</span></span>

-   <span data-ttu-id="8fa5a-163">Экспортировать журнал запросов или избранные запросы пользователя.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-163">Export a user’s query history or favorite queries</span></span>

-   <span data-ttu-id="8fa5a-164">Удалять ссылки на имена пользователей в журнале запросов.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-164">Remove references to user names in the query history</span></span>

#### <a name="export-a-users-queries-since-a-specific-date"></a><span data-ttu-id="8fa5a-165">Экспорт запросов пользователя начиная с определенной даты</span><span class="sxs-lookup"><span data-stu-id="8fa5a-165">Export a user’s queries since a specific date</span></span> 

<span data-ttu-id="8fa5a-166">Используйте следующую процедуру, чтобы экспортировать запросы, выполненные пользователем @UserName начиная с @StartTime, из таблиц журнала запросов Link Store.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-166">Use the following procedure to export queries from the Link Store query log tables, performed by @UserName since @StartTime.</span></span>

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

#### <a name="export-a-users-queries-from-the-past-100-days"></a><span data-ttu-id="8fa5a-167">Экспорт запросов пользователя за последние 100 дней</span><span class="sxs-lookup"><span data-stu-id="8fa5a-167">Export a user’s queries from the past 100 days</span></span>

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetQueryTermsForUser '0#.w|domain\username', @FROMDATE 
```

#### <a name="export-a-users-favorite-queries"></a><span data-ttu-id="8fa5a-168">Экспорт избранных запросов пользователя</span><span class="sxs-lookup"><span data-stu-id="8fa5a-168">Export a user’s favorite queries</span></span>

<span data-ttu-id="8fa5a-169">Выполните указанные ниже действия, чтобы экспортировать избранные запросы пользователя, выполненные пользователем @UserName начиная с <DateTime>, из таблиц личных результатов базы данных администрирования поиска.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-169">Use the following procedure to export a user's favorite queries from the Search Admin DB personal result tables, performed by @UserName, since <DateTime>.</span></span>

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

#### <a name="export-a-users-favorite-queries-from-the-past-100-days"></a><span data-ttu-id="8fa5a-170">Экспорт избранных запросов пользователя за последние 100 дней</span><span class="sxs-lookup"><span data-stu-id="8fa5a-170">Export a user’s favorite queries from the past 100 days</span></span> 

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetPersonalFavoriteQueries '0#.w|domain\username', @FROMDATE 
```

#### <a name="remove-references-to-user-names-that-are-more-than-x-days-old"></a><span data-ttu-id="8fa5a-171">Удаление ссылок на имена пользователей, которые старше X дней</span><span class="sxs-lookup"><span data-stu-id="8fa5a-171">Remove references to user names that are more than X days old</span></span>

<span data-ttu-id="8fa5a-p113">Используйте следующую процедуру, чтобы удалить ссылки на *все* имена пользователей, которые старше @Days, из таблиц журнала запросов Links Store. Процедура удаляет прошлые ссылки, пока не будет достигнуто время @LastCleanupTime.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p113">Use the following procedure to remove references to *all* user names that are more than @Days old, from the Links Store query log tables. The procedure only removes references backwards in time until it reaches the @LastCleanupTime.</span></span>

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

#### <a name="remove-references-to-a-specific-user-name-thats-more-than-x-days-old"></a><span data-ttu-id="8fa5a-174">Удаление ссылок на определенное имя пользователя, которые старше X дней</span><span class="sxs-lookup"><span data-stu-id="8fa5a-174">Remove references to a specific user name that’s more than X days old</span></span>

<span data-ttu-id="8fa5a-p114">Используйте следующую процедуру, чтобы удалить ссылки на *определенное* имя пользователя из таблиц журнала запросов Links Store, где ссылки старше @Days. Процедура удаляет прошлые ссылки, пока не будет достигнуто время @LastCleanupTime.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p114">Use the following procedure to remove references to a *specific* user name from the Links Store query log tables, where the references are more than @Days old. The procedure only removes references backwards in time until it reaches the @LastCleanupTime.</span></span>

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

#### <a name="remove-references-to-all-user-names-in-the-query-history-from-a-date-and-up-to-the-past-30-days"></a><span data-ttu-id="8fa5a-177">Удаление ссылок на все имена пользователей в журнале запросов за последние несколько (до 30) дней начиная с определенной даты</span><span class="sxs-lookup"><span data-stu-id="8fa5a-177">Remove references to all user names in the query history from a date and up to the past 30 days</span></span>

```sql
EXECUTE proc_MSS_QLog_Cleanup_Users '1-1-2017', 30 
```

### <a name="delete-usage-records"></a><span data-ttu-id="8fa5a-178">Удаление записей об использовании</span><span class="sxs-lookup"><span data-stu-id="8fa5a-178">Delete usage records</span></span>

<span data-ttu-id="8fa5a-p115">SharePoint Server автоматически удаляет записи об использовании через 3 года. Вы можете вручную удалить такие записи с помощью описанной ниже процедуры:</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p115">SharePoint Server automatically deletes usage records after 3 years. You can manually delete such records using the procedure below:</span></span>

<span data-ttu-id="8fa5a-181">Чтобы удалить все записи об использовании, связанные с удаленными документами:</span><span class="sxs-lookup"><span data-stu-id="8fa5a-181">To delete all usage records associated with deleted documents:</span></span> 

1.  <span data-ttu-id="8fa5a-182">Убедитесь, что у вас установлено последнее обновление SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-182">Ensure that you have the latest SharePoint update installed.</span></span> 

2.  <span data-ttu-id="8fa5a-183">Запустите командную консоль SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-183">Start a SharePoint Management shell.</span></span>

3.  <span data-ttu-id="8fa5a-184">Остановите аналитику использования и очистите ее данные:</span><span class="sxs-lookup"><span data-stu-id="8fa5a-184">Stop and Clear the Usage Analytics analysis:</span></span> 

    ```powershell
    $tj = Get-SPTimerJob -Type Microsoft.Office.Server.Search.Analytics.UsageAnalyticsJobDefinition 
    $tj.DisableTimerjobSchedule()
    $tj.StopAnalysis() 
    $tj.ClearAnalysis() 
    $tj.EnableTimerjobSchedule()
    ```

4.  <span data-ttu-id="8fa5a-185">Подождите, пока аналитика не запустится снова (может потребоваться до 24 часов).</span><span class="sxs-lookup"><span data-stu-id="8fa5a-185">Wait for the analysis to start again (might take up to 24 hours).</span></span> 

5.  <span data-ttu-id="8fa5a-p116">При следующем запуске аналитики все записи из базы данных отчетов аналитики будут записаны в дамп. Выполнение полного дампа большой базы данных с множеством записей может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p116">On the next run of the analysis, it will dump all records from the Analytics Reporting database. This full dump may take a while for a large database with many entries.</span></span>

6.  <span data-ttu-id="8fa5a-p117">Подождите 10 дней. Аналитика запускается ежедневно, и записи, связанные с удаленными документами, будут удалены после 10-го запуска. Если удаляемых записей очень много, этот запуск может занять больше времени, чем обычно.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p117">Wait for 10 days. The analysis runs daily, and records associated with deleted documents will be removed after the 10^th^ run. This run may take longer than normal if many records need to be deleted.</span></span> 

### <a name="personal-information-and-search-in-sharepoint-server-2010"></a><span data-ttu-id="8fa5a-191">Персональные данные и поиск в SharePoint Server 2010</span><span class="sxs-lookup"><span data-stu-id="8fa5a-191">Personal information and search in SharePoint Server 2010</span></span>

#### <a name="fast-search-server-2010-for-sharepoint"></a><span data-ttu-id="8fa5a-192">FAST Search Server 2010 для SharePoint</span><span class="sxs-lookup"><span data-stu-id="8fa5a-192">FAST Search Server 2010 for SharePoint</span></span> 

<span data-ttu-id="8fa5a-p118">Помимо индекса, надстройка FAST Search Server 2010 также хранит файлы в промежуточном формате, называемом FixML. Файлы FiXML регулярно сжимаются (по умолчанию каждую ночь с 3:00 до 5:00). При сжатии из этих файлов автоматически исключаются удаленные файлы. Чтобы обеспечить своевременное удаление информации, принадлежащей удаленным пользователям или документам, убедитесь, что функция сжатия всегда включена.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p118">In addition to storing files in the index, the FAST Search Server 2010 Add-On also stores files in an intermediate format called FixML. FiXML files are compacted regularly, by default between 3 am and 5 am every night. Compaction removes deleted files from the FiXML files automatically. To ensure timely removal of information belonging to deleted users or documents, ensure that compaction is always enabled.</span></span>

### <a name="hybrid-search"></a><span data-ttu-id="8fa5a-197">Гибридный поиск</span><span class="sxs-lookup"><span data-stu-id="8fa5a-197">Hybrid Search</span></span> 

<span data-ttu-id="8fa5a-p119">Рекомендуемые действия для решений гибридного поиска аналогичны действиям для поиска в SharePoint Server или SharePoint Online. Существует два решения гибридного поиска:</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p119">The recommended actions for hybrid search solutions are the same as for search in SharePoint Server or SharePoint Online. There are two hybrid search solutions:</span></span>

<span data-ttu-id="8fa5a-p120">**Решение для облачного гибридного поиска.** Вы вносите весь просканированный контент, в том числе локальный, в индекс поиска Office 365. Когда пользователи запрашивают информацию в индексе поиска Office 365, они получают результат из локального контента и контента Office 365. При удалении документов из среды SharePoint Server они также удаляются из индекса поиска Office 365. Чтобы лучше понять, как GDPR влияет на гибридную среду, [ознакомьтесь с информацией о решении для облачного гибридного поиска](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint) и [взаимодействии поисковых компонентов и баз данных в облачном гибридном поиске](https://docs.microsoft.com/sharepoint/hybrid/plan-cloud-hybrid-search-for-sharepoint).</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p120">**The cloud hybrid search solution -** With the cloud hybrid search solution for SharePoint, you index all your crawled content, including on-premises content, in your search index in Office 365. When users query your search index in Office 365, they get search results from both on-premises and Office 365 content. When documents are deleted from the SharePoint Server environment, they are also deleted from the search index in Office 365. [Read more about the cloud hybrid search solution](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint) and [how search components and databases interact in cloud hybrid search](https://docs.microsoft.com/sharepoint/hybrid/plan-cloud-hybrid-search-for-sharepoint) to understand better how GDPR affects the hybrid environment.</span></span>

<span data-ttu-id="8fa5a-p121">**Решение для гибридного федеративного поиска.** Вы используете индексы как из SharePoint Server, так и из Office 365. Службы поиска SharePoint Server и SharePoint Online могут отправлять запросы к индексу поиска в другой среде и возвращать федеративные результаты. Когда пользователи выполняют поиск в центре поиска, результаты поступают из поисковых индексов как в SharePoint Server, так и в Office 365. Чтобы лучше понять, как GDPR влияет на гибридную среду, [ознакомьтесь с информацией о решении для гибридного федеративного поиска](https://docs.microsoft.com/sharepoint/hybrid/learn-about-hybrid-federated-search-for-sharepoint).</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p121">**The hybrid federated search solution -** With the hybrid federated search solution, you use both your index in SharePoint Server and your index in Office 365. Both SharePoint Server and SharePoint Online Search services can query the search index in the other environment and return federated results. When users search from a Search Center, the search results come from both your search index in SharePoint Server and your search index in Office 365. [Read more about the hybrid federated search solution](https://docs.microsoft.com/sharepoint/hybrid/learn-about-hybrid-federated-search-for-sharepoint) to understand better how GDPR affects the hybrid environment.</span></span>

## <a name="on-prem-to-cloud-migrations"></a><span data-ttu-id="8fa5a-208">Перенос локальных данных в облако</span><span class="sxs-lookup"><span data-stu-id="8fa5a-208">On Prem to Cloud Migrations</span></span>

<span data-ttu-id="8fa5a-p122">При переносе данных из SharePoint Server в SharePoint Online в течение определенного времени данные могут дублироваться. Если у вас есть данные, которые необходимо удалить в середине переноса, рекомендуем сначала выполнить перенос, а затем удалить их из обоих расположений. Вы можете запросить данные для экспорта из любого расположения.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p122">While migrating data from SharePoint Server to SharePoint Online, duplicate data may exist in both locations for a time. If you have data that you need to delete that is in mid-migration, we recommend that you complete the migration first, and then delete the data from both locations. You can query data for export from either location.</span></span>

## <a name="user-profile-data"></a><span data-ttu-id="8fa5a-212">Данные профиля пользователя</span><span class="sxs-lookup"><span data-stu-id="8fa5a-212">User Profile data</span></span>

<span data-ttu-id="8fa5a-p123">Служба профилей пользователей позволяет импортировать данные профилей из различных внешних источников. Запросы и обновления таких данных профиля пользователя должны обрабатываться в системах, управляющих этими данными. Если вы обновляете внешние системы, не забудьте повторно синхронизировать профили пользователей в SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p123">The User Profile Service allows for import of profile data from a variety of external sources. Queries for and update of such user profile data should be handled in the systems in which the data is mastered. If you make updates to the external system, be sure to synchronize the user profiles in SharePoint Server again.</span></span>

<span data-ttu-id="8fa5a-216">Выполните следующие действия, чтобы удалить персональные данные пользователя из его профиля в SharePoint Server:</span><span class="sxs-lookup"><span data-stu-id="8fa5a-216">Follow these basic steps to remove a user’s personal information from their SharePoint Server user profile:</span></span>

1.  <span data-ttu-id="8fa5a-p124">Удалите информацию о пользователе из внешних систем, которые предоставляют данные для профиля в SharePoint Server. Если вы используете синхронизацию службы каталогов, пользователя необходимо удалить из локальной среды Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p124">Remove the user information from any external systems that feed into the SharePoint Server user profile. If you are using directory synchronization, the user must be removed from the on-premises Active Directory environment.</span></span>

2.  <span data-ttu-id="8fa5a-219">Запустите [синхронизацию профилей](https://docs.microsoft.com/sharepoint/administration/start-profile-synchronization-manually) на SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-219">Run a [profile synchronization](https://docs.microsoft.com/sharepoint/administration/start-profile-synchronization-manually) on SharePoint Server.</span></span>

3.  <span data-ttu-id="8fa5a-p125">Удалите профиль с сервера SharePoint Server. После этого SharePoint Server полностью удалит этот профиль из базы данных профилей пользователей в течение 30 дней. Страница профиля и персональный сайт пользователя будут удалены.</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p125">Delete the profile from SharePoint Server. Once this is done, SharePoint Server will fully remove the profile from the User Profile Database in 30 days. The user’s profile page and personal site will be deleted.</span></span>

<span data-ttu-id="8fa5a-p126">После удаления профиля в семействах веб-сайтов, которые посещал этот пользователь, по-прежнему может оставаться некоторая информация (например, ИД пользователя). Чтобы удалить эти данные из определенного семейства веб-сайтов, воспользуйтесь CSOM. Пример сценария представлен ниже:</span><span class="sxs-lookup"><span data-stu-id="8fa5a-p126">After deleting a user’s profile, some limited information (such as user ID) may still be recorded in site collections that the user has visited. If you choose to delete this data from a given site collection, this can be done using CSOM. A sample script is provided below:</span></span>

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
