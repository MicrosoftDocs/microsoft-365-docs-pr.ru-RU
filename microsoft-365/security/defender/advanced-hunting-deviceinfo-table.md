---
title: Таблица DeviceInfo в продвинутой схеме охоты
description: Сведения об ОС, имени компьютера и других сведениях о машине в таблице DeviceInfo в продвинутой схеме охоты
keywords: продвинутая охота, охота на угрозы, охота на киберугрозы, защита от угроз Майкрософт, Microsoft 365, mtp, m365, поиск, запрос, телеметрия, ссылка на схему, kusto, таблица, столбец, тип данных, описание, machineinfo, DeviceInfo, устройство, машина, ОС, платформа, пользователи
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
ms.openlocfilehash: b5baf4adf9c9abaf746c1d6c3ea1c29c3b471b0b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498601"
---
# <a name="deviceinfo"></a><span data-ttu-id="93f76-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="93f76-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="93f76-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="93f76-105">**Applies to:**</span></span>
- <span data-ttu-id="93f76-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93f76-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="93f76-107">Таблица в продвинутой схеме охоты содержит сведения о устройствах в организации, включая версию ОС, активных пользователей `DeviceInfo` и имя компьютера. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="93f76-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="93f76-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="93f76-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="93f76-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="93f76-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="93f76-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="93f76-110">Column name</span></span> | <span data-ttu-id="93f76-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="93f76-111">Data type</span></span> | <span data-ttu-id="93f76-112">Описание</span><span class="sxs-lookup"><span data-stu-id="93f76-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="93f76-113">datetime</span><span class="sxs-lookup"><span data-stu-id="93f76-113">datetime</span></span> | <span data-ttu-id="93f76-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="93f76-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="93f76-115">string</span><span class="sxs-lookup"><span data-stu-id="93f76-115">string</span></span> | <span data-ttu-id="93f76-116">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="93f76-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="93f76-117">string</span><span class="sxs-lookup"><span data-stu-id="93f76-117">string</span></span> | <span data-ttu-id="93f76-118">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="93f76-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="93f76-119">string</span><span class="sxs-lookup"><span data-stu-id="93f76-119">string</span></span> | <span data-ttu-id="93f76-120">Версия агента конечной точки или датчика, запущенного на компьютере</span><span class="sxs-lookup"><span data-stu-id="93f76-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="93f76-121">string</span><span class="sxs-lookup"><span data-stu-id="93f76-121">string</span></span> | <span data-ttu-id="93f76-122">Общедоступный IP-адрес, используемый бортовой машиной для подключения к службе Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="93f76-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="93f76-123">Это может быть IP-адрес самой машины, устройство NAT или прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="93f76-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="93f76-124">string</span><span class="sxs-lookup"><span data-stu-id="93f76-124">string</span></span> | <span data-ttu-id="93f76-125">Архитектура операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="93f76-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="93f76-126">string</span><span class="sxs-lookup"><span data-stu-id="93f76-126">string</span></span> | <span data-ttu-id="93f76-127">Платформа операционной системы, используемой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="93f76-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="93f76-128">Это указывает на определенные операционные системы, в том числе варианты в одной семье, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="93f76-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="93f76-129">string</span><span class="sxs-lookup"><span data-stu-id="93f76-129">string</span></span> | <span data-ttu-id="93f76-130">Сборка версии операционной системы, запущенной на компьютере</span><span class="sxs-lookup"><span data-stu-id="93f76-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="93f76-131">boolean</span><span class="sxs-lookup"><span data-stu-id="93f76-131">boolean</span></span> | <span data-ttu-id="93f76-132">Индикатор Boolean о том, присоединяется ли машина к Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="93f76-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="93f76-133">string</span><span class="sxs-lookup"><span data-stu-id="93f76-133">string</span></span> | <span data-ttu-id="93f76-134">Уникальный идентификатор устройства в Azure AD</span><span class="sxs-lookup"><span data-stu-id="93f76-134">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="93f76-135">string</span><span class="sxs-lookup"><span data-stu-id="93f76-135">string</span></span> | <span data-ttu-id="93f76-136">Список всех пользователей, зарегистрированных на компьютере во время события в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="93f76-136">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="93f76-137">string</span><span class="sxs-lookup"><span data-stu-id="93f76-137">string</span></span> | <span data-ttu-id="93f76-138">Тег машины, добавленный в реестр</span><span class="sxs-lookup"><span data-stu-id="93f76-138">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="93f76-139">string</span><span class="sxs-lookup"><span data-stu-id="93f76-139">string</span></span> | <span data-ttu-id="93f76-140">Версия операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="93f76-140">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="93f76-141">string</span><span class="sxs-lookup"><span data-stu-id="93f76-141">string</span></span> | <span data-ttu-id="93f76-142">Машинная группа машины.</span><span class="sxs-lookup"><span data-stu-id="93f76-142">Machine group of the machine.</span></span> <span data-ttu-id="93f76-143">Эта группа используется управлением доступом на основе ролей для определения доступа к машине</span><span class="sxs-lookup"><span data-stu-id="93f76-143">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="93f76-144">long</span><span class="sxs-lookup"><span data-stu-id="93f76-144">long</span></span> | <span data-ttu-id="93f76-145">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="93f76-145">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="93f76-146">Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp.</span><span class="sxs-lookup"><span data-stu-id="93f76-146">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="93f76-147">string</span><span class="sxs-lookup"><span data-stu-id="93f76-147">string</span></span> | <span data-ttu-id="93f76-148">Дополнительные сведения о событии в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="93f76-148">Additional information about the event in JSON array format</span></span> |

<span data-ttu-id="93f76-149">В таблице содержится информация об устройстве на основе пульса, которые являются периодическими отчетами или `DeviceInfo` сигналами с устройства.</span><span class="sxs-lookup"><span data-stu-id="93f76-149">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="93f76-150">Каждые 15 минут устройство отправляет частичное сердцебиение, которое содержит часто меняющиеся атрибуты, такие как `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="93f76-150">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="93f76-151">Один раз в день отправляется полное сердцебиение, содержащее атрибуты устройства.</span><span class="sxs-lookup"><span data-stu-id="93f76-151">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="93f76-152">Чтобы получить последнее состояние устройства, можно использовать следующий пример запроса:</span><span class="sxs-lookup"><span data-stu-id="93f76-152">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="93f76-153">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="93f76-153">Related topics</span></span>
- [<span data-ttu-id="93f76-154">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="93f76-154">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="93f76-155">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="93f76-155">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="93f76-156">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="93f76-156">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="93f76-157">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="93f76-157">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="93f76-158">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="93f76-158">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="93f76-159">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="93f76-159">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
