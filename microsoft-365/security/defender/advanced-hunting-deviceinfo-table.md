---
title: Таблица DeviceInfo в продвинутой схеме охоты
description: Сведения об ОС, имени компьютера и других сведениях о машине в таблице DeviceInfo в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, ссылка схемы, kusto, таблица, столбец, тип данных, описание, machineinfo, DeviceInfo, устройство, машина, ОС, платформа, пользователи
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 99a07b1517058b0e5ab241aaae9c6899e2994432
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689113"
---
# <a name="deviceinfo"></a><span data-ttu-id="6f462-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="6f462-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6f462-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6f462-105">**Applies to:**</span></span>
- <span data-ttu-id="6f462-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f462-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="6f462-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6f462-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="6f462-108">Таблица в продвинутой схеме охоты содержит сведения о устройствах в организации, включая версию ОС, активных пользователей `DeviceInfo` и имя компьютера. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6f462-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="6f462-109">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="6f462-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="6f462-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="6f462-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6f462-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="6f462-111">Column name</span></span> | <span data-ttu-id="6f462-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6f462-112">Data type</span></span> | <span data-ttu-id="6f462-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6f462-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6f462-114">datetime</span><span class="sxs-lookup"><span data-stu-id="6f462-114">datetime</span></span> | <span data-ttu-id="6f462-115">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="6f462-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="6f462-116">string</span><span class="sxs-lookup"><span data-stu-id="6f462-116">string</span></span> | <span data-ttu-id="6f462-117">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="6f462-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6f462-118">string</span><span class="sxs-lookup"><span data-stu-id="6f462-118">string</span></span> | <span data-ttu-id="6f462-119">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="6f462-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="6f462-120">string</span><span class="sxs-lookup"><span data-stu-id="6f462-120">string</span></span> | <span data-ttu-id="6f462-121">Версия агента конечной точки или датчика, запущенного на компьютере</span><span class="sxs-lookup"><span data-stu-id="6f462-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="6f462-122">Строка</span><span class="sxs-lookup"><span data-stu-id="6f462-122">string</span></span> | <span data-ttu-id="6f462-123">Общедоступный IP-адрес, используемый бортовой машиной для подключения к службе Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="6f462-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="6f462-124">Это может быть IP-адрес самой машины, устройство NAT или прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="6f462-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="6f462-125">string</span><span class="sxs-lookup"><span data-stu-id="6f462-125">string</span></span> | <span data-ttu-id="6f462-126">Архитектура операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="6f462-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="6f462-127">string</span><span class="sxs-lookup"><span data-stu-id="6f462-127">string</span></span> | <span data-ttu-id="6f462-128">Платформа операционной системы, используемой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6f462-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="6f462-129">Это указывает на конкретные операционные системы, в том числе варианты в одной семье, такие как Windows 10 и Windows 7</span><span class="sxs-lookup"><span data-stu-id="6f462-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="6f462-130">Строка</span><span class="sxs-lookup"><span data-stu-id="6f462-130">string</span></span> | <span data-ttu-id="6f462-131">Сборка версии операционной системы, запущенной на компьютере</span><span class="sxs-lookup"><span data-stu-id="6f462-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="6f462-132">boolean</span><span class="sxs-lookup"><span data-stu-id="6f462-132">boolean</span></span> | <span data-ttu-id="6f462-133">Индикатор Boolean о том, присоединяется ли машина к Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6f462-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="6f462-134">Строка</span><span class="sxs-lookup"><span data-stu-id="6f462-134">string</span></span> | <span data-ttu-id="6f462-135">Уникальный идентификатор устройства в Azure AD</span><span class="sxs-lookup"><span data-stu-id="6f462-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="6f462-136">Строка</span><span class="sxs-lookup"><span data-stu-id="6f462-136">string</span></span> | <span data-ttu-id="6f462-137">Список всех пользователей, зарегистрированных на компьютере во время события в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="6f462-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="6f462-138">Строка</span><span class="sxs-lookup"><span data-stu-id="6f462-138">string</span></span> | <span data-ttu-id="6f462-139">Тег машины, добавленный в реестр</span><span class="sxs-lookup"><span data-stu-id="6f462-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="6f462-140">string</span><span class="sxs-lookup"><span data-stu-id="6f462-140">string</span></span> | <span data-ttu-id="6f462-141">Версия операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="6f462-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="6f462-142">string</span><span class="sxs-lookup"><span data-stu-id="6f462-142">string</span></span> | <span data-ttu-id="6f462-143">Машинная группа машины.</span><span class="sxs-lookup"><span data-stu-id="6f462-143">Machine group of the machine.</span></span> <span data-ttu-id="6f462-144">Эта группа используется управлением доступом на основе ролей для определения доступа к машине</span><span class="sxs-lookup"><span data-stu-id="6f462-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="6f462-145">long</span><span class="sxs-lookup"><span data-stu-id="6f462-145">long</span></span> | <span data-ttu-id="6f462-146">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="6f462-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="6f462-147">Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp.</span><span class="sxs-lookup"><span data-stu-id="6f462-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OnboardingStatus` | <span data-ttu-id="6f462-148">Строка</span><span class="sxs-lookup"><span data-stu-id="6f462-148">string</span></span> | <span data-ttu-id="6f462-149">Указывает, является ли устройство в настоящее время на борту или нет в Microsoft Defender Для конечной точки или если устройство не поддерживается</span><span class="sxs-lookup"><span data-stu-id="6f462-149">Indicates whether the device is currently onboarded or not to Microsoft Defender For Endpoint or if the device is not supported</span></span> |
|`AdditionalFields` | <span data-ttu-id="6f462-150">Строка</span><span class="sxs-lookup"><span data-stu-id="6f462-150">string</span></span> | <span data-ttu-id="6f462-151">Дополнительные сведения о событии в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="6f462-151">Additional information about the event in JSON array format</span></span> |
|`DeviceCategory` | <span data-ttu-id="6f462-152">Строка</span><span class="sxs-lookup"><span data-stu-id="6f462-152">string</span></span> | <span data-ttu-id="6f462-153">Более широкая классификация, которая группировать определенные типы устройств в следующих категориях: Endpoint, Network device, IoT, Unknown</span><span class="sxs-lookup"><span data-stu-id="6f462-153">Broader classification that groups certain device types under the following categories: Endpoint, Network device, IoT, Unknown</span></span> |
|`DeviceType` | <span data-ttu-id="6f462-154">Строка</span><span class="sxs-lookup"><span data-stu-id="6f462-154">string</span></span> | <span data-ttu-id="6f462-155">Тип устройства, основанного на целях и функциональных возможностях, таких как сетевое устройство, рабочие станции, сервер, мобильный телефон, игровая консоль или принтер</span><span class="sxs-lookup"><span data-stu-id="6f462-155">Type of device based on purpose and functionality, such as network device, workstation, server, mobile, gaming console, or printer</span></span> |
|`DeviceSubType` | <span data-ttu-id="6f462-156">Строка</span><span class="sxs-lookup"><span data-stu-id="6f462-156">string</span></span> | <span data-ttu-id="6f462-157">Дополнительный модификатор для определенных типов устройств, например, мобильное устройство может быть планшетом или смартфоном</span><span class="sxs-lookup"><span data-stu-id="6f462-157">Additional modifier for certain types of devices, for example, a mobile device can be a tablet or a smartphone</span></span> |
|`Model` | <span data-ttu-id="6f462-158">Строка</span><span class="sxs-lookup"><span data-stu-id="6f462-158">string</span></span> | <span data-ttu-id="6f462-159">Имя модели или номер продукта от поставщика или производителя</span><span class="sxs-lookup"><span data-stu-id="6f462-159">Model name or number of the product from the vendor or manufacturer</span></span> |
|`Vendor` | <span data-ttu-id="6f462-160">Строка</span><span class="sxs-lookup"><span data-stu-id="6f462-160">string</span></span> | <span data-ttu-id="6f462-161">Имя поставщика или производителя продукта</span><span class="sxs-lookup"><span data-stu-id="6f462-161">Name of the product vendor or manufacturer</span></span> |
|`OSDistribution` | <span data-ttu-id="6f462-162">Строка</span><span class="sxs-lookup"><span data-stu-id="6f462-162">string</span></span> | <span data-ttu-id="6f462-163">Распространение платформы ОС, таких как Ubuntu или RedHat для платформ Linux</span><span class="sxs-lookup"><span data-stu-id="6f462-163">Distribution of the OS platform, such as Ubuntu or RedHat for Linux platforms</span></span> |
|`OSVersionInfo` | <span data-ttu-id="6f462-164">Строка</span><span class="sxs-lookup"><span data-stu-id="6f462-164">string</span></span> | <span data-ttu-id="6f462-165">Дополнительные сведения о версии ОС, таких как популярное имя, кодовое имя или номер версии</span><span class="sxs-lookup"><span data-stu-id="6f462-165">Additional information about the OS version, such as the popular name, code name, or version number</span></span> |
|`MergedDeviceIds` | <span data-ttu-id="6f462-166">Строка</span><span class="sxs-lookup"><span data-stu-id="6f462-166">string</span></span> | <span data-ttu-id="6f462-167">Предыдущие ID устройства, которые были назначены одному устройству</span><span class="sxs-lookup"><span data-stu-id="6f462-167">Previous device IDs that have been assigned to the same device</span></span> |
|`MergedToDeviceId` | <span data-ttu-id="6f462-168">Строка</span><span class="sxs-lookup"><span data-stu-id="6f462-168">string</span></span> | <span data-ttu-id="6f462-169">Самый последний ID устройства, присвоенный устройству</span><span class="sxs-lookup"><span data-stu-id="6f462-169">The most recent device ID assigned to a device</span></span> |

<span data-ttu-id="6f462-170">В таблице содержится информация об устройстве на основе пульса, которые являются периодическими отчетами или `DeviceInfo` сигналами с устройства.</span><span class="sxs-lookup"><span data-stu-id="6f462-170">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="6f462-171">Каждые 15 минут устройство отправляет частичное сердцебиение, которое содержит часто меняющиеся атрибуты, такие как `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="6f462-171">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="6f462-172">Один раз в день отправляется полное сердцебиение, содержащее атрибуты устройства.</span><span class="sxs-lookup"><span data-stu-id="6f462-172">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="6f462-173">Чтобы получить последнее состояние устройства, можно использовать следующий пример запроса:</span><span class="sxs-lookup"><span data-stu-id="6f462-173">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="6f462-174">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6f462-174">Related topics</span></span>
- [<span data-ttu-id="6f462-175">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="6f462-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6f462-176">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="6f462-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6f462-177">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="6f462-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6f462-178">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="6f462-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6f462-179">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="6f462-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6f462-180">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="6f462-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
