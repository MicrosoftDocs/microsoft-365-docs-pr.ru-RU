---
title: Таблица девицеинфо в схеме расширенного поискового окна
description: Сведения о ОС, имени компьютера и других сведениях о компьютере в таблице Девицеинфо расширенной схемы подсистемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, мачинеинфо, Девицеинфо, устройство, компьютер, ОС, платформа, пользователи
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 526e210a472862593f2652e9b2b21957702c48f0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899283"
---
# <a name="deviceinfo"></a><span data-ttu-id="2f8fa-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="2f8fa-104">DeviceInfo</span></span>

<span data-ttu-id="2f8fa-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="2f8fa-105">**Applies to:**</span></span>
- <span data-ttu-id="2f8fa-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="2f8fa-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="2f8fa-107">`DeviceInfo`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о машинах в Организации, включая версию ОС, активные пользователи и имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="2f8fa-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="2f8fa-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="2f8fa-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="2f8fa-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2f8fa-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2f8fa-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="2f8fa-110">Column name</span></span> | <span data-ttu-id="2f8fa-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2f8fa-111">Data type</span></span> | <span data-ttu-id="2f8fa-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2f8fa-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2f8fa-113">datetime</span><span class="sxs-lookup"><span data-stu-id="2f8fa-113">datetime</span></span> | <span data-ttu-id="2f8fa-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="2f8fa-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="2f8fa-115">string</span><span class="sxs-lookup"><span data-stu-id="2f8fa-115">string</span></span> | <span data-ttu-id="2f8fa-116">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="2f8fa-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2f8fa-117">string</span><span class="sxs-lookup"><span data-stu-id="2f8fa-117">string</span></span> | <span data-ttu-id="2f8fa-118">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="2f8fa-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="2f8fa-119">string</span><span class="sxs-lookup"><span data-stu-id="2f8fa-119">string</span></span> | <span data-ttu-id="2f8fa-120">Версия агента конечной точки или датчика, запущенного на компьютере</span><span class="sxs-lookup"><span data-stu-id="2f8fa-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="2f8fa-121">string</span><span class="sxs-lookup"><span data-stu-id="2f8fa-121">string</span></span> | <span data-ttu-id="2f8fa-122">Общедоступный IP-адрес, используемый подключенным компьютером для подключения к службе Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="2f8fa-122">Public IP address used by the onboarded machine to connect to the Microsoft Defender ATP service.</span></span> <span data-ttu-id="2f8fa-123">Это может быть IP-адрес самого компьютера, устройства NAT или прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="2f8fa-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="2f8fa-124">string</span><span class="sxs-lookup"><span data-stu-id="2f8fa-124">string</span></span> | <span data-ttu-id="2f8fa-125">Архитектура операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="2f8fa-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="2f8fa-126">string</span><span class="sxs-lookup"><span data-stu-id="2f8fa-126">string</span></span> | <span data-ttu-id="2f8fa-127">Платформа операционной системы, используемой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2f8fa-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="2f8fa-128">Это указывает на конкретные операционные системы, в том числе варианты в пределах одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="2f8fa-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="2f8fa-129">string</span><span class="sxs-lookup"><span data-stu-id="2f8fa-129">string</span></span> | <span data-ttu-id="2f8fa-130">Сборка версии операционной системы, запущенной на компьютере</span><span class="sxs-lookup"><span data-stu-id="2f8fa-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="2f8fa-131">boolean</span><span class="sxs-lookup"><span data-stu-id="2f8fa-131">boolean</span></span> | <span data-ttu-id="2f8fa-132">Логический индикатор того, присоединен ли компьютер к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2f8fa-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="2f8fa-133">string</span><span class="sxs-lookup"><span data-stu-id="2f8fa-133">string</span></span> | <span data-ttu-id="2f8fa-134">Список всех пользователей, вошедших в систему на момент события в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="2f8fa-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="2f8fa-135">string</span><span class="sxs-lookup"><span data-stu-id="2f8fa-135">string</span></span> | <span data-ttu-id="2f8fa-136">Тег компьютера добавлен через реестр</span><span class="sxs-lookup"><span data-stu-id="2f8fa-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="2f8fa-137">long</span><span class="sxs-lookup"><span data-stu-id="2f8fa-137">long</span></span> | <span data-ttu-id="2f8fa-138">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="2f8fa-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="2f8fa-139">Чтобы определить уникальные события, этот столбец должен использоваться в сочетании со столбцами DeviceName и timestamp</span><span class="sxs-lookup"><span data-stu-id="2f8fa-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="2f8fa-140">string</span><span class="sxs-lookup"><span data-stu-id="2f8fa-140">string</span></span> | <span data-ttu-id="2f8fa-141">Версия операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="2f8fa-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="2f8fa-142">string</span><span class="sxs-lookup"><span data-stu-id="2f8fa-142">string</span></span> | <span data-ttu-id="2f8fa-143">Группа компьютеров компьютера.</span><span class="sxs-lookup"><span data-stu-id="2f8fa-143">Machine group of the machine.</span></span> <span data-ttu-id="2f8fa-144">Эта группа используется в управлении доступом на основе ролей для определения доступа к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="2f8fa-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2f8fa-145">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="2f8fa-145">Related topics</span></span>
- [<span data-ttu-id="2f8fa-146">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="2f8fa-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2f8fa-147">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="2f8fa-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2f8fa-148">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="2f8fa-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2f8fa-149">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="2f8fa-149">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2f8fa-150">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="2f8fa-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2f8fa-151">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="2f8fa-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
