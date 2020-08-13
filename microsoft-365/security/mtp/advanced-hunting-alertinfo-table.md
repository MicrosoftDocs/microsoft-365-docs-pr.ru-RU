---
title: Таблица алертинфо в схеме расширенного поискового окна
description: Сведения о событиях создания оповещений в таблице Алертинфо расширенной схемы подсистемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справочник по схемам, Кусто, таблица, столбец, тип данных, описание, Алертинфо, предупреждение, серьезность, категория, МИТРЕ, ATT&а,, мдатп, МКАС, Майкрософт для пакета ATP 365, и Azure ATP.
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
ms.openlocfilehash: 36e76ae097dc31c6d7eb7eeff18dd2128ff0cc5c
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649491"
---
# <a name="alertinfo"></a><span data-ttu-id="5e153-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="5e153-104">AlertInfo</span></span>

<span data-ttu-id="5e153-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5e153-105">**Applies to:**</span></span>
- <span data-ttu-id="5e153-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="5e153-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="5e153-107">`AlertInfo`В таблице в [расширенной](advanced-hunting-overview.md) схеме Поиск содержатся сведения об ОПОВЕЩЕНИЯХ из пакета ATP для защитника майкрософт, Office 365 ATP, Microsoft Cloud App Security и Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="5e153-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="5e153-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="5e153-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="5e153-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="5e153-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5e153-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="5e153-110">Column name</span></span> | <span data-ttu-id="5e153-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="5e153-111">Data type</span></span> | <span data-ttu-id="5e153-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5e153-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="5e153-113">datetime</span><span class="sxs-lookup"><span data-stu-id="5e153-113">datetime</span></span> | <span data-ttu-id="5e153-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="5e153-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="5e153-115">string</span><span class="sxs-lookup"><span data-stu-id="5e153-115">string</span></span> | <span data-ttu-id="5e153-116">Уникальный идентификатор оповещения</span><span class="sxs-lookup"><span data-stu-id="5e153-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="5e153-117">string</span><span class="sxs-lookup"><span data-stu-id="5e153-117">string</span></span> | <span data-ttu-id="5e153-118">Название оповещения</span><span class="sxs-lookup"><span data-stu-id="5e153-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="5e153-119">string</span><span class="sxs-lookup"><span data-stu-id="5e153-119">string</span></span> | <span data-ttu-id="5e153-120">Тип индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="5e153-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="5e153-121">string</span><span class="sxs-lookup"><span data-stu-id="5e153-121">string</span></span> | <span data-ttu-id="5e153-122">Указывает возможное воздействие (высокое, среднее или низкое) индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="5e153-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="5e153-123">string</span><span class="sxs-lookup"><span data-stu-id="5e153-123">string</span></span> | <span data-ttu-id="5e153-124">Продукт или услуга, которые предоставили информацию оповещений</span><span class="sxs-lookup"><span data-stu-id="5e153-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="5e153-125">string</span><span class="sxs-lookup"><span data-stu-id="5e153-125">string</span></span> | <span data-ttu-id="5e153-126">Технология обнаружения или датчик, идентифицирующий существенный компонент или активность</span><span class="sxs-lookup"><span data-stu-id="5e153-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="5e153-127">string</span><span class="sxs-lookup"><span data-stu-id="5e153-127">string</span></span> | <span data-ttu-id="5e153-128">МИТРЕ ATT&а, связанные с действием, которое инициировало оповещение</span><span class="sxs-lookup"><span data-stu-id="5e153-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5e153-129">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="5e153-129">Related topics</span></span>
- [<span data-ttu-id="5e153-130">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="5e153-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5e153-131">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="5e153-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5e153-132">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="5e153-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5e153-133">Слежение за устройствами, сообщениями электронной почты, приложениями и удостоверениями</span><span class="sxs-lookup"><span data-stu-id="5e153-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5e153-134">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="5e153-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5e153-135">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="5e153-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
