---
title: Просмотр журнала аудита администратора в автономной службе EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Администраторы могут узнать, как просматривать и искать журнал аудита администратора в автономных exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab6bf0a2739a88a075b636b990539b24006f3e63
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286481"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="99a39-103">Просмотр журнала аудита администратора в автономной службе EOP</span><span class="sxs-lookup"><span data-stu-id="99a39-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="99a39-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="99a39-104">**Applies to**</span></span>
- [<span data-ttu-id="99a39-105">Автономный exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="99a39-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="99a39-106">В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online можно использовать Центр администрирования Exchange (EAC) или автономный EOP PowerShell для поиска и просмотра записей в журнале аудита администратора.</span><span class="sxs-lookup"><span data-stu-id="99a39-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="99a39-107">В журнал аудита действий администратора записываются определенные действия, основанные на автономных cmdlets EOP PowerShell, которые делают администраторы и пользователи, которым были назначены права администратора.</span><span class="sxs-lookup"><span data-stu-id="99a39-107">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="99a39-108">Записи в журнале аудита администратора предоставляют сведения о том, какой был запуск, какие параметры использовались, кто запустил этот и какие объекты были затронуты.</span><span class="sxs-lookup"><span data-stu-id="99a39-108">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="99a39-109">Ведение журнала аудита администратора включено по умолчанию, и его нельзя отключить.</span><span class="sxs-lookup"><span data-stu-id="99a39-109">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="99a39-110">В журнал аудита действий администратора не записываются действия, основанные на действиях, которые начинаются с глаголов **Get,** **Search** или **Test.**</span><span class="sxs-lookup"><span data-stu-id="99a39-110">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="99a39-111">Записи журнала аудита хранятся в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="99a39-111">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="99a39-112">Если возраст записи превышает 90 дней, она удаляется</span><span class="sxs-lookup"><span data-stu-id="99a39-112">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="99a39-113">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="99a39-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="99a39-114">Чтобы открыть Центр администрирования Exchange, см. центр [администрирования Exchange в режиме автономных EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="99a39-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="99a39-115">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="99a39-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="99a39-116">Для работы с процедурами, которые данная статья, вам должны быть назначены разрешения в Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="99a39-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="99a39-117">В частности, вам  потребуется роль  "Журналы аудита" или "Только просмотр журналов аудита", которые по умолчанию назначены группам ролей "Управление организацией", "Управление соответствием требованиям" и "Администратор безопасности".   </span><span class="sxs-lookup"><span data-stu-id="99a39-117">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="99a39-118">Дополнительные сведения см. в сведениях о разрешениях в автономных [EOP](feature-permissions-in-eop.md) и использовании EAC для изменения списка участников [в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="99a39-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="99a39-119">Сведения о сочетаниях клавиш, которые могут применяться к процедурам в этой статье, см. в статье "Сочетания клавиш" для Центра администрирования [Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="99a39-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="99a39-120">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="99a39-120">Having problems?</span></span> <span data-ttu-id="99a39-121">Обратитесь за помощью на форум по [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).</span><span class="sxs-lookup"><span data-stu-id="99a39-121">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="99a39-122">Просмотр журнала аудита администратора с помощью EAC</span><span class="sxs-lookup"><span data-stu-id="99a39-122">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="99a39-123">В EAC перейдите  к аудиту управления соответствием и выберите "Запуск отчета журнала \>  **аудита администратора".**</span><span class="sxs-lookup"><span data-stu-id="99a39-123">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="99a39-124">На **открываемой** странице "Поиск изменений в  группах ролей администраторов" выберите дату начала и окончания **(диапазон** по умолчанию — последние две недели), а затем выберите **"Поиск".**</span><span class="sxs-lookup"><span data-stu-id="99a39-124">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="99a39-125">Отображаются все изменения конфигурации, внесенные в указанный период времени, и их можно отсортировать, используя следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="99a39-125">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="99a39-126">**Дата**: дата и время изменения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="99a39-126">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="99a39-127">Дата и время хранятся в формате времени UTC.</span><span class="sxs-lookup"><span data-stu-id="99a39-127">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="99a39-128">**Cmdlet**: имя cmdlet, который использовался для изменения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="99a39-128">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="99a39-129">**Пользователь**: имя учетной записи пользователя, который внося изменения в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="99a39-129">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="99a39-p107">На нескольких страницах отображается до 5000 записей. Укажите меньший диапазон дат, чтобы сократить число результатов. Если выбрать отдельный результат, в области сведений отображаются следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="99a39-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="99a39-133">**Измененный** объект: объект, измененный с помощью cmdlet.</span><span class="sxs-lookup"><span data-stu-id="99a39-133">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="99a39-134">**Параметры (параметр:значение):** использованные параметры и любое значение, указанное с помощью параметра.</span><span class="sxs-lookup"><span data-stu-id="99a39-134">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="99a39-135">Если вы хотите напечатать определенную запись журнала, нажмите кнопку **Печать** в области сведений.</span><span class="sxs-lookup"><span data-stu-id="99a39-135">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="99a39-136">Просмотр журнала аудита администратора с помощью автономных EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="99a39-136">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="99a39-137">Вы можете использовать автономный EOP PowerShell для поиска записей журнала аудита, которые соответствуют занижаемой вами критерии.</span><span class="sxs-lookup"><span data-stu-id="99a39-137">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="99a39-138">Используйте указанный ниже синтаксис.</span><span class="sxs-lookup"><span data-stu-id="99a39-138">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="99a39-139">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="99a39-139">**Notes**:</span></span>

- <span data-ttu-id="99a39-140">Параметр _Parameters_ можно использовать только вместе с параметром _Cmdlets._</span><span class="sxs-lookup"><span data-stu-id="99a39-140">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="99a39-141">Параметр _ObjectIds_ фильтрует результаты по объекту, который был изменен с помощью этого параметра.</span><span class="sxs-lookup"><span data-stu-id="99a39-141">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="99a39-142">Допустимые значения зависят от того, как объект представлен в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="99a39-142">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="99a39-143">Например,</span><span class="sxs-lookup"><span data-stu-id="99a39-143">For example:</span></span>

  - <span data-ttu-id="99a39-144">Имя</span><span class="sxs-lookup"><span data-stu-id="99a39-144">Name</span></span>
  - <span data-ttu-id="99a39-145">Каноническое различается имя (например, contoso.com/Users/Akia Al-Zuhairi)</span><span class="sxs-lookup"><span data-stu-id="99a39-145">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="99a39-146">Скорее всего, вам потребуется использовать другие параметры фильтрации в этом cmdlet, чтобы сузить результаты и определить интересующие вас типы объектов.</span><span class="sxs-lookup"><span data-stu-id="99a39-146">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="99a39-147">Параметр _UserIds_ фильтрует результаты по пользователю, внося изменения (который запустил этот cmdlet).</span><span class="sxs-lookup"><span data-stu-id="99a39-147">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="99a39-148">Для _параметров StartDate_ и _EndDate,_ если указать значение даты и времени без часовой пояс, значение будет указано в UTC.</span><span class="sxs-lookup"><span data-stu-id="99a39-148">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="99a39-149">Чтобы указать значение даты или времени для этого параметра, воспользуйтесь одним из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="99a39-149">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="99a39-150">Укажите значение даты / времени в формате UTC: например, «2016-05-06 14: 30: 00z».</span><span class="sxs-lookup"><span data-stu-id="99a39-150">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="99a39-151">Укажите значение даты и времени в качестве формулы, которая преобразует дату и время в локальном часовом поясе в UTC: `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` например.</span><span class="sxs-lookup"><span data-stu-id="99a39-151">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="99a39-152">Для получения дополнительной информации см. [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span><span class="sxs-lookup"><span data-stu-id="99a39-152">For more information, see [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="99a39-153">По умолчанию он возвращает не более 1000 записей журнала.</span><span class="sxs-lookup"><span data-stu-id="99a39-153">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="99a39-154">Используйте параметр _ResultSize,_ чтобы указать до 250 000 записей журнала.</span><span class="sxs-lookup"><span data-stu-id="99a39-154">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="99a39-155">Или используйте значение для `Unlimited` возврата всех записей.</span><span class="sxs-lookup"><span data-stu-id="99a39-155">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="99a39-156">В этом примере выполняется поиск всех записей журнала аудита со следующими критериями:</span><span class="sxs-lookup"><span data-stu-id="99a39-156">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="99a39-157">**Дата начала:** 4 августа 2019 г.</span><span class="sxs-lookup"><span data-stu-id="99a39-157">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="99a39-158">**Дата окончания:** 3 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="99a39-158">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="99a39-159">**Cmdlets**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="99a39-159">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="99a39-160">Дополнительные сведения о синтаксисе и параметрах см. в разделе [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="99a39-160">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="99a39-161">Просмотр подробных сведений о записях журнала аудита</span><span class="sxs-lookup"><span data-stu-id="99a39-161">View details of audit log entries</span></span>

<span data-ttu-id="99a39-162">The **Search-AdminAuditLog cmdlet** returns the fields described in the [Audit log contents](#audit-log-contents) section later in this article.</span><span class="sxs-lookup"><span data-stu-id="99a39-162">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this article.</span></span> <span data-ttu-id="99a39-163">Два поля, **CmdletParameters** и **ModifiedProperties,** возвращают дополнительные сведения, которые не возвращаются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="99a39-163">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="99a39-164">Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedProperties**, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="99a39-164">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="99a39-165">Определите критерии поиска, запустите командлет **Search-AdminAuditLog** и сохраните результаты в переменной с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="99a39-165">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="99a39-166">Каждая запись журнала аудита хранится в переменной как элемент `$Results` массива.</span><span class="sxs-lookup"><span data-stu-id="99a39-166">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="99a39-167">Чтобы выбрать элемент массива, укажите его индекс.</span><span class="sxs-lookup"><span data-stu-id="99a39-167">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="99a39-168">Индексы элементов массива начинаются с 0 для первого элемента массива.</span><span class="sxs-lookup"><span data-stu-id="99a39-168">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="99a39-169">Например, чтобы получить пятый элемент массива с индексом 4, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="99a39-169">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="99a39-p115">Предыдущая команда возвращает запись журнала, хранящуюся в элементе массива 4. Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedProperties** для этой записи журнала, используйте следующие команды.</span><span class="sxs-lookup"><span data-stu-id="99a39-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="99a39-172">Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedParameters** в другой записи журнала, измените индекс элемента массива.</span><span class="sxs-lookup"><span data-stu-id="99a39-172">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="99a39-173">Содержимое журнала аудита</span><span class="sxs-lookup"><span data-stu-id="99a39-173">Audit log contents</span></span>

<span data-ttu-id="99a39-174">Каждая запись журнала аудита содержит сведения, описанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="99a39-174">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="99a39-175">Журнал аудита содержит одну или несколько записей.</span><span class="sxs-lookup"><span data-stu-id="99a39-175">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="99a39-176">Поле</span><span class="sxs-lookup"><span data-stu-id="99a39-176">Field</span></span>|<span data-ttu-id="99a39-177">Описание</span><span class="sxs-lookup"><span data-stu-id="99a39-177">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="99a39-178">Это поле используется внутри EOP.</span><span class="sxs-lookup"><span data-stu-id="99a39-178">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="99a39-179">Это поле содержит объект, измененный с помощью указанного в поле `CmdletName` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="99a39-179">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="99a39-180">В этом поле содержится имя запускаемого пользователем в поле `Caller` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="99a39-180">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="99a39-181">Это поле содержит параметры, которые были заданы при запуске в `CmdletName` поле.</span><span class="sxs-lookup"><span data-stu-id="99a39-181">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="99a39-182">В этом поле, при наличии, также хранится, но не отображается в выходных данных по умолчанию, значение, указанное с помощью параметра.</span><span class="sxs-lookup"><span data-stu-id="99a39-182">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="99a39-183">Это поле содержит свойства, которые были изменены для объекта в `ObjectModified` поле.</span><span class="sxs-lookup"><span data-stu-id="99a39-183">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="99a39-184">В этом поле также хранятся значения свойств  как старые, так и новые (сохраненные).</span><span class="sxs-lookup"><span data-stu-id="99a39-184">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="99a39-185">В этом поле содержится учетная запись пользователя, выдавшего в поле этот `CmdletName` код.</span><span class="sxs-lookup"><span data-stu-id="99a39-185">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="99a39-186">Это поле используется внутри EOP.</span><span class="sxs-lookup"><span data-stu-id="99a39-186">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="99a39-187">В этом поле указывается, успешно ли выполнился указанный в `CmdletName` поле.</span><span class="sxs-lookup"><span data-stu-id="99a39-187">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="99a39-188">Значением является либо `True` `False` .</span><span class="sxs-lookup"><span data-stu-id="99a39-188">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="99a39-189">В этом поле содержится сообщение об ошибке, которое создается, если не удалось выполнить его `CmdletName` успешно.</span><span class="sxs-lookup"><span data-stu-id="99a39-189">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="99a39-190">Это поле содержит дату и время запуска этого `CmdletName` поля.</span><span class="sxs-lookup"><span data-stu-id="99a39-190">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="99a39-191">Дата и время хранятся в формате времени UTC.</span><span class="sxs-lookup"><span data-stu-id="99a39-191">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="99a39-192">Это поле указывает сервер, на котором был запускаться указанный в `CmdletName` поле.</span><span class="sxs-lookup"><span data-stu-id="99a39-192">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="99a39-193">Это поле используется внутри EOP.</span><span class="sxs-lookup"><span data-stu-id="99a39-193">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="99a39-194">Это поле используется внутри EOP.</span><span class="sxs-lookup"><span data-stu-id="99a39-194">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="99a39-195">Это поле используется внутри EOP.</span><span class="sxs-lookup"><span data-stu-id="99a39-195">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="99a39-196">Это поле используется внутри EOP.</span><span class="sxs-lookup"><span data-stu-id="99a39-196">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="99a39-197">Это поле используется внутри EOP.</span><span class="sxs-lookup"><span data-stu-id="99a39-197">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="99a39-198">Это поле используется внутри EOP.</span><span class="sxs-lookup"><span data-stu-id="99a39-198">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="99a39-199">Это поле используется внутри EOP.</span><span class="sxs-lookup"><span data-stu-id="99a39-199">This field is used internally by EOP.</span></span>|
|
