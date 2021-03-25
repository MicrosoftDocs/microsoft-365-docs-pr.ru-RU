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
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e86cba39663e96beffc00aa94d6cbcdf7a6e1e42
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075102"
---
# <a name="deviceinfo"></a><span data-ttu-id="e0aef-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="e0aef-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e0aef-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e0aef-105">**Applies to:**</span></span>
- [<span data-ttu-id="e0aef-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e0aef-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="e0aef-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="e0aef-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e0aef-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="e0aef-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="e0aef-109">Таблица в продвинутой схеме охоты содержит сведения о устройствах в организации, включая их версию ОС, активных пользователей `DeviceInfo` и имя компьютера. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e0aef-109">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including their OS version, active users, and computer name.</span></span> <span data-ttu-id="e0aef-110">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="e0aef-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="e0aef-111">Сведения о других таблицах в продвинутой схеме охоты см. в справке [о схеме охоты.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="e0aef-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="e0aef-112">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="e0aef-112">Column name</span></span> | <span data-ttu-id="e0aef-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e0aef-113">Data type</span></span> | <span data-ttu-id="e0aef-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e0aef-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e0aef-115">datetime</span><span class="sxs-lookup"><span data-stu-id="e0aef-115">datetime</span></span> | <span data-ttu-id="e0aef-116">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="e0aef-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="e0aef-117">string</span><span class="sxs-lookup"><span data-stu-id="e0aef-117">string</span></span> | <span data-ttu-id="e0aef-118">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="e0aef-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e0aef-119">строка</span><span class="sxs-lookup"><span data-stu-id="e0aef-119">string</span></span> | <span data-ttu-id="e0aef-120">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="e0aef-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ClientVersion` | <span data-ttu-id="e0aef-121">строка</span><span class="sxs-lookup"><span data-stu-id="e0aef-121">string</span></span> | <span data-ttu-id="e0aef-122">Версия агента конечной точки или датчика, запущенного на устройстве</span><span class="sxs-lookup"><span data-stu-id="e0aef-122">Version of the endpoint agent or sensor running on the device</span></span> |
| `PublicIP` | <span data-ttu-id="e0aef-123">строка</span><span class="sxs-lookup"><span data-stu-id="e0aef-123">string</span></span> | <span data-ttu-id="e0aef-124">Общедоступный IP-адрес, используемый на бортовом устройстве для подключения к службе Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="e0aef-124">Public IP address used by the onboarded device to connect to the Defender for Endpoint service.</span></span> <span data-ttu-id="e0aef-125">Это может быть IP-адрес самого устройства, устройство NAT или прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="e0aef-125">This could be the IP address of the device itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="e0aef-126">строка</span><span class="sxs-lookup"><span data-stu-id="e0aef-126">string</span></span> | <span data-ttu-id="e0aef-127">Архитектура операционной системы, запущенной на устройстве</span><span class="sxs-lookup"><span data-stu-id="e0aef-127">Architecture of the operating system running on the device</span></span> |
| `OSPlatform` | <span data-ttu-id="e0aef-128">строка</span><span class="sxs-lookup"><span data-stu-id="e0aef-128">string</span></span> | <span data-ttu-id="e0aef-129">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="e0aef-129">Platform of the operating system running on the device.</span></span> <span data-ttu-id="e0aef-130">Это указывает на определенные операционные системы, в том числе варианты в одной семье, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="e0aef-130">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="e0aef-131">строка</span><span class="sxs-lookup"><span data-stu-id="e0aef-131">string</span></span> | <span data-ttu-id="e0aef-132">Сборка версии операционной системы, запущенной на устройстве</span><span class="sxs-lookup"><span data-stu-id="e0aef-132">Build version of the operating system running on the device</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="e0aef-133">boolean</span><span class="sxs-lookup"><span data-stu-id="e0aef-133">boolean</span></span> | <span data-ttu-id="e0aef-134">Индикатор Boolean о том, присоединяется ли устройство к Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e0aef-134">Boolean indicator of whether device is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="e0aef-135">строка</span><span class="sxs-lookup"><span data-stu-id="e0aef-135">string</span></span> | <span data-ttu-id="e0aef-136">Список всех пользователей, зарегистрированных на устройстве во время события в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="e0aef-136">List of all users that are logged on the device at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="e0aef-137">строка</span><span class="sxs-lookup"><span data-stu-id="e0aef-137">string</span></span> | <span data-ttu-id="e0aef-138">Тег устройства, добавленный в реестр</span><span class="sxs-lookup"><span data-stu-id="e0aef-138">Device tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="e0aef-139">long</span><span class="sxs-lookup"><span data-stu-id="e0aef-139">long</span></span> | <span data-ttu-id="e0aef-140">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="e0aef-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="e0aef-141">Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp.</span><span class="sxs-lookup"><span data-stu-id="e0aef-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="e0aef-142">строка</span><span class="sxs-lookup"><span data-stu-id="e0aef-142">string</span></span> | <span data-ttu-id="e0aef-143">Версия операционной системы, запущенной на устройстве</span><span class="sxs-lookup"><span data-stu-id="e0aef-143">Version of the operating system running on the device</span></span> |
| `MachineGroup` | <span data-ttu-id="e0aef-144">строка</span><span class="sxs-lookup"><span data-stu-id="e0aef-144">string</span></span> | <span data-ttu-id="e0aef-145">Машинная группа машины.</span><span class="sxs-lookup"><span data-stu-id="e0aef-145">Machine group of the machine.</span></span> <span data-ttu-id="e0aef-146">Эта группа используется управлением доступом на основе ролей для определения доступа к машине</span><span class="sxs-lookup"><span data-stu-id="e0aef-146">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e0aef-147">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e0aef-147">Related topics</span></span>
- [<span data-ttu-id="e0aef-148">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="e0aef-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e0aef-149">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="e0aef-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e0aef-150">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="e0aef-150">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
