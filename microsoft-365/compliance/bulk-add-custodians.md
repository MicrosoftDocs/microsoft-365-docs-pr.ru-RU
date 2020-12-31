---
title: Импорт хранителей в дело Advanced eDiscovery
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
description: Используйте средство импорта dto быстрое добавление нескольких хранителей и связанных с ними источников данных в дело в Advanced eDiscovery.
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740306"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="d8adc-103">Импорт хранителей в дело Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d8adc-103">Import custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="d8adc-104">Для случаев Advanced eDiscovery, в которых используется множество хранителей, вы можете одновременно импортировать несколько хранителей с помощью CSV-файла, который содержит сведения, необходимые для их добавления в дело.</span><span class="sxs-lookup"><span data-stu-id="d8adc-104">For Advanced eDiscovery cases that involve many custodians, you can import multiple custodians at once by using a CSV file that contains the information necessary to add them to a case.</span></span>

## <a name="import-custodians"></a><span data-ttu-id="d8adc-105">Импорт хранителей</span><span class="sxs-lookup"><span data-stu-id="d8adc-105">Import custodians</span></span>

1. <span data-ttu-id="d8adc-106">Откройте дело Advanced eDiscovery и выберите вкладку **"Источники данных".**</span><span class="sxs-lookup"><span data-stu-id="d8adc-106">Open the Advanced eDiscovery case and select the **Data sources** tab.</span></span>

2. <span data-ttu-id="d8adc-107">Нажмите **кнопку "Добавить хранителей**  >  **импорта источника данных".**</span><span class="sxs-lookup"><span data-stu-id="d8adc-107">Click **Add data source** > **Import custodians**.</span></span>

3. <span data-ttu-id="d8adc-108">На странице **"Импорт хранителей"** щелкните **"Скачать пустой** шаблон", чтобы скачать CSV-файл шаблона хранителя.</span><span class="sxs-lookup"><span data-stu-id="d8adc-108">On the **Import custodians** flyout page, click **Download a blank template** to download a custodian template CSV file.</span></span>

   ![Скачивание шаблона CSV со страницы "Импорт хранителей"](../media/ImportCustodians1.png)

4. <span data-ttu-id="d8adc-110">Добавьте сведения об хранителях в CSV-файл и сохраните их на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d8adc-110">Add the custodial information to the CSV file and save it to your local computer.</span></span> <span data-ttu-id="d8adc-111">Сведения о необходимых свойствах в CSV-файле см. в разделе [CSV-файла Custodian.](#custodian-csv-file)</span><span class="sxs-lookup"><span data-stu-id="d8adc-111">See the [Custodian CSV file](#custodian-csv-file) section for information about the required properties in the CSV file.</span></span>

5. <span data-ttu-id="d8adc-112">После подготовки CSV-файла с данными хранителя снова  перейдите на вкладку "Источники данных" и снова нажмите кнопку **"Добавить** хранителей импорта источника  >  **данных".**</span><span class="sxs-lookup"><span data-stu-id="d8adc-112">After you've prepared the CSV file with the custodian information, go back to the **Data sources** tab, and click **Add data source** > **Import custodians** again.</span></span>

6. <span data-ttu-id="d8adc-113">На странице **"Импорт хранителей"** нажмите кнопку "Обзор", а затем загрузите CSV-файл, содержащий сведения об хранителях. </span><span class="sxs-lookup"><span data-stu-id="d8adc-113">On the **Import custodians** flyout page, click **Browse** and then upload the CSV file that contains the custodian information.</span></span>

   <span data-ttu-id="d8adc-114">После отправки CSV-файла создается задание **BulkAddCustodian** и отображается на вкладке **"Задания".** Задание проверяет хранителей и связанные с ними источники данных, а затем добавляет их на страницу источников данных дела. </span><span class="sxs-lookup"><span data-stu-id="d8adc-114">After the CSV file is uploaded, a job named **BulkAddCustodian** is created and displayed on the **Jobs** tab. The job validates the custodians and their associated data sources and then adds them to the **Data sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="d8adc-115">CSV-файл хранителя</span><span class="sxs-lookup"><span data-stu-id="d8adc-115">Custodian CSV file</span></span>

<span data-ttu-id="d8adc-116">После загрузки шаблона хранителя CSV можно добавить хранителей и их источник данных в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="d8adc-116">After you download the CSV custodian template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="d8adc-117">Не изменяя имена столбцов в строке колонок.</span><span class="sxs-lookup"><span data-stu-id="d8adc-117">Be sure not to change the column names in the header row.</span></span> <span data-ttu-id="d8adc-118">Используйте столбцы расположения рабочей нагрузки и типа рабочей нагрузки, чтобы связать другие источники данных с хранителями.</span><span class="sxs-lookup"><span data-stu-id="d8adc-118">Use the workload type and workload location columns to associate other data sources to a custodian.</span></span>

| <span data-ttu-id="d8adc-119">Столбец</span><span class="sxs-lookup"><span data-stu-id="d8adc-119">Column name</span></span>|<span data-ttu-id="d8adc-120">Описание</span><span class="sxs-lookup"><span data-stu-id="d8adc-120">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="d8adc-121">**Custodian contactEmail**</span><span class="sxs-lookup"><span data-stu-id="d8adc-121">**Custodian contactEmail**</span></span>     |<span data-ttu-id="d8adc-122">Электронный адрес upN хранителя.</span><span class="sxs-lookup"><span data-stu-id="d8adc-122">The custodian's UPN email address.</span></span> <span data-ttu-id="d8adc-123">Например, sarad@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="d8adc-123">For example, sarad@contoso.onmicrosoft.com.</span></span>           |
|<span data-ttu-id="d8adc-124">**Exchange Enabled**</span><span class="sxs-lookup"><span data-stu-id="d8adc-124">**Exchange Enabled**</span></span> | <span data-ttu-id="d8adc-125">Значение TRUE или FALSE, чтобы включить или не включать почтовый ящик хранителя.</span><span class="sxs-lookup"><span data-stu-id="d8adc-125">TRUE/FALSE value to include or not include the custodian's mailbox.</span></span>      |
|<span data-ttu-id="d8adc-126">**OneDrive включен**</span><span class="sxs-lookup"><span data-stu-id="d8adc-126">**OneDrive Enabled**</span></span> | <span data-ttu-id="d8adc-127">Значение TRUE или FALSE, чтобы включить или не включить учетную запись OneDrive для бизнеса хранителя.</span><span class="sxs-lookup"><span data-stu-id="d8adc-127">TRUE/FALSE value to include or not included the custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="d8adc-128">**Is OnHold**</span><span class="sxs-lookup"><span data-stu-id="d8adc-128">**Is OnHold**</span></span>        | <span data-ttu-id="d8adc-129">Значение TRUE или FALSE, чтобы указать, следует ли разместить источники данных хранителя на удержание.</span><span class="sxs-lookup"><span data-stu-id="d8adc-129">TRUE/FALSE value to indicate whether to place the custodian data sources on hold.</span></span>       |
|<span data-ttu-id="d8adc-130">**Тип workload1**</span><span class="sxs-lookup"><span data-stu-id="d8adc-130">**Workload1 Type**</span></span>         |<span data-ttu-id="d8adc-131">Строка, указывающая тип источника данных, связываемого с хранителями.</span><span class="sxs-lookup"><span data-stu-id="d8adc-131">String value indicating the type of data source to associate with the custodian.</span></span> <span data-ttu-id="d8adc-132">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="d8adc-132">Possible values include:</span></span> <br/><span data-ttu-id="d8adc-133">- ExchangeMailbox</span><span class="sxs-lookup"><span data-stu-id="d8adc-133">- ExchangeMailbox</span></span><br/> <span data-ttu-id="d8adc-134">- SharePointSite</span><span class="sxs-lookup"><span data-stu-id="d8adc-134">- SharePointSite</span></span><br/><span data-ttu-id="d8adc-135">- TeamsMailbox</span><span class="sxs-lookup"><span data-stu-id="d8adc-135">- TeamsMailbox</span></span><br/><span data-ttu-id="d8adc-136">- TeamsSite</span><span class="sxs-lookup"><span data-stu-id="d8adc-136">- TeamsSite</span></span><br/> <span data-ttu-id="d8adc-137">- YammerMailbox</span><span class="sxs-lookup"><span data-stu-id="d8adc-137">- YammerMailbox</span></span><br/><span data-ttu-id="d8adc-138">- YammerSite</span><span class="sxs-lookup"><span data-stu-id="d8adc-138">- YammerSite</span></span> |
|<span data-ttu-id="d8adc-139">**Расположение workload1**</span><span class="sxs-lookup"><span data-stu-id="d8adc-139">**Workload1 Location**</span></span>     | <span data-ttu-id="d8adc-140">В зависимости от типа рабочей нагрузки это расположение источника данных.</span><span class="sxs-lookup"><span data-stu-id="d8adc-140">Depending on your workload type, this would be the location of the data source.</span></span> <span data-ttu-id="d8adc-141">Например, адрес электронной почты для почтового ящика Exchange или URL-адрес сайта SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d8adc-141">For example, the email address for an Exchange mailbox or the URL for a SharePoint site.</span></span> |
|||

<span data-ttu-id="d8adc-142">Вот пример CSV-файла с информацией об хранителях:</span><span class="sxs-lookup"><span data-stu-id="d8adc-142">Here's an example of a CSV file with custodian information:</span></span><br/><br/>

|<span data-ttu-id="d8adc-143">Custodian contactEmail</span><span class="sxs-lookup"><span data-stu-id="d8adc-143">Custodian contactEmail</span></span>      | <span data-ttu-id="d8adc-144">Exchange Enabled</span><span class="sxs-lookup"><span data-stu-id="d8adc-144">Exchange Enabled</span></span> | <span data-ttu-id="d8adc-145">OneDrive включен</span><span class="sxs-lookup"><span data-stu-id="d8adc-145">OneDrive Enabled</span></span> | <span data-ttu-id="d8adc-146">Is OnHold</span><span class="sxs-lookup"><span data-stu-id="d8adc-146">Is OnHold</span></span> | <span data-ttu-id="d8adc-147">Тип workload1</span><span class="sxs-lookup"><span data-stu-id="d8adc-147">Workload1 Type</span></span> | <span data-ttu-id="d8adc-148">Расположение workload1</span><span class="sxs-lookup"><span data-stu-id="d8adc-148">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="d8adc-149">robinc@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d8adc-149">robinc@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="d8adc-150">TRUE</span><span class="sxs-lookup"><span data-stu-id="d8adc-150">TRUE</span></span>             | <span data-ttu-id="d8adc-151">TRUE</span><span class="sxs-lookup"><span data-stu-id="d8adc-151">TRUE</span></span>             | <span data-ttu-id="d8adc-152">TRUE</span><span class="sxs-lookup"><span data-stu-id="d8adc-152">TRUE</span></span>      | <span data-ttu-id="d8adc-153">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="d8adc-153">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="d8adc-154">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d8adc-154">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="d8adc-155">TRUE</span><span class="sxs-lookup"><span data-stu-id="d8adc-155">TRUE</span></span>             | <span data-ttu-id="d8adc-156">TRUE</span><span class="sxs-lookup"><span data-stu-id="d8adc-156">TRUE</span></span>             | <span data-ttu-id="d8adc-157">TRUE</span><span class="sxs-lookup"><span data-stu-id="d8adc-157">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="d8adc-158">Проверка хранителя и источника данных</span><span class="sxs-lookup"><span data-stu-id="d8adc-158">Custodian and data source validation</span></span>

<span data-ttu-id="d8adc-159">После отправки CSV-файла хранителя Advanced eDiscovery делает следующее:</span><span class="sxs-lookup"><span data-stu-id="d8adc-159">After you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="d8adc-160">Проверяет хранителей и их источники данных.</span><span class="sxs-lookup"><span data-stu-id="d8adc-160">Validates the custodians and their data sources.</span></span>

2. <span data-ttu-id="d8adc-161">Индексирует все источники данных для каждого хранителя и помещает их на удержание (если для свойства **Is OnHold** в CSV-файле установлено true).</span><span class="sxs-lookup"><span data-stu-id="d8adc-161">Indexes all data sources for each custodian and places them on hold (if the **Is OnHold** property in the CSV file is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="d8adc-162">Проверка хранителя</span><span class="sxs-lookup"><span data-stu-id="d8adc-162">Custodian validation</span></span>

<span data-ttu-id="d8adc-163">В настоящее время мы поддерживаем импорт только хранителей, включенных в Azure Active Directory (Azure AD) вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d8adc-163">Currently, we only support importing custodians that are included in your organization's Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="d8adc-164">Средство импорта хранителей находит и проверяет хранителей, используя значение UPN в столбце **Custodian contactEmail** в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="d8adc-164">The custodian import tool finds and validates custodians using the UPN value in the **Custodian contactEmail** column in the CSV file.</span></span> <span data-ttu-id="d8adc-165">Проверяемая хранители автоматически добавляются в дело и перечислены на вкладке **"Источники** данных" дела.</span><span class="sxs-lookup"><span data-stu-id="d8adc-165">Custodians that are validated are automatically added to the case and listed on the **Data sources** tab of the case.</span></span> <span data-ttu-id="d8adc-166">Если хранители не могут быть проверены, они перечислены в журнале ошибок для задания BulkAddCustodian, которое указано на вкладке **"Задания"** в этом случае.</span><span class="sxs-lookup"><span data-stu-id="d8adc-166">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="d8adc-167">Неоцененные хранители не добавляются в дело или не перечислены на **вкладке "Источники** данных".</span><span class="sxs-lookup"><span data-stu-id="d8adc-167">Unvalidated custodians are not added to the case or listed on the **Data sources** tab.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="d8adc-168">Проверка источника данных</span><span class="sxs-lookup"><span data-stu-id="d8adc-168">Data source validation</span></span>

<span data-ttu-id="d8adc-169">После проверки и добавления хранителей в дело добавляются все основные почтовые ящики и учетная запись OneDrive, связанные с хранителями.</span><span class="sxs-lookup"><span data-stu-id="d8adc-169">After custodians are validated and added to the case, each primary mailbox and OneDrive account that's associated with a custodian is added.</span></span>

<span data-ttu-id="d8adc-170">Однако если не удалось найти другие источники данных (например, сайты SharePoint, Microsoft Teams, группы Microsoft 365 или группы Yammer), связанные с хранителями, ни один из  них не назначен хранителям, а значение **"Не** проверено" отображается в столбце "Состояние" рядом с хранителя на вкладке "Источники данных". </span><span class="sxs-lookup"><span data-stu-id="d8adc-170">However, if any of the other data sources (such as SharePoint sites, Microsoft Teams, Microsoft 365 Groups, or Yammer groups) associated with a custodian can't be found, none of them are assigned to the custodian and the value **Not validated** is displayed in the **Status** column next to the custodian on the **Data sources** tab.</span></span>

<span data-ttu-id="d8adc-171">Добавление проверенных источников данных для хранителя:</span><span class="sxs-lookup"><span data-stu-id="d8adc-171">To add validated data sources for a custodian:</span></span>

1. <span data-ttu-id="d8adc-172">На **вкладке "Источники** данных" выберите хранителя, который содержит не проверенные источники данных.</span><span class="sxs-lookup"><span data-stu-id="d8adc-172">On the **Data sources** tab, select a custodian that contains data sources that aren't validated.</span></span>

2. <span data-ttu-id="d8adc-173">На странице flyout хранителя прокрутите страницу до раздела "Расположения хранителя", чтобы просмотреть проверенные и неоцененные источники данных, связанные с хранителями. </span><span class="sxs-lookup"><span data-stu-id="d8adc-173">On the custodian flyout page, scroll to the **Custodial locations** section to view both validated and unvalidated data sources that are associated with custodian.</span></span>

3. <span data-ttu-id="d8adc-174">Нажмите **кнопку** "Изменить" в верхней части страницы, чтобы удалить недопустимые источники данных или добавить новые.</span><span class="sxs-lookup"><span data-stu-id="d8adc-174">Click **Edit** at the top of the flyout page to remove invalid data sources or add new ones.</span></span>

4. <span data-ttu-id="d8adc-175">После удаления неоцененных источников данных или добавления нового значения значение  **Active** отображается в столбце "Состояние" для хранителя на вкладке "Источники **данных".** Чтобы добавить источники, которые ранее были недопустимыми, выполните действия по исправлению ниже, чтобы вручную добавить их к хранителю.</span><span class="sxs-lookup"><span data-stu-id="d8adc-175">After you remove unvalidated data sources or add a new one, the value **Active** is displayed in **Status** column for the custodian on the **Data sources** tab. To add sources that previously appeared to be invalid, follow the remediation steps below to manually add them to a custodian.</span></span>

### <a name="remediating-invalid-data-sources"></a><span data-ttu-id="d8adc-176">Устранение недопустимых источников данных</span><span class="sxs-lookup"><span data-stu-id="d8adc-176">Remediating invalid data sources</span></span>

<span data-ttu-id="d8adc-177">Чтобы вручную добавить и связать источник данных, который ранее был недопустимым:</span><span class="sxs-lookup"><span data-stu-id="d8adc-177">To manually add and associate a data source that was previously invalid:</span></span>

1. <span data-ttu-id="d8adc-178">На **вкладке "Источники** данных" выберите хранителя, чтобы вручную добавить и связать источник данных, который ранее был недопустимым.</span><span class="sxs-lookup"><span data-stu-id="d8adc-178">On the **Data sources** tab, select a custodian to manually add and associate a data source that was previously invalid.</span></span>

2. <span data-ttu-id="d8adc-179">Нажмите **кнопку** "Изменить" в верхней части страницы, чтобы связать почтовые ящики, сайты, группы Teams или Yammer с хранителями.</span><span class="sxs-lookup"><span data-stu-id="d8adc-179">Click **Edit** at the top of the flyout page to associate mailboxes, sites, Teams, or Yammer groups to the custodian.</span></span> <span data-ttu-id="d8adc-180">Для этого нажмите кнопку **"Изменить"** рядом с соответствующим типом расположения данных.</span><span class="sxs-lookup"><span data-stu-id="d8adc-180">Do this by clicking **Edit** next to the appropriate data location type.</span></span>

3. <span data-ttu-id="d8adc-181">Нажмите **кнопку** "Далее", **чтобы** отобразить страницу параметров удержания и настроить параметр удержания для добавленных источников данных.</span><span class="sxs-lookup"><span data-stu-id="d8adc-181">Click **Next** to display the **Hold settings** page and configure the hold setting for the data sources you added.</span></span>

4. <span data-ttu-id="d8adc-182">Нажмите **кнопку** "Далее", чтобы отобразить страницу **"Просмотр хранителей",** а затем нажмите кнопку **"Отправить",** чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="d8adc-182">Click **Next** to display the **Review custodians** page, and then click **Submit** to save your changes.</span></span>
