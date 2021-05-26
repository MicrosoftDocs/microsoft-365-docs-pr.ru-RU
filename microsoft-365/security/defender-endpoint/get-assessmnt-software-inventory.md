---
title: Экспорт оценки инвентаризации программного обеспечения на устройство
description: Возвращает таблицу с записью для каждой уникальной комбинации DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.
keywords: api, api, export assessment, per device assessment, vulnerability assessment report, device vulnerability assessment, device vulnerability report, secure configuration assessment, secure configuration report, software vulnerabilities assessment, software vulnerability report, vulnerability report by machine,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: ecfeaa10eda6b3832b7196c0598d6584783bb5ff
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653682"
---
# <a name="export-software-inventory-assessment-per-device"></a><span data-ttu-id="adc60-104">Экспорт оценки инвентаризации программного обеспечения на устройство</span><span class="sxs-lookup"><span data-stu-id="adc60-104">Export software inventory assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="adc60-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="adc60-105">**Applies to:**</span></span>

- [<span data-ttu-id="adc60-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="adc60-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="adc60-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="adc60-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="adc60-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="adc60-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="adc60-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="adc60-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="adc60-110">Существуют различные вызовы API для получения различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="adc60-110">There are different API calls to get different types of data.</span></span> <span data-ttu-id="adc60-111">Так как объем данных может быть очень большим, их можно получить двумя способами:</span><span class="sxs-lookup"><span data-stu-id="adc60-111">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="adc60-112">**OData**  API передает все данные в организации в качестве ответов Json, следуя протоколу OData.</span><span class="sxs-lookup"><span data-stu-id="adc60-112">**OData**  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="adc60-113">Этот метод лучше всего используется для небольших организаций с устройствами _менее 100 К._</span><span class="sxs-lookup"><span data-stu-id="adc60-113">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="adc60-114">Ответ paginated, поэтому вы можете использовать поле odata.nextLink из ответа, чтобы \@ получить следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="adc60-114">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="adc60-115">**с помощью файлов** Это решение API позволяет быстрее и более надежно тянуть большие объемы данных.</span><span class="sxs-lookup"><span data-stu-id="adc60-115">**via files** This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="adc60-116">Поэтому рекомендуется для крупных организаций с более чем 100 устройствами K.</span><span class="sxs-lookup"><span data-stu-id="adc60-116">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="adc60-117">Этот API извлекает все данные в организации в качестве файлов загрузки.</span><span class="sxs-lookup"><span data-stu-id="adc60-117">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="adc60-118">Ответ содержит URL-адреса для загрузки всех данных из служба хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="adc60-118">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="adc60-119">Этот API позволяет загружать все данные из служба хранилища Azure следующим образом:</span><span class="sxs-lookup"><span data-stu-id="adc60-119">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="adc60-120">Позвоните в API, чтобы получить список загружаемых URL-адресов со всеми данными организации.</span><span class="sxs-lookup"><span data-stu-id="adc60-120">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="adc60-121">Скачайте все файлы с помощью URL-адресов загрузки и обработать данные, как вам нравится.</span><span class="sxs-lookup"><span data-stu-id="adc60-121">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="adc60-122">Собранные данные (для _OData_ или с помощью _файлов)_ являются текущим снимком текущего состояния и не содержат исторических данных.</span><span class="sxs-lookup"><span data-stu-id="adc60-122">The data that is collected (for either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="adc60-123">Чтобы собрать исторические данные, клиенты должны сохранять данные в собственных хранилищах данных.</span><span class="sxs-lookup"><span data-stu-id="adc60-123">In order to collect historic data, customers must save the data in their own data storages.</span></span>

<span data-ttu-id="adc60-124">Если не указано обратное, все \*\*\*\* перечисленные методы оценки экспорта являются полным экспортом и по устройству **_(также_** именуемой как **_на устройстве)._**</span><span class="sxs-lookup"><span data-stu-id="adc60-124">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-inventory-assessment-odata"></a><span data-ttu-id="adc60-125">1. Оценка инвентаризации по экспорту программного обеспечения (OData)</span><span class="sxs-lookup"><span data-stu-id="adc60-125">1. Export software inventory assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="adc60-126">Описание метода API 1.1</span><span class="sxs-lookup"><span data-stu-id="adc60-126">1.1 API method description</span></span>

<span data-ttu-id="adc60-127">Этот ответ API содержит все данные установленного программного обеспечения на устройство.</span><span class="sxs-lookup"><span data-stu-id="adc60-127">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="adc60-128">Возвращает таблицу с записью для каждой уникальной комбинации DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span><span class="sxs-lookup"><span data-stu-id="adc60-128">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="limitations"></a><span data-ttu-id="adc60-129">Ограничения</span><span class="sxs-lookup"><span data-stu-id="adc60-129">Limitations</span></span>

- <span data-ttu-id="adc60-130">Максимальный размер страницы — 200 000.</span><span class="sxs-lookup"><span data-stu-id="adc60-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="adc60-131">Ограничения скорости для этого API : 30 вызовов в минуту и 1000 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="adc60-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="adc60-132">1.2 Разрешения</span><span class="sxs-lookup"><span data-stu-id="adc60-132">1.2 Permissions</span></span>

<span data-ttu-id="adc60-133">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="adc60-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="adc60-134">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="adc60-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="adc60-135">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="adc60-135">Permission type</span></span> | <span data-ttu-id="adc60-136">Разрешение</span><span class="sxs-lookup"><span data-stu-id="adc60-136">Permission</span></span> | <span data-ttu-id="adc60-137">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="adc60-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="adc60-138">Приложение</span><span class="sxs-lookup"><span data-stu-id="adc60-138">Application</span></span> | <span data-ttu-id="adc60-139">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="adc60-139">Software.Read.All</span></span> | <span data-ttu-id="adc60-140">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="adc60-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="adc60-141">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="adc60-141">Delegated (work or school account)</span></span> | <span data-ttu-id="adc60-142">Software.Read</span><span class="sxs-lookup"><span data-stu-id="adc60-142">Software.Read</span></span> | <span data-ttu-id="adc60-143">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="adc60-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="adc60-144">1.3 URL-адрес</span><span class="sxs-lookup"><span data-stu-id="adc60-144">1.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="adc60-145">1.4 Параметры</span><span class="sxs-lookup"><span data-stu-id="adc60-145">1.4 Parameters</span></span>

- <span data-ttu-id="adc60-146">pageSize (по умолчанию = 50 000) — количество результатов в ответе.</span><span class="sxs-lookup"><span data-stu-id="adc60-146">pageSize (default = 50,000) – number of results in response.</span></span>

- <span data-ttu-id="adc60-147">$top — количество возвращаемого результата (не возвращает @odata.nextLink и, следовательно, не вытягивает все данные)</span><span class="sxs-lookup"><span data-stu-id="adc60-147">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="adc60-148">1.5 Свойства</span><span class="sxs-lookup"><span data-stu-id="adc60-148">1.5 Properties</span></span>

>[!NOTE]
>
><span data-ttu-id="adc60-149">-Каждая запись — это примерно 0,5 КБ данных.</span><span class="sxs-lookup"><span data-stu-id="adc60-149">-Each record is approximately 0.5KB of data.</span></span> <span data-ttu-id="adc60-150">Это следует учитывать при выборе правильного параметра PageSize для вас.</span><span class="sxs-lookup"><span data-stu-id="adc60-150">You should take this into account when choosing the correct pageSize parameter for you.</span></span>

><span data-ttu-id="adc60-151">-Свойства, определенные в следующей таблице, перечислены в альфа-числе, по ID свойства.</span><span class="sxs-lookup"><span data-stu-id="adc60-151">-The properties defined in the following table are listed alphanumerically, by property ID.</span></span> <span data-ttu-id="adc60-152">При запуске этого API результат не обязательно возвращается в том же порядке, который указан в этих таблицах.</span><span class="sxs-lookup"><span data-stu-id="adc60-152">When running this API, the resulting output will not necessarily be returned in the same order listed in these tables.</span></span>
>
><span data-ttu-id="adc60-153">-Некоторые дополнительные столбцы могут быть возвращены в ответе.</span><span class="sxs-lookup"><span data-stu-id="adc60-153">-Some additional columns might be returned in the response.</span></span> <span data-ttu-id="adc60-154">Эти столбцы являются временными и могут быть удалены, используйте только задокументированные столбцы.</span><span class="sxs-lookup"><span data-stu-id="adc60-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>

<span data-ttu-id="adc60-155">Свойство (id)</span><span class="sxs-lookup"><span data-stu-id="adc60-155">Property (id)</span></span> | <span data-ttu-id="adc60-156">Тип данных</span><span class="sxs-lookup"><span data-stu-id="adc60-156">Data type</span></span> | <span data-ttu-id="adc60-157">Описание</span><span class="sxs-lookup"><span data-stu-id="adc60-157">Description</span></span> | <span data-ttu-id="adc60-158">Пример возвращенного значения</span><span class="sxs-lookup"><span data-stu-id="adc60-158">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="adc60-159">DeviceId</span><span class="sxs-lookup"><span data-stu-id="adc60-159">DeviceId</span></span> | <span data-ttu-id="adc60-160">string</span><span class="sxs-lookup"><span data-stu-id="adc60-160">string</span></span> | <span data-ttu-id="adc60-161">Уникальный идентификатор устройства в службе.</span><span class="sxs-lookup"><span data-stu-id="adc60-161">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="adc60-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="adc60-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="adc60-163">DeviceName</span><span class="sxs-lookup"><span data-stu-id="adc60-163">DeviceName</span></span> | <span data-ttu-id="adc60-164">string</span><span class="sxs-lookup"><span data-stu-id="adc60-164">string</span></span> | <span data-ttu-id="adc60-165">Полное доменное имя (FQDN) устройства.</span><span class="sxs-lookup"><span data-stu-id="adc60-165">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="adc60-166">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="adc60-166">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="adc60-167">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="adc60-167">DiskPaths</span></span> | <span data-ttu-id="adc60-168">Array[string]</span><span class="sxs-lookup"><span data-stu-id="adc60-168">Array[string]</span></span>  | <span data-ttu-id="adc60-169">Дисковые данные о том, что продукт установлен на устройстве.</span><span class="sxs-lookup"><span data-stu-id="adc60-169">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="adc60-170">[C: \\ Файлы программы (x86) \\ Microsoft \\ Silverlight \\ Application \\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="adc60-170">[ "C:\\Program Files (x86)\\Microsoft\\Silverlight\\Application\\silverlight.exe" ]</span></span>
<span data-ttu-id="adc60-171">EndOfSupportDate</span><span class="sxs-lookup"><span data-stu-id="adc60-171">EndOfSupportDate</span></span> | <span data-ttu-id="adc60-172">string</span><span class="sxs-lookup"><span data-stu-id="adc60-172">string</span></span> | <span data-ttu-id="adc60-173">Дата, в которой поддержка этого программного обеспечения имеет или закончится.</span><span class="sxs-lookup"><span data-stu-id="adc60-173">The date in which support for this software has or will end.</span></span> | <span data-ttu-id="adc60-174">2020-12-30</span><span class="sxs-lookup"><span data-stu-id="adc60-174">2020-12-30</span></span>
<span data-ttu-id="adc60-175">EndOfSupportStatus</span><span class="sxs-lookup"><span data-stu-id="adc60-175">EndOfSupportStatus</span></span> | <span data-ttu-id="adc60-176">string</span><span class="sxs-lookup"><span data-stu-id="adc60-176">string</span></span> | <span data-ttu-id="adc60-177">Конец состояния поддержки.</span><span class="sxs-lookup"><span data-stu-id="adc60-177">End of support status.</span></span> <span data-ttu-id="adc60-178">Может содержать эти возможные значения: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span><span class="sxs-lookup"><span data-stu-id="adc60-178">Can contain these possible values: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span></span> | <span data-ttu-id="adc60-179">Предстоящий EOS</span><span class="sxs-lookup"><span data-stu-id="adc60-179">Upcoming EOS</span></span>
<span data-ttu-id="adc60-180">Id</span><span class="sxs-lookup"><span data-stu-id="adc60-180">Id</span></span> | <span data-ttu-id="adc60-181">string</span><span class="sxs-lookup"><span data-stu-id="adc60-181">string</span></span> | <span data-ttu-id="adc60-182">Уникальный идентификатор для записи.</span><span class="sxs-lookup"><span data-stu-id="adc60-182">Unique identifier for the record.</span></span> | <span data-ttu-id="adc60-183">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="adc60-183">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="adc60-184">NumberOfWeaknesses</span><span class="sxs-lookup"><span data-stu-id="adc60-184">NumberOfWeaknesses</span></span> | <span data-ttu-id="adc60-185">int</span><span class="sxs-lookup"><span data-stu-id="adc60-185">int</span></span> | <span data-ttu-id="adc60-186">Количество недостатков этого программного обеспечения на этом устройстве</span><span class="sxs-lookup"><span data-stu-id="adc60-186">Number of weaknesses on this software on this device</span></span> | <span data-ttu-id="adc60-187">3</span><span class="sxs-lookup"><span data-stu-id="adc60-187">3</span></span>
<span data-ttu-id="adc60-188">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="adc60-188">OSPlatform</span></span> | <span data-ttu-id="adc60-189">string</span><span class="sxs-lookup"><span data-stu-id="adc60-189">string</span></span> | <span data-ttu-id="adc60-190">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="adc60-190">Platform of the operating system running on the device.</span></span> <span data-ttu-id="adc60-191">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="adc60-191">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="adc60-192">Подробные сведения см. в материале tvm supported operating systems and platforms.</span><span class="sxs-lookup"><span data-stu-id="adc60-192">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="adc60-193">Windows10</span><span class="sxs-lookup"><span data-stu-id="adc60-193">Windows10</span></span>
<span data-ttu-id="adc60-194">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="adc60-194">RbacGroupName</span></span> | <span data-ttu-id="adc60-195">string</span><span class="sxs-lookup"><span data-stu-id="adc60-195">string</span></span> | <span data-ttu-id="adc60-196">Группа управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="adc60-196">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="adc60-197">Если это устройство не назначено какой-либо группе RBAC, значение будет "Unassigned".</span><span class="sxs-lookup"><span data-stu-id="adc60-197">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="adc60-198">Если организация не содержит групп RBAC, значение будет "Нет".</span><span class="sxs-lookup"><span data-stu-id="adc60-198">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="adc60-199">Servers</span><span class="sxs-lookup"><span data-stu-id="adc60-199">Servers</span></span>
<span data-ttu-id="adc60-200">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="adc60-200">RegistryPaths</span></span> | <span data-ttu-id="adc60-201">Array[string]</span><span class="sxs-lookup"><span data-stu-id="adc60-201">Array[string]</span></span> | <span data-ttu-id="adc60-202">Свидетельство реестра о том, что продукт установлен на устройстве.</span><span class="sxs-lookup"><span data-stu-id="adc60-202">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="adc60-203">[HKEY_LOCAL_MACHINE \\ ПРОГРАММНОЕ \\ ОБЕСПЕЧЕНИЕ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion удалить Microsoft \\ \\ Silverlight" ]</span><span class="sxs-lookup"><span data-stu-id="adc60-203">[ "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Silverlight" ]</span></span>
<span data-ttu-id="adc60-204">SoftwareFirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="adc60-204">SoftwareFirstSeenTimestamp</span></span> | <span data-ttu-id="adc60-205">string</span><span class="sxs-lookup"><span data-stu-id="adc60-205">string</span></span> | <span data-ttu-id="adc60-206">Впервые это программное обеспечение было замечено на устройстве.</span><span class="sxs-lookup"><span data-stu-id="adc60-206">The first time this software was seen on the device.</span></span> | <span data-ttu-id="adc60-207">2019-04-07 02:06:47</span><span class="sxs-lookup"><span data-stu-id="adc60-207">2019-04-07 02:06:47</span></span>
<span data-ttu-id="adc60-208">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="adc60-208">SoftwareName</span></span> | <span data-ttu-id="adc60-209">string</span><span class="sxs-lookup"><span data-stu-id="adc60-209">string</span></span> | <span data-ttu-id="adc60-210">Имя программного продукта.</span><span class="sxs-lookup"><span data-stu-id="adc60-210">Name of the software product.</span></span> | <span data-ttu-id="adc60-211">Silverlight</span><span class="sxs-lookup"><span data-stu-id="adc60-211">Silverlight</span></span>
<span data-ttu-id="adc60-212">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="adc60-212">SoftwareVendor</span></span> | <span data-ttu-id="adc60-213">string</span><span class="sxs-lookup"><span data-stu-id="adc60-213">string</span></span> | <span data-ttu-id="adc60-214">Имя поставщика программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="adc60-214">Name of the software vendor.</span></span> | <span data-ttu-id="adc60-215">Microsoft</span><span class="sxs-lookup"><span data-stu-id="adc60-215">microsoft</span></span>
<span data-ttu-id="adc60-216">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="adc60-216">SoftwareVersion</span></span> | <span data-ttu-id="adc60-217">string</span><span class="sxs-lookup"><span data-stu-id="adc60-217">string</span></span> | <span data-ttu-id="adc60-218">Номер версии программного продукта.</span><span class="sxs-lookup"><span data-stu-id="adc60-218">Version number of the software product.</span></span> | <span data-ttu-id="adc60-219">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="adc60-219">81.0.4044.138</span></span>

### <a name="16-examples"></a><span data-ttu-id="adc60-220">1.6 Примеры</span><span class="sxs-lookup"><span data-stu-id="adc60-220">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="adc60-221">Пример запроса 1.6.1</span><span class="sxs-lookup"><span data-stu-id="adc60-221">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a><span data-ttu-id="adc60-222">1.6.2 Пример ответа</span><span class="sxs-lookup"><span data-stu-id="adc60-222">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a><span data-ttu-id="adc60-223">2. Экспорт инвентаризации программного обеспечения (с помощью файлов)</span><span class="sxs-lookup"><span data-stu-id="adc60-223">2. Export software inventory assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="adc60-224">Описание метода API 2.1</span><span class="sxs-lookup"><span data-stu-id="adc60-224">2.1 API method description</span></span>

<span data-ttu-id="adc60-225">Этот ответ API содержит все данные установленного программного обеспечения на устройство.</span><span class="sxs-lookup"><span data-stu-id="adc60-225">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="adc60-226">Возвращает таблицу с записью для каждой уникальной комбинации DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span><span class="sxs-lookup"><span data-stu-id="adc60-226">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="211-limitations"></a><span data-ttu-id="adc60-227">2.1.1 Ограничения</span><span class="sxs-lookup"><span data-stu-id="adc60-227">2.1.1 Limitations</span></span>

<span data-ttu-id="adc60-228">Ограничения скорости для этого API : 5 вызовов в минуту и 20 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="adc60-228">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="adc60-229">2.2 Разрешения</span><span class="sxs-lookup"><span data-stu-id="adc60-229">2.2 Permissions</span></span>

<span data-ttu-id="adc60-230">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="adc60-230">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="adc60-231">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="adc60-231">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="adc60-232">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="adc60-232">Permission type</span></span> | <span data-ttu-id="adc60-233">Разрешение</span><span class="sxs-lookup"><span data-stu-id="adc60-233">Permission</span></span> | <span data-ttu-id="adc60-234">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="adc60-234">Permission display name</span></span>
---|---|---
<span data-ttu-id="adc60-235">Приложение</span><span class="sxs-lookup"><span data-stu-id="adc60-235">Application</span></span> | <span data-ttu-id="adc60-236">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="adc60-236">Software.Read.All</span></span> | <span data-ttu-id="adc60-237">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="adc60-237">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="adc60-238">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="adc60-238">Delegated (work or school account)</span></span> | <span data-ttu-id="adc60-239">Software.Read</span><span class="sxs-lookup"><span data-stu-id="adc60-239">Software.Read</span></span> | <span data-ttu-id="adc60-240">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="adc60-240">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="adc60-241">2.3 URL-адрес</span><span class="sxs-lookup"><span data-stu-id="adc60-241">2.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a><span data-ttu-id="adc60-242">Parameters</span><span class="sxs-lookup"><span data-stu-id="adc60-242">Parameters</span></span>

- <span data-ttu-id="adc60-243">sasValidHours — количество часов, за которые будут действительны URL-адреса загрузки (максимум 24 часа)</span><span class="sxs-lookup"><span data-stu-id="adc60-243">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="adc60-244">2.5 Свойства</span><span class="sxs-lookup"><span data-stu-id="adc60-244">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="adc60-245">Файлы являются сжатой gzip & в многолинейном формате Json.</span><span class="sxs-lookup"><span data-stu-id="adc60-245">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="adc60-246">Url-адреса загрузки действительны только в течение 3 часов.</span><span class="sxs-lookup"><span data-stu-id="adc60-246">The download URLs are only valid for 3 hours.</span></span> <span data-ttu-id="adc60-247">В противном случае можно использовать параметр.</span><span class="sxs-lookup"><span data-stu-id="adc60-247">Otherwise you can use the parameter.</span></span>
>
><span data-ttu-id="adc60-248">_ Для максимальной скорости скачивания данных можно убедиться, что вы скачиваете из того же региона Azure, в который находятся ваши данные.</span><span class="sxs-lookup"><span data-stu-id="adc60-248">_ For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>
<span data-ttu-id="adc60-249">Свойство (id)</span><span class="sxs-lookup"><span data-stu-id="adc60-249">Property (id)</span></span> | <span data-ttu-id="adc60-250">Тип данных</span><span class="sxs-lookup"><span data-stu-id="adc60-250">Data type</span></span> | <span data-ttu-id="adc60-251">Описание</span><span class="sxs-lookup"><span data-stu-id="adc60-251">Description</span></span> | <span data-ttu-id="adc60-252">Пример возвращенного значения</span><span class="sxs-lookup"><span data-stu-id="adc60-252">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="adc60-253">Экспорт файлов</span><span class="sxs-lookup"><span data-stu-id="adc60-253">Export files</span></span> | <span data-ttu-id="adc60-254">строка \[ массива\]</span><span class="sxs-lookup"><span data-stu-id="adc60-254">array\[string\]</span></span> | <span data-ttu-id="adc60-255">Список загрузок URL-адресов для файлов с текущим снимком организации</span><span class="sxs-lookup"><span data-stu-id="adc60-255">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="adc60-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="adc60-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="adc60-257">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="adc60-257">GeneratedTime</span></span> | <span data-ttu-id="adc60-258">string</span><span class="sxs-lookup"><span data-stu-id="adc60-258">string</span></span> | <span data-ttu-id="adc60-259">Время, за которое был создан экспорт.</span><span class="sxs-lookup"><span data-stu-id="adc60-259">The time that the export was generated.</span></span> | <span data-ttu-id="adc60-260">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="adc60-260">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="adc60-261">2.6 Примеры</span><span class="sxs-lookup"><span data-stu-id="adc60-261">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="adc60-262">Пример запроса 2.6.1</span><span class="sxs-lookup"><span data-stu-id="adc60-262">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a><span data-ttu-id="adc60-263">2.6.2 Пример ответа</span><span class="sxs-lookup"><span data-stu-id="adc60-263">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="adc60-264">См. также</span><span class="sxs-lookup"><span data-stu-id="adc60-264">See also</span></span>

- [<span data-ttu-id="adc60-265">Методы и свойства экспортной оценки на устройство</span><span class="sxs-lookup"><span data-stu-id="adc60-265">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="adc60-266">Экспорт безопасной оценки конфигурации на устройство</span><span class="sxs-lookup"><span data-stu-id="adc60-266">Export secure configuration assessment per device</span></span>](get-assessmnt-secure-cfg.md)

- [<span data-ttu-id="adc60-267">Экспорт оценки уязвимостей программного обеспечения на устройство</span><span class="sxs-lookup"><span data-stu-id="adc60-267">Export software vulnerabilities assessment per device</span></span>](get-assessmnt-software-vulnerabilities.md)

<span data-ttu-id="adc60-268">Другие связанные</span><span class="sxs-lookup"><span data-stu-id="adc60-268">Other related</span></span>

- [<span data-ttu-id="adc60-269">Риск на основе угрозы & управление уязвимостями</span><span class="sxs-lookup"><span data-stu-id="adc60-269">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="adc60-270">Уязвимости в организации</span><span class="sxs-lookup"><span data-stu-id="adc60-270">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)