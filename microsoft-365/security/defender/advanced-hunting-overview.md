---
title: Обзор — расширенный поиск
description: В статье рассказывается о запросах расширенного выслеживания в Microsoft 365 и о том, как их использовать для профилактического обнаружения угроз и слабых мест в своей сети.
keywords: передовая охота, охота на угрозы, охота на киберугрозы, защита от угроз Майкрософт, Microsoft 365, mtp, m365, поиск, запрос, телеметрия, настраиваемые обнаружения, схема, кусто, microsoft 365, Microsoft Threat Protection
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 0338e87c103bef0f12a45277a14152ef429d0067
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076349"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a><span data-ttu-id="039fd-104">Активная охота на угрозы с расширенным поиском в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="039fd-104">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="039fd-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="039fd-105">**Applies to:**</span></span>
- <span data-ttu-id="039fd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="039fd-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="039fd-107">Хотите испытать Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="039fd-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="039fd-108">Вы можете [оценить его в лабораторной среде](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) или запустить [пилотный проект в производстве.](m365d-pilot.md?ocid=cx-evalpilot)</span><span class="sxs-lookup"><span data-stu-id="039fd-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="039fd-109">Расширенное выслеживание— это средство для выслеживания угроз на основе запросов, которое позволяет изучать необработанные данные за период до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="039fd-109">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="039fd-110">Вы можете упреждающий осмотр событий в сети, чтобы найти индикаторы и объекты угрозы.</span><span class="sxs-lookup"><span data-stu-id="039fd-110">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="039fd-111">Гибкий доступ к данным позволяет безудержно искать как известные, так и потенциальные угрозы.</span><span class="sxs-lookup"><span data-stu-id="039fd-111">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

<span data-ttu-id="039fd-112">Вы можете использовать одни и те же запросы на поиск угроз для создания пользовательских правил обнаружения.</span><span class="sxs-lookup"><span data-stu-id="039fd-112">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="039fd-113">Эти правила запускаются автоматически для проверки и реагирования на предполагаемые нарушения, неправильного устройства и других выводов.</span><span class="sxs-lookup"><span data-stu-id="039fd-113">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

<span data-ttu-id="039fd-114">Эта возможность аналогична продвинутой охоте [в Microsoft Defender для конечной точки.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)</span><span class="sxs-lookup"><span data-stu-id="039fd-114">This capability is similar to [advanced hunting in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview).</span></span> <span data-ttu-id="039fd-115">Эта возможность доступна в центре безопасности Microsoft 365 и поддерживает запросы, которые проверяют более широкий набор данных из:</span><span class="sxs-lookup"><span data-stu-id="039fd-115">Available in Microsoft 365 security center, this capability supports queries that check a broader data set from:</span></span>

- <span data-ttu-id="039fd-116">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="039fd-116">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="039fd-117">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="039fd-117">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="039fd-118">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="039fd-118">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="039fd-119">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="039fd-119">Microsoft Defender for Identity</span></span>

<span data-ttu-id="039fd-120">Чтобы использовать передовую охоту, [включи Microsoft 365 Defender.](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="039fd-120">To use advanced hunting, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="039fd-121">Начало работы с расширенным выслеживанием</span><span class="sxs-lookup"><span data-stu-id="039fd-121">Get started with advanced hunting</span></span>

<span data-ttu-id="039fd-122">Мы рекомендуем пройти несколько этапов, чтобы быстро начать работу с расширенным поиском.</span><span class="sxs-lookup"><span data-stu-id="039fd-122">We recommend going through several steps to quickly get started with advanced hunting.</span></span>

| <span data-ttu-id="039fd-123">Цель обучения</span><span class="sxs-lookup"><span data-stu-id="039fd-123">Learning goal</span></span> | <span data-ttu-id="039fd-124">Описание</span><span class="sxs-lookup"><span data-stu-id="039fd-124">Description</span></span> | <span data-ttu-id="039fd-125">Ресурс</span><span class="sxs-lookup"><span data-stu-id="039fd-125">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="039fd-126">**Выучат язык**</span><span class="sxs-lookup"><span data-stu-id="039fd-126">**Learn the language**</span></span> | <span data-ttu-id="039fd-127">Advanced hunting is based on [Kusto query language,](/azure/kusto/query/)supporting the same syntax and operators.</span><span class="sxs-lookup"><span data-stu-id="039fd-127">Advanced hunting is based on [Kusto query language](/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="039fd-128">Начать изучение языка запросов можно, выполнив свой первый запрос.</span><span class="sxs-lookup"><span data-stu-id="039fd-128">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="039fd-129">Сведения о языке запросов</span><span class="sxs-lookup"><span data-stu-id="039fd-129">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="039fd-130">**Узнайте, как использовать результаты запроса**</span><span class="sxs-lookup"><span data-stu-id="039fd-130">**Learn how to use the query results**</span></span> | <span data-ttu-id="039fd-131">Узнайте о диаграммах и различных способах просмотра или экспорта результатов.</span><span class="sxs-lookup"><span data-stu-id="039fd-131">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="039fd-132">Узнайте, как быстро настроить запросы, разверлить, чтобы получить более подробную информацию, и принять меры реагирования.</span><span class="sxs-lookup"><span data-stu-id="039fd-132">Explore how you can quickly tweak queries, drill down to get richer information, and take response actions.</span></span> | <span data-ttu-id="039fd-133">- [Работа с результатами запроса](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="039fd-133">- [Work with query results](advanced-hunting-query-results.md)</span></span><br><span data-ttu-id="039fd-134">- [Действие по результатам запроса](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="039fd-134">- [Take action on query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="039fd-135">**Сведения о схеме**</span><span class="sxs-lookup"><span data-stu-id="039fd-135">**Understand the schema**</span></span> | <span data-ttu-id="039fd-136">Формирование четкого и глубокого представления о таблицах схемы и входящих в них столбцах.</span><span class="sxs-lookup"><span data-stu-id="039fd-136">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="039fd-137">Узнайте, где искать данные при построении запросов.</span><span class="sxs-lookup"><span data-stu-id="039fd-137">Learn where to look for data when constructing your queries.</span></span> | <span data-ttu-id="039fd-138">- [Ссылка на схему](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="039fd-138">- [Schema reference](advanced-hunting-schema-tables.md)</span></span><br><span data-ttu-id="039fd-139">- [Переход от Microsoft Defender для конечной точки](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="039fd-139">- [Transition from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md)</span></span> |
| <span data-ttu-id="039fd-140">**Получить советы и примеры экспертов**</span><span class="sxs-lookup"><span data-stu-id="039fd-140">**Get expert tips and examples**</span></span> | <span data-ttu-id="039fd-141">Обучение бесплатно с помощью руководств от экспертов Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="039fd-141">Train for free with guides from Microsoft experts.</span></span> <span data-ttu-id="039fd-142">Возможен поиск в коллекции предварительно настроенных запросов для использования при разных сценариев выслеживания угроз.</span><span class="sxs-lookup"><span data-stu-id="039fd-142">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | <span data-ttu-id="039fd-143">- [Обучение экспертов](advanced-hunting-expert-training.md)</span><span class="sxs-lookup"><span data-stu-id="039fd-143">- [Get expert training](advanced-hunting-expert-training.md)</span></span><br><span data-ttu-id="039fd-144">- [Использование общих запросов](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="039fd-144">- [Use shared queries](advanced-hunting-shared-queries.md)</span></span><br><span data-ttu-id="039fd-145">- [Go hunt](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="039fd-145">- [Go hunt](advanced-hunting-go-hunt.md)</span></span><br><span data-ttu-id="039fd-146">- [Поиск угроз на устройствах, электронной почте, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)</span><span class="sxs-lookup"><span data-stu-id="039fd-146">- [Hunt for threats across devices, emails, apps, and identities](advanced-hunting-query-emails-devices.md)</span></span> |
| <span data-ttu-id="039fd-147">**Оптимизация запросов и обработка ошибок**</span><span class="sxs-lookup"><span data-stu-id="039fd-147">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="039fd-148">Понять, как создавать эффективные и без ошибок запросы.</span><span class="sxs-lookup"><span data-stu-id="039fd-148">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="039fd-149">- [Наилучшие методы запроса](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="039fd-149">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br><span data-ttu-id="039fd-150">- [Обработка ошибок](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="039fd-150">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="039fd-151">**Создание настраиваемой системы обнаружения**</span><span class="sxs-lookup"><span data-stu-id="039fd-151">**Create custom detection rules**</span></span> | <span data-ttu-id="039fd-152">Понимание того, как можно использовать расширенные запросы на охоту для запуска оповещений и автоматически принимать ответные действия.</span><span class="sxs-lookup"><span data-stu-id="039fd-152">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="039fd-153">- [Пользовательский обзор обнаружения](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="039fd-153">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="039fd-154">- [Настраиваемые правила обнаружения](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="039fd-154">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="039fd-155">Получить доступ</span><span class="sxs-lookup"><span data-stu-id="039fd-155">Get access</span></span>
<span data-ttu-id="039fd-156">Чтобы использовать расширенные возможности для охоты или [других возможностей Защитника Microsoft 365,](microsoft-365-defender.md) вам потребуется соответствующая роль в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="039fd-156">To use advanced hunting or other [Microsoft 365 Defender](microsoft-365-defender.md) capabilities, you need an appropriate role in Azure Active Directory.</span></span> <span data-ttu-id="039fd-157">Кроме того, доступ к данным конечной точки определяется настройками управления доступом на основе ролей (RBAC) в Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="039fd-157">Also, your access to endpoint data is determined by role-based access control (RBAC) settings in Microsoft Defender for Endpoint.</span></span> [<span data-ttu-id="039fd-158">Узнайте об управлении доступом к Защитнику Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="039fd-158">Read about managing access to Microsoft 365 Defender</span></span>](m365d-permissions.md)

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="039fd-159">Свежесть данных и частота обновления</span><span class="sxs-lookup"><span data-stu-id="039fd-159">Data freshness and update frequency</span></span>
<span data-ttu-id="039fd-160">Расширенные данные охоты можно классифицируется на два различных типа, каждый из которых консолидируется по-разному.</span><span class="sxs-lookup"><span data-stu-id="039fd-160">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="039fd-161">**Данные событий или действий** заполняют таблицы оповещений, событий безопасности, системных событий и обычных оценок.</span><span class="sxs-lookup"><span data-stu-id="039fd-161">**Event or activity data**—populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="039fd-162">Расширенный поиск получает эти данные практически сразу после того, как собранные ими датчики успешно передают их в соответствующие облачные службы.</span><span class="sxs-lookup"><span data-stu-id="039fd-162">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to the corresponding cloud services.</span></span> <span data-ttu-id="039fd-163">Например, вы можете запрашивать данные о событиях с здоровых датчиков на рабочих станциях или контроллерах домена почти сразу после того, как они будут доступны в Microsoft Defender for Endpoint и Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="039fd-163">For example, you can query event data from healthy sensors on workstations or domain controllers almost immediately after they are available on Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>
- <span data-ttu-id="039fd-164">**Данные Entity** заполняют таблицы сведениями о пользователях и устройствах.</span><span class="sxs-lookup"><span data-stu-id="039fd-164">**Entity data**—populates tables with information about users and devices.</span></span> <span data-ttu-id="039fd-165">Эти данные приходят как из относительно статических источников данных, так и из динамических источников, таких как записи Active Directory и журналы событий.</span><span class="sxs-lookup"><span data-stu-id="039fd-165">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="039fd-166">Чтобы предоставить свежие данные, таблицы обновляются каждые 15 минут, добавляя строки, которые могут быть заполнены не полностью.</span><span class="sxs-lookup"><span data-stu-id="039fd-166">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="039fd-167">Каждые 24 часа данные консолидированы, чтобы вставить запись, содержающую последний, наиболее полный набор данных о каждом объекте.</span><span class="sxs-lookup"><span data-stu-id="039fd-167">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="039fd-168">Часовой пояс</span><span class="sxs-lookup"><span data-stu-id="039fd-168">Time zone</span></span>
<span data-ttu-id="039fd-169">Сведения о времени в продвинутой охоте в часовом поясе UTC.</span><span class="sxs-lookup"><span data-stu-id="039fd-169">Time information in advanced hunting is in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="039fd-170">См. также</span><span class="sxs-lookup"><span data-stu-id="039fd-170">Related topics</span></span>
- [<span data-ttu-id="039fd-171">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="039fd-171">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="039fd-172">Учебные курсы для экспертов</span><span class="sxs-lookup"><span data-stu-id="039fd-172">Get expert training</span></span>](advanced-hunting-expert-training.md)
- [<span data-ttu-id="039fd-173">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="039fd-173">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="039fd-174">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="039fd-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="039fd-175">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="039fd-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="039fd-176">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="039fd-176">Custom detections overview</span></span>](custom-detections-overview.md)