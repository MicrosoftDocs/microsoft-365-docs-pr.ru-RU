---
title: Защита информации в обзоре Windows
ms.reviewer: ''
description: Сведения о том, как защита информации работает в Windows для идентификации и защиты конфиденциальной информации
keywords: сведения, защита, dlp, данные, потери, предотвращение, защита
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 733f86ed48b9cc7a68fb0cd346c7b15fdcc3ce65
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187509"
---
# <a name="information-protection-in-windows-overview"></a><span data-ttu-id="ff7cf-104">Защита информации в обзоре Windows</span><span class="sxs-lookup"><span data-stu-id="ff7cf-104">Information protection in Windows overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ff7cf-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ff7cf-105">**Applies to:**</span></span>

- [<span data-ttu-id="ff7cf-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ff7cf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ff7cf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff7cf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ff7cf-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ff7cf-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ff7cf-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="ff7cf-110">Защита информации является неотъемлемой частью пакета Microsoft 365 Enterprise, обеспечивая интеллектуальную защиту для обеспечения безопасности конфиденциальных данных, обеспечивая при этом производительность на рабочем месте.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-110">Information protection is an integral part of Microsoft 365 Enterprise suite, providing intelligent protection to keep sensitive data secure while enabling productivity in the workplace.</span></span>


>[!TIP]
> <span data-ttu-id="ff7cf-111">Ознакомьтесь с нашим сообщением в блоге о том, как ATP Защитника Майкрософт интегрируется с Microsoft Information Protection для обнаружения, защиты и мониторинга конфиденциальных данных [на устройствах Windows.](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)</span><span class="sxs-lookup"><span data-stu-id="ff7cf-111">Read our blog post about how [Microsoft Defender ATP integrates with Microsoft Information Protection to discover, protect, and monitor sensitive data on Windows devices](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/).</span></span>

<span data-ttu-id="ff7cf-112">Defender for Endpoint применяет следующие методы обнаружения, классификации и защиты данных:</span><span class="sxs-lookup"><span data-stu-id="ff7cf-112">Defender for Endpoint applies the following methods to discover, classify, and protect data:</span></span>

- <span data-ttu-id="ff7cf-113">**Обнаружение данных** . Определение конфиденциальных данных на устройствах с Windows в опасности</span><span class="sxs-lookup"><span data-stu-id="ff7cf-113">**Data discovery** - Identify sensitive data on Windows devices at risk</span></span>
- <span data-ttu-id="ff7cf-114">**Классификация** данных — автоматически классифицировать данные на основе общих политик microsoft Information Protection (MIP), управляемых в Центре безопасности Office 365 & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-114">**Data classification** - Automatically classify data based on common Microsoft Information Protection (MIP) policies managed in Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="ff7cf-115">Автоматическая классификация позволяет защищать конфиденциальные данные, даже если конечный пользователь не классифицировал их вручную.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-115">Auto-classification allows you to protect sensitive data even if the end user hasn’t manually classified it.</span></span>


## <a name="data-discovery-and-data-classification"></a><span data-ttu-id="ff7cf-116">Обнаружение данных и классификация данных</span><span class="sxs-lookup"><span data-stu-id="ff7cf-116">Data discovery and data classification</span></span>

<span data-ttu-id="ff7cf-117">Defender for Endpoint автоматически обнаруживает файлы с метами конфиденциальности и файлы, содержащие типы конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-117">Defender for Endpoint automatically discovers files with sensitivity labels and files that contain sensitive information types.</span></span>

<span data-ttu-id="ff7cf-118">Метки конфиденциальности классифицируют и помогают защитить конфиденциальный контент.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-118">Sensitivity labels classify and help protect sensitive content.</span></span>

<span data-ttu-id="ff7cf-119">Типы конфиденциальной информации в реализации office 365 по предотвращению потери данных (DLP) подпадают под две категории:</span><span class="sxs-lookup"><span data-stu-id="ff7cf-119">Sensitive information types in the Office 365 data loss prevention (DLP) implementation fall under two categories:</span></span>

- <span data-ttu-id="ff7cf-120">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="ff7cf-120">Default</span></span>
- <span data-ttu-id="ff7cf-121">Пользовательские</span><span class="sxs-lookup"><span data-stu-id="ff7cf-121">Custom</span></span>

<span data-ttu-id="ff7cf-122">Типы конфиденциальной информации по умолчанию включают такие сведения, как номера банковских счетов, номера социального страхования или национальные ID.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-122">Default sensitive information types include information such as bank account numbers, social security numbers, or national IDs.</span></span> <span data-ttu-id="ff7cf-123">Дополнительные сведения см. [в дополнительных сведениях о том, как выглядит тип конфиденциальной информации.](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for)</span><span class="sxs-lookup"><span data-stu-id="ff7cf-123">For more information, see [What the sensitive information type look for](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for).</span></span>

<span data-ttu-id="ff7cf-124">Настраиваемые типы — это те типы, которые вы определяете и предназначено для защиты конфиденциальной информации другого типа (например, номеров сотрудников или номеров проектов).</span><span class="sxs-lookup"><span data-stu-id="ff7cf-124">Custom types are ones that you define and is designed to protect a different type of sensitive information (for example, employee IDs or project numbers).</span></span> <span data-ttu-id="ff7cf-125">Дополнительные сведения см. [введите настраиваемый тип конфиденциальной информации.](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type)</span><span class="sxs-lookup"><span data-stu-id="ff7cf-125">For more information see, [Create a custom sensitive information type](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type).</span></span>

<span data-ttu-id="ff7cf-126">Когда файл создается или редактируется на устройстве Windows, Defender for Endpoint сканирует содержимое, чтобы оценить, содержится ли в нем конфиденциальную информацию.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-126">When a file is created or edited on a  Windows device, Defender for Endpoint scans the content to evaluate if it contains sensitive information.</span></span>

<span data-ttu-id="ff7cf-127">Включив интеграцию Azure Information Protection, чтобы когда файл, содержащий конфиденциальные сведения, был обнаружен Защитником для конечной точки, хотя метки или типы информации, он автоматически передается в Azure Information Protection с устройства.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-127">Turn on the Azure Information Protection integration so that when a file that contains sensitive information is discovered by Defender for Endpoint though labels or information types, it is automatically forwarded to Azure Information Protection from the device.</span></span>

![Изображение страницы параметров с помощью Azure Information Protection](images/atp-settings-aip.png)

<span data-ttu-id="ff7cf-129">Отчетные сигналы можно просмотреть на панели данных Azure Information Protection — Data discovery.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-129">The reported signals can be viewed on the Azure Information Protection – Data discovery dashboard.</span></span>

## <a name="azure-information-protection---data-discovery-dashboard"></a><span data-ttu-id="ff7cf-130">Azure Information Protection — панель мониторинга обнаружения данных</span><span class="sxs-lookup"><span data-stu-id="ff7cf-130">Azure Information Protection - Data discovery dashboard</span></span>

<span data-ttu-id="ff7cf-131">На этой панели мониторинга представлена сводная информация об обнаружении данных, обнаруженных как Защитником для конечной точки, так и Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-131">This dashboard presents a summarized discovery information of data discovered by both Defender for Endpoint and Azure Information Protection.</span></span> <span data-ttu-id="ff7cf-132">Данные из Defender для конечной точки отмечены типом расположения — конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-132">Data from Defender for Endpoint is marked with Location Type - Endpoint.</span></span>

![Изображение Azure Information Protection — обнаружение данных](images/azure-data-discovery.png)

<span data-ttu-id="ff7cf-134">Обратите внимание на столбец риск устройства справа, этот риск устройства выводится непосредственно из Defender для конечной точки, указав уровень риска устройства безопасности, на котором был обнаружен файл, на основе активных угроз безопасности, обнаруженных Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-134">Notice the Device Risk column on the right, this device risk is derived directly from Defender for Endpoint, indicating the risk level of the security device where the file was discovered, based on the active security threats detected by Defender for Endpoint.</span></span>

<span data-ttu-id="ff7cf-135">Щелкните на устройстве, чтобы просмотреть список файлов, наблюдаемых на этом устройстве, с метами и типами сведений о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-135">Click on a device to view a list of files observed on this device, with their sensitivity labels and information types.</span></span>

>[!NOTE]
><span data-ttu-id="ff7cf-136">Дайте примерно 15-20 минут на обнаружение панели мониторинга информационной защиты Azure для отражения обнаруженных файлов.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-136">Please allow approximately 15-20 minutes for the Azure Information Protection Dashboard Discovery to reflect discovered files.</span></span>

## <a name="log-analytics"></a><span data-ttu-id="ff7cf-137">Аналитика журналов</span><span class="sxs-lookup"><span data-stu-id="ff7cf-137">Log Analytics</span></span>

<span data-ttu-id="ff7cf-138">Обнаружение данных на основе Defender для конечной точки также доступно в [Azure Log Analytics,](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)где можно выполнять сложные запросы по необработанных данных.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-138">Data discovery based on Defender for Endpoint is also available in [Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview), where you can perform complex queries over the raw data.</span></span>

<span data-ttu-id="ff7cf-139">Дополнительные сведения об аналитике azure Information Protection см. в центре [отчетов для Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/reports-aip)</span><span class="sxs-lookup"><span data-stu-id="ff7cf-139">For more information on Azure Information Protection analytics, see [Central reporting for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/reports-aip).</span></span>

<span data-ttu-id="ff7cf-140">Откройте Azure Log Analytics на портале Azure и откройте строитель запросов (стандартный или классический).</span><span class="sxs-lookup"><span data-stu-id="ff7cf-140">Open Azure Log Analytics in Azure portal and open a query builder (standard or classic).</span></span>

<span data-ttu-id="ff7cf-141">Чтобы просмотреть данные Defender для конечных точек, выполните запрос, содержащий:</span><span class="sxs-lookup"><span data-stu-id="ff7cf-141">To view Defender for Endpoint data, perform a query that contains:</span></span>

```
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

<span data-ttu-id="ff7cf-142">**Предварительные требования:**</span><span class="sxs-lookup"><span data-stu-id="ff7cf-142">**Prerequisites:**</span></span>

- <span data-ttu-id="ff7cf-143">Клиенты должны иметь подписку на Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-143">Customers must have a subscription for Azure Information Protection.</span></span>
- <span data-ttu-id="ff7cf-144">Включение интеграции Azure information Protection в Центре безопасности Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="ff7cf-144">Enable Azure Information Protection integration in Microsoft Defender Security Center:</span></span>
    - <span data-ttu-id="ff7cf-145">Перейдите **к параметрам** в Центре безопасности защитника Майкрософт, щелкните **расширенные параметры** под **общим .**</span><span class="sxs-lookup"><span data-stu-id="ff7cf-145">Go to **Settings** in Microsoft Defender Security Center, click on **Advanced Settings** under **General**.</span></span>



