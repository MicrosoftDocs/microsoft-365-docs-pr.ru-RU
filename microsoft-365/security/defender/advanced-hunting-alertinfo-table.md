---
title: Таблица AlertInfo в продвинутой схеме охоты
description: Узнайте о событиях генерации оповещений в таблице AlertInfo в продвинутой схеме охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft threat protection, Microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, severity, category, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS, and Azure ATP
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
ms.openlocfilehash: 1386830a4b3e05009b19a7d0e3a4ea62ce3321f2
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499827"
---
# <a name="alertinfo"></a><span data-ttu-id="8a0a1-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="8a0a1-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8a0a1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8a0a1-105">**Applies to:**</span></span>
- <span data-ttu-id="8a0a1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a0a1-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="8a0a1-107">В таблице в схеме расширенных схем охоты содержатся сведения о оповещениях из `AlertInfo` Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security и Microsoft Defender for Identity. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8a0a1-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="8a0a1-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="8a0a1-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="8a0a1-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="8a0a1-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8a0a1-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="8a0a1-110">Column name</span></span> | <span data-ttu-id="8a0a1-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="8a0a1-111">Data type</span></span> | <span data-ttu-id="8a0a1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8a0a1-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="8a0a1-113">datetime</span><span class="sxs-lookup"><span data-stu-id="8a0a1-113">datetime</span></span> | <span data-ttu-id="8a0a1-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="8a0a1-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="8a0a1-115">string</span><span class="sxs-lookup"><span data-stu-id="8a0a1-115">string</span></span> | <span data-ttu-id="8a0a1-116">Уникальный идентификатор оповещения</span><span class="sxs-lookup"><span data-stu-id="8a0a1-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="8a0a1-117">string</span><span class="sxs-lookup"><span data-stu-id="8a0a1-117">string</span></span> | <span data-ttu-id="8a0a1-118">Название оповещения</span><span class="sxs-lookup"><span data-stu-id="8a0a1-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="8a0a1-119">string</span><span class="sxs-lookup"><span data-stu-id="8a0a1-119">string</span></span> | <span data-ttu-id="8a0a1-120">Тип индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="8a0a1-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="8a0a1-121">string</span><span class="sxs-lookup"><span data-stu-id="8a0a1-121">string</span></span> | <span data-ttu-id="8a0a1-122">Указывает возможное воздействие (высокое, среднее или низкое) индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="8a0a1-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="8a0a1-123">string</span><span class="sxs-lookup"><span data-stu-id="8a0a1-123">string</span></span> | <span data-ttu-id="8a0a1-124">Продукт или служба, которые предоставили сведения об оповещении</span><span class="sxs-lookup"><span data-stu-id="8a0a1-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="8a0a1-125">string</span><span class="sxs-lookup"><span data-stu-id="8a0a1-125">string</span></span> | <span data-ttu-id="8a0a1-126">Технология обнаружения или датчик, которые определили заметный компонент или действие</span><span class="sxs-lookup"><span data-stu-id="8a0a1-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="8a0a1-127">string</span><span class="sxs-lookup"><span data-stu-id="8a0a1-127">string</span></span> | <span data-ttu-id="8a0a1-128">МЕТОДЫ ATT MITRE&CK, связанные с действиями, которые вызвали оповещение</span><span class="sxs-lookup"><span data-stu-id="8a0a1-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8a0a1-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8a0a1-129">Related topics</span></span>
- [<span data-ttu-id="8a0a1-130">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="8a0a1-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8a0a1-131">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="8a0a1-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8a0a1-132">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="8a0a1-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8a0a1-133">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="8a0a1-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8a0a1-134">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="8a0a1-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8a0a1-135">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="8a0a1-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
