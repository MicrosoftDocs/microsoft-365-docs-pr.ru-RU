---
title: Импорт хранителей в дело advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Используйте средство импорта dto быстрое добавление нескольких хранителей и связанных с ними источников данных в дело в advanced eDiscovery.
ms.openlocfilehash: 98ff3690fe7fd8c956fce436585014ef0db82a26
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421616"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="95e9b-103">Импорт хранителей в дело advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="95e9b-103">Import custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="95e9b-104">В случаях с расширенным открытием электронных данных, в которых задействовано множество хранителей, можно импортировать сразу несколько хранителей, используя CSV-файл, содержащий сведения, необходимые для добавления их в дело.</span><span class="sxs-lookup"><span data-stu-id="95e9b-104">For Advanced eDiscovery cases that involve many custodians, you can import multiple custodians at once by using a CSV file that contains the information necessary to add them to a case.</span></span>

## <a name="import-custodians"></a><span data-ttu-id="95e9b-105">Хранители импорта</span><span class="sxs-lookup"><span data-stu-id="95e9b-105">Import custodians</span></span>

1. <span data-ttu-id="95e9b-106">Откройте дело advanced eDiscovery и выберите вкладку **Источники** данных.</span><span class="sxs-lookup"><span data-stu-id="95e9b-106">Open the Advanced eDiscovery case and select the **Data sources** tab.</span></span>

2. <span data-ttu-id="95e9b-107">Нажмите **кнопку Добавить хранители импорта источника**  >  **данных**.</span><span class="sxs-lookup"><span data-stu-id="95e9b-107">Click **Add data source** > **Import custodians**.</span></span>

3. <span data-ttu-id="95e9b-108">На странице **Flyout хранителей** импорта щелкните **Скачать пустой** шаблон, чтобы скачать CSV-файл шаблона хранителя.</span><span class="sxs-lookup"><span data-stu-id="95e9b-108">On the **Import custodians** flyout page, click **Download a blank template** to download a custodian template CSV file.</span></span>

   ![Скачайте шаблон CSV со страницы flyout хранителей импорта](../media/ImportCustodians1.png)

4. <span data-ttu-id="95e9b-110">Добавьте сведения о хранителях в CSV-файл и сохраните их на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="95e9b-110">Add the custodial information to the CSV file and save it to your local computer.</span></span> <span data-ttu-id="95e9b-111">Сведения о необходимых свойствах в [CSV-файле](#custodian-csv-file) см. в разделе Файл хранителя CSV.</span><span class="sxs-lookup"><span data-stu-id="95e9b-111">See the [Custodian CSV file](#custodian-csv-file) section for information about the required properties in the CSV file.</span></span>

5. <span data-ttu-id="95e9b-112">После подготовки CSV-файла с данными хранителя перейдите на вкладку **Источники** данных и нажмите **кнопку Добавить** хранители импорта источника  >   данных.</span><span class="sxs-lookup"><span data-stu-id="95e9b-112">After you've prepared the CSV file with the custodian information, go back to the **Data sources** tab, and click **Add data source** > **Import custodians** again.</span></span>

6. <span data-ttu-id="95e9b-113">На странице **Flyout хранителей** импорта щелкните **Обзор** и загрузите CSV-файл, содержащий сведения о хранителях.</span><span class="sxs-lookup"><span data-stu-id="95e9b-113">On the **Import custodians** flyout page, click **Browse** and then upload the CSV file that contains the custodian information.</span></span>

   <span data-ttu-id="95e9b-114">После отправки файла CSV на вкладке **Jobs** создается и отображается задание **BulkAddCustodian.** Задание проверяет хранителей и связанные с ними источники данных, а затем добавляет их на страницу **источников** данных дела.</span><span class="sxs-lookup"><span data-stu-id="95e9b-114">After the CSV file is uploaded, a job named **BulkAddCustodian** is created and displayed on the **Jobs** tab. The job validates the custodians and their associated data sources and then adds them to the **Data sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="95e9b-115">Файл CSV custodian</span><span class="sxs-lookup"><span data-stu-id="95e9b-115">Custodian CSV file</span></span>

<span data-ttu-id="95e9b-116">После загрузки шаблона хранителя CSV можно добавить хранителей и их источник данных в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="95e9b-116">After you download the CSV custodian template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="95e9b-117">Не следует изменять имена столбцов в строке заглавной строки.</span><span class="sxs-lookup"><span data-stu-id="95e9b-117">Be sure not to change the column names in the header row.</span></span> <span data-ttu-id="95e9b-118">Используйте столбцы типа рабочей нагрузки и расположения рабочей нагрузки, чтобы связать другие источники данных с хранителями.</span><span class="sxs-lookup"><span data-stu-id="95e9b-118">Use the workload type and workload location columns to associate other data sources to a custodian.</span></span>

| <span data-ttu-id="95e9b-119">Столбец</span><span class="sxs-lookup"><span data-stu-id="95e9b-119">Column name</span></span>|<span data-ttu-id="95e9b-120">Description</span><span class="sxs-lookup"><span data-stu-id="95e9b-120">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="95e9b-121">**Custodian contactEmail**</span><span class="sxs-lookup"><span data-stu-id="95e9b-121">**Custodian contactEmail**</span></span>     |<span data-ttu-id="95e9b-122">Адрес электронной почты upN хранителя.</span><span class="sxs-lookup"><span data-stu-id="95e9b-122">The custodian's UPN email address.</span></span> <span data-ttu-id="95e9b-123">Например, sarad@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="95e9b-123">For example, sarad@contoso.onmicrosoft.com.</span></span>           |
|<span data-ttu-id="95e9b-124">**Включена Exchange**</span><span class="sxs-lookup"><span data-stu-id="95e9b-124">**Exchange Enabled**</span></span> | <span data-ttu-id="95e9b-125">Значение TRUE/FALSE, чтобы включить или не включить почтовый ящик хранителя.</span><span class="sxs-lookup"><span data-stu-id="95e9b-125">TRUE/FALSE value to include or not include the custodian's mailbox.</span></span>      |
|<span data-ttu-id="95e9b-126">**Включен OneDrive**</span><span class="sxs-lookup"><span data-stu-id="95e9b-126">**OneDrive Enabled**</span></span> | <span data-ttu-id="95e9b-127">Значение TRUE/FALSE, чтобы включить или не включить учетную запись OneDrive для бизнеса хранителя.</span><span class="sxs-lookup"><span data-stu-id="95e9b-127">TRUE/FALSE value to include or not included the custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="95e9b-128">**Is OnHold**</span><span class="sxs-lookup"><span data-stu-id="95e9b-128">**Is OnHold**</span></span>        | <span data-ttu-id="95e9b-129">Значение TRUE/FALSE, чтобы указать, следует ли удерживать источники данных хранителя.</span><span class="sxs-lookup"><span data-stu-id="95e9b-129">TRUE/FALSE value to indicate whether to place the custodian data sources on hold.</span></span> <span data-ttu-id="95e9b-130"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="95e9b-130"><sup>1</sup></span></span>     |
|<span data-ttu-id="95e9b-131">**Тип workload1**</span><span class="sxs-lookup"><span data-stu-id="95e9b-131">**Workload1 Type**</span></span>         |<span data-ttu-id="95e9b-132">Строковая величина, указывающая тип источника данных для связи с хранителями.</span><span class="sxs-lookup"><span data-stu-id="95e9b-132">String value indicating the type of data source to associate with the custodian.</span></span> <span data-ttu-id="95e9b-133">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="95e9b-133">Possible values include:</span></span> <br/><span data-ttu-id="95e9b-134">- ExchangeMailbox</span><span class="sxs-lookup"><span data-stu-id="95e9b-134">- ExchangeMailbox</span></span><br/> <span data-ttu-id="95e9b-135">- SharePointSite</span><span class="sxs-lookup"><span data-stu-id="95e9b-135">- SharePointSite</span></span><br/><span data-ttu-id="95e9b-136">- TeamsMailbox</span><span class="sxs-lookup"><span data-stu-id="95e9b-136">- TeamsMailbox</span></span><br/><span data-ttu-id="95e9b-137">- TeamsSite</span><span class="sxs-lookup"><span data-stu-id="95e9b-137">- TeamsSite</span></span><br/> <span data-ttu-id="95e9b-138">- YammerMailbox</span><span class="sxs-lookup"><span data-stu-id="95e9b-138">- YammerMailbox</span></span><br/><span data-ttu-id="95e9b-139">- YammerSite</span><span class="sxs-lookup"><span data-stu-id="95e9b-139">- YammerSite</span></span> |
|<span data-ttu-id="95e9b-140">**Место workload1**</span><span class="sxs-lookup"><span data-stu-id="95e9b-140">**Workload1 Location**</span></span>     | <span data-ttu-id="95e9b-141">В зависимости от типа рабочей нагрузки это будет расположение источника данных.</span><span class="sxs-lookup"><span data-stu-id="95e9b-141">Depending on your workload type, this would be the location of the data source.</span></span> <span data-ttu-id="95e9b-142">Например, адрес электронной почты для почтового ящика Exchange или URL-адрес сайта SharePoint.</span><span class="sxs-lookup"><span data-stu-id="95e9b-142">For example, the email address for an Exchange mailbox or the URL for a SharePoint site.</span></span> |
|||

> [!NOTE]
> <span data-ttu-id="95e9b-143"><sup>1</sup> Можно разместить не более 1000 почтовых ящиков и 100 сайтов с помощью процесса импорта хранителя и CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="95e9b-143"><sup>1</sup> You can place a maximum of 1,000 mailboxes and 100 sites on hold by using the custodian import process and CSV file.</span></span> <span data-ttu-id="95e9b-144">Этот процесс можно использовать для добавления более 1000 хранителей в дело, но ограничения на хранение по-прежнему применяются.</span><span class="sxs-lookup"><span data-stu-id="95e9b-144">You can use this process to add more than 1,000 custodians to a case, but the hold limits still apply.</span></span> <span data-ttu-id="95e9b-145">Дополнительные сведения об ограничениях для удержания см. в дополнительных сведениях о ограничениях [в области расширенных электронных данных.](limits-ediscovery20.md#hold-limits)</span><span class="sxs-lookup"><span data-stu-id="95e9b-145">For more information about hold limits, see [Limits in Advanced eDiscovery](limits-ediscovery20.md#hold-limits).</span></span>

<span data-ttu-id="95e9b-146">Вот пример CSV-файла с данными хранителя:</span><span class="sxs-lookup"><span data-stu-id="95e9b-146">Here's an example of a CSV file with custodian information:</span></span><br/><br/>

|<span data-ttu-id="95e9b-147">Custodian contactEmail</span><span class="sxs-lookup"><span data-stu-id="95e9b-147">Custodian contactEmail</span></span>      | <span data-ttu-id="95e9b-148">Включена Exchange</span><span class="sxs-lookup"><span data-stu-id="95e9b-148">Exchange Enabled</span></span> | <span data-ttu-id="95e9b-149">Включен OneDrive</span><span class="sxs-lookup"><span data-stu-id="95e9b-149">OneDrive Enabled</span></span> | <span data-ttu-id="95e9b-150">Is OnHold</span><span class="sxs-lookup"><span data-stu-id="95e9b-150">Is OnHold</span></span> | <span data-ttu-id="95e9b-151">Тип workload1</span><span class="sxs-lookup"><span data-stu-id="95e9b-151">Workload1 Type</span></span> | <span data-ttu-id="95e9b-152">Место workload1</span><span class="sxs-lookup"><span data-stu-id="95e9b-152">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="95e9b-153">robinc@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95e9b-153">robinc@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="95e9b-154">TRUE</span><span class="sxs-lookup"><span data-stu-id="95e9b-154">TRUE</span></span>             | <span data-ttu-id="95e9b-155">TRUE</span><span class="sxs-lookup"><span data-stu-id="95e9b-155">TRUE</span></span>             | <span data-ttu-id="95e9b-156">TRUE</span><span class="sxs-lookup"><span data-stu-id="95e9b-156">TRUE</span></span>      | <span data-ttu-id="95e9b-157">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="95e9b-157">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="95e9b-158">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95e9b-158">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="95e9b-159">TRUE</span><span class="sxs-lookup"><span data-stu-id="95e9b-159">TRUE</span></span>             | <span data-ttu-id="95e9b-160">TRUE</span><span class="sxs-lookup"><span data-stu-id="95e9b-160">TRUE</span></span>             | <span data-ttu-id="95e9b-161">TRUE</span><span class="sxs-lookup"><span data-stu-id="95e9b-161">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="95e9b-162">Проверка хранителя и источника данных</span><span class="sxs-lookup"><span data-stu-id="95e9b-162">Custodian and data source validation</span></span>

<span data-ttu-id="95e9b-163">После отправки CSV-файла хранителя advanced eDiscovery делает следующие вещи:</span><span class="sxs-lookup"><span data-stu-id="95e9b-163">After you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="95e9b-164">Проверяет хранителей и их источники данных.</span><span class="sxs-lookup"><span data-stu-id="95e9b-164">Validates the custodians and their data sources.</span></span>

2. <span data-ttu-id="95e9b-165">Индексирует все источники данных для каждого хранителя и помещает их на удержание (если свойство **Is OnHold** в CSV-файле настроено на TRUE).</span><span class="sxs-lookup"><span data-stu-id="95e9b-165">Indexes all data sources for each custodian and places them on hold (if the **Is OnHold** property in the CSV file is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="95e9b-166">Проверка хранителя</span><span class="sxs-lookup"><span data-stu-id="95e9b-166">Custodian validation</span></span>

<span data-ttu-id="95e9b-167">В настоящее время мы поддерживаем только импорт хранителей, включенных в Azure Active Directory вашей организации (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="95e9b-167">Currently, we only support importing custodians that are included in your organization's Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="95e9b-168">Средство импорта хранителя находит и проверяет хранителей с помощью значения UPN в столбце **ContactEmail custodian** в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="95e9b-168">The custodian import tool finds and validates custodians using the UPN value in the **Custodian contactEmail** column in the CSV file.</span></span> <span data-ttu-id="95e9b-169">Проверяемые хранители автоматически добавляются в дело и перечислены на вкладке **Источники** данных дела.</span><span class="sxs-lookup"><span data-stu-id="95e9b-169">Custodians that are validated are automatically added to the case and listed on the **Data sources** tab of the case.</span></span> <span data-ttu-id="95e9b-170">Если хранитель не может быть проверен, он указан в журнале ошибок для задания BulkAddCustodian, которое перечислены на вкладке **Jobs** в этом случае.</span><span class="sxs-lookup"><span data-stu-id="95e9b-170">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="95e9b-171">Неоцененные хранители не добавляются в дело или не перечислены на вкладке **Источники** данных.</span><span class="sxs-lookup"><span data-stu-id="95e9b-171">Unvalidated custodians are not added to the case or listed on the **Data sources** tab.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="95e9b-172">Проверка источника данных</span><span class="sxs-lookup"><span data-stu-id="95e9b-172">Data source validation</span></span>

<span data-ttu-id="95e9b-173">После проверки и добавления хранителей в дело добавляется каждый основной почтовый ящик и учетная запись OneDrive, связанная с хранителями.</span><span class="sxs-lookup"><span data-stu-id="95e9b-173">After custodians are validated and added to the case, each primary mailbox and OneDrive account that's associated with a custodian is added.</span></span>

<span data-ttu-id="95e9b-174">Однако если какие-либо из других источников данных (таких как сайты SharePoint, Microsoft Teams, Microsoft 365 Groups или Группы Yammer), связанные с хранителями, не могут быть  найдены, ни один из них не назначен хранителям, и значение Not **validated** отображается в столбце Состояние рядом с хранителя на вкладке **Источники** данных.</span><span class="sxs-lookup"><span data-stu-id="95e9b-174">However, if any of the other data sources (such as SharePoint sites, Microsoft Teams, Microsoft 365 Groups, or Yammer groups) associated with a custodian can't be found, none of them are assigned to the custodian and the value **Not validated** is displayed in the **Status** column next to the custodian on the **Data sources** tab.</span></span>

<span data-ttu-id="95e9b-175">Добавление проверенных источников данных для хранителя:</span><span class="sxs-lookup"><span data-stu-id="95e9b-175">To add validated data sources for a custodian:</span></span>

1. <span data-ttu-id="95e9b-176">На **вкладке Источники** данных выберите хранителя, который содержит не проверенные источники данных.</span><span class="sxs-lookup"><span data-stu-id="95e9b-176">On the **Data sources** tab, select a custodian that contains data sources that aren't validated.</span></span>

2. <span data-ttu-id="95e9b-177">На странице flyout хранителя прокрутите в раздел **Расположения custodial,** чтобы просмотреть как проверенные, так и неоцененные источники данных, связанные с хранителями.</span><span class="sxs-lookup"><span data-stu-id="95e9b-177">On the custodian flyout page, scroll to the **Custodial locations** section to view both validated and unvalidated data sources that are associated with custodian.</span></span>

3. <span data-ttu-id="95e9b-178">Нажмите **кнопку Изменить** в верхней части страницы вылетов, чтобы удалить недействительные источники данных или добавить новые.</span><span class="sxs-lookup"><span data-stu-id="95e9b-178">Click **Edit** at the top of the flyout page to remove invalid data sources or add new ones.</span></span>

4. <span data-ttu-id="95e9b-179">После удаления неоцененных источников данных или добавления  нового значения Active отображается в столбце **Status** для хранителя на вкладке **Источники** данных. Чтобы добавить источники, которые ранее оказались недействительными, выполните ниже действия по исправлению, чтобы вручную добавить их к хранителю.</span><span class="sxs-lookup"><span data-stu-id="95e9b-179">After you remove unvalidated data sources or add a new one, the value **Active** is displayed in **Status** column for the custodian on the **Data sources** tab. To add sources that previously appeared to be invalid, follow the remediation steps below to manually add them to a custodian.</span></span>

### <a name="remediating-invalid-data-sources"></a><span data-ttu-id="95e9b-180">Исправление недействительных источников данных</span><span class="sxs-lookup"><span data-stu-id="95e9b-180">Remediating invalid data sources</span></span>

<span data-ttu-id="95e9b-181">Чтобы вручную добавить и связать источник данных, который ранее был недействительным:</span><span class="sxs-lookup"><span data-stu-id="95e9b-181">To manually add and associate a data source that was previously invalid:</span></span>

1. <span data-ttu-id="95e9b-182">На **вкладке Источники** данных выберите хранителя, чтобы вручную добавить и связать источник данных, который ранее был недействительным.</span><span class="sxs-lookup"><span data-stu-id="95e9b-182">On the **Data sources** tab, select a custodian to manually add and associate a data source that was previously invalid.</span></span>

2. <span data-ttu-id="95e9b-183">Щелкните **Изменить** в верхней части страницы вылетов, чтобы связать почтовые ящики, сайты, группы teams или Yammer с хранителями.</span><span class="sxs-lookup"><span data-stu-id="95e9b-183">Click **Edit** at the top of the flyout page to associate mailboxes, sites, Teams, or Yammer groups to the custodian.</span></span> <span data-ttu-id="95e9b-184">Сделайте это, нажав **кнопку Изменить** рядом с соответствующим типом расположения данных.</span><span class="sxs-lookup"><span data-stu-id="95e9b-184">Do this by clicking **Edit** next to the appropriate data location type.</span></span>

3. <span data-ttu-id="95e9b-185">Нажмите **кнопку Далее,** чтобы отобразить страницу **Параметры удержания** и настроить параметр удержания для добавленных источников данных.</span><span class="sxs-lookup"><span data-stu-id="95e9b-185">Click **Next** to display the **Hold settings** page and configure the hold setting for the data sources you added.</span></span>

4. <span data-ttu-id="95e9b-186">Нажмите **кнопку Далее,** чтобы отобразить страницу **Хранители** просмотреть, а затем нажмите **кнопку Отправить,** чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="95e9b-186">Click **Next** to display the **Review custodians** page, and then click **Submit** to save your changes.</span></span>
