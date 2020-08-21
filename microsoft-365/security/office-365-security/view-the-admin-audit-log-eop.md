---
title: Просмотр журнала аудита администратора в автономном EOP
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
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Администраторы могут просматривать журнал аудита действий администратора и выполнять их поиск в автономной службе Exchange Online Protection (EOP).
ms.openlocfilehash: 8890ab8f2f2db01ed6bd22657a9bea8f77b25d08
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825081"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="7170b-103">Просмотр журнала аудита администратора в автономном EOP</span><span class="sxs-lookup"><span data-stu-id="7170b-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="7170b-104">В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online можно использовать Центр администрирования Exchange или автономную службу EOP PowerShell для поиска и просмотра записей в журнале аудита действий администратора.</span><span class="sxs-lookup"><span data-stu-id="7170b-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="7170b-105">В журнал аудита действий администратора записывается определенные действия на основе отдельных командлетов PowerShell eop, выполняемых администраторами и пользователями с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="7170b-105">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="7170b-106">В записях журнала аудита действий администратора указано, какой командлет выполнен, какие параметры использованы, кто выполнял командлет, а также какие объекты задействованы.</span><span class="sxs-lookup"><span data-stu-id="7170b-106">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="7170b-107">Ведение журнала аудита действий администратора по умолчанию включено, его невозможно отключить.</span><span class="sxs-lookup"><span data-stu-id="7170b-107">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="7170b-108">В журнал аудита действий администратора не записываются действия на основе командлетов, которые начинаются с глаголов **"Get",** **"Search"** или **"Test".**</span><span class="sxs-lookup"><span data-stu-id="7170b-108">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="7170b-109">Записи журнала аудита хранятся в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="7170b-109">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="7170b-110">Когда срок хранения записи превышает 90 дней, она удаляется.</span><span class="sxs-lookup"><span data-stu-id="7170b-110">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7170b-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="7170b-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7170b-112">Сведения о том, как открыть Центр администрирования [Exchange, см. в центре администрирования Exchange в автономной службе EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="7170b-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="7170b-113">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="7170b-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="7170b-114">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="7170b-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="7170b-115">В частности, вам нужна роль "Журналы аудита" или "Только просмотр журналов аудита", по умолчанию назначенные группам ролей ComplianceManagement, OrganizationManagement (глобальные администраторы) и SecurityAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7170b-115">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="7170b-116">Дополнительные сведения см. в разделе ["Разрешения в автономной службе EOP"](feature-permissions-in-eop.md) и использовании Центра администрирования [Exchange для изменения списка членов в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="7170b-116">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="7170b-117">Сочетания клавиш для процедур, описанных в этой статье, приведены в разделе сочетания клавиш для [Центра администрирования Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="7170b-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="7170b-118">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="7170b-118">Having problems?</span></span> <span data-ttu-id="7170b-119">Обратитесь за помощью на форум по [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="7170b-119">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="7170b-120">Использование EAC для просмотра журнала аудита действий администратора</span><span class="sxs-lookup"><span data-stu-id="7170b-120">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="7170b-121">В Центре администрирования Exchange выберите пункт **"Аудит** \> **управления соответствием требованиям"** и **выберите отчет журнала аудита действий администратора.**</span><span class="sxs-lookup"><span data-stu-id="7170b-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="7170b-122">На **открывшейся странице "Поиск изменений группы ролей** администраторов" выберите дату начала и **окончания** (диапазон по умолчанию — это последние две недели), а затем нажмите **кнопку "Поиск".** **Start date**</span><span class="sxs-lookup"><span data-stu-id="7170b-122">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="7170b-123">Все изменения конфигурации, выполненные в течение заданного периода времени, отображаются и могут сортироваться сортируются соследующими данными:</span><span class="sxs-lookup"><span data-stu-id="7170b-123">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="7170b-124">**Дата:** дата и время внесения изменения в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="7170b-124">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="7170b-125">Дата и время хранятся в формате времени UTC.</span><span class="sxs-lookup"><span data-stu-id="7170b-125">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="7170b-126">**Командлет**— имя командлета, который использовался для изменения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7170b-126">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="7170b-127">**User**— имя учетной записи пользователя, который изменил конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="7170b-127">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="7170b-p107">На нескольких страницах отображается до 5000 записей. Укажите меньший диапазон дат, чтобы сократить число результатов. Если выбрать отдельный результат, в области сведений отображаются следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="7170b-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="7170b-131">**Измененобъект:** объект, измененный с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="7170b-131">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="7170b-132">**Параметры (параметр:значение):** использованные параметры командлета, а также их значения.</span><span class="sxs-lookup"><span data-stu-id="7170b-132">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="7170b-133">Если вы хотите напечатать определенную запись журнала, нажмите кнопку **Печать** в области сведений.</span><span class="sxs-lookup"><span data-stu-id="7170b-133">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="7170b-134">Просмотр журнала аудита действий администратора с помощью автономной службы EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="7170b-134">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="7170b-135">Можно использовать автономную оболочку EOP PowerShell для поиска записей журнала аудита, соответствующих указанным критериям.</span><span class="sxs-lookup"><span data-stu-id="7170b-135">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="7170b-136">Используйте указанный ниже синтаксис.</span><span class="sxs-lookup"><span data-stu-id="7170b-136">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="7170b-137">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="7170b-137">**Notes**:</span></span>

- <span data-ttu-id="7170b-138">ПараметрParameters можно _использовать_ только вместе с _параметром Cmdlets._</span><span class="sxs-lookup"><span data-stu-id="7170b-138">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="7170b-139">Параметр _ObjectIds_ фильтрует результаты по объекту, измененному командлетом.</span><span class="sxs-lookup"><span data-stu-id="7170b-139">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="7170b-140">Допустимое значение зависит от того, как объект представляется в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="7170b-140">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="7170b-141">Пример:</span><span class="sxs-lookup"><span data-stu-id="7170b-141">For example:</span></span>

  - <span data-ttu-id="7170b-142">Имя</span><span class="sxs-lookup"><span data-stu-id="7170b-142">Name</span></span>
  - <span data-ttu-id="7170b-143">Различающиеся имя канонического имени (например, contoso.com/Users/Akia Al-Zuhairi)</span><span class="sxs-lookup"><span data-stu-id="7170b-143">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="7170b-144">Скорее всего, потребуется использовать другие параметры фильтрации этого командлета, чтобы сузить результаты и определить типы объектов, которые вас интересуют.</span><span class="sxs-lookup"><span data-stu-id="7170b-144">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="7170b-145">Параметр _UserIds фильтрует_ результаты по пользователю, который внес изменение (кто запустил командлет).</span><span class="sxs-lookup"><span data-stu-id="7170b-145">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="7170b-146">Для _параметров StartDate_ _и EndDate,_ если указать значение даты/времени без часового пояса, это значение будет указано в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="7170b-146">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="7170b-147">Чтобы указать значение даты или времени для этого параметра, воспользуйтесь одним из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="7170b-147">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="7170b-148">Укажите значение даты / времени в формате UTC: например, «2016-05-06 14: 30: 00z».</span><span class="sxs-lookup"><span data-stu-id="7170b-148">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="7170b-149">Укажите значение даты/времени в виде формулы, которая преобразует дату/время в своем местное время в формате UTC: `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` например.</span><span class="sxs-lookup"><span data-stu-id="7170b-149">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="7170b-150">Для получения дополнительной информации см. [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span><span class="sxs-lookup"><span data-stu-id="7170b-150">For more information, see [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="7170b-151">По умолчанию командлет возвращает максимум 1000 записей журнала.</span><span class="sxs-lookup"><span data-stu-id="7170b-151">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="7170b-152">Параметр _ResultSize используется_ для указания до 250 000 записей журнала.</span><span class="sxs-lookup"><span data-stu-id="7170b-152">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="7170b-153">Также можно использовать значение для `Unlimited` возврата всех записей.</span><span class="sxs-lookup"><span data-stu-id="7170b-153">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="7170b-154">В этом примере выполняется поиск всех записей журнала аудита со следующими критериями:</span><span class="sxs-lookup"><span data-stu-id="7170b-154">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="7170b-155">**Дата начала:** 4 августа 2019 г.</span><span class="sxs-lookup"><span data-stu-id="7170b-155">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="7170b-156">**Дата**окончания: 3 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="7170b-156">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="7170b-157">**Командлеты**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="7170b-157">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="7170b-158">Дополнительные сведения о синтаксисе и параметрах см. в разделе [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="7170b-158">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="7170b-159">Просмотр подробных сведений о записях журнала аудита</span><span class="sxs-lookup"><span data-stu-id="7170b-159">View details of audit log entries</span></span>

<span data-ttu-id="7170b-160">Командлет **Search-AdminAuditLog** возвращает поля, описанные далее в разделе ["Содержимое журнала](#audit-log-contents) аудита".</span><span class="sxs-lookup"><span data-stu-id="7170b-160">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this topic.</span></span> <span data-ttu-id="7170b-161">Поля **CmdletParameters** и **ModifiedProperties,** возвращаемые командлетом, содержат дополнительные сведения, которые не возвращаются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7170b-161">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="7170b-162">Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedProperties**, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7170b-162">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="7170b-163">Определите критерии поиска, запустите командлет **Search-AdminAuditLog** и сохраните результаты в переменной с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="7170b-163">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="7170b-164">Каждая запись журнала сохраняется в переменной в виде элемента `$Results` массива.</span><span class="sxs-lookup"><span data-stu-id="7170b-164">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="7170b-165">Чтобы выбрать элемент массива, укажите его индекс.</span><span class="sxs-lookup"><span data-stu-id="7170b-165">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="7170b-166">Индексы элементов массива начинаются с 0 для первого элемента массива.</span><span class="sxs-lookup"><span data-stu-id="7170b-166">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="7170b-167">Например, чтобы получить пятый элемент массива с индексом 4, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="7170b-167">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="7170b-p115">Предыдущая команда возвращает запись журнала, хранящуюся в элементе массива 4. Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedProperties** для этой записи журнала, используйте следующие команды.</span><span class="sxs-lookup"><span data-stu-id="7170b-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="7170b-170">Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedParameters** в другой записи журнала, измените индекс элемента массива.</span><span class="sxs-lookup"><span data-stu-id="7170b-170">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="7170b-171">Содержимое журнала аудита</span><span class="sxs-lookup"><span data-stu-id="7170b-171">Audit log contents</span></span>

<span data-ttu-id="7170b-172">Каждая запись журнала аудита содержит сведения, описанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="7170b-172">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="7170b-173">Журнал аудита содержит одну или несколько записей.</span><span class="sxs-lookup"><span data-stu-id="7170b-173">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="7170b-174">Поле</span><span class="sxs-lookup"><span data-stu-id="7170b-174">Field</span></span>|<span data-ttu-id="7170b-175">Описание</span><span class="sxs-lookup"><span data-stu-id="7170b-175">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="7170b-176">Это поле предназначено для внутренней службы EOP.</span><span class="sxs-lookup"><span data-stu-id="7170b-176">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="7170b-177">В этом поле содержится объект, измененный с помощью командлета, указанного в `CmdletName` поле.</span><span class="sxs-lookup"><span data-stu-id="7170b-177">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="7170b-178">Это поле содержит имя командлета, запущенного пользователем в `Caller` поле.</span><span class="sxs-lookup"><span data-stu-id="7170b-178">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="7170b-179">Это поле содержит параметры, заданные при запуске `CmdletName` командлета, указанного в поле.</span><span class="sxs-lookup"><span data-stu-id="7170b-179">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="7170b-180">В этом поле, при наличии, также хранится, но не отображается в выходных данных по умолчанию, значение, указанное с помощью параметра.</span><span class="sxs-lookup"><span data-stu-id="7170b-180">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="7170b-181">Это поле содержит измененные свойства объекта в `ObjectModified` поле.</span><span class="sxs-lookup"><span data-stu-id="7170b-181">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="7170b-182">В этом поле также хранятся значения свойств  как старые, так и новые (сохраненные).</span><span class="sxs-lookup"><span data-stu-id="7170b-182">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="7170b-183">В этом поле содержится учетная запись пользователя, запустившего командлет в `CmdletName` поле.</span><span class="sxs-lookup"><span data-stu-id="7170b-183">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="7170b-184">Это поле предназначено для внутренней службы EOP.</span><span class="sxs-lookup"><span data-stu-id="7170b-184">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="7170b-185">В этом поле указывается, успешно ли `CmdletName` был выполнен командлет, запущены в поле.</span><span class="sxs-lookup"><span data-stu-id="7170b-185">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="7170b-186">Возможные значения: `True` `False` или.</span><span class="sxs-lookup"><span data-stu-id="7170b-186">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="7170b-187">Это поле содержит сообщение об ошибке, которое создается при сбое `CmdletName` выполнения командлета, выполненного в поле.</span><span class="sxs-lookup"><span data-stu-id="7170b-187">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="7170b-188">В этом поле содержатся дата и время выполнения `CmdletName` командлета, заданных в поле.</span><span class="sxs-lookup"><span data-stu-id="7170b-188">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="7170b-189">Дата и время хранятся в формате времени UTC.</span><span class="sxs-lookup"><span data-stu-id="7170b-189">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="7170b-190">В этом поле указывается сервер, на котором был выполнен `CmdletName` командлет, указанный в поле.</span><span class="sxs-lookup"><span data-stu-id="7170b-190">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="7170b-191">Это поле предназначено для внутренней службы EOP.</span><span class="sxs-lookup"><span data-stu-id="7170b-191">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="7170b-192">Это поле предназначено для внутренней службы EOP.</span><span class="sxs-lookup"><span data-stu-id="7170b-192">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="7170b-193">Это поле предназначено для внутренней службы EOP.</span><span class="sxs-lookup"><span data-stu-id="7170b-193">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="7170b-194">Это поле предназначено для внутренней службы EOP.</span><span class="sxs-lookup"><span data-stu-id="7170b-194">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="7170b-195">Это поле предназначено для внутренней службы EOP.</span><span class="sxs-lookup"><span data-stu-id="7170b-195">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="7170b-196">Это поле предназначено для внутренней службы EOP.</span><span class="sxs-lookup"><span data-stu-id="7170b-196">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="7170b-197">Это поле предназначено для внутренней службы EOP.</span><span class="sxs-lookup"><span data-stu-id="7170b-197">This field is used internally by EOP.</span></span>|
|
