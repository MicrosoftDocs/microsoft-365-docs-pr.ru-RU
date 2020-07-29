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
ms.openlocfilehash: 1a2a8cd91d0cc32dc5a10b1eb1dd28714cd4f6c4
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429970"
---
# <a name="whats-new-in-microsoft-threat-protection"></a><span data-ttu-id="e3f99-104">Что нового в службе защиты от угроз (Майкрософт)?</span><span class="sxs-lookup"><span data-stu-id="e3f99-104">What's new in Microsoft Threat Protection</span></span>

<span data-ttu-id="e3f99-105">Приведенные ниже функции обычно доступны в новейшей версии Microsoft Threat protection.</span><span class="sxs-lookup"><span data-stu-id="e3f99-105">The following features are generally available (GA) in the latest release of Microsoft Threat Protection.</span></span>

<span data-ttu-id="e3f99-106">RSS-канал: получите уведомление, когда эта страница будет обновлена, скопировав и вставив следующий URL-адрес в устройство чтения веб-каналов:</span><span class="sxs-lookup"><span data-stu-id="e3f99-106">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
## <a name="july-2020"></a><span data-ttu-id="e3f99-107">Июль 2020 г.</span><span class="sxs-lookup"><span data-stu-id="e3f99-107">July 2020</span></span>
- [<span data-ttu-id="e3f99-108">Функция Филепрофиле ()</span><span class="sxs-lookup"><span data-stu-id="e3f99-108">FileProfile() function</span></span>](advanced-hunting-fileprofile-function.md) <br> <span data-ttu-id="e3f99-109">Используйте эту функцию в [расширенных](advanced-hunting-overview.md) запросах поиска, чтобы расширить результаты с полными сведениями о файлах.</span><span class="sxs-lookup"><span data-stu-id="e3f99-109">Use this function in your [advanced hunting](advanced-hunting-overview.md) queries to enrich results with comprehensive file information.</span></span>
- [<span data-ttu-id="e3f99-110">Таблицы удостоверений и приложений</span><span class="sxs-lookup"><span data-stu-id="e3f99-110">Identity and app tables</span></span>](advanced-hunting-schema-tables.md)<br> <span data-ttu-id="e3f99-111">Получите представление о событиях проверки подлинности, запросах Active Directory и действиях, связанных с приложениями, с помощью таблиц [идентитилогоневентс](advanced-hunting-identitylogonevents-table.md), [идентитикуеревентс](advanced-hunting-identityqueryevents-table.md)и [аппфиливентс](advanced-hunting-appfileevents-table.md) в схеме расширенного поискового запроса.</span><span class="sxs-lookup"><span data-stu-id="e3f99-111">Get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>
- [<span data-ttu-id="e3f99-112">Запуск слежения</span><span class="sxs-lookup"><span data-stu-id="e3f99-112">Go hunt</span></span>](advanced-hunting-go-hunt.md)<br> <span data-ttu-id="e3f99-113">Быстрое сведение из исследования инцидента для проверки определенного события, пользователя, устройства или других типов сущностей с помощью [расширенных](advanced-hunting-overview.md) возможностей поиска на основе запросов.</span><span class="sxs-lookup"><span data-stu-id="e3f99-113">Quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types using query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span>

## <a name="june-2020"></a><span data-ttu-id="e3f99-114">Июнь 2020 г.</span><span class="sxs-lookup"><span data-stu-id="e3f99-114">June 2020</span></span>
- <span data-ttu-id="e3f99-115">Веб-канал Twitter</span><span class="sxs-lookup"><span data-stu-id="e3f99-115">Twitter feed</span></span> <br> <span data-ttu-id="e3f99-116">Получите новейшие исследования безопасности, сведения о угрозах, новости о продуктах и т. д. в панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="e3f99-116">Get the latest security research, threat intelligence, product news, and more - right inside the dashboard.</span></span>
- [<span data-ttu-id="e3f99-117">Таблица схемы Емаилпостделиверевентс</span><span class="sxs-lookup"><span data-stu-id="e3f99-117">EmailPostDeliveryEvents schema table</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) <br> <span data-ttu-id="e3f99-118">Внедрять сведения о действиях после доставки, выполняемых в сообщениях электронной почты в расширенных запросах на поиск.</span><span class="sxs-lookup"><span data-stu-id="e3f99-118">Incorporate information about post-delivery actions taken on email messages in your advanced hunting queries.</span></span>
- [<span data-ttu-id="e3f99-119">Проверка записей в расширенном поиске</span><span class="sxs-lookup"><span data-stu-id="e3f99-119">Inspect records in advanced hunting</span></span>](advanced-hunting-query-results.md#drill-down-from-query-results) <br> <span data-ttu-id="e3f99-120">Быстро проверить записи в результатах запроса с помощью новой панели сведений.</span><span class="sxs-lookup"><span data-stu-id="e3f99-120">Quickly inspect records in your query results with the new details panel.</span></span>

## <a name="may-2020"></a><span data-ttu-id="e3f99-121">Май 2020 г.</span><span class="sxs-lookup"><span data-stu-id="e3f99-121">May 2020</span></span>
- [<span data-ttu-id="e3f99-122">Настраиваемое обнаружение</span><span class="sxs-lookup"><span data-stu-id="e3f99-122">Custom detections</span></span>](custom-detections-overview.md) <br> <span data-ttu-id="e3f99-123">Используйте расширенные запросы поиска для создания настраиваемых правил обнаружения, которые автоматически отслеживают события безопасности и состояния системы и отвечают на них.</span><span class="sxs-lookup"><span data-stu-id="e3f99-123">Use advanced hunting queries to create custom detection rules that automatically monitor for and respond to security events and system states.</span></span>

## <a name="february-2020"></a><span data-ttu-id="e3f99-124">Февраль 2020 г.</span><span class="sxs-lookup"><span data-stu-id="e3f99-124">February 2020</span></span>
- [<span data-ttu-id="e3f99-125">Инциденты</span><span class="sxs-lookup"><span data-stu-id="e3f99-125">Incidents</span></span>](incidents-overview.md) <br> <span data-ttu-id="e3f99-126">Точно знать, где началась атака, и другие сведения, которые помогут вам понять степень атаки.</span><span class="sxs-lookup"><span data-stu-id="e3f99-126">Know exactly where an attack started and other details to help you see the extent of the attack.</span></span>
- [<span data-ttu-id="e3f99-127">Автоматизированный анализ угроз и реакция на угрозы</span><span class="sxs-lookup"><span data-stu-id="e3f99-127">Automated investigation and response</span></span>](mtp-autoir.md) <br> <span data-ttu-id="e3f99-128">Благодаря AIR служба обеспечения безопасности может значительно повысить потенциал вашей организации по работе с оповещениями безопасности и инцидентами.</span><span class="sxs-lookup"><span data-stu-id="e3f99-128">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span>
- [<span data-ttu-id="e3f99-129">Расширенные возможности поискового по поиску</span><span class="sxs-lookup"><span data-stu-id="e3f99-129">Advanced hunting enhancements</span></span>](advanced-hunting-overview.md) <br> <span data-ttu-id="e3f99-130">Профилактическое профилактическое слежение за угрозами в современной рабочей области с помощью языка запросов Кусто и схемы, оптимизированной для безопасности.</span><span class="sxs-lookup"><span data-stu-id="e3f99-130">Proactively hunt for threats across the modern workspace with Kusto Query Language and a security-optimized schema.</span></span>

## <a name="march-2019"></a><span data-ttu-id="e3f99-131">Март 2019 г.</span><span class="sxs-lookup"><span data-stu-id="e3f99-131">March 2019</span></span>
- <span data-ttu-id="e3f99-132">Расширенная охота на угрозы</span><span class="sxs-lookup"><span data-stu-id="e3f99-132">Advanced hunting</span></span> <br> <span data-ttu-id="e3f99-133">Целевая страница для различных функций поиска, позволяющих проактивно обнаружить угрозы, затрагивающие электронную почту и данные, устройства и удостоверения.</span><span class="sxs-lookup"><span data-stu-id="e3f99-133">Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.</span></span>
- [<span data-ttu-id="e3f99-134">Оценка безопасности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="e3f99-134">Microsoft Secure Score</span></span>](microsoft-secure-score.md) <br> <span data-ttu-id="e3f99-135">Единица измерения уровня безопасности Организации с большим номером, указывающим дополнительные действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="e3f99-135">Measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="e3f99-136">Следуя рекомендациям по оценке безопасности, можно защитить организацию от угроз.</span><span class="sxs-lookup"><span data-stu-id="e3f99-136">Following the Security Score recommendations can protect your organization from threats.</span></span> 
- [<span data-ttu-id="e3f99-137">Отчеты</span><span class="sxs-lookup"><span data-stu-id="e3f99-137">Reports</span></span>](monitoring-and-reporting.md) <br>  <span data-ttu-id="e3f99-138">В этой функции размещаются карты, охватывающие различные области, которые отслеживаются аналитиками и администраторами безопасности в рамках повседневных операций.</span><span class="sxs-lookup"><span data-stu-id="e3f99-138">Features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span>
