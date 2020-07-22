---
title: Что нового в службе защиты от угроз (Майкрософт)?
description: Перечисляет новые функции и функции системы защиты от угроз Майкрософт
keywords: новые возможности Microsoft Threat Protection, GA, обычно доступные, возможности, доступные, новые
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: fca4889167dd7eb5f57d4980c4b033e0903209eb
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204939"
---
# <a name="whats-new-in-microsoft-threat-protection"></a><span data-ttu-id="dfa02-104">Что нового в службе защиты от угроз (Майкрософт)?</span><span class="sxs-lookup"><span data-stu-id="dfa02-104">What's new in Microsoft Threat Protection</span></span>

<span data-ttu-id="dfa02-105">Приведенные ниже функции обычно доступны в новейшей версии Microsoft Threat protection.</span><span class="sxs-lookup"><span data-stu-id="dfa02-105">The following features are generally available (GA) in the latest release of Microsoft Threat Protection.</span></span>

<span data-ttu-id="dfa02-106">RSS-канал: получите уведомление, когда эта страница будет обновлена, скопировав и вставив следующий URL-адрес в устройство чтения веб-каналов:</span><span class="sxs-lookup"><span data-stu-id="dfa02-106">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
## <a name="july-2020"></a><span data-ttu-id="dfa02-107">Июль 2020 г.</span><span class="sxs-lookup"><span data-stu-id="dfa02-107">July 2020</span></span>
- [<span data-ttu-id="dfa02-108">Функция Филепрофиле ()</span><span class="sxs-lookup"><span data-stu-id="dfa02-108">FileProfile() function</span></span>](advanced-hunting-fileprofile-function.md) <br> <span data-ttu-id="dfa02-109">Используйте эту функцию в [расширенных](advanced-hunting-overview.md) запросах поиска, чтобы расширить результаты с полными сведениями о файлах.</span><span class="sxs-lookup"><span data-stu-id="dfa02-109">Use this function in your [advanced hunting](advanced-hunting-overview.md) queries to enrich results with comprehensive file information.</span></span>
- [<span data-ttu-id="dfa02-110">Таблицы удостоверений и приложений</span><span class="sxs-lookup"><span data-stu-id="dfa02-110">Identity and app tables</span></span>](advanced-hunting-schema-tables.md)<br> <span data-ttu-id="dfa02-111">Получите представление о событиях проверки подлинности, запросах Active Directory и действиях, связанных с приложениями, с помощью таблиц [идентитилогоневентс](advanced-hunting-identitylogonevents-table.md), [идентитикуеревентс](advanced-hunting-identityqueryevents-table.md)и [аппфиливентс](advanced-hunting-appfileevents-table.md) в схеме расширенного поискового запроса.</span><span class="sxs-lookup"><span data-stu-id="dfa02-111">Get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>

## <a name="june-2020"></a><span data-ttu-id="dfa02-112">Июнь 2020 г.</span><span class="sxs-lookup"><span data-stu-id="dfa02-112">June 2020</span></span>
- <span data-ttu-id="dfa02-113">Веб-канал Twitter</span><span class="sxs-lookup"><span data-stu-id="dfa02-113">Twitter feed</span></span> <br> <span data-ttu-id="dfa02-114">Получите новейшие исследования безопасности, сведения о угрозах, новости о продуктах и т. д. в панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="dfa02-114">Get the latest security research, threat intelligence, product news, and more - right inside the dashboard.</span></span>
- [<span data-ttu-id="dfa02-115">Таблица схемы Емаилпостделиверевентс</span><span class="sxs-lookup"><span data-stu-id="dfa02-115">EmailPostDeliveryEvents schema table</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) <br> <span data-ttu-id="dfa02-116">Внедрять сведения о действиях после доставки, выполняемых в сообщениях электронной почты в расширенных запросах на поиск.</span><span class="sxs-lookup"><span data-stu-id="dfa02-116">Incorporate information about post-delivery actions taken on email messages in your advanced hunting queries.</span></span>
- [<span data-ttu-id="dfa02-117">Проверка записей в расширенном поиске</span><span class="sxs-lookup"><span data-stu-id="dfa02-117">Inspect records in advanced hunting</span></span>](advanced-hunting-query-results.md#drill-down-from-query-results) <br> <span data-ttu-id="dfa02-118">Быстро проверить записи в результатах запроса с помощью новой панели сведений.</span><span class="sxs-lookup"><span data-stu-id="dfa02-118">Quickly inspect records in your query results with the new details panel.</span></span>

## <a name="may-2020"></a><span data-ttu-id="dfa02-119">Май 2020 г.</span><span class="sxs-lookup"><span data-stu-id="dfa02-119">May 2020</span></span>
- [<span data-ttu-id="dfa02-120">Настраиваемое обнаружение</span><span class="sxs-lookup"><span data-stu-id="dfa02-120">Custom detections</span></span>](custom-detections-overview.md) <br> <span data-ttu-id="dfa02-121">Используйте расширенные запросы поиска для создания настраиваемых правил обнаружения, которые автоматически отслеживают события безопасности и состояния системы и отвечают на них.</span><span class="sxs-lookup"><span data-stu-id="dfa02-121">Use advanced hunting queries to create custom detection rules that automatically monitor for and respond to security events and system states.</span></span>

## <a name="february-2020"></a><span data-ttu-id="dfa02-122">Февраль 2020 г.</span><span class="sxs-lookup"><span data-stu-id="dfa02-122">February 2020</span></span>
- [<span data-ttu-id="dfa02-123">Инциденты</span><span class="sxs-lookup"><span data-stu-id="dfa02-123">Incidents</span></span>](incidents-overview.md) <br> <span data-ttu-id="dfa02-124">Точно знать, где началась атака, и другие сведения, которые помогут вам понять степень атаки.</span><span class="sxs-lookup"><span data-stu-id="dfa02-124">Know exactly where an attack started and other details to help you see the extent of the attack.</span></span>
- [<span data-ttu-id="dfa02-125">Автоматизированный анализ угроз и реакция на угрозы</span><span class="sxs-lookup"><span data-stu-id="dfa02-125">Automated investigation and response</span></span>](mtp-autoir.md) <br> <span data-ttu-id="dfa02-126">Благодаря AIR служба обеспечения безопасности может значительно повысить потенциал вашей организации по работе с оповещениями безопасности и инцидентами.</span><span class="sxs-lookup"><span data-stu-id="dfa02-126">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span>
- [<span data-ttu-id="dfa02-127">Расширенные возможности поискового по поиску</span><span class="sxs-lookup"><span data-stu-id="dfa02-127">Advanced hunting enhancements</span></span>](advanced-hunting-overview.md) <br> <span data-ttu-id="dfa02-128">Профилактическое профилактическое слежение за угрозами в современной рабочей области с помощью языка запросов Кусто и схемы, оптимизированной для безопасности.</span><span class="sxs-lookup"><span data-stu-id="dfa02-128">Proactively hunt for threats across the modern workspace with Kusto Query Language and a security-optimized schema.</span></span>

## <a name="march-2019"></a><span data-ttu-id="dfa02-129">Март 2019 г.</span><span class="sxs-lookup"><span data-stu-id="dfa02-129">March 2019</span></span>
- <span data-ttu-id="dfa02-130">Расширенная охота на угрозы</span><span class="sxs-lookup"><span data-stu-id="dfa02-130">Advanced hunting</span></span> <br> <span data-ttu-id="dfa02-131">Целевая страница для различных функций поиска, позволяющих проактивно обнаружить угрозы, затрагивающие электронную почту и данные, устройства и удостоверения.</span><span class="sxs-lookup"><span data-stu-id="dfa02-131">Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.</span></span>
- [<span data-ttu-id="dfa02-132">Оценка безопасности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="dfa02-132">Microsoft Secure Score</span></span>](microsoft-secure-score.md) <br> <span data-ttu-id="dfa02-133">Единица измерения уровня безопасности Организации с большим номером, указывающим дополнительные действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="dfa02-133">Measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="dfa02-134">Следуя рекомендациям по оценке безопасности, можно защитить организацию от угроз.</span><span class="sxs-lookup"><span data-stu-id="dfa02-134">Following the Security Score recommendations can protect your organization from threats.</span></span> 
- [<span data-ttu-id="dfa02-135">Отчеты</span><span class="sxs-lookup"><span data-stu-id="dfa02-135">Reports</span></span>](monitoring-and-reporting.md) <br>  <span data-ttu-id="dfa02-136">В этой функции размещаются карты, охватывающие различные области, которые отслеживаются аналитиками и администраторами безопасности в рамках повседневных операций.</span><span class="sxs-lookup"><span data-stu-id="dfa02-136">Features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span>
