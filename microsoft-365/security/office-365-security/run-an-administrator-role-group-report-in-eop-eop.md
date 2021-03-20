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
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как запустить отчет группы ролей администратора в автономных Exchange Online Protection (EOP). Этот отчет входит в журнал, когда администратор добавляет членов в группы ролей администратора или удаляет их из них.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0281dcb13f5cee0ba8db8c4faed5054f481337cf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908798"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="bd0cc-104">Запуск отчета группы ролей администратора в автономной службе EOP</span><span class="sxs-lookup"><span data-stu-id="bd0cc-104">Run an administrator role group report in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bd0cc-105">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="bd0cc-105">**Applies to**</span></span>
-  [<span data-ttu-id="bd0cc-106">Автономный exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bd0cc-106">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="bd0cc-107">В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online администратор добавляет членов в группы административных ролей или удаляет их, служба регистрирует каждое событие.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-107">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="bd0cc-108">Дополнительные сведения о группах ролей в автономных EOP см. в рублях [Permissions in standalone EOP.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="bd0cc-108">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="bd0cc-109">При запуске отчета группы ролей администратора в центре администрирования Exchange (EAC) записи отображаются в качестве результатов поиска и включают затронутые группы ролей, которые изменили членство в группе ролей и когда и какие обновления членства были сделаны.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-109">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="bd0cc-110">Этот отчет можно использовать для отслеживания изменений в административных разрешениях, назначенных пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-110">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bd0cc-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="bd0cc-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bd0cc-112">Чтобы открыть центр администрирования Exchange, см. в [центре администрирования Exchange в режиме автономный EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="bd0cc-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="bd0cc-113">Вам необходимо получить разрешения в Exchange Online Protection, прежде чем вы сможете сделать процедуры в этой статье.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="bd0cc-114">В частности, вам  потребуется роль  журналов аудита или журналов аудита только для просмотра,  которые по умолчанию назначены группам ролей "Управление **организацией",**"Управление соответствием требованиям" и "Администратор безопасности".</span><span class="sxs-lookup"><span data-stu-id="bd0cc-114">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="bd0cc-115">Дополнительные сведения см. в рублях Разрешения в автономных [EOP](feature-permissions-in-eop.md) и Use the EAC изменить список участников [в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="bd0cc-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="bd0cc-116">Сведения о ярлыках клавиатуры, которые могут применяться к процедурам в этой статье, см. в статье Клавишные ярлыки для центра администрирования Exchange в [Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="bd0cc-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="bd0cc-117">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="bd0cc-117">Having problems?</span></span> <span data-ttu-id="bd0cc-118">Обратитесь за помощью на форум по [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).</span><span class="sxs-lookup"><span data-stu-id="bd0cc-118">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="bd0cc-119">Запуск отчета о группе ролей администраторов с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="bd0cc-119">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="bd0cc-120">Запустите отчет группы ролей администратора, чтобы найти изменения в группах ролей управления в определенный период времени.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-120">Run the administrator role group report to find the changes to management role groups within a particular time frame.</span></span>

1. <span data-ttu-id="bd0cc-121">В EAC перейдите **к** аудиту управления соответствием, а затем выберите Отчет группы ролей \>  **администратора.**</span><span class="sxs-lookup"><span data-stu-id="bd0cc-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="bd0cc-122">На **открываемой странице Поиск** изменений групп ролей администратора настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="bd0cc-122">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="bd0cc-123">**Дата начала** и **дата окончания.** Введите диапазон дат.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-123">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="bd0cc-124">По умолчанию отчет выполняет поиск изменений в группе ролей администраторов за последние две недели.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-124">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="bd0cc-125">**Выберите группы ролей.** По умолчанию все группы ролей будут искаться.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-125">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="bd0cc-126">Чтобы фильтровать результаты определенными группами ролей, щелкните **Выберите группы ролей.**</span><span class="sxs-lookup"><span data-stu-id="bd0cc-126">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="bd0cc-127">В диалоговом октаге, который отображается, выберите группу ролей и нажмите **кнопку добавить ->**.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-127">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="bd0cc-128">Повторите этот шаг столько раз, сколько необходимо, а затем нажмите **кнопку ОК,** когда вы закончите.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-128">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="bd0cc-129">Когда вы закончите, нажмите кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-129">When you're finished, click **Search**.</span></span>

<span data-ttu-id="bd0cc-p108">Если будут найдены любые изменения, соответствующие заданным критериям, они появятся в области результатов. Чтобы в области сведений увидеть изменения, выберите группу ролей в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-p108">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="bd0cc-132">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="bd0cc-132">How do you know this worked?</span></span>

<span data-ttu-id="bd0cc-p109">Если отчет о группе ролей администрирования запущен успешно, группы ролей, измененные в рамках диапазона дат, отображаются в области результатов поиска. Если результатов нет  в указанный диапазон дат группы ролей изменены не были. Если вы считаете, что результаты должны быть, измените диапазон дат и повторно запустите отчет.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-p109">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="bd0cc-136">Отслеживание изменений состава группы ролей</span><span class="sxs-lookup"><span data-stu-id="bd0cc-136">Monitor changes to role group membership</span></span>

<span data-ttu-id="bd0cc-p110">При добавлении или удалении участников группы ролей результаты поиска в области сведений указывают на изменение состава группы ролей с указанием ее текущих участников. В результатах не говорится явно, кто был добавлен или удален.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-p110">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="bd0cc-p111">Чтобы определить, был ли добавлен или удален пользователь, следует сравнить две записи в отчете. Например, рассмотрим следующие записи журнала для группы ролей **HelpDesk**.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-p111">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="bd0cc-141">1/27/2018 16:43</span><span class="sxs-lookup"><span data-stu-id="bd0cc-141">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="bd0cc-142">Администратор</span><span class="sxs-lookup"><span data-stu-id="bd0cc-142">Administrator</span></span> <br> <span data-ttu-id="bd0cc-143">Обновленные участники: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="bd0cc-143">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="bd0cc-144">02.06.2018 10:09</span><span class="sxs-lookup"><span data-stu-id="bd0cc-144">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="bd0cc-145">Администратор</span><span class="sxs-lookup"><span data-stu-id="bd0cc-145">Administrator</span></span> <br> <span data-ttu-id="bd0cc-146">Обновленные участники: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="bd0cc-146">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="bd0cc-147">19.19.2018 14:12</span><span class="sxs-lookup"><span data-stu-id="bd0cc-147">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="bd0cc-148">Администратор</span><span class="sxs-lookup"><span data-stu-id="bd0cc-148">Administrator</span></span> <br> <span data-ttu-id="bd0cc-149">Обновленные участники: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="bd0cc-149">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="bd0cc-150">В этом примере администратор внес следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="bd0cc-150">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="bd0cc-151">2.06.2018 они добавили пользовательский tonip.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-151">On 2/06/2018, they added the user tonip.</span></span>
- <span data-ttu-id="bd0cc-152">2/19/2018 они удалили pilarp пользователя.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-152">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="bd0cc-153">Для поиска записей журналов аудита используйте автономный Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd0cc-153">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="bd0cc-154">Вы можете использовать Exchange Online PowerShell для поиска записей журналов аудита, которые соответствуют критериям, которые вы указываете.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-154">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="bd0cc-155">Список критериев поиска см. в списке критериев поиска [Search-AdminAuditLog.](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)</span><span class="sxs-lookup"><span data-stu-id="bd0cc-155">For a list of search criteria, see [Search-AdminAuditLog search criteria](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="bd0cc-156">Эта процедура использует **кодлет Search-AdminAuditLog** и отображает результаты поиска в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-156">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="bd0cc-157">Этот комдлет можно использовать, когда необходимо вернуть набор результатов, превышает ограничения, определенные в комлете **New-AdminAuditLogSearch** или в отчетах аудита EAC.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-157">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="bd0cc-158">Чтобы выполнить поиск по указанному критерию журнала аудита, используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-158">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="bd0cc-159">Командлет **Search-AdminAuditLog** по умолчанию возвращает максимум 1000 записей журнала.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-159">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="bd0cc-160">Чтобы указать до 250 000 записей журнала, используйте параметр _ResultSize._</span><span class="sxs-lookup"><span data-stu-id="bd0cc-160">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="bd0cc-161">Или используйте значение для `Unlimited` возврата всех записей.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-161">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="bd0cc-162">В этом примере выполняется поиск всех записей журнала аудита со следующими критериями:</span><span class="sxs-lookup"><span data-stu-id="bd0cc-162">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="bd0cc-163">**Дата начала:** 08.04.2018</span><span class="sxs-lookup"><span data-stu-id="bd0cc-163">**Start date**: 08/04/2018</span></span>
- <span data-ttu-id="bd0cc-164">**Дата окончания:** 10.03.2018</span><span class="sxs-lookup"><span data-stu-id="bd0cc-164">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="bd0cc-165">**Пользовательские ID:** `davids` , `chrisd``kima`</span><span class="sxs-lookup"><span data-stu-id="bd0cc-165">**User IDs**: `davids`, `chrisd`, `kima`</span></span>
- <span data-ttu-id="bd0cc-166">**Cmdlets:** **Set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="bd0cc-166">**Cmdlets**: **Set-Mailbox**</span></span>
- <span data-ttu-id="bd0cc-167">**Параметры:** _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="bd0cc-167">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="bd0cc-p114">В этом примере выполняется поиск изменений определенных почтовых ящиков. Это позволяет определить неполадку или предоставить сведения для диагностики. Используются следующие критерии:</span><span class="sxs-lookup"><span data-stu-id="bd0cc-p114">This example searches for changes made to a specific mailbox. This is useful if you're troubleshooting or you need to provide information for an investigation. The following criteria are used:</span></span>

- <span data-ttu-id="bd0cc-171">**Дата начала:** 05/01/2018</span><span class="sxs-lookup"><span data-stu-id="bd0cc-171">**Start date**: 05/01/2018</span></span>
- <span data-ttu-id="bd0cc-172">**Дата окончания:** 10.03.2018</span><span class="sxs-lookup"><span data-stu-id="bd0cc-172">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="bd0cc-173">**ID объекта:** contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="bd0cc-173">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="bd0cc-174">Если поиск возвращает множество записей журналов, рекомендуется использовать процедуру, предусмотренную в **Use Exchange Online PowerShell,** для поиска записей журналов аудита и отправки результатов получателю позже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-174">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article.</span></span> <span data-ttu-id="bd0cc-175">Действия в этом разделе позволяют отправить XML-файл в виде вложения сообщения электронной почты указанным отправителям, чтобы быстрее извлечь интересующие данные.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-175">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="bd0cc-176">Дополнительные сведения о синтаксисе и параметрах см. в разделе [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="bd0cc-176">For detailed syntax and parameter information, see [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="bd0cc-177">Просмотр подробных сведений о записях журнала аудита</span><span class="sxs-lookup"><span data-stu-id="bd0cc-177">View details of audit log entries</span></span>

<span data-ttu-id="bd0cc-178">В **кодлете Search-AdminAuditLog** возвращаются поля, описанные в содержимом [журнала аудита.](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)</span><span class="sxs-lookup"><span data-stu-id="bd0cc-178">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="bd0cc-179">Поля **CmdletParameters** и **ModifiedProperties**, возвращаемые командлетом, содержат дополнительные сведения, которые невозможно просмотреть по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-179">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="bd0cc-180">Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedProperties**, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-180">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="bd0cc-181">Или вы можете использовать процедуру в **Use Exchange Online PowerShell** для поиска записей журналов аудита и отправки результатов получателю позже в этой статье для создания XML-файла.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-181">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article to create an XML file.</span></span>

<span data-ttu-id="bd0cc-182">В этой процедуре используются следующие основные понятия:</span><span class="sxs-lookup"><span data-stu-id="bd0cc-182">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="bd0cc-183">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="bd0cc-183">about_Arrays</span></span>](/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="bd0cc-184">about_Variables</span><span class="sxs-lookup"><span data-stu-id="bd0cc-184">about_Variables</span></span>](/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="bd0cc-185">Определите критерии поиска, запустите командлет **Search-AdminAuditLog** и сохраните результаты в переменной с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-185">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. <span data-ttu-id="bd0cc-186">Каждая запись журнала аудита хранится в качестве элемента массива в `$Results` переменной.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-186">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="bd0cc-187">Чтобы выбрать элемент массива, укажите его индекс.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-187">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="bd0cc-188">Индексы элементов массива начинаются с 0 для первого элемента массива.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-188">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="bd0cc-189">Например, чтобы получить пятый элемент массива с индексом 4, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-189">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

   ```PowerShell
   $Results[4]
   ```

3. <span data-ttu-id="bd0cc-p119">Предыдущая команда возвращает запись журнала, хранящуюся в элементе массива 4. Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedProperties** для этой записи журнала, используйте следующие команды.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-p119">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. <span data-ttu-id="bd0cc-192">Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedParameters** в другой записи журнала, измените индекс элемента массива.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-192">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>