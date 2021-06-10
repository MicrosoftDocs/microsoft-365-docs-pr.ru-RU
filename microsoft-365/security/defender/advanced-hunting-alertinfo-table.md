---
title: Таблица AlertInfo в продвинутой схеме охоты
description: Узнайте о событиях генерации оповещений в таблице AlertInfo в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, ссылка на схему, кусто, таблица, столбец, тип данных, описание, AlertInfo, предупреждение, серьезность, категория, MITRE, ATT&CK, Microsoft Defender для Endpoint, Microsoft Defender для Office 365, Microsoft Cloud App Security, MCAS, и Защитник Майкрософт для identity
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
ms.openlocfilehash: 69c9201dbc3458cd4ad09a72f2ea0d7ea3bb2d2a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933701"
---
# <a name="alertinfo"></a><span data-ttu-id="cbe30-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="cbe30-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cbe30-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="cbe30-105">**Applies to:**</span></span>
- <span data-ttu-id="cbe30-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cbe30-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="cbe30-107">Таблица в схеме предварительной охоты содержит сведения о оповещениях из Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Cloud App Security и `AlertInfo` Microsoft Defender for Identity. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="cbe30-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="cbe30-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="cbe30-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="cbe30-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="cbe30-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="cbe30-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="cbe30-110">Column name</span></span> | <span data-ttu-id="cbe30-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="cbe30-111">Data type</span></span> | <span data-ttu-id="cbe30-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cbe30-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="cbe30-113">datetime</span><span class="sxs-lookup"><span data-stu-id="cbe30-113">datetime</span></span> | <span data-ttu-id="cbe30-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="cbe30-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="cbe30-115">string</span><span class="sxs-lookup"><span data-stu-id="cbe30-115">string</span></span> | <span data-ttu-id="cbe30-116">Уникальный идентификатор оповещения</span><span class="sxs-lookup"><span data-stu-id="cbe30-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="cbe30-117">string</span><span class="sxs-lookup"><span data-stu-id="cbe30-117">string</span></span> | <span data-ttu-id="cbe30-118">Название оповещения</span><span class="sxs-lookup"><span data-stu-id="cbe30-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="cbe30-119">string</span><span class="sxs-lookup"><span data-stu-id="cbe30-119">string</span></span> | <span data-ttu-id="cbe30-120">Тип индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="cbe30-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="cbe30-121">string</span><span class="sxs-lookup"><span data-stu-id="cbe30-121">string</span></span> | <span data-ttu-id="cbe30-122">Указывает возможное воздействие (высокое, среднее или низкое) индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="cbe30-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="cbe30-123">string</span><span class="sxs-lookup"><span data-stu-id="cbe30-123">string</span></span> | <span data-ttu-id="cbe30-124">Продукт или служба, которые предоставили сведения об оповещении</span><span class="sxs-lookup"><span data-stu-id="cbe30-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="cbe30-125">Строка</span><span class="sxs-lookup"><span data-stu-id="cbe30-125">string</span></span> | <span data-ttu-id="cbe30-126">Технология обнаружения или датчик, которые определили заметный компонент или действие</span><span class="sxs-lookup"><span data-stu-id="cbe30-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="cbe30-127">Строка</span><span class="sxs-lookup"><span data-stu-id="cbe30-127">string</span></span> | <span data-ttu-id="cbe30-128">МЕТОДЫ ATT MITRE&CK, связанные с действиями, которые вызвали оповещение</span><span class="sxs-lookup"><span data-stu-id="cbe30-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="cbe30-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cbe30-129">Related topics</span></span>
- [<span data-ttu-id="cbe30-130">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="cbe30-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cbe30-131">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="cbe30-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cbe30-132">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="cbe30-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="cbe30-133">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="cbe30-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="cbe30-134">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="cbe30-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="cbe30-135">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="cbe30-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
