---
title: Таблица DeviceInfo в продвинутой схеме охоты
description: Сведения об ОС, имени компьютера и других сведениях об устройстве в таблице DeviceInfo в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, поиск, запрос, телеметрия, справочная схема, кусто, таблица, столбец, тип данных, описание, deviceinfo, устройство, ОС, платформа, пользователи, DeviceInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e6a11af94a5d2b2099d14b660cf65c846532ebd1
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500836"
---
# <a name="deviceinfo"></a><span data-ttu-id="303ec-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="303ec-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="303ec-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="303ec-105">**Applies to:**</span></span>
- [<span data-ttu-id="303ec-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="303ec-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="303ec-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="303ec-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="303ec-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="303ec-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="303ec-109">Таблица в продвинутой схеме охоты содержит сведения о устройствах в организации, включая их версию ОС, активных пользователей `DeviceInfo` и имя компьютера. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="303ec-109">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including their OS version, active users, and computer name.</span></span> <span data-ttu-id="303ec-110">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="303ec-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="303ec-111">Сведения о других таблицах в продвинутой схеме охоты см. в справке [о схеме охоты.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="303ec-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="303ec-112">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="303ec-112">Column name</span></span> | <span data-ttu-id="303ec-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="303ec-113">Data type</span></span> | <span data-ttu-id="303ec-114">Описание</span><span class="sxs-lookup"><span data-stu-id="303ec-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="303ec-115">datetime</span><span class="sxs-lookup"><span data-stu-id="303ec-115">datetime</span></span> | <span data-ttu-id="303ec-116">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="303ec-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="303ec-117">string</span><span class="sxs-lookup"><span data-stu-id="303ec-117">string</span></span> | <span data-ttu-id="303ec-118">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="303ec-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="303ec-119">string</span><span class="sxs-lookup"><span data-stu-id="303ec-119">string</span></span> | <span data-ttu-id="303ec-120">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="303ec-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ClientVersion` | <span data-ttu-id="303ec-121">string</span><span class="sxs-lookup"><span data-stu-id="303ec-121">string</span></span> | <span data-ttu-id="303ec-122">Версия агента конечной точки или датчика, запущенного на устройстве</span><span class="sxs-lookup"><span data-stu-id="303ec-122">Version of the endpoint agent or sensor running on the device</span></span> |
| `PublicIP` | <span data-ttu-id="303ec-123">string</span><span class="sxs-lookup"><span data-stu-id="303ec-123">string</span></span> | <span data-ttu-id="303ec-124">Общедоступный IP-адрес, используемый на бортовом устройстве для подключения к службе Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="303ec-124">Public IP address used by the onboarded device to connect to the Defender for Endpoint service.</span></span> <span data-ttu-id="303ec-125">Это может быть IP-адрес самого устройства, устройство NAT или прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="303ec-125">This could be the IP address of the device itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="303ec-126">string</span><span class="sxs-lookup"><span data-stu-id="303ec-126">string</span></span> | <span data-ttu-id="303ec-127">Архитектура операционной системы, запущенной на устройстве</span><span class="sxs-lookup"><span data-stu-id="303ec-127">Architecture of the operating system running on the device</span></span> |
| `OSPlatform` | <span data-ttu-id="303ec-128">string</span><span class="sxs-lookup"><span data-stu-id="303ec-128">string</span></span> | <span data-ttu-id="303ec-129">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="303ec-129">Platform of the operating system running on the device.</span></span> <span data-ttu-id="303ec-130">Это указывает на определенные операционные системы, в том числе варианты в одной семье, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="303ec-130">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="303ec-131">string</span><span class="sxs-lookup"><span data-stu-id="303ec-131">string</span></span> | <span data-ttu-id="303ec-132">Сборка версии операционной системы, запущенной на устройстве</span><span class="sxs-lookup"><span data-stu-id="303ec-132">Build version of the operating system running on the device</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="303ec-133">boolean</span><span class="sxs-lookup"><span data-stu-id="303ec-133">boolean</span></span> | <span data-ttu-id="303ec-134">Индикатор Boolean о том, присоединяется ли устройство к Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="303ec-134">Boolean indicator of whether device is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="303ec-135">string</span><span class="sxs-lookup"><span data-stu-id="303ec-135">string</span></span> | <span data-ttu-id="303ec-136">Список всех пользователей, зарегистрированных на устройстве во время события в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="303ec-136">List of all users that are logged on the device at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="303ec-137">string</span><span class="sxs-lookup"><span data-stu-id="303ec-137">string</span></span> | <span data-ttu-id="303ec-138">Тег устройства, добавленный в реестр</span><span class="sxs-lookup"><span data-stu-id="303ec-138">Device tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="303ec-139">long</span><span class="sxs-lookup"><span data-stu-id="303ec-139">long</span></span> | <span data-ttu-id="303ec-140">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="303ec-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="303ec-141">Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp.</span><span class="sxs-lookup"><span data-stu-id="303ec-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="303ec-142">string</span><span class="sxs-lookup"><span data-stu-id="303ec-142">string</span></span> | <span data-ttu-id="303ec-143">Версия операционной системы, запущенной на устройстве</span><span class="sxs-lookup"><span data-stu-id="303ec-143">Version of the operating system running on the device</span></span> |
| `MachineGroup` | <span data-ttu-id="303ec-144">string</span><span class="sxs-lookup"><span data-stu-id="303ec-144">string</span></span> | <span data-ttu-id="303ec-145">Машинная группа машины.</span><span class="sxs-lookup"><span data-stu-id="303ec-145">Machine group of the machine.</span></span> <span data-ttu-id="303ec-146">Эта группа используется управлением доступом на основе ролей для определения доступа к машине</span><span class="sxs-lookup"><span data-stu-id="303ec-146">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="303ec-147">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="303ec-147">Related topics</span></span>
- [<span data-ttu-id="303ec-148">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="303ec-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="303ec-149">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="303ec-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="303ec-150">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="303ec-150">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
