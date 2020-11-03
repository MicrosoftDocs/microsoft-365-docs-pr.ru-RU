---
title: Новые возможности защитника Microsoft 365
description: Список новых функций и функций защитника Microsoft 365
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 5214f7c399ab511ec16231e4dda97a2c33b37668
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844708"
---
# <a name="whats-new-in-microsoft-365-defender"></a><span data-ttu-id="19a74-104">Новые возможности защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="19a74-104">What's new in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="19a74-105">В последней версии защитника Microsoft 365 доступны следующие функции (GA).</span><span class="sxs-lookup"><span data-stu-id="19a74-105">The following features are generally available (GA) in the latest release of Microsoft 365 Defender.</span></span>

<span data-ttu-id="19a74-106">RSS-канал: получите уведомление, когда эта страница будет обновлена, скопировав и вставив следующий URL-адрес в устройство чтения веб-каналов:</span><span class="sxs-lookup"><span data-stu-id="19a74-106">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
## <a name="september-2020"></a><span data-ttu-id="19a74-107">Сентябрь 2020 г.</span><span class="sxs-lookup"><span data-stu-id="19a74-107">September 2020</span></span>
- [<span data-ttu-id="19a74-108">Таблица Идентитидиректоревентс</span><span class="sxs-lookup"><span data-stu-id="19a74-108">IdentityDirectoryEvents table</span></span>](advanced-hunting-identitydirectoryevents-table.md) <br> <span data-ttu-id="19a74-109">Поиск событий, связанных с локальным контроллером домена, на котором работает Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="19a74-109">Find events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="19a74-110">Эта таблица [расширенной](advanced-hunting-overview.md) схемы подсистемы Поиск охватывает диапазон событий, связанных с удостоверениями, и системные события на контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="19a74-110">This [advanced hunting](advanced-hunting-overview.md) schema table covers a range of identity-related events and system events on the domain controller.</span></span>
- [<span data-ttu-id="19a74-111">Функция Ассигнедипаддрессес ()</span><span class="sxs-lookup"><span data-stu-id="19a74-111">AssignedIPAddresses() function</span></span>](advanced-hunting-assignedipaddresses-function.md) <br> <span data-ttu-id="19a74-112">Используйте эту функцию в расширенных запросах на поиск, чтобы быстро получить последние IP-адреса, назначенные устройству или последним IP-адресам за определенное время.</span><span class="sxs-lookup"><span data-stu-id="19a74-112">Use this function in your advanced hunting queries to quickly obtain the latest IP addresses assigned to a device or the most recent IP addresses from a specific time.</span></span>

## <a name="july-2020"></a><span data-ttu-id="19a74-113">Июль 2020 г.</span><span class="sxs-lookup"><span data-stu-id="19a74-113">July 2020</span></span>
- [<span data-ttu-id="19a74-114">Функция Филепрофиле ()</span><span class="sxs-lookup"><span data-stu-id="19a74-114">FileProfile() function</span></span>](advanced-hunting-fileprofile-function.md) <br> <span data-ttu-id="19a74-115">Используйте эту функцию в расширенных запросах поиска, чтобы расширить результаты с полными сведениями о файлах.</span><span class="sxs-lookup"><span data-stu-id="19a74-115">Use this function in your advanced hunting queries to enrich results with comprehensive file information.</span></span>
- [<span data-ttu-id="19a74-116">Таблицы удостоверений и приложений</span><span class="sxs-lookup"><span data-stu-id="19a74-116">Identity and app tables</span></span>](advanced-hunting-schema-tables.md)<br> <span data-ttu-id="19a74-117">Получите представление о событиях проверки подлинности, запросах Active Directory и действиях, связанных с приложениями, с помощью таблиц [идентитилогоневентс](advanced-hunting-identitylogonevents-table.md), [идентитикуеревентс](advanced-hunting-identityqueryevents-table.md)и [аппфиливентс](advanced-hunting-appfileevents-table.md) в схеме расширенного поискового запроса.</span><span class="sxs-lookup"><span data-stu-id="19a74-117">Get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>
- [<span data-ttu-id="19a74-118">Запуск слежения</span><span class="sxs-lookup"><span data-stu-id="19a74-118">Go hunt</span></span>](advanced-hunting-go-hunt.md)<br> <span data-ttu-id="19a74-119">Быстрое сведение об инциденте для проверки определенного события, пользователя, устройства или других типов сущностей в расширенном поиске.</span><span class="sxs-lookup"><span data-stu-id="19a74-119">Quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types on advanced hunting.</span></span>

## <a name="june-2020"></a><span data-ttu-id="19a74-120">Июнь 2020 г.</span><span class="sxs-lookup"><span data-stu-id="19a74-120">June 2020</span></span>
- <span data-ttu-id="19a74-121">Веб-канал Twitter</span><span class="sxs-lookup"><span data-stu-id="19a74-121">Twitter feed</span></span> <br> <span data-ttu-id="19a74-122">Получите новейшие исследования безопасности, сведения о угрозах, новости о продуктах и т. д. в панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="19a74-122">Get the latest security research, threat intelligence, product news, and more - right inside the dashboard.</span></span>
- [<span data-ttu-id="19a74-123">Таблица схемы Емаилпостделиверевентс</span><span class="sxs-lookup"><span data-stu-id="19a74-123">EmailPostDeliveryEvents schema table</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) <br> <span data-ttu-id="19a74-124">Внедрять сведения о действиях после доставки, выполняемых в сообщениях электронной почты в расширенных запросах на поиск.</span><span class="sxs-lookup"><span data-stu-id="19a74-124">Incorporate information about post-delivery actions taken on email messages in your advanced hunting queries.</span></span>
- [<span data-ttu-id="19a74-125">Проверка записей в расширенном поиске</span><span class="sxs-lookup"><span data-stu-id="19a74-125">Inspect records in advanced hunting</span></span>](advanced-hunting-query-results.md#drill-down-from-query-results) <br> <span data-ttu-id="19a74-126">Быстро проверить записи в результатах запроса с помощью новой панели сведений.</span><span class="sxs-lookup"><span data-stu-id="19a74-126">Quickly inspect records in your query results with the new details panel.</span></span>

## <a name="may-2020"></a><span data-ttu-id="19a74-127">Май 2020 г.</span><span class="sxs-lookup"><span data-stu-id="19a74-127">May 2020</span></span>
- [<span data-ttu-id="19a74-128">Настраиваемое обнаружение</span><span class="sxs-lookup"><span data-stu-id="19a74-128">Custom detections</span></span>](custom-detections-overview.md) <br> <span data-ttu-id="19a74-129">Используйте расширенные запросы поиска для создания настраиваемых правил обнаружения, которые автоматически отслеживают события безопасности и состояния системы и отвечают на них.</span><span class="sxs-lookup"><span data-stu-id="19a74-129">Use advanced hunting queries to create custom detection rules that automatically monitor for and respond to security events and system states.</span></span>

## <a name="february-2020"></a><span data-ttu-id="19a74-130">Февраль 2020 г.</span><span class="sxs-lookup"><span data-stu-id="19a74-130">February 2020</span></span>
- [<span data-ttu-id="19a74-131">Инциденты</span><span class="sxs-lookup"><span data-stu-id="19a74-131">Incidents</span></span>](incidents-overview.md) <br> <span data-ttu-id="19a74-132">Точно знать, где началась атака, и другие сведения, которые помогут вам понять степень атаки.</span><span class="sxs-lookup"><span data-stu-id="19a74-132">Know exactly where an attack started and other details to help you see the extent of the attack.</span></span>
- [<span data-ttu-id="19a74-133">Автоматизированный анализ угроз и реагирование на них</span><span class="sxs-lookup"><span data-stu-id="19a74-133">Automated investigation and response</span></span>](mtp-autoir.md) <br> <span data-ttu-id="19a74-134">Благодаря AIR служба обеспечения безопасности может значительно повысить потенциал вашей организации по работе с оповещениями безопасности и инцидентами.</span><span class="sxs-lookup"><span data-stu-id="19a74-134">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span>
- [<span data-ttu-id="19a74-135">Расширенные возможности поискового по поиску</span><span class="sxs-lookup"><span data-stu-id="19a74-135">Advanced hunting enhancements</span></span>](advanced-hunting-overview.md) <br> <span data-ttu-id="19a74-136">Профилактическое профилактическое слежение за угрозами в современной рабочей области с помощью языка запросов Кусто и схемы, оптимизированной для безопасности.</span><span class="sxs-lookup"><span data-stu-id="19a74-136">Proactively hunt for threats across the modern workspace with Kusto Query Language and a security-optimized schema.</span></span>

## <a name="march-2019"></a><span data-ttu-id="19a74-137">Март 2019 г.</span><span class="sxs-lookup"><span data-stu-id="19a74-137">March 2019</span></span>
- <span data-ttu-id="19a74-138">Расширенная охота на угрозы</span><span class="sxs-lookup"><span data-stu-id="19a74-138">Advanced hunting</span></span> <br> <span data-ttu-id="19a74-139">Целевая страница для различных функций поиска, позволяющих проактивно обнаружить угрозы, затрагивающие электронную почту и данные, устройства и удостоверения.</span><span class="sxs-lookup"><span data-stu-id="19a74-139">Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.</span></span>
- [<span data-ttu-id="19a74-140">Оценка безопасности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="19a74-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md) <br> <span data-ttu-id="19a74-141">Единица измерения уровня безопасности Организации с большим номером, указывающим дополнительные действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="19a74-141">Measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="19a74-142">Следуя рекомендациям по оценке безопасности, можно защитить организацию от угроз.</span><span class="sxs-lookup"><span data-stu-id="19a74-142">Following the Security Score recommendations can protect your organization from threats.</span></span> 
- [<span data-ttu-id="19a74-143">Отчеты</span><span class="sxs-lookup"><span data-stu-id="19a74-143">Reports</span></span>](monitoring-and-reporting.md) <br>  <span data-ttu-id="19a74-144">В этой функции размещаются карты, охватывающие различные области, которые отслеживаются аналитиками и администраторами безопасности в рамках повседневных операций.</span><span class="sxs-lookup"><span data-stu-id="19a74-144">Features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span>
