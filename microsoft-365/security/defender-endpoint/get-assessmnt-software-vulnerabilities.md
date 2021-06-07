---
title: Экспорт оценки уязвимостей программного обеспечения на устройство
description: Ответ API на устройство содержит уязвимое программное обеспечение, установленное на подверженных устройствах, а также любые известные уязвимости в этих программных продуктах. Эта таблица также содержит сведения об операционной системе, ИД CVE и сведения о серьезности уязвимости.
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
ms.openlocfilehash: 951f78ba361a12e404a5cce2071f931eab30c43f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778358"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="7852e-105">Экспорт оценки уязвимостей программного обеспечения на устройство</span><span class="sxs-lookup"><span data-stu-id="7852e-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7852e-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7852e-106">**Applies to:**</span></span>

- [<span data-ttu-id="7852e-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7852e-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7852e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7852e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7852e-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="7852e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7852e-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="7852e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="7852e-111">Возвращает все известные уязвимости программного обеспечения и их сведения для всех устройств на основе каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="7852e-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="7852e-112">Существуют различные вызовы API для получения различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="7852e-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="7852e-113">Так как объем данных может быть очень большим, их можно получить двумя способами:</span><span class="sxs-lookup"><span data-stu-id="7852e-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="7852e-114">[Оценка уязвимостей по экспорту программного обеспечения OData](#1-export-software-vulnerabilities-assessment-odata)  API передает все данные в организации в качестве ответов Json, следуя протоколу OData.</span><span class="sxs-lookup"><span data-stu-id="7852e-114">[Export software vulnerabilities assessment OData](#1-export-software-vulnerabilities-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="7852e-115">Этот метод лучше всего используется для небольших организаций с устройствами _менее 100 К._</span><span class="sxs-lookup"><span data-stu-id="7852e-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="7852e-116">Ответ paginated, поэтому вы можете использовать поле odata.nextLink из ответа, чтобы \@ получить следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="7852e-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="7852e-117">[Экспорт оценки уязвимостей программного обеспечения с помощью файлов](#2-export-software-vulnerabilities-assessment-via-files) Это решение API позволяет быстрее и более надежно тянуть большие объемы данных.</span><span class="sxs-lookup"><span data-stu-id="7852e-117">[Export software vulnerabilities assessment via files](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="7852e-118">Поэтому рекомендуется для крупных организаций с более чем 100 устройствами K.</span><span class="sxs-lookup"><span data-stu-id="7852e-118">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="7852e-119">Этот API извлекает все данные в организации в качестве файлов загрузки.</span><span class="sxs-lookup"><span data-stu-id="7852e-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="7852e-120">Ответ содержит URL-адреса для загрузки всех данных из служба хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="7852e-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="7852e-121">Этот API позволяет загружать все данные из служба хранилища Azure следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7852e-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="7852e-122">Позвоните в API, чтобы получить список загружаемых URL-адресов со всеми данными организации.</span><span class="sxs-lookup"><span data-stu-id="7852e-122">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="7852e-123">Скачайте все файлы с помощью URL-адресов загрузки и обработать данные, как вам нравится.</span><span class="sxs-lookup"><span data-stu-id="7852e-123">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="7852e-124">Собранные данные (с помощью _OData_ или _с_ помощью файлов) являются текущим снимком текущего состояния и не содержат исторических данных.</span><span class="sxs-lookup"><span data-stu-id="7852e-124">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="7852e-125">Чтобы собрать исторические данные, клиенты должны сохранять данные в собственных хранилищах данных.</span><span class="sxs-lookup"><span data-stu-id="7852e-125">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="7852e-126">Если не указано обратное, все \*\*\*\* перечисленные методы оценки экспорта являются полным экспортом и по устройству **_(также_** именуемой как **_на устройстве)._**</span><span class="sxs-lookup"><span data-stu-id="7852e-126">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-odata"></a><span data-ttu-id="7852e-127">1. Оценка уязвимостей по экспорту программного обеспечения (OData)</span><span class="sxs-lookup"><span data-stu-id="7852e-127">1. Export software vulnerabilities assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="7852e-128">Описание метода API 1.1</span><span class="sxs-lookup"><span data-stu-id="7852e-128">1.1 API method description</span></span>

<span data-ttu-id="7852e-129">Этот ответ API содержит все данные установленного программного обеспечения на устройство.</span><span class="sxs-lookup"><span data-stu-id="7852e-129">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="7852e-130">Возвращает таблицу с записью для каждой уникальной комбинации DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="7852e-130">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="limitations"></a><span data-ttu-id="7852e-131">Ограничения</span><span class="sxs-lookup"><span data-stu-id="7852e-131">Limitations</span></span>

>- <span data-ttu-id="7852e-132">Максимальный размер страницы — 200 000.</span><span class="sxs-lookup"><span data-stu-id="7852e-132">Maximum page size is 200,000.</span></span>
>
>- <span data-ttu-id="7852e-133">Ограничения скорости для этого API : 30 вызовов в минуту и 1000 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="7852e-133">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="7852e-134">1.2 Разрешения</span><span class="sxs-lookup"><span data-stu-id="7852e-134">1.2 Permissions</span></span>

<span data-ttu-id="7852e-135">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="7852e-135">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7852e-136">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="7852e-136">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="7852e-137">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="7852e-137">Permission type</span></span> | <span data-ttu-id="7852e-138">Разрешение</span><span class="sxs-lookup"><span data-stu-id="7852e-138">Permission</span></span> | <span data-ttu-id="7852e-139">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="7852e-139">Permission display name</span></span>
---|---|---
<span data-ttu-id="7852e-140">Приложение</span><span class="sxs-lookup"><span data-stu-id="7852e-140">Application</span></span> | <span data-ttu-id="7852e-141">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="7852e-141">Vulnerability.Read.All</span></span> | <span data-ttu-id="7852e-142">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="7852e-142">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="7852e-143">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="7852e-143">Delegated (work or school account)</span></span> | <span data-ttu-id="7852e-144">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="7852e-144">Vulnerability.Read</span></span> | <span data-ttu-id="7852e-145">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="7852e-145">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="7852e-146">1.3 URL-адрес</span><span class="sxs-lookup"><span data-stu-id="7852e-146">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="7852e-147">1.4 Параметры</span><span class="sxs-lookup"><span data-stu-id="7852e-147">1.4 Parameters</span></span>

- <span data-ttu-id="7852e-148">pageSize (по умолчанию = 50 000) — количество результатов в ответе</span><span class="sxs-lookup"><span data-stu-id="7852e-148">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="7852e-149">$top — количество возвращаемого результата (не возвращает @odata.nextLink и, следовательно, не вытягивает все данные)</span><span class="sxs-lookup"><span data-stu-id="7852e-149">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="7852e-150">1.5 Свойства</span><span class="sxs-lookup"><span data-stu-id="7852e-150">1.5 Properties</span></span>
>
>[!Note]
>
>- <span data-ttu-id="7852e-151">Каждая запись — это примерно 1KB данных.</span><span class="sxs-lookup"><span data-stu-id="7852e-151">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="7852e-152">Это следует учитывать при выборе правильного параметра PageSize для вас.</span><span class="sxs-lookup"><span data-stu-id="7852e-152">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="7852e-153">Некоторые дополнительные столбцы могут быть возвращены в ответе.</span><span class="sxs-lookup"><span data-stu-id="7852e-153">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="7852e-154">Эти столбцы являются временными и могут быть удалены, используйте только задокументированные столбцы.</span><span class="sxs-lookup"><span data-stu-id="7852e-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="7852e-155">Свойства, определенные в следующей таблице, перечислены в алфавитном порядке по ID свойства.</span><span class="sxs-lookup"><span data-stu-id="7852e-155">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="7852e-156">При запуске этого API результат не обязательно возвращается в том же порядке, который указан в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="7852e-156">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>

<span data-ttu-id="7852e-157">Свойство (ID)</span><span class="sxs-lookup"><span data-stu-id="7852e-157">Property (ID)</span></span> | <span data-ttu-id="7852e-158">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7852e-158">Data type</span></span> | <span data-ttu-id="7852e-159">Описание</span><span class="sxs-lookup"><span data-stu-id="7852e-159">Description</span></span> | <span data-ttu-id="7852e-160">Пример возвращенного значения</span><span class="sxs-lookup"><span data-stu-id="7852e-160">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="7852e-161">CveId</span><span class="sxs-lookup"><span data-stu-id="7852e-161">CveId</span></span> | <span data-ttu-id="7852e-162">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-162">string</span></span> | <span data-ttu-id="7852e-163">Уникальный идентификатор, присвоенный уязвимости безопасности в системе Common Vulnerabilities and Exposures (CVE).</span><span class="sxs-lookup"><span data-stu-id="7852e-163">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="7852e-164">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="7852e-164">CVE-2020-15992</span></span>
<span data-ttu-id="7852e-165">CvssScore</span><span class="sxs-lookup"><span data-stu-id="7852e-165">CvssScore</span></span> | <span data-ttu-id="7852e-166">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-166">string</span></span> | <span data-ttu-id="7852e-167">Оценка CVSS CVE.</span><span class="sxs-lookup"><span data-stu-id="7852e-167">The CVSS score of the CVE.</span></span> | <span data-ttu-id="7852e-168">6.2</span><span class="sxs-lookup"><span data-stu-id="7852e-168">6.2</span></span>
<span data-ttu-id="7852e-169">DeviceId</span><span class="sxs-lookup"><span data-stu-id="7852e-169">DeviceId</span></span> | <span data-ttu-id="7852e-170">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-170">string</span></span> | <span data-ttu-id="7852e-171">Уникальный идентификатор устройства в службе.</span><span class="sxs-lookup"><span data-stu-id="7852e-171">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="7852e-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="7852e-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="7852e-173">DeviceName</span><span class="sxs-lookup"><span data-stu-id="7852e-173">DeviceName</span></span> | <span data-ttu-id="7852e-174">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-174">string</span></span> | <span data-ttu-id="7852e-175">Полное доменное имя (FQDN) устройства.</span><span class="sxs-lookup"><span data-stu-id="7852e-175">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="7852e-176">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7852e-176">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="7852e-177">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="7852e-177">DiskPaths</span></span>  | <span data-ttu-id="7852e-178">Строка \[ Array\]</span><span class="sxs-lookup"><span data-stu-id="7852e-178">Array\[string\]</span></span> | <span data-ttu-id="7852e-179">Дисковые данные о том, что продукт установлен на устройстве.</span><span class="sxs-lookup"><span data-stu-id="7852e-179">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="7852e-180">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="7852e-180">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="7852e-181">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="7852e-181">ExploitabilityLevel</span></span> | <span data-ttu-id="7852e-182">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-182">string</span></span> | <span data-ttu-id="7852e-183">Уровень эксплуатации этой уязвимости (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="7852e-183">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="7852e-184">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="7852e-184">ExploitIsInKit</span></span>
<span data-ttu-id="7852e-185">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="7852e-185">FirstSeenTimestamp</span></span> | <span data-ttu-id="7852e-186">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-186">string</span></span> | <span data-ttu-id="7852e-187">Впервые CVE этого продукта был замечен на устройстве.</span><span class="sxs-lookup"><span data-stu-id="7852e-187">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="7852e-188">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="7852e-188">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="7852e-189">Id</span><span class="sxs-lookup"><span data-stu-id="7852e-189">Id</span></span> | <span data-ttu-id="7852e-190">string</span><span class="sxs-lookup"><span data-stu-id="7852e-190">string</span></span> | <span data-ttu-id="7852e-191">Уникальный идентификатор для записи.</span><span class="sxs-lookup"><span data-stu-id="7852e-191">Unique identifier for the record.</span></span> | <span data-ttu-id="7852e-192">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="7852e-192">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="7852e-193">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="7852e-193">LastSeenTimestamp</span></span> | <span data-ttu-id="7852e-194">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-194">string</span></span> | <span data-ttu-id="7852e-195">Последний раз CVE был замечен на устройстве.</span><span class="sxs-lookup"><span data-stu-id="7852e-195">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="7852e-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="7852e-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="7852e-197">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="7852e-197">OSPlatform</span></span> | <span data-ttu-id="7852e-198">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-198">string</span></span> | <span data-ttu-id="7852e-199">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="7852e-199">Platform of the operating system running on the device.</span></span> <span data-ttu-id="7852e-200">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="7852e-200">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="7852e-201">Подробные сведения см. в материале tvm supported operating systems and platforms.</span><span class="sxs-lookup"><span data-stu-id="7852e-201">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="7852e-202">Windows10</span><span class="sxs-lookup"><span data-stu-id="7852e-202">Windows10</span></span>
<span data-ttu-id="7852e-203">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="7852e-203">RbacGroupName</span></span>  | <span data-ttu-id="7852e-204">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-204">string</span></span> | <span data-ttu-id="7852e-205">Группа управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="7852e-205">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="7852e-206">Если это устройство не назначено какой-либо группе RBAC, значение будет "Unassigned".</span><span class="sxs-lookup"><span data-stu-id="7852e-206">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="7852e-207">Если организация не содержит групп RBAC, значение будет "Нет".</span><span class="sxs-lookup"><span data-stu-id="7852e-207">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="7852e-208">Servers</span><span class="sxs-lookup"><span data-stu-id="7852e-208">Servers</span></span>
<span data-ttu-id="7852e-209">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="7852e-209">RecommendationReference</span></span> | <span data-ttu-id="7852e-210">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-210">string</span></span> | <span data-ttu-id="7852e-211">Ссылка на номер рекомендации, связанный с этим программным обеспечением.</span><span class="sxs-lookup"><span data-stu-id="7852e-211">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="7852e-212">va-_-microsoft-silverlight_</span><span class="sxs-lookup"><span data-stu-id="7852e-212">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="7852e-213">RecommendedSecurityUpdate (необязательный)</span><span class="sxs-lookup"><span data-stu-id="7852e-213">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="7852e-214">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-214">string</span></span> | <span data-ttu-id="7852e-215">Имя или описание обновления безопасности, предоставляемого поставщиком программного обеспечения для устранения уязвимости.</span><span class="sxs-lookup"><span data-stu-id="7852e-215">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="7852e-216">Обновления безопасности за апрель 2020 г.</span><span class="sxs-lookup"><span data-stu-id="7852e-216">April 2020 Security Updates</span></span>
<span data-ttu-id="7852e-217">RecommendedSecurityUpdateId (необязательный)</span><span class="sxs-lookup"><span data-stu-id="7852e-217">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="7852e-218">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-218">string</span></span> | <span data-ttu-id="7852e-219">Идентификатор применимых обновлений или идентификаторов безопасности для соответствующих статей руководства или базы знаний (KB).</span><span class="sxs-lookup"><span data-stu-id="7852e-219">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="7852e-220">4550961</span><span class="sxs-lookup"><span data-stu-id="7852e-220">4550961</span></span>
<span data-ttu-id="7852e-221">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="7852e-221">RegistryPaths</span></span>  | <span data-ttu-id="7852e-222">Строка \[ Array\]</span><span class="sxs-lookup"><span data-stu-id="7852e-222">Array\[string\]</span></span> | <span data-ttu-id="7852e-223">Свидетельство реестра о том, что продукт установлен на устройстве.</span><span class="sxs-lookup"><span data-stu-id="7852e-223">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="7852e-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="7852e-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="7852e-225">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="7852e-225">SoftwareName</span></span> | <span data-ttu-id="7852e-226">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-226">string</span></span> | <span data-ttu-id="7852e-227">Имя программного продукта.</span><span class="sxs-lookup"><span data-stu-id="7852e-227">Name of the software product.</span></span> | <span data-ttu-id="7852e-228">chrome</span><span class="sxs-lookup"><span data-stu-id="7852e-228">chrome</span></span>
<span data-ttu-id="7852e-229">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="7852e-229">SoftwareVendor</span></span> | <span data-ttu-id="7852e-230">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-230">string</span></span> | <span data-ttu-id="7852e-231">Имя поставщика программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="7852e-231">Name of the software vendor.</span></span> | <span data-ttu-id="7852e-232">Google</span><span class="sxs-lookup"><span data-stu-id="7852e-232">google</span></span>
<span data-ttu-id="7852e-233">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="7852e-233">SoftwareVersion</span></span> | <span data-ttu-id="7852e-234">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-234">string</span></span> | <span data-ttu-id="7852e-235">Номер версии программного продукта.</span><span class="sxs-lookup"><span data-stu-id="7852e-235">Version number of the software product.</span></span> | <span data-ttu-id="7852e-236">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="7852e-236">81.0.4044.138</span></span>
<span data-ttu-id="7852e-237">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="7852e-237">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="7852e-238">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-238">string</span></span> | <span data-ttu-id="7852e-239">Уровень серьезности, присвоенный уязвимости безопасности на основе показателей CVSS и динамических факторов, влияющих на ландшафт угроз.</span><span class="sxs-lookup"><span data-stu-id="7852e-239">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="7852e-240">Средний</span><span class="sxs-lookup"><span data-stu-id="7852e-240">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="7852e-241">1.6 Примеры</span><span class="sxs-lookup"><span data-stu-id="7852e-241">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="7852e-242">Пример запроса 1.6.1</span><span class="sxs-lookup"><span data-stu-id="7852e-242">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="7852e-243">1.6.2 Пример ответа</span><span class="sxs-lookup"><span data-stu-id="7852e-243">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="7852e-244">2. Экспорт оценки уязвимостей программного обеспечения (с помощью файлов)</span><span class="sxs-lookup"><span data-stu-id="7852e-244">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="7852e-245">Описание метода API 2.1</span><span class="sxs-lookup"><span data-stu-id="7852e-245">2.1 API method description</span></span>

<span data-ttu-id="7852e-246">Этот ответ API содержит все данные установленного программного обеспечения на устройство.</span><span class="sxs-lookup"><span data-stu-id="7852e-246">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="7852e-247">Возвращает таблицу с записью для каждой уникальной комбинации DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="7852e-247">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="7852e-248">2.1.2 Ограничения</span><span class="sxs-lookup"><span data-stu-id="7852e-248">2.1.2 Limitations</span></span>

<span data-ttu-id="7852e-249">Ограничения скорости для этого API : 5 вызовов в минуту и 20 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="7852e-249">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="7852e-250">2.2 Разрешения</span><span class="sxs-lookup"><span data-stu-id="7852e-250">2.2 Permissions</span></span>

<span data-ttu-id="7852e-251">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="7852e-251">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7852e-252">Дополнительные сведения, в том числе о выборе разрешений, см. в дополнительных сведениях: [Использование API API](apis-intro.md)конечных точек Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="7852e-252">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="7852e-253">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="7852e-253">Permission type</span></span> | <span data-ttu-id="7852e-254">Разрешение</span><span class="sxs-lookup"><span data-stu-id="7852e-254">Permission</span></span> | <span data-ttu-id="7852e-255">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="7852e-255">Permission display name</span></span>
---|---|---
<span data-ttu-id="7852e-256">Приложение</span><span class="sxs-lookup"><span data-stu-id="7852e-256">Application</span></span> | <span data-ttu-id="7852e-257">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="7852e-257">Vulnerability.Read.All</span></span> | <span data-ttu-id="7852e-258">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="7852e-258">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="7852e-259">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="7852e-259">Delegated (work or school account)</span></span> | <span data-ttu-id="7852e-260">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="7852e-260">Vulnerability.Read</span></span> | <span data-ttu-id="7852e-261">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="7852e-261">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="7852e-262">2.3 URL-адрес</span><span class="sxs-lookup"><span data-stu-id="7852e-262">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="7852e-263">2.4 Параметры</span><span class="sxs-lookup"><span data-stu-id="7852e-263">2.4 Parameters</span></span>

- <span data-ttu-id="7852e-264">sasValidHours — количество часов, за которые будут действительны URL-адреса загрузки (максимум 24 часа)</span><span class="sxs-lookup"><span data-stu-id="7852e-264">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="7852e-265">2.5 Свойства</span><span class="sxs-lookup"><span data-stu-id="7852e-265">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="7852e-266">Файлы являются сжатой gzip & в многолинейном формате Json.</span><span class="sxs-lookup"><span data-stu-id="7852e-266">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="7852e-267">Url-адреса загрузки действительны только в течение 3 часов; в противном случае параметр можно использовать.</span><span class="sxs-lookup"><span data-stu-id="7852e-267">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="7852e-268">Для максимальной скорости скачивания данных можно убедиться, что вы скачиваете из того же региона Azure, в который находятся ваши данные.</span><span class="sxs-lookup"><span data-stu-id="7852e-268">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="7852e-269">Каждая запись — это примерно 1KB данных.</span><span class="sxs-lookup"><span data-stu-id="7852e-269">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="7852e-270">Это следует учитывать при выборе правильного параметра PageSize для вас.</span><span class="sxs-lookup"><span data-stu-id="7852e-270">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="7852e-271">Некоторые дополнительные столбцы могут быть возвращены в ответе.</span><span class="sxs-lookup"><span data-stu-id="7852e-271">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="7852e-272">Эти столбцы являются временными и могут быть удалены, используйте только задокументированные столбцы.</span><span class="sxs-lookup"><span data-stu-id="7852e-272">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="7852e-273">Свойство (ID)</span><span class="sxs-lookup"><span data-stu-id="7852e-273">Property (ID)</span></span> | <span data-ttu-id="7852e-274">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7852e-274">Data type</span></span> | <span data-ttu-id="7852e-275">Описание</span><span class="sxs-lookup"><span data-stu-id="7852e-275">Description</span></span> | <span data-ttu-id="7852e-276">Пример возвращенного значения</span><span class="sxs-lookup"><span data-stu-id="7852e-276">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="7852e-277">Экспорт файлов</span><span class="sxs-lookup"><span data-stu-id="7852e-277">Export files</span></span> | <span data-ttu-id="7852e-278">строка \[ массива\]</span><span class="sxs-lookup"><span data-stu-id="7852e-278">array\[string\]</span></span>  | <span data-ttu-id="7852e-279">Список загрузок URL-адресов для файлов с текущим снимком организации.</span><span class="sxs-lookup"><span data-stu-id="7852e-279">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="7852e-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="7852e-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="7852e-281">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="7852e-281">GeneratedTime</span></span> | <span data-ttu-id="7852e-282">Строка</span><span class="sxs-lookup"><span data-stu-id="7852e-282">string</span></span> | <span data-ttu-id="7852e-283">Время, за которое был создан экспорт.</span><span class="sxs-lookup"><span data-stu-id="7852e-283">The time that the export was generated.</span></span> | <span data-ttu-id="7852e-284">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="7852e-284">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="7852e-285">2.6 Примеры</span><span class="sxs-lookup"><span data-stu-id="7852e-285">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="7852e-286">Пример запроса 2.6.1</span><span class="sxs-lookup"><span data-stu-id="7852e-286">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="7852e-287">2.6.2 Пример ответа</span><span class="sxs-lookup"><span data-stu-id="7852e-287">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="7852e-288">См. также</span><span class="sxs-lookup"><span data-stu-id="7852e-288">See also</span></span>

- [<span data-ttu-id="7852e-289">Методы и свойства экспортной оценки на устройство</span><span class="sxs-lookup"><span data-stu-id="7852e-289">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="7852e-290">Экспорт безопасной оценки конфигурации на устройство</span><span class="sxs-lookup"><span data-stu-id="7852e-290">Export secure configuration assessment per device</span></span>](get-assessmnt-secure-cfg.md)

- [<span data-ttu-id="7852e-291">Экспорт оценки инвентаризации программного обеспечения на устройство</span><span class="sxs-lookup"><span data-stu-id="7852e-291">Export software inventory assessment per device</span></span>](get-assessmnt-software-inventory.md)

<span data-ttu-id="7852e-292">Другие связанные</span><span class="sxs-lookup"><span data-stu-id="7852e-292">Other related</span></span>

- [<span data-ttu-id="7852e-293">Риск на основе угрозы & управление уязвимостями</span><span class="sxs-lookup"><span data-stu-id="7852e-293">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="7852e-294">Уязвимости в организации</span><span class="sxs-lookup"><span data-stu-id="7852e-294">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
