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
ms.openlocfilehash: 87fb5c62b520168a686cc0b95a321becdd4656ba
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "53052967"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="c19b3-105">Экспорт оценки уязвимостей программного обеспечения на устройство</span><span class="sxs-lookup"><span data-stu-id="c19b3-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c19b3-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c19b3-106">**Applies to:**</span></span>

- [<span data-ttu-id="c19b3-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c19b3-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c19b3-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c19b3-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c19b3-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c19b3-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c19b3-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c19b3-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="c19b3-111">Возвращает все известные уязвимости программного обеспечения и их сведения для всех устройств на основе каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="c19b3-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="c19b3-112">Существуют различные вызовы API для получения различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="c19b3-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="c19b3-113">Так как объем данных может быть очень большим, их можно получить двумя способами:</span><span class="sxs-lookup"><span data-stu-id="c19b3-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

1. <span data-ttu-id="c19b3-114">[Оценка уязвимостей по экспорту **программного обеспечения JSON**](#1-export-software-vulnerabilities-assessment-json-response)  API извлекет все данные в организации в качестве ответов Json.</span><span class="sxs-lookup"><span data-stu-id="c19b3-114">[Export software vulnerabilities assessment **JSON response**](#1-export-software-vulnerabilities-assessment-json-response)  The API pulls all data in your organization as Json responses.</span></span> <span data-ttu-id="c19b3-115">Этот метод лучше всего используется для небольших организаций с устройствами _менее 100 К._</span><span class="sxs-lookup"><span data-stu-id="c19b3-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="c19b3-116">Ответ paginated, поэтому вы можете использовать поле odata.nextLink из ответа, чтобы \@ получить следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="c19b3-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

2. <span data-ttu-id="c19b3-117">[Экспорт оценки уязвимостей программного **обеспечения с помощью файлов**](#2-export-software-vulnerabilities-assessment-via-files) Это решение API позволяет быстрее и более надежно тянуть большие объемы данных.</span><span class="sxs-lookup"><span data-stu-id="c19b3-117">[Export software vulnerabilities assessment **via files**](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="c19b3-118">Виа-файлы рекомендуется использовать для крупных организаций с более чем 100 устройствами K.</span><span class="sxs-lookup"><span data-stu-id="c19b3-118">Via-files is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="c19b3-119">Этот API извлекает все данные в организации в качестве файлов загрузки.</span><span class="sxs-lookup"><span data-stu-id="c19b3-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="c19b3-120">Ответ содержит URL-адреса для загрузки всех данных из служба хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="c19b3-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="c19b3-121">Этот API позволяет загружать все данные из служба хранилища Azure следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c19b3-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

   - <span data-ttu-id="c19b3-122">Позвоните в API, чтобы получить список загружаемых URL-адресов со всеми данными организации.</span><span class="sxs-lookup"><span data-stu-id="c19b3-122">Call the API to get a list of download URLs with all your organization data.</span></span>

   - <span data-ttu-id="c19b3-123">Скачайте все файлы с помощью URL-адресов загрузки и обработать данные, как вам нравится.</span><span class="sxs-lookup"><span data-stu-id="c19b3-123">Download all the files using the download URLs and process the data as you like.</span></span>

3. <span data-ttu-id="c19b3-124">[Оценка уязвимостей **JSON**](#3-delta-export-software-vulnerabilities-assessment-json-response) по оценке уязвимостей экспортного программного обеспечения Delta  Возвращает таблицу с записью для каждого уникального сочетания: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId и EventTimestamp.</span><span class="sxs-lookup"><span data-stu-id="c19b3-124">[Delta export software vulnerabilities assessment **JSON response**](#3-delta-export-software-vulnerabilities-assessment-json-response)  Returns a table with an entry for every unique combination of: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId, and EventTimestamp.</span></span>
<span data-ttu-id="c19b3-125">API извлекет данные в организации в качестве ответов Json.</span><span class="sxs-lookup"><span data-stu-id="c19b3-125">The API pulls data in your organization as Json responses.</span></span> <span data-ttu-id="c19b3-126">Ответ paginated, поэтому вы можете использовать поле @odata.nextLink из ответа, чтобы получить следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="c19b3-126">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <br><br> <span data-ttu-id="c19b3-127">В отличие от полной "оценки уязвимостей программного обеспечения (ответ JSON)", которая используется для получения полного снимка оценки уязвимостей программного обеспечения вашей организации с помощью устройства, вызов API экспорта дельты используется для получения только изменений, которые произошли между выбранной датой и текущей датой (вызов API delta).</span><span class="sxs-lookup"><span data-stu-id="c19b3-127">Unlike the full "software vulnerabilities assessment (JSON response)" - which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device - the delta export API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="c19b3-128">Вместо того чтобы получать полный экспорт с большим объемом данных каждый раз, вы получите только конкретные сведения о новых, исправленных и обновленных уязвимостях.</span><span class="sxs-lookup"><span data-stu-id="c19b3-128">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="c19b3-129">Вызов API API API ответов JSON экспорта Delta также можно использовать для вычисления различных KPI, таких как "сколько уязвимостей было исправлено?"</span><span class="sxs-lookup"><span data-stu-id="c19b3-129">Delta export JSON response API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="c19b3-130">или "сколько новых уязвимостей было добавлено в мою организацию?"</span><span class="sxs-lookup"><span data-stu-id="c19b3-130">or “how many new vulnerabilities were added to my organization?”</span></span> <br><br> <span data-ttu-id="c19b3-131">Так как вызов API API ответов JSON экспорта Delta для уязвимостей программного обеспечения возвращает данные только для целевого диапазона дат, он не считается _полным экспортом._</span><span class="sxs-lookup"><span data-stu-id="c19b3-131">Because the Delta export JSON response API call for software vulnerabilities returns data for only a targeted date range, it is not considered a _full export_.</span></span>

<span data-ttu-id="c19b3-132">Собранные данные (с помощью ответа _Json_ или с помощью _файлов)_ являются текущим снимком текущего состояния и не содержат исторических данных.</span><span class="sxs-lookup"><span data-stu-id="c19b3-132">Data that is collected (using either _Json response_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="c19b3-133">Чтобы собрать исторические данные, клиенты должны сохранять данные в собственных хранилищах данных.</span><span class="sxs-lookup"><span data-stu-id="c19b3-133">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="c19b3-134">Если не указано обратное, все \*\*\*\* перечисленные методы оценки экспорта являются полным экспортом и по устройству **_(также_** именуемой как **_на устройстве)._**</span><span class="sxs-lookup"><span data-stu-id="c19b3-134">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-json-response"></a><span data-ttu-id="c19b3-135">1. Оценка уязвимостей по экспорту программного обеспечения (ответ JSON)</span><span class="sxs-lookup"><span data-stu-id="c19b3-135">1. Export software vulnerabilities assessment (JSON response)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="c19b3-136">Описание метода API 1.1</span><span class="sxs-lookup"><span data-stu-id="c19b3-136">1.1 API method description</span></span>

<span data-ttu-id="c19b3-137">Этот ответ API содержит все данные установленного программного обеспечения на устройство.</span><span class="sxs-lookup"><span data-stu-id="c19b3-137">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="c19b3-138">Возвращает таблицу с записью для каждой уникальной комбинации DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="c19b3-138">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="c19b3-139">1.1.1 Ограничения</span><span class="sxs-lookup"><span data-stu-id="c19b3-139">1.1.1 Limitations</span></span>

- <span data-ttu-id="c19b3-140">Максимальный размер страницы — 200 000.</span><span class="sxs-lookup"><span data-stu-id="c19b3-140">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="c19b3-141">Ограничения скорости для этого API : 30 вызовов в минуту и 1000 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="c19b3-141">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="c19b3-142">1.2 Разрешения</span><span class="sxs-lookup"><span data-stu-id="c19b3-142">1.2 Permissions</span></span>

<span data-ttu-id="c19b3-143">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="c19b3-143">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c19b3-144">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c19b3-144">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="c19b3-145">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="c19b3-145">Permission type</span></span> | <span data-ttu-id="c19b3-146">Разрешение</span><span class="sxs-lookup"><span data-stu-id="c19b3-146">Permission</span></span> | <span data-ttu-id="c19b3-147">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="c19b3-147">Permission display name</span></span>
---|---|---
<span data-ttu-id="c19b3-148">Приложение</span><span class="sxs-lookup"><span data-stu-id="c19b3-148">Application</span></span> | <span data-ttu-id="c19b3-149">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="c19b3-149">Vulnerability.Read.All</span></span> | <span data-ttu-id="c19b3-150">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="c19b3-150">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="c19b3-151">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="c19b3-151">Delegated (work or school account)</span></span> | <span data-ttu-id="c19b3-152">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="c19b3-152">Vulnerability.Read</span></span> | <span data-ttu-id="c19b3-153">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="c19b3-153">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="c19b3-154">1.3 URL-адрес</span><span class="sxs-lookup"><span data-stu-id="c19b3-154">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="c19b3-155">1.4 Параметры</span><span class="sxs-lookup"><span data-stu-id="c19b3-155">1.4 Parameters</span></span>

- <span data-ttu-id="c19b3-156">pageSize (по умолчанию = 50 000) — количество результатов в ответе</span><span class="sxs-lookup"><span data-stu-id="c19b3-156">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="c19b3-157">$top — количество возвращаемого результата (не возвращает @odata.nextLink и, следовательно, не вытягивает все данные)</span><span class="sxs-lookup"><span data-stu-id="c19b3-157">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="c19b3-158">1.5 Свойства</span><span class="sxs-lookup"><span data-stu-id="c19b3-158">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="c19b3-159">Каждая запись — это примерно 1 КБ данных.</span><span class="sxs-lookup"><span data-stu-id="c19b3-159">Each record is approximately 1 KB of data.</span></span> <span data-ttu-id="c19b3-160">Это следует учитывать при выборе правильного параметра PageSize для вас.</span><span class="sxs-lookup"><span data-stu-id="c19b3-160">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="c19b3-161">Некоторые дополнительные столбцы могут быть возвращены в ответе.</span><span class="sxs-lookup"><span data-stu-id="c19b3-161">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="c19b3-162">Эти столбцы являются временными и могут быть удалены, используйте только задокументированные столбцы.</span><span class="sxs-lookup"><span data-stu-id="c19b3-162">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="c19b3-163">Свойства, определенные в следующей таблице, перечислены в алфавитном порядке по ID свойства.</span><span class="sxs-lookup"><span data-stu-id="c19b3-163">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="c19b3-164">При запуске этого API результат не обязательно возвращается в том же порядке, который указан в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="c19b3-164">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>

<br/>

<span data-ttu-id="c19b3-165">Свойство (ID)</span><span class="sxs-lookup"><span data-stu-id="c19b3-165">Property (ID)</span></span> | <span data-ttu-id="c19b3-166">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c19b3-166">Data type</span></span> | <span data-ttu-id="c19b3-167">Описание</span><span class="sxs-lookup"><span data-stu-id="c19b3-167">Description</span></span> | <span data-ttu-id="c19b3-168">Пример возвращенного значения</span><span class="sxs-lookup"><span data-stu-id="c19b3-168">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="c19b3-169">CveId</span><span class="sxs-lookup"><span data-stu-id="c19b3-169">CveId</span></span> | <span data-ttu-id="c19b3-170">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-170">string</span></span> | <span data-ttu-id="c19b3-171">Уникальный идентификатор, присвоенный уязвимости безопасности в системе Common Vulnerabilities and Exposures (CVE).</span><span class="sxs-lookup"><span data-stu-id="c19b3-171">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="c19b3-172">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="c19b3-172">CVE-2020-15992</span></span>
<span data-ttu-id="c19b3-173">CvssScore</span><span class="sxs-lookup"><span data-stu-id="c19b3-173">CvssScore</span></span> | <span data-ttu-id="c19b3-174">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-174">string</span></span> | <span data-ttu-id="c19b3-175">Оценка CVSS CVE.</span><span class="sxs-lookup"><span data-stu-id="c19b3-175">The CVSS score of the CVE.</span></span> | <span data-ttu-id="c19b3-176">6.2</span><span class="sxs-lookup"><span data-stu-id="c19b3-176">6.2</span></span>
<span data-ttu-id="c19b3-177">DeviceId</span><span class="sxs-lookup"><span data-stu-id="c19b3-177">DeviceId</span></span> | <span data-ttu-id="c19b3-178">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-178">string</span></span> | <span data-ttu-id="c19b3-179">Уникальный идентификатор устройства в службе.</span><span class="sxs-lookup"><span data-stu-id="c19b3-179">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="c19b3-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="c19b3-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="c19b3-181">DeviceName</span><span class="sxs-lookup"><span data-stu-id="c19b3-181">DeviceName</span></span> | <span data-ttu-id="c19b3-182">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-182">string</span></span> | <span data-ttu-id="c19b3-183">Полное доменное имя (FQDN) устройства.</span><span class="sxs-lookup"><span data-stu-id="c19b3-183">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="c19b3-184">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c19b3-184">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="c19b3-185">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="c19b3-185">DiskPaths</span></span>  | <span data-ttu-id="c19b3-186">Строка \[ Array\]</span><span class="sxs-lookup"><span data-stu-id="c19b3-186">Array\[string\]</span></span> | <span data-ttu-id="c19b3-187">Дисковые данные о том, что продукт установлен на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c19b3-187">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="c19b3-188">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="c19b3-188">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="c19b3-189">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="c19b3-189">ExploitabilityLevel</span></span> | <span data-ttu-id="c19b3-190">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-190">string</span></span> | <span data-ttu-id="c19b3-191">Уровень эксплуатации этой уязвимости (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="c19b3-191">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="c19b3-192">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="c19b3-192">ExploitIsInKit</span></span>
<span data-ttu-id="c19b3-193">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="c19b3-193">FirstSeenTimestamp</span></span> | <span data-ttu-id="c19b3-194">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-194">string</span></span> | <span data-ttu-id="c19b3-195">Впервые CVE этого продукта был замечен на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c19b3-195">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="c19b3-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="c19b3-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="c19b3-197">Id</span><span class="sxs-lookup"><span data-stu-id="c19b3-197">Id</span></span> | <span data-ttu-id="c19b3-198">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-198">string</span></span> | <span data-ttu-id="c19b3-199">Уникальный идентификатор для записи.</span><span class="sxs-lookup"><span data-stu-id="c19b3-199">Unique identifier for the record.</span></span> | <span data-ttu-id="c19b3-200">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="c19b3-200">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="c19b3-201">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="c19b3-201">LastSeenTimestamp</span></span> | <span data-ttu-id="c19b3-202">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-202">string</span></span> | <span data-ttu-id="c19b3-203">Последний раз CVE был замечен на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c19b3-203">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="c19b3-204">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="c19b3-204">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="c19b3-205">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="c19b3-205">OSPlatform</span></span> | <span data-ttu-id="c19b3-206">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-206">string</span></span> | <span data-ttu-id="c19b3-207">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c19b3-207">Platform of the operating system running on the device.</span></span> <span data-ttu-id="c19b3-208">Это свойство указывает на определенные операционные системы, в том числе варианты в одной семье, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="c19b3-208">This property indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="c19b3-209">Подробные сведения см. в материале tvm supported operating systems and platforms.</span><span class="sxs-lookup"><span data-stu-id="c19b3-209">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="c19b3-210">Windows10</span><span class="sxs-lookup"><span data-stu-id="c19b3-210">Windows10</span></span>
<span data-ttu-id="c19b3-211">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="c19b3-211">RbacGroupName</span></span>  | <span data-ttu-id="c19b3-212">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-212">string</span></span> | <span data-ttu-id="c19b3-213">Группа управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="c19b3-213">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="c19b3-214">Если это устройство не назначено какой-либо группе RBAC, значение будет "Unassigned".</span><span class="sxs-lookup"><span data-stu-id="c19b3-214">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="c19b3-215">Если организация не содержит групп RBAC, значение будет "Нет".</span><span class="sxs-lookup"><span data-stu-id="c19b3-215">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="c19b3-216">Servers</span><span class="sxs-lookup"><span data-stu-id="c19b3-216">Servers</span></span>
<span data-ttu-id="c19b3-217">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="c19b3-217">RecommendationReference</span></span> | <span data-ttu-id="c19b3-218">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-218">string</span></span> | <span data-ttu-id="c19b3-219">Ссылка на номер рекомендации, связанный с этим программным обеспечением.</span><span class="sxs-lookup"><span data-stu-id="c19b3-219">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="c19b3-220">va-_-microsoft-silverlight_</span><span class="sxs-lookup"><span data-stu-id="c19b3-220">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="c19b3-221">RecommendedSecurityUpdate (необязательный)</span><span class="sxs-lookup"><span data-stu-id="c19b3-221">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="c19b3-222">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-222">string</span></span> | <span data-ttu-id="c19b3-223">Имя или описание обновления безопасности, предоставляемого поставщиком программного обеспечения для устранения уязвимости.</span><span class="sxs-lookup"><span data-stu-id="c19b3-223">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="c19b3-224">Обновления безопасности за апрель 2020 г.</span><span class="sxs-lookup"><span data-stu-id="c19b3-224">April 2020 Security Updates</span></span>
<span data-ttu-id="c19b3-225">RecommendedSecurityUpdateId (необязательный)</span><span class="sxs-lookup"><span data-stu-id="c19b3-225">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="c19b3-226">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-226">string</span></span> | <span data-ttu-id="c19b3-227">Идентификатор применимых обновлений или идентификаторов безопасности для соответствующих статей руководства или базы знаний (KB).</span><span class="sxs-lookup"><span data-stu-id="c19b3-227">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="c19b3-228">4550961</span><span class="sxs-lookup"><span data-stu-id="c19b3-228">4550961</span></span>
<span data-ttu-id="c19b3-229">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="c19b3-229">RegistryPaths</span></span>  | <span data-ttu-id="c19b3-230">Строка \[ Array\]</span><span class="sxs-lookup"><span data-stu-id="c19b3-230">Array\[string\]</span></span> | <span data-ttu-id="c19b3-231">Свидетельство реестра о том, что продукт установлен на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c19b3-231">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="c19b3-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="c19b3-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="c19b3-233">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="c19b3-233">SoftwareName</span></span> | <span data-ttu-id="c19b3-234">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-234">string</span></span> | <span data-ttu-id="c19b3-235">Имя программного продукта.</span><span class="sxs-lookup"><span data-stu-id="c19b3-235">Name of the software product.</span></span> | <span data-ttu-id="c19b3-236">chrome</span><span class="sxs-lookup"><span data-stu-id="c19b3-236">chrome</span></span>
<span data-ttu-id="c19b3-237">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="c19b3-237">SoftwareVendor</span></span> | <span data-ttu-id="c19b3-238">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-238">string</span></span> | <span data-ttu-id="c19b3-239">Имя поставщика программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="c19b3-239">Name of the software vendor.</span></span> | <span data-ttu-id="c19b3-240">Google</span><span class="sxs-lookup"><span data-stu-id="c19b3-240">google</span></span>
<span data-ttu-id="c19b3-241">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="c19b3-241">SoftwareVersion</span></span> | <span data-ttu-id="c19b3-242">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-242">string</span></span> | <span data-ttu-id="c19b3-243">Номер версии программного продукта.</span><span class="sxs-lookup"><span data-stu-id="c19b3-243">Version number of the software product.</span></span> | <span data-ttu-id="c19b3-244">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="c19b3-244">81.0.4044.138</span></span>
<span data-ttu-id="c19b3-245">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="c19b3-245">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="c19b3-246">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-246">string</span></span> | <span data-ttu-id="c19b3-247">Уровень серьезности, присвоенный уязвимости безопасности на основе показателей CVSS и динамических факторов, влияющих на ландшафт угроз.</span><span class="sxs-lookup"><span data-stu-id="c19b3-247">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="c19b3-248">Средний</span><span class="sxs-lookup"><span data-stu-id="c19b3-248">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="c19b3-249">1.6 Примеры</span><span class="sxs-lookup"><span data-stu-id="c19b3-249">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="c19b3-250">Пример запроса 1.6.1</span><span class="sxs-lookup"><span data-stu-id="c19b3-250">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="c19b3-251">1.6.2 Пример ответа</span><span class="sxs-lookup"><span data-stu-id="c19b3-251">1.6.2 Response example</span></span>

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

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="c19b3-252">2. Экспорт оценки уязвимостей программного обеспечения (с помощью файлов)</span><span class="sxs-lookup"><span data-stu-id="c19b3-252">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="c19b3-253">Описание метода API 2.1</span><span class="sxs-lookup"><span data-stu-id="c19b3-253">2.1 API method description</span></span>

<span data-ttu-id="c19b3-254">Этот ответ API содержит все данные установленного программного обеспечения на устройство.</span><span class="sxs-lookup"><span data-stu-id="c19b3-254">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="c19b3-255">Возвращает таблицу с записью для каждой уникальной комбинации DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="c19b3-255">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="c19b3-256">2.1.2 Ограничения</span><span class="sxs-lookup"><span data-stu-id="c19b3-256">2.1.2 Limitations</span></span>

<span data-ttu-id="c19b3-257">Ограничения скорости для этого API : 5 вызовов в минуту и 20 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="c19b3-257">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="c19b3-258">2.2 Разрешения</span><span class="sxs-lookup"><span data-stu-id="c19b3-258">2.2 Permissions</span></span>

<span data-ttu-id="c19b3-259">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="c19b3-259">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c19b3-260">Дополнительные сведения, в том числе о выборе разрешений, см. в дополнительных сведениях: [Использование API API](apis-intro.md)конечных точек Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c19b3-260">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="c19b3-261">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="c19b3-261">Permission type</span></span> | <span data-ttu-id="c19b3-262">Разрешение</span><span class="sxs-lookup"><span data-stu-id="c19b3-262">Permission</span></span> | <span data-ttu-id="c19b3-263">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="c19b3-263">Permission display name</span></span>
---|---|---
<span data-ttu-id="c19b3-264">Приложение</span><span class="sxs-lookup"><span data-stu-id="c19b3-264">Application</span></span> | <span data-ttu-id="c19b3-265">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="c19b3-265">Vulnerability.Read.All</span></span> | <span data-ttu-id="c19b3-266">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="c19b3-266">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="c19b3-267">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="c19b3-267">Delegated (work or school account)</span></span> | <span data-ttu-id="c19b3-268">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="c19b3-268">Vulnerability.Read</span></span> | <span data-ttu-id="c19b3-269">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="c19b3-269">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="c19b3-270">2.3 URL-адрес</span><span class="sxs-lookup"><span data-stu-id="c19b3-270">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="c19b3-271">2.4 Параметры</span><span class="sxs-lookup"><span data-stu-id="c19b3-271">2.4 Parameters</span></span>

- <span data-ttu-id="c19b3-272">sasValidHours — количество часов, за которые будут действительны URL-адреса загрузки (максимум 24 часа)</span><span class="sxs-lookup"><span data-stu-id="c19b3-272">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="c19b3-273">2.5 Свойства</span><span class="sxs-lookup"><span data-stu-id="c19b3-273">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="c19b3-274">Файлы являются сжатой gzip & в многолинейном формате Json.</span><span class="sxs-lookup"><span data-stu-id="c19b3-274">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="c19b3-275">Url-адреса загрузки действительны только в течение 3 часов; в противном случае параметр можно использовать.</span><span class="sxs-lookup"><span data-stu-id="c19b3-275">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="c19b3-276">Для максимальной скорости скачивания данных можно убедиться, что вы скачиваете из того же региона Azure, в который находятся ваши данные.</span><span class="sxs-lookup"><span data-stu-id="c19b3-276">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="c19b3-277">Каждая запись — это примерно 1KB данных.</span><span class="sxs-lookup"><span data-stu-id="c19b3-277">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="c19b3-278">Это следует учитывать при выборе правильного параметра PageSize для вас.</span><span class="sxs-lookup"><span data-stu-id="c19b3-278">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="c19b3-279">Некоторые дополнительные столбцы могут быть возвращены в ответе.</span><span class="sxs-lookup"><span data-stu-id="c19b3-279">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="c19b3-280">Эти столбцы являются временными и могут быть удалены, используйте только задокументированные столбцы.</span><span class="sxs-lookup"><span data-stu-id="c19b3-280">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="c19b3-281">Свойство (ID)</span><span class="sxs-lookup"><span data-stu-id="c19b3-281">Property (ID)</span></span> | <span data-ttu-id="c19b3-282">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c19b3-282">Data type</span></span> | <span data-ttu-id="c19b3-283">Описание</span><span class="sxs-lookup"><span data-stu-id="c19b3-283">Description</span></span> | <span data-ttu-id="c19b3-284">Пример возвращенного значения</span><span class="sxs-lookup"><span data-stu-id="c19b3-284">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="c19b3-285">Экспорт файлов</span><span class="sxs-lookup"><span data-stu-id="c19b3-285">Export files</span></span> | <span data-ttu-id="c19b3-286">строка \[ массива\]</span><span class="sxs-lookup"><span data-stu-id="c19b3-286">array\[string\]</span></span>  | <span data-ttu-id="c19b3-287">Список загрузок URL-адресов для файлов с текущим снимком организации.</span><span class="sxs-lookup"><span data-stu-id="c19b3-287">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="c19b3-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="c19b3-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="c19b3-289">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="c19b3-289">GeneratedTime</span></span> | <span data-ttu-id="c19b3-290">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-290">string</span></span> | <span data-ttu-id="c19b3-291">Время, за которое был создан экспорт.</span><span class="sxs-lookup"><span data-stu-id="c19b3-291">The time that the export was generated.</span></span> | <span data-ttu-id="c19b3-292">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="c19b3-292">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="c19b3-293">2.6 Примеры</span><span class="sxs-lookup"><span data-stu-id="c19b3-293">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="c19b3-294">Пример запроса 2.6.1</span><span class="sxs-lookup"><span data-stu-id="c19b3-294">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="c19b3-295">2.6.2 Пример ответа</span><span class="sxs-lookup"><span data-stu-id="c19b3-295">2.6.2 Response example</span></span>

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

## <a name="3-delta-export-software-vulnerabilities-assessment-json-response"></a><span data-ttu-id="c19b3-296">3. Оценка уязвимостей экспортного программного обеспечения Delta (ответ JSON)</span><span class="sxs-lookup"><span data-stu-id="c19b3-296">3. Delta export software vulnerabilities assessment (JSON response)</span></span>

### <a name="31-api-method-description"></a><span data-ttu-id="c19b3-297">Описание метода API 3.1</span><span class="sxs-lookup"><span data-stu-id="c19b3-297">3.1 API method description</span></span>

<span data-ttu-id="c19b3-298">Возвращает таблицу с записью для каждой уникальной комбинации DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span><span class="sxs-lookup"><span data-stu-id="c19b3-298">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span></span> <span data-ttu-id="c19b3-299">API извлекет данные в организации в качестве ответов Json.</span><span class="sxs-lookup"><span data-stu-id="c19b3-299">The API pulls data in your organization as Json responses.</span></span> <span data-ttu-id="c19b3-300">Ответ paginated, поэтому вы можете использовать поле @odata.nextLink из ответа, чтобы получить следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="c19b3-300">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <span data-ttu-id="c19b3-301">В отличие от полной оценки уязвимостей программного обеспечения (ответ JSON), которая используется для получения полного снимка оценки уязвимостей программного обеспечения вашей организации с помощью устройства, вызов API API ответов JSON экспорта delta используется для получения только изменений, которые произошли между выбранной датой и текущей датой (вызов API delta).</span><span class="sxs-lookup"><span data-stu-id="c19b3-301">Unlike the full software vulnerabilities assessment (JSON response)—which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device—the delta export JSON response API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="c19b3-302">Вместо того чтобы получать полный экспорт с большим объемом данных каждый раз, вы получите только конкретные сведения о новых, исправленных и обновленных уязвимостях.</span><span class="sxs-lookup"><span data-stu-id="c19b3-302">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="c19b3-303">Вызов API API API ответов JSON экспорта Delta также можно использовать для вычисления различных KPI, таких как "сколько уязвимостей было исправлено?"</span><span class="sxs-lookup"><span data-stu-id="c19b3-303">Delta export JSON response API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="c19b3-304">или "сколько новых уязвимостей было добавлено в мою организацию?"</span><span class="sxs-lookup"><span data-stu-id="c19b3-304">or “how many new vulnerabilities were added to my organization?”</span></span>

>[!NOTE]
>
><span data-ttu-id="c19b3-305">Рекомендуется использовать полную оценку уязвимостей экспортируемого программного обеспечения по вызову API устройств по крайней мере один раз в неделю, и этот дополнительный экспорт уязвимостей программного обеспечения изменяется при вызове API устройства (delta) все остальные дни недели.</span><span class="sxs-lookup"><span data-stu-id="c19b3-305">It is highly recommended you use the full export software vulnerabilities assessment by device API call at least once a week, and this additional export software vulnerabilities changes by device (delta) API call all the other days of the week.</span></span>  <span data-ttu-id="c19b3-306">В отличие от других API ответов JSON, "дельта экспорт" не является полным экспортом.</span><span class="sxs-lookup"><span data-stu-id="c19b3-306">Unlike the other Assessments JSON response APIs, the “delta export” is not a full export.</span></span> <span data-ttu-id="c19b3-307">Экспорт дельты включает только изменения, которые произошли между выбранной датой и текущей датой (вызов API дельты).</span><span class="sxs-lookup"><span data-stu-id="c19b3-307">The delta export includes only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span>

#### <a name="311-limitations"></a><span data-ttu-id="c19b3-308">3.1.1 Ограничения</span><span class="sxs-lookup"><span data-stu-id="c19b3-308">3.1.1 Limitations</span></span>

- <span data-ttu-id="c19b3-309">Максимальный размер страницы — 200 000.</span><span class="sxs-lookup"><span data-stu-id="c19b3-309">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="c19b3-310">Параметр sinceTime имеет максимум 14 дней.</span><span class="sxs-lookup"><span data-stu-id="c19b3-310">The sinceTime parameter has a maximum of 14 days.</span></span>

- <span data-ttu-id="c19b3-311">Ограничения скорости для этого API : 30 вызовов в минуту и 1000 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="c19b3-311">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="32-permissions"></a><span data-ttu-id="c19b3-312">3.2 Разрешения</span><span class="sxs-lookup"><span data-stu-id="c19b3-312">3.2 Permissions</span></span>

<span data-ttu-id="c19b3-313">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="c19b3-313">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c19b3-314">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c19b3-314">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="c19b3-315">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="c19b3-315">Permission type</span></span> | <span data-ttu-id="c19b3-316">Разрешение</span><span class="sxs-lookup"><span data-stu-id="c19b3-316">Permission</span></span> | <span data-ttu-id="c19b3-317">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="c19b3-317">Permission display name</span></span>
---|---|---
<span data-ttu-id="c19b3-318">Приложение</span><span class="sxs-lookup"><span data-stu-id="c19b3-318">Application</span></span> | <span data-ttu-id="c19b3-319">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="c19b3-319">Vulnerability.Read.All</span></span> | <span data-ttu-id="c19b3-320">'Read Threat and Vulnerability Management vulnerability information'</span><span class="sxs-lookup"><span data-stu-id="c19b3-320">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="c19b3-321">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="c19b3-321">Delegated (work or school account)</span></span> | <span data-ttu-id="c19b3-322">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="c19b3-322">Vulnerability.Read</span></span> | <span data-ttu-id="c19b3-323">'Read Threat and Vulnerability Management vulnerability information'</span><span class="sxs-lookup"><span data-stu-id="c19b3-323">'Read Threat and Vulnerability Management vulnerability information'</span></span>

### <a name="33-url"></a><span data-ttu-id="c19b3-324">3.3 URL-адрес</span><span class="sxs-lookup"><span data-stu-id="c19b3-324">3.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine 
```

### <a name="34-parameters"></a><span data-ttu-id="c19b3-325">3.4 Параметры</span><span class="sxs-lookup"><span data-stu-id="c19b3-325">3.4 Parameters</span></span>

- <span data-ttu-id="c19b3-326">sinceTime (обязательно) — данные между выбранным временем и сегодняшним днем.</span><span class="sxs-lookup"><span data-stu-id="c19b3-326">sinceTime (required) – The data between a selected time and today.</span></span>
- <span data-ttu-id="c19b3-327">pageSize (по умолчанию = 50 000) — количество результатов в ответе</span><span class="sxs-lookup"><span data-stu-id="c19b3-327">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="c19b3-328">$top — количество возвращаемого результата (не возвращает @odata.nextLink и, следовательно, не вытягивает все данные)</span><span class="sxs-lookup"><span data-stu-id="c19b3-328">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="35-properties"></a><span data-ttu-id="c19b3-329">3.5 Свойства</span><span class="sxs-lookup"><span data-stu-id="c19b3-329">3.5 Properties</span></span>

<span data-ttu-id="c19b3-330">Каждая возвращенная запись содержит все данные из полной оценки уязвимостей программного обеспечения для экспорта по API устройства, а также два дополнительных поля: _**EventTimestamp**_ и _**Status.**_</span><span class="sxs-lookup"><span data-stu-id="c19b3-330">Each returned record contains all the data from the full export software vulnerabilities assessment by device API, plus two additional fields:  _**EventTimestamp**_ and _**Status**_.</span></span>

>[!NOTE]
>- <span data-ttu-id="c19b3-331">Некоторые дополнительные столбцы могут быть возвращены в ответе.</span><span class="sxs-lookup"><span data-stu-id="c19b3-331">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="c19b3-332">Эти столбцы являются временными и могут быть удалены, поэтому используйте только задокументированные столбцы.</span><span class="sxs-lookup"><span data-stu-id="c19b3-332">These columns are temporary and might be removed, so please use only the documented columns.</span></span>
>
>- <span data-ttu-id="c19b3-333">Свойства, определенные в следующей таблице, перечислены в алфавитном порядке по ID свойства.</span><span class="sxs-lookup"><span data-stu-id="c19b3-333">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="c19b3-334">При запуске этого API результат не обязательно возвращается в том же порядке, который указан в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="c19b3-334">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
<br><br/>

<span data-ttu-id="c19b3-335">Свойство (ID)</span><span class="sxs-lookup"><span data-stu-id="c19b3-335">Property (ID)</span></span> | <span data-ttu-id="c19b3-336">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c19b3-336">Data type</span></span> | <span data-ttu-id="c19b3-337">Описание</span><span class="sxs-lookup"><span data-stu-id="c19b3-337">Description</span></span> | <span data-ttu-id="c19b3-338">Пример возвращенного значения</span><span class="sxs-lookup"><span data-stu-id="c19b3-338">Example of returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="c19b3-339">CveId</span><span class="sxs-lookup"><span data-stu-id="c19b3-339">CveId</span></span> | <span data-ttu-id="c19b3-340">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-340">string</span></span> | <span data-ttu-id="c19b3-341">Уникальный идентификатор, присвоенный уязвимости безопасности в системе Common Vulnerabilities and Exposures (CVE).</span><span class="sxs-lookup"><span data-stu-id="c19b3-341">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="c19b3-342">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="c19b3-342">CVE-2020-15992</span></span>  
<span data-ttu-id="c19b3-343">CvssScore</span><span class="sxs-lookup"><span data-stu-id="c19b3-343">CvssScore</span></span> | <span data-ttu-id="c19b3-344">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-344">string</span></span> | <span data-ttu-id="c19b3-345">Оценка CVSS CVE.</span><span class="sxs-lookup"><span data-stu-id="c19b3-345">The CVSS score of the CVE.</span></span> | <span data-ttu-id="c19b3-346">6.2</span><span class="sxs-lookup"><span data-stu-id="c19b3-346">6.2</span></span>  
<span data-ttu-id="c19b3-347">DeviceId</span><span class="sxs-lookup"><span data-stu-id="c19b3-347">DeviceId</span></span> | <span data-ttu-id="c19b3-348">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-348">string</span></span> | <span data-ttu-id="c19b3-349">Уникальный идентификатор устройства в службе.</span><span class="sxs-lookup"><span data-stu-id="c19b3-349">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="c19b3-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="c19b3-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>  
<span data-ttu-id="c19b3-351">DeviceName</span><span class="sxs-lookup"><span data-stu-id="c19b3-351">DeviceName</span></span> | <span data-ttu-id="c19b3-352">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-352">string</span></span> | <span data-ttu-id="c19b3-353">Полное доменное имя (FQDN) устройства.</span><span class="sxs-lookup"><span data-stu-id="c19b3-353">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="c19b3-354">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c19b3-354">johnlaptop.europe.contoso.com</span></span>  
<span data-ttu-id="c19b3-355">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="c19b3-355">DiskPaths</span></span> | <span data-ttu-id="c19b3-356">Array[string]</span><span class="sxs-lookup"><span data-stu-id="c19b3-356">Array[string]</span></span> | <span data-ttu-id="c19b3-357">Дисковые данные о том, что продукт установлен на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c19b3-357">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="c19b3-358">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="c19b3-358">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>  
<span data-ttu-id="c19b3-359">EventTimestamp</span><span class="sxs-lookup"><span data-stu-id="c19b3-359">EventTimestamp</span></span> | <span data-ttu-id="c19b3-360">Строка</span><span class="sxs-lookup"><span data-stu-id="c19b3-360">String</span></span> | <span data-ttu-id="c19b3-361">Время, когда это событие дельты было найдено.</span><span class="sxs-lookup"><span data-stu-id="c19b3-361">The time this delta event was found.</span></span> | <span data-ttu-id="c19b3-362">2021-01-11T11:06:08.291Z</span><span class="sxs-lookup"><span data-stu-id="c19b3-362">2021-01-11T11:06:08.291Z</span></span>
<span data-ttu-id="c19b3-363">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="c19b3-363">ExploitabilityLevel</span></span> | <span data-ttu-id="c19b3-364">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-364">string</span></span> | <span data-ttu-id="c19b3-365">Уровень эксплуатации этой уязвимости (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="c19b3-365">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="c19b3-366">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="c19b3-366">ExploitIsInKit</span></span>  
<span data-ttu-id="c19b3-367">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="c19b3-367">FirstSeenTimestamp</span></span> | <span data-ttu-id="c19b3-368">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-368">string</span></span> | <span data-ttu-id="c19b3-369">Впервые CVE этого продукта был замечен на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c19b3-369">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="c19b3-370">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="c19b3-370">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="c19b3-371">Id</span><span class="sxs-lookup"><span data-stu-id="c19b3-371">Id</span></span> | <span data-ttu-id="c19b3-372">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-372">string</span></span> | <span data-ttu-id="c19b3-373">Уникальный идентификатор для записи.</span><span class="sxs-lookup"><span data-stu-id="c19b3-373">Unique identifier for the record.</span></span> | <span data-ttu-id="c19b3-374">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="c19b3-374">123ABG55_573AG&mnp!</span></span>  
<span data-ttu-id="c19b3-375">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="c19b3-375">LastSeenTimestamp</span></span> | <span data-ttu-id="c19b3-376">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-376">string</span></span> | <span data-ttu-id="c19b3-377">Последний раз CVE был замечен на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c19b3-377">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="c19b3-378">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="c19b3-378">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="c19b3-379">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="c19b3-379">OSPlatform</span></span> | <span data-ttu-id="c19b3-380">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-380">string</span></span> | <span data-ttu-id="c19b3-381">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c19b3-381">Platform of the operating system running on the device.</span></span> <span data-ttu-id="c19b3-382">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="c19b3-382">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="c19b3-383">Подробные сведения см. в материале tvm supported operating systems and platforms.</span><span class="sxs-lookup"><span data-stu-id="c19b3-383">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="c19b3-384">Windows10</span><span class="sxs-lookup"><span data-stu-id="c19b3-384">Windows10</span></span>  
<span data-ttu-id="c19b3-385">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="c19b3-385">RbacGroupName</span></span> | <span data-ttu-id="c19b3-386">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-386">string</span></span> | <span data-ttu-id="c19b3-387">Группа управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="c19b3-387">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="c19b3-388">Если это устройство не назначено какой-либо группе RBAC, значение будет "Unassigned".</span><span class="sxs-lookup"><span data-stu-id="c19b3-388">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="c19b3-389">Если организация не содержит групп RBAC, значение будет "Нет".</span><span class="sxs-lookup"><span data-stu-id="c19b3-389">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="c19b3-390">Servers</span><span class="sxs-lookup"><span data-stu-id="c19b3-390">Servers</span></span>  
<span data-ttu-id="c19b3-391">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="c19b3-391">RecommendationReference</span></span> | <span data-ttu-id="c19b3-392">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-392">string</span></span> | <span data-ttu-id="c19b3-393">Ссылка на номер рекомендации, связанный с этим программным обеспечением.</span><span class="sxs-lookup"><span data-stu-id="c19b3-393">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="c19b3-394">va--microsoft--silverlight</span><span class="sxs-lookup"><span data-stu-id="c19b3-394">va--microsoft--silverlight</span></span>  
<span data-ttu-id="c19b3-395">RecommendedSecurityUpdate</span><span class="sxs-lookup"><span data-stu-id="c19b3-395">RecommendedSecurityUpdate</span></span>  | <span data-ttu-id="c19b3-396">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-396">string</span></span> | <span data-ttu-id="c19b3-397">Имя или описание обновления безопасности, предоставляемого поставщиком программного обеспечения для устранения уязвимости.</span><span class="sxs-lookup"><span data-stu-id="c19b3-397">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="c19b3-398">Обновления безопасности за апрель 2020 г.</span><span class="sxs-lookup"><span data-stu-id="c19b3-398">April 2020 Security Updates</span></span>  
<span data-ttu-id="c19b3-399">RecommendedSecurityUpdateId</span><span class="sxs-lookup"><span data-stu-id="c19b3-399">RecommendedSecurityUpdateId</span></span>  | <span data-ttu-id="c19b3-400">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-400">string</span></span> | <span data-ttu-id="c19b3-401">Идентификатор применимых обновлений или идентификаторов безопасности для соответствующих статей руководства или базы знаний (KB).</span><span class="sxs-lookup"><span data-stu-id="c19b3-401">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="c19b3-402">4550961</span><span class="sxs-lookup"><span data-stu-id="c19b3-402">4550961</span></span>  
<span data-ttu-id="c19b3-403">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="c19b3-403">RegistryPaths</span></span>  | <span data-ttu-id="c19b3-404">Array[string]</span><span class="sxs-lookup"><span data-stu-id="c19b3-404">Array[string]</span></span> | <span data-ttu-id="c19b3-405">Свидетельство реестра о том, что продукт установлен на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c19b3-405">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="c19b3-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span><span class="sxs-lookup"><span data-stu-id="c19b3-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span></span>  
<span data-ttu-id="c19b3-407">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="c19b3-407">SoftwareName</span></span> | <span data-ttu-id="c19b3-408">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-408">string</span></span> | <span data-ttu-id="c19b3-409">Имя программного продукта.</span><span class="sxs-lookup"><span data-stu-id="c19b3-409">Name of the software product.</span></span> | <span data-ttu-id="c19b3-410">chrome</span><span class="sxs-lookup"><span data-stu-id="c19b3-410">chrome</span></span>  
<span data-ttu-id="c19b3-411">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="c19b3-411">SoftwareVendor</span></span> | <span data-ttu-id="c19b3-412">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-412">string</span></span> | <span data-ttu-id="c19b3-413">Имя поставщика программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="c19b3-413">Name of the software vendor.</span></span> | <span data-ttu-id="c19b3-414">Google</span><span class="sxs-lookup"><span data-stu-id="c19b3-414">google</span></span>  
<span data-ttu-id="c19b3-415">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="c19b3-415">SoftwareVersion</span></span> | <span data-ttu-id="c19b3-416">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-416">string</span></span> | <span data-ttu-id="c19b3-417">Номер версии программного продукта.</span><span class="sxs-lookup"><span data-stu-id="c19b3-417">Version number of the software product.</span></span> | <span data-ttu-id="c19b3-418">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="c19b3-418">81.0.4044.138</span></span>  
<span data-ttu-id="c19b3-419">Состояние</span><span class="sxs-lookup"><span data-stu-id="c19b3-419">Status</span></span> | <span data-ttu-id="c19b3-420">Строка</span><span class="sxs-lookup"><span data-stu-id="c19b3-420">String</span></span> | <span data-ttu-id="c19b3-421">**Новые**   (для новой уязвимости, введенной на устройстве)  (1) **Исправлено**(если эта уязвимость больше не существует на устройстве, что означает   ее исправление).</span><span class="sxs-lookup"><span data-stu-id="c19b3-421">**New** (for a new vulnerability introduced on a device)  (1) **Fixed** (if this vulnerability doesn’t exist anymore on the device, which means it was remediated).</span></span> <span data-ttu-id="c19b3-422">(2)  **Обновлено**   (если уязвимость на устройстве изменилась.</span><span class="sxs-lookup"><span data-stu-id="c19b3-422">(2) **Updated** (if a vulnerability on a device has changed.</span></span> <span data-ttu-id="c19b3-423">Возможные изменения: оценка CVSS, уровень эксплуатации, уровень серьезности, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span><span class="sxs-lookup"><span data-stu-id="c19b3-423">The possible changes are: CVSS score, exploitability level, severity level, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span></span> | <span data-ttu-id="c19b3-424">ИСПРАВЛЕНО</span><span class="sxs-lookup"><span data-stu-id="c19b3-424">Fixed</span></span>
<span data-ttu-id="c19b3-425">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="c19b3-425">VulnerabilitySeverityLevel</span></span> | <span data-ttu-id="c19b3-426">string</span><span class="sxs-lookup"><span data-stu-id="c19b3-426">string</span></span> | <span data-ttu-id="c19b3-427">Уровень серьезности, присвоенный уязвимости безопасности на основе показателей CVSS и динамических факторов, влияющих на ландшафт угроз.</span><span class="sxs-lookup"><span data-stu-id="c19b3-427">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="c19b3-428">Средний</span><span class="sxs-lookup"><span data-stu-id="c19b3-428">Medium</span></span>  

#### <a name="clarifications"></a><span data-ttu-id="c19b3-429">Уточнения</span><span class="sxs-lookup"><span data-stu-id="c19b3-429">Clarifications</span></span>

- <span data-ttu-id="c19b3-430">Если программное обеспечение было обновлено с версии 1.0 до версии 2.0 и обе версии будут подвергаться воздействию CVE-A, вы получите 2 отдельных события:</span><span class="sxs-lookup"><span data-stu-id="c19b3-430">If the software was updated from version 1.0 to version 2.0, and both versions are exposed to CVE-A, you will receive 2 separate events:</span></span>  
   1. <span data-ttu-id="c19b3-431">Исправлено . Исправлена CVE-A в версии 1.0</span><span class="sxs-lookup"><span data-stu-id="c19b3-431">Fixed – CVE-A on version 1.0 was fixed</span></span>  
   1. <span data-ttu-id="c19b3-432">New — добавлен CVE-A в версии 2.0</span><span class="sxs-lookup"><span data-stu-id="c19b3-432">New – CVE-A on version 2.0 was added</span></span>

- <span data-ttu-id="c19b3-433">Если определенная уязвимость (например, CVE-A) впервые была замечена в определенное время (например, 10 января) в программном обеспечении с версией 1.0, а через несколько дней это программное обеспечение было обновлено до версии 2.0, которая также подверглась воздействию того же CVE-A, вы получите эти два разделенных события:</span><span class="sxs-lookup"><span data-stu-id="c19b3-433">If a specific vulnerability (for example, CVE-A) was first seen at a specific time (for example, January 10) on software with version 1.0, and a few days later that software was updated to version 2.0 which also exposed to the same CVE-A, you will receive these two separated events:</span></span>  
   1. <span data-ttu-id="c19b3-434">Исправлено : CVE-X, FirstSeenTimestamp 10 января, версия 1,0.</span><span class="sxs-lookup"><span data-stu-id="c19b3-434">Fixed – CVE-X, FirstSeenTimestamp January 10, version 1,0.</span></span>  
   1. <span data-ttu-id="c19b3-435">New — CVE-X, FirstSeenTimestamp 10 января, версия 2.0.</span><span class="sxs-lookup"><span data-stu-id="c19b3-435">New – CVE-X, FirstSeenTimestamp January 10, version 2.0.</span></span>

### <a name="36-examples"></a><span data-ttu-id="c19b3-436">3.6 Примеры</span><span class="sxs-lookup"><span data-stu-id="c19b3-436">3.6 Examples</span></span>

#### <a name="361-request-example"></a><span data-ttu-id="c19b3-437">Пример запроса 3.6.1</span><span class="sxs-lookup"><span data-stu-id="c19b3-437">3.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a><span data-ttu-id="c19b3-438">Пример ответа 3.6.2</span><span class="sxs-lookup"><span data-stu-id="c19b3-438">3.6.2 Response example</span></span>

```json
{ 
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)", 
    "value": [ 
        { 
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__", 
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "87.0.4280.88", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome" 
            ], 
            "lastSeenTimestamp": "2021-01-04 00:29:42", 
            "firstSeenTimestamp": "2020-11-06 03:12:44", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__", 
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "onedrive", 
            "softwareVersion": "20.64.329.3", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe" 
            ], 
            "lastSeenTimestamp": "2020-12-11 19:49:48", 
            "firstSeenTimestamp": "2020-12-07 18:25:47", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-onedrive", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_", 
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "mozilla", 
            "softwareName": "firefox", 
            "softwareVersion": "83.0.0.0", 
            "cveId": "CVE-2020-26971", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "193220", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)" 
            ], 
            "lastSeenTimestamp": "2021-01-05 17:04:30", 
            "firstSeenTimestamp": "2020-05-06 12:42:19", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-mozilla-_-firefox", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__", 
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "project", 
            "softwareVersion": "16.0.13701.20000", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us" 
            ], 
            "lastSeenTimestamp": "2021-01-03 23:38:03", 
            "firstSeenTimestamp": "2019-08-01 22:56:12", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-project", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_", 
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "81.0.4044.138", 
            "cveId": "CVE-2020-16011", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "ADV 200002", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}" 
            ], 
            "lastSeenTimestamp": "2020-12-10 22:45:41", 
            "firstSeenTimestamp": "2020-07-26 02:13:43", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        } 
    ], 
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9" 
} 
```

## <a name="see-also"></a><span data-ttu-id="c19b3-439">См. также</span><span class="sxs-lookup"><span data-stu-id="c19b3-439">See also</span></span>

- [<span data-ttu-id="c19b3-440">Методы и свойства экспортной оценки на устройство</span><span class="sxs-lookup"><span data-stu-id="c19b3-440">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="c19b3-441">Экспорт безопасной оценки конфигурации на устройство</span><span class="sxs-lookup"><span data-stu-id="c19b3-441">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="c19b3-442">Экспорт оценки инвентаризации программного обеспечения на устройство</span><span class="sxs-lookup"><span data-stu-id="c19b3-442">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

<span data-ttu-id="c19b3-443">Другие связанные</span><span class="sxs-lookup"><span data-stu-id="c19b3-443">Other related</span></span>

- [<span data-ttu-id="c19b3-444">Риск на основе угрозы & управление уязвимостями</span><span class="sxs-lookup"><span data-stu-id="c19b3-444">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="c19b3-445">Уязвимости в организации</span><span class="sxs-lookup"><span data-stu-id="c19b3-445">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
