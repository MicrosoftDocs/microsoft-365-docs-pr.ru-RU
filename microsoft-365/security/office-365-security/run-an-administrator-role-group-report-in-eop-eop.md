---
title: Запуск отчета группы ролей администратора в автономной службе EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как запускать отчет о группе ролей администраторов в автономных службах Exchange Online Protection (EOP). Этот отчет занося в журнал, когда администратор добавляет участников в группы ролей администраторов или удаляет их из них.
ms.openlocfilehash: cd7ca13a3d863240a0f2608ed13321cbe3d50ad2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659291"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="81e06-104">Запуск отчета группы ролей администратора в автономной службе EOP</span><span class="sxs-lookup"><span data-stu-id="81e06-104">Run an administrator role group report in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="81e06-105">В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online, когда администратор добавляет участников в группы административных ролей или удаляет их из них, служба регистрирует каждое событие.</span><span class="sxs-lookup"><span data-stu-id="81e06-105">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="81e06-106">Дополнительные сведения о группах ролей в автономных EOP см. в [подгоне "Разрешения" в автономных EOP.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="81e06-106">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="81e06-107">При запуске отчета о группе ролей администраторов в Центре администрирования Exchange записи отображаются в качестве результатов поиска и включают затронутые группы ролей, кто изменил членство в группе ролей и когда, а также какие обновления членства были сделаны.</span><span class="sxs-lookup"><span data-stu-id="81e06-107">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="81e06-108">Этот отчет можно использовать для отслеживания изменений в административных разрешениях, назначенных пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="81e06-108">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="81e06-109">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="81e06-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="81e06-110">Чтобы открыть Центр администрирования Exchange, см. центр [администрирования Exchange в режиме автономных EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="81e06-110">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="81e06-111">Для работы с процедурами, которые данная статья, вам должны быть назначены разрешения в Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="81e06-111">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="81e06-112">В частности, вам  потребуется роль  "Журналы аудита" или "Только просмотр журналов аудита", которые по умолчанию назначены группам ролей "Управление организацией", "Управление соответствием требованиям" и "Администратор безопасности".   </span><span class="sxs-lookup"><span data-stu-id="81e06-112">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="81e06-113">Дополнительные сведения см. в сведениях о разрешениях в автономных [EOP](feature-permissions-in-eop.md) и использовании EAC для изменения списка участников [в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="81e06-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="81e06-114">Сведения о сочетаниях клавиш, которые могут применяться к процедурам в этой статье, см. в статье "Сочетания клавиш" для Центра администрирования [Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="81e06-114">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="81e06-115">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="81e06-115">Having problems?</span></span> <span data-ttu-id="81e06-116">Обратитесь за помощью на форум по [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="81e06-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="81e06-117">Запуск отчета о группе ролей администраторов с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="81e06-117">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="81e06-118">Запустите отчет о группе ролей администраторов, чтобы найти изменения в группах ролей управления за определенный период времени.</span><span class="sxs-lookup"><span data-stu-id="81e06-118">Run the administrator role group report to find the changes to management role groups within a particular time frame.</span></span>

1. <span data-ttu-id="81e06-119">В EAC перейдите  в "Аудит соответствия требованиям" и выберите "Запуск отчета о группе ролей \>  **администраторов".**</span><span class="sxs-lookup"><span data-stu-id="81e06-119">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="81e06-120">На **открываемой странице "Поиск** изменений в группах ролей администраторов" настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="81e06-120">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="81e06-121">**Дата начала** и **дата окончания:** введите диапазон дат.</span><span class="sxs-lookup"><span data-stu-id="81e06-121">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="81e06-122">По умолчанию отчет выполняет поиск изменений в группе ролей администраторов за последние две недели.</span><span class="sxs-lookup"><span data-stu-id="81e06-122">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="81e06-123">**Выберите группы ролей:** по умолчанию поиск ведется во всех группах ролей.</span><span class="sxs-lookup"><span data-stu-id="81e06-123">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="81e06-124">Чтобы отфильтровать результаты по определенным группам ролей, щелкните **"Выбрать группы ролей".**</span><span class="sxs-lookup"><span data-stu-id="81e06-124">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="81e06-125">В отображемом диалоговом окте выберите группу ролей и нажмите **кнопку add ->.**</span><span class="sxs-lookup"><span data-stu-id="81e06-125">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="81e06-126">Повторите этот шаг столько раз,  сколько необходимо, и нажмите кнопку "ОК", когда закончите.</span><span class="sxs-lookup"><span data-stu-id="81e06-126">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="81e06-127">По завершению нажмите кнопку **"Поиск".**</span><span class="sxs-lookup"><span data-stu-id="81e06-127">When you're finished, click **Search**.</span></span>

<span data-ttu-id="81e06-p108">Если будут найдены любые изменения, соответствующие заданным критериям, они появятся в области результатов. Чтобы в области сведений увидеть изменения, выберите группу ролей в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="81e06-p108">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="81e06-130">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="81e06-130">How do you know this worked?</span></span>

<span data-ttu-id="81e06-p109">Если отчет о группе ролей администрирования запущен успешно, группы ролей, измененные в рамках диапазона дат, отображаются в области результатов поиска. Если результатов нет  в указанный диапазон дат группы ролей изменены не были. Если вы считаете, что результаты должны быть, измените диапазон дат и повторно запустите отчет.</span><span class="sxs-lookup"><span data-stu-id="81e06-p109">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="81e06-134">Отслеживание изменений состава группы ролей</span><span class="sxs-lookup"><span data-stu-id="81e06-134">Monitor changes to role group membership</span></span>

<span data-ttu-id="81e06-p110">При добавлении или удалении участников группы ролей результаты поиска в области сведений указывают на изменение состава группы ролей с указанием ее текущих участников. В результатах не говорится явно, кто был добавлен или удален.</span><span class="sxs-lookup"><span data-stu-id="81e06-p110">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="81e06-p111">Чтобы определить, был ли добавлен или удален пользователь, следует сравнить две записи в отчете. Например, рассмотрим следующие записи журнала для группы ролей **HelpDesk**.</span><span class="sxs-lookup"><span data-stu-id="81e06-p111">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="81e06-139">27.01.2018 16:43</span><span class="sxs-lookup"><span data-stu-id="81e06-139">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="81e06-140">Администратор</span><span class="sxs-lookup"><span data-stu-id="81e06-140">Administrator</span></span> <br> <span data-ttu-id="81e06-141">Обновленные участники: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="81e06-141">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="81e06-142">06.02.2018 10:09</span><span class="sxs-lookup"><span data-stu-id="81e06-142">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="81e06-143">Администратор</span><span class="sxs-lookup"><span data-stu-id="81e06-143">Administrator</span></span> <br> <span data-ttu-id="81e06-144">Обновленные участники: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="81e06-144">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="81e06-145">19.02.2018 14:12</span><span class="sxs-lookup"><span data-stu-id="81e06-145">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="81e06-146">Администратор</span><span class="sxs-lookup"><span data-stu-id="81e06-146">Administrator</span></span> <br> <span data-ttu-id="81e06-147">Обновленные участники: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="81e06-147">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="81e06-148">В этом примере администратор внес следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="81e06-148">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="81e06-149">06.02.2018 добавлен пользователь для фрагмента.</span><span class="sxs-lookup"><span data-stu-id="81e06-149">On 2/06/2018, they added the user tonip.</span></span>
- <span data-ttu-id="81e06-150">19.02.2018 они удалили пользователя pilarp.</span><span class="sxs-lookup"><span data-stu-id="81e06-150">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="81e06-151">Использование автономных Exchange Online PowerShell для поиска записей журнала аудита</span><span class="sxs-lookup"><span data-stu-id="81e06-151">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="81e06-152">Вы можете использовать Exchange Online PowerShell для поиска записей журнала аудита, которые соответствуют заявляемой вами критерии.</span><span class="sxs-lookup"><span data-stu-id="81e06-152">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="81e06-153">Список критериев поиска см. в поиске [Search-AdminAuditLog.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)</span><span class="sxs-lookup"><span data-stu-id="81e06-153">For a list of search criteria, see [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="81e06-154">В этой процедуре используется **cmdlet Search-AdminAuditLog** и отображаются результаты поиска в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81e06-154">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="81e06-155">Его можно использовать, если вам нужно вернуть набор результатов, превыша который превышает ограничения, определенные в данных о новом **администратореAuditLogSearch** или в отчетах отчетов аудита EAC.</span><span class="sxs-lookup"><span data-stu-id="81e06-155">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="81e06-156">Чтобы выполнить поиск по указанному критерию журнала аудита, используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="81e06-156">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="81e06-157">Командлет **Search-AdminAuditLog** по умолчанию возвращает максимум 1000 записей журнала.</span><span class="sxs-lookup"><span data-stu-id="81e06-157">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="81e06-158">Используйте параметр _ResultSize,_ чтобы указать до 250 000 записей журнала.</span><span class="sxs-lookup"><span data-stu-id="81e06-158">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="81e06-159">Или используйте значение для `Unlimited` возврата всех записей.</span><span class="sxs-lookup"><span data-stu-id="81e06-159">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="81e06-160">В этом примере выполняется поиск всех записей журнала аудита со следующими критериями:</span><span class="sxs-lookup"><span data-stu-id="81e06-160">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="81e06-161">**Дата начала:** 04.08.2018</span><span class="sxs-lookup"><span data-stu-id="81e06-161">**Start date**: 08/04/2018</span></span>
- <span data-ttu-id="81e06-162">**Дата окончания:** 03.01.2018</span><span class="sxs-lookup"><span data-stu-id="81e06-162">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="81e06-163">**ИД пользователей:** `davids` , `chrisd` , `kima`</span><span class="sxs-lookup"><span data-stu-id="81e06-163">**User IDs**: `davids`, `chrisd`, `kima`</span></span>
- <span data-ttu-id="81e06-164">**Cmdlets**: **Set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="81e06-164">**Cmdlets**: **Set-Mailbox**</span></span>
- <span data-ttu-id="81e06-165">**Параметры:** _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="81e06-165">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="81e06-p114">В этом примере выполняется поиск изменений определенных почтовых ящиков. Это позволяет определить неполадку или предоставить сведения для диагностики. Используются следующие критерии:</span><span class="sxs-lookup"><span data-stu-id="81e06-p114">This example searches for changes made to a specific mailbox. This is useful if you're troubleshooting or you need to provide information for an investigation. The following criteria are used:</span></span>

- <span data-ttu-id="81e06-169">**Дата начала:** 01.05.2018</span><span class="sxs-lookup"><span data-stu-id="81e06-169">**Start date**: 05/01/2018</span></span>
- <span data-ttu-id="81e06-170">**Дата окончания:** 03.01.2018</span><span class="sxs-lookup"><span data-stu-id="81e06-170">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="81e06-171">**ИД объекта**: contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="81e06-171">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="81e06-172">Если поиск возвращает много записей журнала, рекомендуется использовать процедуру, представленную в **Exchange Online PowerShell,** для поиска записей журнала аудита и отправки результатов получателю далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="81e06-172">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article.</span></span> <span data-ttu-id="81e06-173">Действия в этом разделе позволяют отправить XML-файл в виде вложения сообщения электронной почты указанным отправителям, чтобы быстрее извлечь интересующие данные.</span><span class="sxs-lookup"><span data-stu-id="81e06-173">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="81e06-174">Дополнительные сведения о синтаксисе и параметрах см. в разделе [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="81e06-174">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="81e06-175">Просмотр подробных сведений о записях журнала аудита</span><span class="sxs-lookup"><span data-stu-id="81e06-175">View details of audit log entries</span></span>

<span data-ttu-id="81e06-176">The **Search-AdminAuditLog cmdlet** returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span><span class="sxs-lookup"><span data-stu-id="81e06-176">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="81e06-177">Поля **CmdletParameters** и **ModifiedProperties**, возвращаемые командлетом, содержат дополнительные сведения, которые невозможно просмотреть по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="81e06-177">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="81e06-178">Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedProperties**, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="81e06-178">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="81e06-179">Кроме того, вы можете использовать процедуру в **Exchange Online PowerShell** для поиска записей журнала аудита и отправки результатов получателю далее в этой статье, чтобы создать XML-файл.</span><span class="sxs-lookup"><span data-stu-id="81e06-179">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article to create an XML file.</span></span>

<span data-ttu-id="81e06-180">В этой процедуре используются следующие основные понятия:</span><span class="sxs-lookup"><span data-stu-id="81e06-180">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="81e06-181">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="81e06-181">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="81e06-182">about_Variables</span><span class="sxs-lookup"><span data-stu-id="81e06-182">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="81e06-183">Определите критерии поиска, запустите командлет **Search-AdminAuditLog** и сохраните результаты в переменной с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="81e06-183">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. <span data-ttu-id="81e06-184">Каждая запись журнала аудита хранится в переменной как элемент `$Results` массива.</span><span class="sxs-lookup"><span data-stu-id="81e06-184">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="81e06-185">Чтобы выбрать элемент массива, укажите его индекс.</span><span class="sxs-lookup"><span data-stu-id="81e06-185">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="81e06-186">Индексы элементов массива начинаются с 0 для первого элемента массива.</span><span class="sxs-lookup"><span data-stu-id="81e06-186">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="81e06-187">Например, чтобы получить пятый элемент массива с индексом 4, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="81e06-187">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

   ```PowerShell
   $Results[4]
   ```

3. <span data-ttu-id="81e06-p119">Предыдущая команда возвращает запись журнала, хранящуюся в элементе массива 4. Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedProperties** для этой записи журнала, используйте следующие команды.</span><span class="sxs-lookup"><span data-stu-id="81e06-p119">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. <span data-ttu-id="81e06-190">Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedParameters** в другой записи журнала, измените индекс элемента массива.</span><span class="sxs-lookup"><span data-stu-id="81e06-190">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>
