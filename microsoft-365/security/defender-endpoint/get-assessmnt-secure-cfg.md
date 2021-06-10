---
title: Экспорт безопасной оценки конфигурации на устройство
description: Возвращает запись для каждой уникальной комбинации DeviceId, ConfigurationId.
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
ms.openlocfilehash: ab33db7fb7acf1969973a7af8f80ea97ef3d378f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778369"
---
# <a name="export-secure-configuration-assessment-per-device"></a><span data-ttu-id="f8032-104">Экспорт безопасной оценки конфигурации на устройство</span><span class="sxs-lookup"><span data-stu-id="f8032-104">Export secure configuration assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f8032-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f8032-105">**Applies to:**</span></span>

- [<span data-ttu-id="f8032-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f8032-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f8032-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8032-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f8032-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="f8032-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f8032-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="f8032-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="f8032-110">Возвращает все конфигурации и их состояние на основе каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="f8032-110">Returns all of the configurations and their status, on a per-device basis.</span></span>

<span data-ttu-id="f8032-111">Существуют различные вызовы API для получения различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="f8032-111">There are different API calls to get different types of data.</span></span> <span data-ttu-id="f8032-112">Так как объем данных может быть большим, их можно получить двумя способами:</span><span class="sxs-lookup"><span data-stu-id="f8032-112">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="f8032-113">[Экспортная оценка **OData**](#1-export-secure-configuration-assessment-odata)для безопасной конфигурации: API передает все данные в организации в качестве ответов Json, следуя протоколу OData.</span><span class="sxs-lookup"><span data-stu-id="f8032-113">[Export secure configuration assessment **OData**](#1-export-secure-configuration-assessment-odata):  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="f8032-114">Этот метод лучше всего используется для небольших организаций с устройствами _менее 100 К._</span><span class="sxs-lookup"><span data-stu-id="f8032-114">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="f8032-115">Ответ paginated, поэтому вы можете использовать поле odata.nextLink из ответа, чтобы \@ получить следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="f8032-115">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="f8032-116">[Экспорт безопасной оценки **конфигурации**](#2-export-secure-configuration-assessment-via-files)с помощью файлов. Это решение API позволяет быстрее и надежнее тянуть большие объемы данных.</span><span class="sxs-lookup"><span data-stu-id="f8032-116">[Export secure configuration assessment **via files**](#2-export-secure-configuration-assessment-via-files): This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="f8032-117">Поэтому рекомендуется для крупных организаций с более чем 100 устройствами K.</span><span class="sxs-lookup"><span data-stu-id="f8032-117">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="f8032-118">Этот API извлекает все данные в организации в качестве файлов загрузки.</span><span class="sxs-lookup"><span data-stu-id="f8032-118">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="f8032-119">Ответ содержит URL-адреса для загрузки всех данных из служба хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="f8032-119">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="f8032-120">Этот API позволяет загружать все данные из служба хранилища Azure следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f8032-120">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="f8032-121">Позвоните в API, чтобы получить список загружаемых URL-адресов со всеми данными организации.</span><span class="sxs-lookup"><span data-stu-id="f8032-121">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="f8032-122">Скачайте все файлы с помощью URL-адресов загрузки и обработать данные, как вам нравится.</span><span class="sxs-lookup"><span data-stu-id="f8032-122">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="f8032-123">Собранные данные (с помощью _OData_ или _с_ помощью файлов) являются текущим снимком текущего состояния и не содержат исторических данных.</span><span class="sxs-lookup"><span data-stu-id="f8032-123">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="f8032-124">Чтобы собрать исторические данные, клиенты должны сохранять данные в собственных хранилищах данных.</span><span class="sxs-lookup"><span data-stu-id="f8032-124">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="f8032-125">Если не указано обратное, все \*\*\*\* перечисленные методы оценки экспорта являются полным экспортом и по устройству **_(также_** именуемой как **_на устройстве)._**</span><span class="sxs-lookup"><span data-stu-id="f8032-125">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-secure-configuration-assessment-odata"></a><span data-ttu-id="f8032-126">1. Оценка безопасной конфигурации экспорта (OData)</span><span class="sxs-lookup"><span data-stu-id="f8032-126">1. Export secure configuration assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="f8032-127">Описание метода API 1.1</span><span class="sxs-lookup"><span data-stu-id="f8032-127">1.1 API method description</span></span>

<span data-ttu-id="f8032-128">Этот ответ API содержит оценку безопасной конфигурации на выставленных устройствах и возвращает запись для каждой уникальной комбинации DeviceId, ConfigurationId.</span><span class="sxs-lookup"><span data-stu-id="f8032-128">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="f8032-129">1.1.1 Ограничения</span><span class="sxs-lookup"><span data-stu-id="f8032-129">1.1.1 Limitations</span></span>

- <span data-ttu-id="f8032-130">Максимальный размер страницы — 200 000.</span><span class="sxs-lookup"><span data-stu-id="f8032-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="f8032-131">Ограничения скорости для этого API : 30 вызовов в минуту и 1000 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="f8032-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="f8032-132">1.2 Разрешения</span><span class="sxs-lookup"><span data-stu-id="f8032-132">1.2 Permissions</span></span>

<span data-ttu-id="f8032-133">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="f8032-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f8032-134">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f8032-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="f8032-135">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="f8032-135">Permission type</span></span> | <span data-ttu-id="f8032-136">Разрешение</span><span class="sxs-lookup"><span data-stu-id="f8032-136">Permission</span></span> | <span data-ttu-id="f8032-137">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="f8032-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="f8032-138">Приложение</span><span class="sxs-lookup"><span data-stu-id="f8032-138">Application</span></span> | <span data-ttu-id="f8032-139">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="f8032-139">Vulnerability.Read.All</span></span> | <span data-ttu-id="f8032-140">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="f8032-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="f8032-141">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="f8032-141">Delegated (work or school account)</span></span> | <span data-ttu-id="f8032-142">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="f8032-142">Vulnerability.Read</span></span> | <span data-ttu-id="f8032-143">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="f8032-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="f8032-144">1.3 URL-адрес</span><span class="sxs-lookup"><span data-stu-id="f8032-144">1.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="f8032-145">1.4 Параметры</span><span class="sxs-lookup"><span data-stu-id="f8032-145">1.4 Parameters</span></span>

- <span data-ttu-id="f8032-146">по умолчанию pageSize \( = 50 000 \) — количество результатов в ответе</span><span class="sxs-lookup"><span data-stu-id="f8032-146">pageSize \(default = 50,000\) – number of results in response</span></span>

- <span data-ttu-id="f8032-147">\$верхняя часть — количество возвращаемого результата не \( возвращает odata.nextLink и, следовательно, не вытягивает \@ все данные\)</span><span class="sxs-lookup"><span data-stu-id="f8032-147">\$top – number of results to return \(doesn’t return \@odata.nextLink and therefore doesn’t pull all the data\)</span></span>

### <a name="15-properties"></a><span data-ttu-id="f8032-148">1.5 Свойства</span><span class="sxs-lookup"><span data-stu-id="f8032-148">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="f8032-149">Свойства, определенные в следующей таблице, перечислены в алфавитном порядке по ID свойства.</span><span class="sxs-lookup"><span data-stu-id="f8032-149">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="f8032-150">При запуске этого API результат не обязательно возвращается в том же порядке, который указан в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="f8032-150">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
>- <span data-ttu-id="f8032-151">Некоторые дополнительные столбцы могут быть возвращены в ответе.</span><span class="sxs-lookup"><span data-stu-id="f8032-151">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="f8032-152">Эти столбцы являются временными и могут быть удалены, используйте только задокументированные столбцы.</span><span class="sxs-lookup"><span data-stu-id="f8032-152">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="f8032-153">Свойство (ID)</span><span class="sxs-lookup"><span data-stu-id="f8032-153">Property (ID)</span></span> | <span data-ttu-id="f8032-154">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f8032-154">Data type</span></span> | <span data-ttu-id="f8032-155">Описание</span><span class="sxs-lookup"><span data-stu-id="f8032-155">Description</span></span> | <span data-ttu-id="f8032-156">Пример возвращенного значения</span><span class="sxs-lookup"><span data-stu-id="f8032-156">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="f8032-157">ConfigurationCategory</span><span class="sxs-lookup"><span data-stu-id="f8032-157">ConfigurationCategory</span></span> | <span data-ttu-id="f8032-158">string</span><span class="sxs-lookup"><span data-stu-id="f8032-158">string</span></span> | <span data-ttu-id="f8032-159">Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности</span><span class="sxs-lookup"><span data-stu-id="f8032-159">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> | <span data-ttu-id="f8032-160">Элементы управления безопасностью</span><span class="sxs-lookup"><span data-stu-id="f8032-160">Security controls</span></span>
<span data-ttu-id="f8032-161">ConfigurationId</span><span class="sxs-lookup"><span data-stu-id="f8032-161">ConfigurationId</span></span> | <span data-ttu-id="f8032-162">string</span><span class="sxs-lookup"><span data-stu-id="f8032-162">string</span></span> | <span data-ttu-id="f8032-163">Уникальный идентификатор определенной настройки</span><span class="sxs-lookup"><span data-stu-id="f8032-163">Unique identifier for a specific configuration</span></span> | <span data-ttu-id="f8032-164">scid-10000</span><span class="sxs-lookup"><span data-stu-id="f8032-164">scid-10000</span></span>
<span data-ttu-id="f8032-165">ConfigurationImpact</span><span class="sxs-lookup"><span data-stu-id="f8032-165">ConfigurationImpact</span></span> | <span data-ttu-id="f8032-166">string</span><span class="sxs-lookup"><span data-stu-id="f8032-166">string</span></span> | <span data-ttu-id="f8032-167">Оценка влияния настройки на общую оценку конфигурации (1–10)</span><span class="sxs-lookup"><span data-stu-id="f8032-167">Rated impact of the configuration to the overall configuration score (1-10)</span></span> | <span data-ttu-id="f8032-168">9 </span><span class="sxs-lookup"><span data-stu-id="f8032-168">9</span></span>
<span data-ttu-id="f8032-169">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="f8032-169">ConfigurationName</span></span> | <span data-ttu-id="f8032-170">string</span><span class="sxs-lookup"><span data-stu-id="f8032-170">string</span></span> | <span data-ttu-id="f8032-171">Отображение названия настройки</span><span class="sxs-lookup"><span data-stu-id="f8032-171">Display name of the configuration</span></span> | <span data-ttu-id="f8032-172">Подключение устройств к Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f8032-172">Onboard devices to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="f8032-173">ConfigurationSubcategory</span><span class="sxs-lookup"><span data-stu-id="f8032-173">ConfigurationSubcategory</span></span> | <span data-ttu-id="f8032-174">string</span><span class="sxs-lookup"><span data-stu-id="f8032-174">string</span></span> | <span data-ttu-id="f8032-175">Подкатегория или подгруппа, к которой относится настройка.</span><span class="sxs-lookup"><span data-stu-id="f8032-175">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="f8032-176">Во многих случаях здесь описываются конкретные возможности или функции.</span><span class="sxs-lookup"><span data-stu-id="f8032-176">In many cases, this describes specific capabilities or features.</span></span> | <span data-ttu-id="f8032-177">Бортовых устройств</span><span class="sxs-lookup"><span data-stu-id="f8032-177">Onboard Devices</span></span>
<span data-ttu-id="f8032-178">DeviceId</span><span class="sxs-lookup"><span data-stu-id="f8032-178">DeviceId</span></span> | <span data-ttu-id="f8032-179">Строка</span><span class="sxs-lookup"><span data-stu-id="f8032-179">string</span></span> | <span data-ttu-id="f8032-180">Уникальный идентификатор устройства в службе.</span><span class="sxs-lookup"><span data-stu-id="f8032-180">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="f8032-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="f8032-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="f8032-182">DeviceName</span><span class="sxs-lookup"><span data-stu-id="f8032-182">DeviceName</span></span> | <span data-ttu-id="f8032-183">Строка</span><span class="sxs-lookup"><span data-stu-id="f8032-183">string</span></span> | <span data-ttu-id="f8032-184">Полное доменное имя (FQDN) устройства.</span><span class="sxs-lookup"><span data-stu-id="f8032-184">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="f8032-185">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f8032-185">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="f8032-186">IsApplicable</span><span class="sxs-lookup"><span data-stu-id="f8032-186">IsApplicable</span></span> | <span data-ttu-id="f8032-187">bool</span><span class="sxs-lookup"><span data-stu-id="f8032-187">bool</span></span> | <span data-ttu-id="f8032-188">Указывает, применима ли конфигурация или политика</span><span class="sxs-lookup"><span data-stu-id="f8032-188">Indicates whether the configuration or policy is applicable</span></span> | <span data-ttu-id="f8032-189">true</span><span class="sxs-lookup"><span data-stu-id="f8032-189">true</span></span>
<span data-ttu-id="f8032-190">IsCompliant</span><span class="sxs-lookup"><span data-stu-id="f8032-190">IsCompliant</span></span> | <span data-ttu-id="f8032-191">bool</span><span class="sxs-lookup"><span data-stu-id="f8032-191">bool</span></span> | <span data-ttu-id="f8032-192">Указывает, правильно ли настроена конфигурация или политика</span><span class="sxs-lookup"><span data-stu-id="f8032-192">Indicates whether the configuration or policy is properly configured</span></span> | <span data-ttu-id="f8032-193">false</span><span class="sxs-lookup"><span data-stu-id="f8032-193">false</span></span>
<span data-ttu-id="f8032-194">IsExpectedUserImpact</span><span class="sxs-lookup"><span data-stu-id="f8032-194">IsExpectedUserImpact</span></span> | <span data-ttu-id="f8032-195">bool</span><span class="sxs-lookup"><span data-stu-id="f8032-195">bool</span></span> | <span data-ttu-id="f8032-196">Указывает, будет ли влияние пользователя, если конфигурация будет применена</span><span class="sxs-lookup"><span data-stu-id="f8032-196">Indicates whether there will be user impact if the configuration will be applied</span></span> | <span data-ttu-id="f8032-197">true</span><span class="sxs-lookup"><span data-stu-id="f8032-197">true</span></span>
<span data-ttu-id="f8032-198">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="f8032-198">OSPlatform</span></span> | <span data-ttu-id="f8032-199">Строка</span><span class="sxs-lookup"><span data-stu-id="f8032-199">string</span></span> | <span data-ttu-id="f8032-200">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="f8032-200">Platform of the operating system running on the device.</span></span> <span data-ttu-id="f8032-201">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="f8032-201">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="f8032-202">Подробные сведения см. в материале tvm supported operating systems and platforms.</span><span class="sxs-lookup"><span data-stu-id="f8032-202">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="f8032-203">Windows10</span><span class="sxs-lookup"><span data-stu-id="f8032-203">Windows10</span></span>
<span data-ttu-id="f8032-204">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="f8032-204">RbacGroupName</span></span> | <span data-ttu-id="f8032-205">Строка</span><span class="sxs-lookup"><span data-stu-id="f8032-205">string</span></span> | <span data-ttu-id="f8032-206">Группа управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="f8032-206">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="f8032-207">Если это устройство не назначено какой-либо группе RBAC, значение будет "Unassigned".</span><span class="sxs-lookup"><span data-stu-id="f8032-207">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="f8032-208">Если организация не содержит групп RBAC, значение будет "Нет".</span><span class="sxs-lookup"><span data-stu-id="f8032-208">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="f8032-209">Servers</span><span class="sxs-lookup"><span data-stu-id="f8032-209">Servers</span></span>
<span data-ttu-id="f8032-210">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="f8032-210">RecommendationReference</span></span> | <span data-ttu-id="f8032-211">Строка</span><span class="sxs-lookup"><span data-stu-id="f8032-211">string</span></span> | <span data-ttu-id="f8032-212">Ссылка на номер рекомендации, связанный с этим программным обеспечением.</span><span class="sxs-lookup"><span data-stu-id="f8032-212">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="f8032-213">sca-_-scid-20000</span><span class="sxs-lookup"><span data-stu-id="f8032-213">sca-_-scid-20000</span></span>
<span data-ttu-id="f8032-214">Timestamp</span><span class="sxs-lookup"><span data-stu-id="f8032-214">Timestamp</span></span> | <span data-ttu-id="f8032-215">Строка</span><span class="sxs-lookup"><span data-stu-id="f8032-215">string</span></span> | <span data-ttu-id="f8032-216">Последний раз, когда конфигурация была замечена на устройстве</span><span class="sxs-lookup"><span data-stu-id="f8032-216">Last time the configuration was seen on the device</span></span> | <span data-ttu-id="f8032-217">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="f8032-217">2020-11-03 10:13:34.8476880</span></span>

### <a name="16-examples"></a><span data-ttu-id="f8032-218">1.6 Примеры</span><span class="sxs-lookup"><span data-stu-id="f8032-218">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="f8032-219">Пример запроса 1.6.1</span><span class="sxs-lookup"><span data-stu-id="f8032-219">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a><span data-ttu-id="f8032-220">1.6.2 Пример ответа</span><span class="sxs-lookup"><span data-stu-id="f8032-220">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a><span data-ttu-id="f8032-221">2. Экспорт безопасной оценки конфигурации (с помощью файлов)</span><span class="sxs-lookup"><span data-stu-id="f8032-221">2. Export secure configuration assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="f8032-222">Описание метода API 2.1</span><span class="sxs-lookup"><span data-stu-id="f8032-222">2.1 API method description</span></span>

<span data-ttu-id="f8032-223">Этот ответ API содержит оценку безопасной конфигурации на выставленных устройствах и возвращает запись для каждой уникальной комбинации DeviceId, ConfigurationId.</span><span class="sxs-lookup"><span data-stu-id="f8032-223">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="f8032-224">2.1.2 Ограничения</span><span class="sxs-lookup"><span data-stu-id="f8032-224">2.1.2 Limitations</span></span>

<span data-ttu-id="f8032-225">Ограничения скорости для этого API : 5 вызовов в минуту и 20 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="f8032-225">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="f8032-226">2.2 Разрешения</span><span class="sxs-lookup"><span data-stu-id="f8032-226">2.2 Permissions</span></span>

<span data-ttu-id="f8032-227">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="f8032-227">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f8032-228">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f8032-228">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="f8032-229">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="f8032-229">Permission type</span></span> | <span data-ttu-id="f8032-230">Разрешение</span><span class="sxs-lookup"><span data-stu-id="f8032-230">Permission</span></span> | <span data-ttu-id="f8032-231">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="f8032-231">Permission display name</span></span>
---|---|---
<span data-ttu-id="f8032-232">Приложение</span><span class="sxs-lookup"><span data-stu-id="f8032-232">Application</span></span> | <span data-ttu-id="f8032-233">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="f8032-233">Vulnerability.Read.All</span></span> | <span data-ttu-id="f8032-234">\'Сведения об уязвимости контроль угроз и уязвимостей "контроль угроз и уязвимостей"\'</span><span class="sxs-lookup"><span data-stu-id="f8032-234">\'Read "threat and vulnerability management" vulnerability information\'</span></span>
<span data-ttu-id="f8032-235">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="f8032-235">Delegated (work or school account)</span></span> | <span data-ttu-id="f8032-236">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="f8032-236">Vulnerability.Read</span></span> | <span data-ttu-id="f8032-237">\'Сведения об уязвимости контроль угроз и уязвимостей "контроль угроз и уязвимостей"\'</span><span class="sxs-lookup"><span data-stu-id="f8032-237">\'Read "threat and vulnerability management" vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="f8032-238">2.3 URL-адрес</span><span class="sxs-lookup"><span data-stu-id="f8032-238">2.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a><span data-ttu-id="f8032-239">Parameters</span><span class="sxs-lookup"><span data-stu-id="f8032-239">Parameters</span></span>

- <span data-ttu-id="f8032-240">sasValidHours — количество часов, на которые будут действительны URL-адреса загрузки (не более 24 часов).</span><span class="sxs-lookup"><span data-stu-id="f8032-240">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours).</span></span>

### <a name="25-properties"></a><span data-ttu-id="f8032-241">2.5 Свойства</span><span class="sxs-lookup"><span data-stu-id="f8032-241">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="f8032-242">Файлы являются сжатой gzip & в многолинейном формате Json.</span><span class="sxs-lookup"><span data-stu-id="f8032-242">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="f8032-243">Url-адреса загрузки действительны только в течение 3 часов; в противном случае параметр можно использовать.</span><span class="sxs-lookup"><span data-stu-id="f8032-243">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="f8032-244">Для максимальной скорости скачивания данных можно убедиться, что вы скачиваете из того же региона Azure, в котором находятся ваши данные.</span><span class="sxs-lookup"><span data-stu-id="f8032-244">For maximum download speed of your data, you can make sure you are downloading from the same Azure region in which your data resides.</span></span>
>
<span data-ttu-id="f8032-245">Свойство (ID)</span><span class="sxs-lookup"><span data-stu-id="f8032-245">Property (ID)</span></span> | <span data-ttu-id="f8032-246">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f8032-246">Data type</span></span> | <span data-ttu-id="f8032-247">Описание</span><span class="sxs-lookup"><span data-stu-id="f8032-247">Description</span></span> | <span data-ttu-id="f8032-248">Пример возвращенного значения</span><span class="sxs-lookup"><span data-stu-id="f8032-248">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="f8032-249">Экспорт файлов</span><span class="sxs-lookup"><span data-stu-id="f8032-249">Export files</span></span> | <span data-ttu-id="f8032-250">строка \[ массива\]</span><span class="sxs-lookup"><span data-stu-id="f8032-250">array\[string\]</span></span> | <span data-ttu-id="f8032-251">Список загрузок URL-адресов для файлов с текущим снимком организации</span><span class="sxs-lookup"><span data-stu-id="f8032-251">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="f8032-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="f8032-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="f8032-253">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="f8032-253">GeneratedTime</span></span> | <span data-ttu-id="f8032-254">Строка</span><span class="sxs-lookup"><span data-stu-id="f8032-254">string</span></span> | <span data-ttu-id="f8032-255">Время, за которое был создан экспорт.</span><span class="sxs-lookup"><span data-stu-id="f8032-255">The time that the export was generated.</span></span> | <span data-ttu-id="f8032-256">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="f8032-256">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="f8032-257">2.6 Примеры</span><span class="sxs-lookup"><span data-stu-id="f8032-257">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="f8032-258">Пример запроса 2.6.1</span><span class="sxs-lookup"><span data-stu-id="f8032-258">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a><span data-ttu-id="f8032-259">2.6.2 Пример ответа</span><span class="sxs-lookup"><span data-stu-id="f8032-259">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="f8032-260">См. также</span><span class="sxs-lookup"><span data-stu-id="f8032-260">See also</span></span>

- [<span data-ttu-id="f8032-261">Методы и свойства экспортной оценки на устройство</span><span class="sxs-lookup"><span data-stu-id="f8032-261">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="f8032-262">Экспорт оценки инвентаризации программного обеспечения на устройство</span><span class="sxs-lookup"><span data-stu-id="f8032-262">Export software inventory assessment per device</span></span>](get-assessmnt-software-inventory.md)

- [<span data-ttu-id="f8032-263">Экспорт оценки уязвимостей программного обеспечения на устройство</span><span class="sxs-lookup"><span data-stu-id="f8032-263">Export software vulnerabilities assessment per device</span></span>](get-assessmnt-software-vulnerabilities.md)

<span data-ttu-id="f8032-264">Другие связанные</span><span class="sxs-lookup"><span data-stu-id="f8032-264">Other related</span></span>

- [<span data-ttu-id="f8032-265">Риск на основе угрозы & управление уязвимостями</span><span class="sxs-lookup"><span data-stu-id="f8032-265">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="f8032-266">Уязвимости в организации</span><span class="sxs-lookup"><span data-stu-id="f8032-266">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
