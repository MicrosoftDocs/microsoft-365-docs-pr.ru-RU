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
ms.openlocfilehash: e4d7ec213a4b4d1108c06784fb5e6675c79429c1
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929520"
---
# <a name="alertinfo"></a><span data-ttu-id="55dda-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="55dda-104">AlertInfo</span></span>

<span data-ttu-id="55dda-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="55dda-105">**Applies to:**</span></span>
- <span data-ttu-id="55dda-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="55dda-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="55dda-107">В `AlertInfo` таблице в [расширенной](advanced-hunting-overview.md) схеме Поиск содержатся сведения об оповещениях из пакета ATP для защитника Майкрософт, Office 365 ATP, Microsoft Cloud App Security и Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="55dda-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="55dda-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="55dda-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="55dda-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="55dda-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="55dda-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="55dda-110">Column name</span></span> | <span data-ttu-id="55dda-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="55dda-111">Data type</span></span> | <span data-ttu-id="55dda-112">Описание</span><span class="sxs-lookup"><span data-stu-id="55dda-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="55dda-113">datetime</span><span class="sxs-lookup"><span data-stu-id="55dda-113">datetime</span></span> | <span data-ttu-id="55dda-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="55dda-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="55dda-115">string</span><span class="sxs-lookup"><span data-stu-id="55dda-115">string</span></span> | <span data-ttu-id="55dda-116">Уникальный идентификатор оповещения</span><span class="sxs-lookup"><span data-stu-id="55dda-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="55dda-117">string</span><span class="sxs-lookup"><span data-stu-id="55dda-117">string</span></span> | <span data-ttu-id="55dda-118">Название оповещения</span><span class="sxs-lookup"><span data-stu-id="55dda-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="55dda-119">string</span><span class="sxs-lookup"><span data-stu-id="55dda-119">string</span></span> | <span data-ttu-id="55dda-120">Тип индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="55dda-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="55dda-121">string</span><span class="sxs-lookup"><span data-stu-id="55dda-121">string</span></span> | <span data-ttu-id="55dda-122">Указывает возможное воздействие (высокое, среднее или низкое) индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="55dda-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="55dda-123">string</span><span class="sxs-lookup"><span data-stu-id="55dda-123">string</span></span> | <span data-ttu-id="55dda-124">Продукт или услуга, которые предоставили информацию оповещений</span><span class="sxs-lookup"><span data-stu-id="55dda-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="55dda-125">string</span><span class="sxs-lookup"><span data-stu-id="55dda-125">string</span></span> | <span data-ttu-id="55dda-126">Технология обнаружения или датчик, идентифицирующий существенный компонент или активность</span><span class="sxs-lookup"><span data-stu-id="55dda-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="55dda-127">string</span><span class="sxs-lookup"><span data-stu-id="55dda-127">string</span></span> | <span data-ttu-id="55dda-128">МИТРЕ ATT&а, связанные с действием, которое инициировало оповещение</span><span class="sxs-lookup"><span data-stu-id="55dda-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="55dda-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="55dda-129">Related topics</span></span>
- [<span data-ttu-id="55dda-130">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="55dda-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="55dda-131">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="55dda-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="55dda-132">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="55dda-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="55dda-133">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="55dda-133">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="55dda-134">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="55dda-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="55dda-135">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="55dda-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
