---
title: Массовое добавление custodians к расширенному случаю обнаружения электронных данных
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 9331e45619f549ea31adcfdd9316eea20e43efef
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432442"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case-preview"></a><span data-ttu-id="faf29-102">Массовое добавление custodians к расширенному случаю обнаружения электронных данных (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="faf29-102">Bulk-add custodians to an Advanced eDiscovery case (preview)</span></span>

<span data-ttu-id="faf29-103">Для расширенных случаев обнаружения электронных данных, включающих множество custodians, вы можете импортировать несколько custodians с помощью CSV-файла, который содержит все сведения, необходимые для добавления в обращение.</span><span class="sxs-lookup"><span data-stu-id="faf29-103">For Advanced eDiscovery cases that involve a lot of custodians, you can import multiple custodians at once by a CSV file that contains all the information necessary to add them to a case.</span></span>

## <a name="bulk-add-custodians"></a><span data-ttu-id="faf29-104">Массовое добавление custodians</span><span class="sxs-lookup"><span data-stu-id="faf29-104">Bulk-add custodians</span></span>

1. <span data-ttu-id="faf29-105">Введите Case и перейдите на вкладку **источники** .</span><span class="sxs-lookup"><span data-stu-id="faf29-105">Enter case and navigate to the **Sources** tab.</span></span>

2. <span data-ttu-id="faf29-106">Нажмите кнопку **Импорт custodians**</span><span class="sxs-lookup"><span data-stu-id="faf29-106">Click **Import custodians**</span></span>

3. <span data-ttu-id="faf29-107">На всплывающей странице щелкните **загрузить пустой шаблон** , чтобы скачать CSV-файл шаблона хранитель.</span><span class="sxs-lookup"><span data-stu-id="faf29-107">On the flyout page, click **Download a blank template** to download a CSV custodian template file.</span></span>

4. <span data-ttu-id="faf29-108">Добавьте сведения о кустодиал в CSV-файл и сохраните его на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="faf29-108">Add the custodial information to the CSV file and save it on your local computer.</span></span> <span data-ttu-id="faf29-109">В следующем разделе приведены сведения о свойствах в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="faf29-109">See the next section for information about the properties in the CSV file.</span></span>

5. <span data-ttu-id="faf29-110">На вкладке **источники** нажмите кнопку **импортировать custodians** еще раз.</span><span class="sxs-lookup"><span data-stu-id="faf29-110">On the **Sources** tab, click **Import Custodians** again.</span></span> 
6. <span data-ttu-id="faf29-111">Во всплывающей странице нажмите кнопку **Обзор** и отправьте CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="faf29-111">On flyout page, click **Browse** and the upload your CSV file.</span></span>

   <span data-ttu-id="faf29-112">После отправки CSV-файла создается задание Булкаддкустодиан и отображается на вкладке **задания** . Задание проверяет custodians и соответствующие им источники данных, а затем добавляет их на вкладку **custodians** на странице **источники** этого случая.</span><span class="sxs-lookup"><span data-stu-id="faf29-112">After the CSV file is uploaded, a BulkAddCustodian job is created and displayed on the **Jobs** tab. The job validates the custodians and their corresponding data sources and then adds them to the **Custodians** tab on the **Sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="faf29-113">CSV-файл хранитель</span><span class="sxs-lookup"><span data-stu-id="faf29-113">Custodian CSV file</span></span>

<span data-ttu-id="faf29-114">После загрузки шаблона CSV можно добавить custodians и их источники данных в каждую строку.</span><span class="sxs-lookup"><span data-stu-id="faf29-114">After you download the CSV template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="faf29-115">Не изменяйте имена столбцов в строке заголовков.</span><span class="sxs-lookup"><span data-stu-id="faf29-115">Be sure not to change the column names in the the header row.</span></span>

| <span data-ttu-id="faf29-116">Столбец</span><span class="sxs-lookup"><span data-stu-id="faf29-116">Column name</span></span>|<span data-ttu-id="faf29-117">Описание</span><span class="sxs-lookup"><span data-stu-id="faf29-117">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="faf29-118">**Хранитель контактный**</span><span class="sxs-lookup"><span data-stu-id="faf29-118">**Custodian ContactEmail**</span></span>     | <span data-ttu-id="faf29-119">Электронная почта UPN для хранитель.</span><span class="sxs-lookup"><span data-stu-id="faf29-119">UPN email of custodian.</span></span> <span data-ttu-id="faf29-120">Пример: sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="faf29-120">Example: sarad@onmicrosoft.contoso.com</span></span>           |
|<span data-ttu-id="faf29-121">**Exchange Enabled**</span><span class="sxs-lookup"><span data-stu-id="faf29-121">**Exchange Enabled**</span></span> | <span data-ttu-id="faf29-122">Значение TRUE/FALSE указывает, следует ли добавить почтовый ящик хранитель.</span><span class="sxs-lookup"><span data-stu-id="faf29-122">TRUE/FALSE value on whether to add custodian's mailbox.</span></span>      |
|<span data-ttu-id="faf29-123">**OneDrive включен**</span><span class="sxs-lookup"><span data-stu-id="faf29-123">**OneDrive Enabled**</span></span> | <span data-ttu-id="faf29-124">Значение TRUE/FALSE указывает, следует ли добавить учетную запись OneDrive для бизнеса хранитель.</span><span class="sxs-lookup"><span data-stu-id="faf29-124">TRUE/FALSE value on whether to add custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="faf29-125">**Ожидание**</span><span class="sxs-lookup"><span data-stu-id="faf29-125">**Is OnHold**</span></span>        | <span data-ttu-id="faf29-126">Значение TRUE/FALSE указывает, следует ли помещать хранитель на удержание.</span><span class="sxs-lookup"><span data-stu-id="faf29-126">TRUE/FALSE value on whether to place custodian on hold.</span></span>       |
|<span data-ttu-id="faf29-127">**Тип Workload1**</span><span class="sxs-lookup"><span data-stu-id="faf29-127">**Workload1 Type**</span></span>         | <span data-ttu-id="faf29-128">Строковое значение, указывающее тип источника данных, связываемого с хранитель.</span><span class="sxs-lookup"><span data-stu-id="faf29-128">String value indicating the type of data source to associate with the custodian.</span></span> <br /><span data-ttu-id="faf29-129">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="faf29-129">Possible values include:</span></span> <br /><span data-ttu-id="faf29-130">Ексчанжемаилбокс, Шарепоинтсите, Теамсмаилбокс, Теамссите, Яммермаилбокс, Яммерсите</span><span class="sxs-lookup"><span data-stu-id="faf29-130">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span></span> |
|<span data-ttu-id="faf29-131">**Расположение Workload1**</span><span class="sxs-lookup"><span data-stu-id="faf29-131">**Workload1 Location**</span></span>     | <span data-ttu-id="faf29-132">В зависимости от типа рабочей нагрузки это будет местоположение данных рабочей нагрузки (например, адрес электронной почты почтового ящика Exchange или URL-адрес сайта SharePoint).</span><span class="sxs-lookup"><span data-stu-id="faf29-132">Depending on your workload type, this would be the data location of your workload (for example, the email address of an Exchange mailbox or the URL for a SharePoint site).</span></span> |
|||

<span data-ttu-id="faf29-133">Ниже приведен пример CSV-файла со сведениями о хранитель:</span><span class="sxs-lookup"><span data-stu-id="faf29-133">Here's an example of a CSV file with custodian information:</span></span>  

| <span data-ttu-id="faf29-134">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="faf29-134">ContactEmail</span></span>      | <span data-ttu-id="faf29-135">Exchange Enabled</span><span class="sxs-lookup"><span data-stu-id="faf29-135">Exchange Enabled</span></span> | <span data-ttu-id="faf29-136">OneDrive включен</span><span class="sxs-lookup"><span data-stu-id="faf29-136">OneDrive Enabled</span></span> | <span data-ttu-id="faf29-137">Ожидание</span><span class="sxs-lookup"><span data-stu-id="faf29-137">Is OnHold</span></span> | <span data-ttu-id="faf29-138">Тип Workload1</span><span class="sxs-lookup"><span data-stu-id="faf29-138">Workload1 Type</span></span> | <span data-ttu-id="faf29-139">Расположение Workload1</span><span class="sxs-lookup"><span data-stu-id="faf29-139">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="faf29-140">sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="faf29-140">sarad@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="faf29-141">TRUE</span><span class="sxs-lookup"><span data-stu-id="faf29-141">TRUE</span></span>             | <span data-ttu-id="faf29-142">TRUE</span><span class="sxs-lookup"><span data-stu-id="faf29-142">TRUE</span></span>             | <span data-ttu-id="faf29-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="faf29-143">TRUE</span></span>      | <span data-ttu-id="faf29-144">шарепоинтсите</span><span class="sxs-lookup"><span data-stu-id="faf29-144">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="faf29-145">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="faf29-145">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="faf29-146">TRUE</span><span class="sxs-lookup"><span data-stu-id="faf29-146">TRUE</span></span>             | <span data-ttu-id="faf29-147">TRUE</span><span class="sxs-lookup"><span data-stu-id="faf29-147">TRUE</span></span>             | <span data-ttu-id="faf29-148">TRUE</span><span class="sxs-lookup"><span data-stu-id="faf29-148">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="faf29-149">Хранитель и проверка источника данных</span><span class="sxs-lookup"><span data-stu-id="faf29-149">Custodian and data source validation</span></span>

<span data-ttu-id="faf29-150">При отправке CSV-файла хранитель, Расширенное обнаружение электронных данных выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="faf29-150">When you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="faf29-151">Проверяет custodians и их источники данных.</span><span class="sxs-lookup"><span data-stu-id="faf29-151">Validates the custodians and their data sources.</span></span> 

2. <span data-ttu-id="faf29-152">Индексирует все источники данных для каждого хранитель и размещает их на удержании (если свойство onhold имеет значение TRUE).</span><span class="sxs-lookup"><span data-stu-id="faf29-152">Indexes all data sources for each custodian and places them on hold (if the Is OnHold property is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="faf29-153">Проверка хранитель</span><span class="sxs-lookup"><span data-stu-id="faf29-153">Custodian validation</span></span>

<span data-ttu-id="faf29-154">В настоящее время поддерживается только импорт custodians, которые находятся в Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="faf29-154">Currently, we only support importing custodians that are in Azure Active Directory (AAD).</span></span>

<span data-ttu-id="faf29-155">Мы проверяем и получаем custodians, используя значение имени участника-пользователя в столбце **Contact email** в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="faf29-155">We validate and find custodians using the UPN value in the **Contact Email** column in the CSV file.</span></span> <span data-ttu-id="faf29-156">Custodians, которые были проверены, автоматически добавляются в обращение и отображаются на вкладке **хранитель** на странице **источники** этого случая.</span><span class="sxs-lookup"><span data-stu-id="faf29-156">Custodians that are validated are automatically added to the case and listed on the **Custodian** tab on the **Sources** page of the case.</span></span> <span data-ttu-id="faf29-157">Если хранитель невозможно проверить, они перечислены в журнале ошибок задания Булкаддкустодиан, которое отображается на вкладке **задания** в случае.</span><span class="sxs-lookup"><span data-stu-id="faf29-157">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="faf29-158">Непроверенные custodians не добавляются в обращение.</span><span class="sxs-lookup"><span data-stu-id="faf29-158">Unvalidated custodians are not added to the case.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="faf29-159">Проверка источника данных</span><span class="sxs-lookup"><span data-stu-id="faf29-159">Data source validation</span></span>

<span data-ttu-id="faf29-160">После проверки и добавления custodians в случае проверяется каждый источник данных, связанный с хранитель.</span><span class="sxs-lookup"><span data-stu-id="faf29-160">After custodians are validated and added to the case, each data source that's associated with a custodian is validated.</span></span> <span data-ttu-id="faf29-161">Если не удается найти какой бы то ни было источник данных для хранитель, то значение **не подтверждено** будет отображаться в столбце **Проверено** на вкладке **хранитель** для этого хранитель.</span><span class="sxs-lookup"><span data-stu-id="faf29-161">If any data source for a custodian can't be found, the value **Not validated** would be displayed in the **Validated** column on the **Custodian** tab for that custodian.</span></span>

### <a name="remediating-unvalidated-data-sources"></a><span data-ttu-id="faf29-162">Устранение непроверенных источников данных</span><span class="sxs-lookup"><span data-stu-id="faf29-162">Remediating unvalidated data sources</span></span>

<span data-ttu-id="faf29-163">Чтобы исправить custodians с непроверенными источниками данных, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="faf29-163">To remediate custodians with unvalidated data sources:</span></span> 

1. <span data-ttu-id="faf29-164">На вкладке **хранитель** выберите хранитель, который не прошел проверку.</span><span class="sxs-lookup"><span data-stu-id="faf29-164">On the **Custodian** tab, select a custodian who isn't validated.</span></span>

2. <span data-ttu-id="faf29-165">В подменю хранитель прокрутите до раздела **Источники данных** , чтобы просмотреть источники данных, связанные с хранитель.</span><span class="sxs-lookup"><span data-stu-id="faf29-165">On the custodian flyout page, scroll to the **Data sources** section to view the data sources that are associated with custodian.</span></span> <span data-ttu-id="faf29-166">В списке указаны как проверенные, так и непроверенные источники данных.</span><span class="sxs-lookup"><span data-stu-id="faf29-166">Both validated and unvalidated data sources are listed.</span></span>

3. <span data-ttu-id="faf29-167">В разделе **Источники данных** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="faf29-167">In the **Data sources** section, click **Edit**.</span></span>

4. <span data-ttu-id="faf29-168">На странице " **Выбор расположений кустодиал** " удалите непроверенный источник данных.</span><span class="sxs-lookup"><span data-stu-id="faf29-168">On the **Choose custodial locations** page, remove an unvalidated data source.</span></span>

5. <span data-ttu-id="faf29-169">На странице " **Выбор дополнительных расположений** " нажмите кнопку **Обновить** , чтобы добавить дополнительные источники данных для хранитель.</span><span class="sxs-lookup"><span data-stu-id="faf29-169">On the **Select additional locations** page, click **Update** to add additional data sources for a custodian.</span></span>
