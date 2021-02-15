---
title: Таблица AlertInfo в схеме повышенной охоты
description: Узнайте о событиях генерации оповещений в таблице AlertInfo схемы повышенной охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, severity, category, MITRE, ATT&CK, MICROSOFT Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS, and Azure ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ac1e28987a944a8f7786af4f10a85362f2f92a80
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929974"
---
# <a name="alertinfo"></a><span data-ttu-id="5ae23-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="5ae23-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5ae23-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5ae23-105">**Applies to:**</span></span>
- <span data-ttu-id="5ae23-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ae23-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="5ae23-107">Таблица в схеме повышенной охоты содержит сведения об оповещениях из Microsoft Defender для `AlertInfo` конечной точки, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender для удостоверений. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5ae23-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="5ae23-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="5ae23-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="5ae23-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="5ae23-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5ae23-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="5ae23-110">Column name</span></span> | <span data-ttu-id="5ae23-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="5ae23-111">Data type</span></span> | <span data-ttu-id="5ae23-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5ae23-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="5ae23-113">datetime</span><span class="sxs-lookup"><span data-stu-id="5ae23-113">datetime</span></span> | <span data-ttu-id="5ae23-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="5ae23-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="5ae23-115">string</span><span class="sxs-lookup"><span data-stu-id="5ae23-115">string</span></span> | <span data-ttu-id="5ae23-116">Уникальный идентификатор оповещения</span><span class="sxs-lookup"><span data-stu-id="5ae23-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="5ae23-117">string</span><span class="sxs-lookup"><span data-stu-id="5ae23-117">string</span></span> | <span data-ttu-id="5ae23-118">Название оповещения</span><span class="sxs-lookup"><span data-stu-id="5ae23-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="5ae23-119">string</span><span class="sxs-lookup"><span data-stu-id="5ae23-119">string</span></span> | <span data-ttu-id="5ae23-120">Тип индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="5ae23-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="5ae23-121">string</span><span class="sxs-lookup"><span data-stu-id="5ae23-121">string</span></span> | <span data-ttu-id="5ae23-122">Указывает возможное воздействие (высокое, среднее или низкое) индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="5ae23-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="5ae23-123">string</span><span class="sxs-lookup"><span data-stu-id="5ae23-123">string</span></span> | <span data-ttu-id="5ae23-124">Продукт или служба, которые предоставили сведения об оповещении</span><span class="sxs-lookup"><span data-stu-id="5ae23-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="5ae23-125">string</span><span class="sxs-lookup"><span data-stu-id="5ae23-125">string</span></span> | <span data-ttu-id="5ae23-126">Технология обнаружения или датчик, которые определили важный компонент или действие</span><span class="sxs-lookup"><span data-stu-id="5ae23-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="5ae23-127">string</span><span class="sxs-lookup"><span data-stu-id="5ae23-127">string</span></span> | <span data-ttu-id="5ae23-128">MITRE ATT&методов CK, связанных с действием, которое вызвало оповещение</span><span class="sxs-lookup"><span data-stu-id="5ae23-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5ae23-129">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="5ae23-129">Related topics</span></span>
- [<span data-ttu-id="5ae23-130">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="5ae23-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5ae23-131">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="5ae23-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5ae23-132">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="5ae23-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5ae23-133">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="5ae23-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5ae23-134">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="5ae23-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5ae23-135">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="5ae23-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
