---
title: Таблица EmailPostDeliveryEvents в продвинутой схеме охоты
description: Узнайте о действиях после доставки Microsoft 365 электронной почты в таблице EmailPostDeliveryEvents в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, поиск киберугроз, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, ссылка схемы, kusto, таблица, столбец, тип данных, описание, EmailPostDeliveryEvents, сетевой код сообщения, отправитель, получатель, имя вложения, имя вложения, вердикт вредоносных программ, вердикт фишинга, граф вложений, количество ссылок, url-адрес
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
ms.openlocfilehash: 444af2441eef5a3720325656f996e6bcdb42937e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935477"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="21f1d-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="21f1d-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="21f1d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="21f1d-105">**Applies to:**</span></span>
- <span data-ttu-id="21f1d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="21f1d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="21f1d-107">Таблица `EmailPostDeliveryEvents` в [продвинутой](advanced-hunting-overview.md) схеме охоты содержит сведения о действиях после доставки, принятых в сообщениях электронной почты, обрабатываемых Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="21f1d-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="21f1d-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="21f1d-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="21f1d-109">Подробные сведения о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в центре безопасности.</span><span class="sxs-lookup"><span data-stu-id="21f1d-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="21f1d-110">Чтобы получить дополнительные сведения об отдельных сообщениях электронной почты, вы также можете использовать [`EmailEvents`](advanced-hunting-emailevents-table.md) таблицы и [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) таблицы.</span><span class="sxs-lookup"><span data-stu-id="21f1d-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="21f1d-111">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="21f1d-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="21f1d-112">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="21f1d-112">Column name</span></span> | <span data-ttu-id="21f1d-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="21f1d-113">Data type</span></span> | <span data-ttu-id="21f1d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="21f1d-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="21f1d-115">datetime</span><span class="sxs-lookup"><span data-stu-id="21f1d-115">datetime</span></span> | <span data-ttu-id="21f1d-116">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="21f1d-116">Date and time when the event was recorded</span></span> |
| `NetworkMessageId` | <span data-ttu-id="21f1d-117">string</span><span class="sxs-lookup"><span data-stu-id="21f1d-117">string</span></span> | <span data-ttu-id="21f1d-118">Уникальный идентификатор для электронной почты, созданный Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="21f1d-118">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="21f1d-119">string</span><span class="sxs-lookup"><span data-stu-id="21f1d-119">string</span></span> | <span data-ttu-id="21f1d-120">Общедоступный идентификатор сообщения электронной почты, устанавливаемый системой отправки электронной почты</span><span class="sxs-lookup"><span data-stu-id="21f1d-120">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="21f1d-121">string</span><span class="sxs-lookup"><span data-stu-id="21f1d-121">string</span></span> | <span data-ttu-id="21f1d-122">Действия, принятые в отношении объекта</span><span class="sxs-lookup"><span data-stu-id="21f1d-122">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="21f1d-123">Строка</span><span class="sxs-lookup"><span data-stu-id="21f1d-123">string</span></span> | <span data-ttu-id="21f1d-124">Тип действий, которые вызвали событие: исправление вручную, Фишинг ZAP, ZAP вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="21f1d-124">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="21f1d-125">Строка</span><span class="sxs-lookup"><span data-stu-id="21f1d-125">string</span></span> | <span data-ttu-id="21f1d-126">Указывает, было ли вызвано действие администратором (вручную или путем утверждения ожидающих автоматического действия) или каким-либо специальным механизмом, например ZAP или динамической доставкой.</span><span class="sxs-lookup"><span data-stu-id="21f1d-126">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="21f1d-127">Строка</span><span class="sxs-lookup"><span data-stu-id="21f1d-127">string</span></span> | <span data-ttu-id="21f1d-128">Результат действия</span><span class="sxs-lookup"><span data-stu-id="21f1d-128">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="21f1d-129">string</span><span class="sxs-lookup"><span data-stu-id="21f1d-129">string</span></span> | <span data-ttu-id="21f1d-130">Адрес электронной почты получателя или адрес электронной почты получателя после расширения списка рассылки</span><span class="sxs-lookup"><span data-stu-id="21f1d-130">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="21f1d-131">string</span><span class="sxs-lookup"><span data-stu-id="21f1d-131">string</span></span> | <span data-ttu-id="21f1d-132">Место доставки сообщения: "Входящие" или другая папка, локальная или внешняя среда, "Спам", "Карантин", "Не выполнено", "Отброшенные" или "Удаленные"</span><span class="sxs-lookup"><span data-stu-id="21f1d-132">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |
| `ReportId` | <span data-ttu-id="21f1d-133">long</span><span class="sxs-lookup"><span data-stu-id="21f1d-133">long</span></span> | <span data-ttu-id="21f1d-134">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="21f1d-134">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="21f1d-135">Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp.</span><span class="sxs-lookup"><span data-stu-id="21f1d-135">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="21f1d-136">Поддерживаемые типы событий</span><span class="sxs-lookup"><span data-stu-id="21f1d-136">Supported event types</span></span>
<span data-ttu-id="21f1d-137">В этой таблице запечатлены события со `ActionType` следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="21f1d-137">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="21f1d-138">**Исправление вручную** — администратор вручную принял меры по сообщению электронной почты после его доставки в почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="21f1d-138">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="21f1d-139">Это включает действия, принятые вручную с помощью [обозревателя угроз](../office-365-security/threat-explorer.md) или утверждения действий автоматического расследования [и реагирования (AIR).](m365d-autoir-actions.md)</span><span class="sxs-lookup"><span data-stu-id="21f1d-139">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](m365d-autoir-actions.md).</span></span>
- <span data-ttu-id="21f1d-140">**Phish ZAP** — автоматическая очистка нулевого часа [(ZAP)](../office-365-security/zero-hour-auto-purge.md) приняла меры по фишинговой электронной почте после доставки.</span><span class="sxs-lookup"><span data-stu-id="21f1d-140">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="21f1d-141">**ZaP вредоносных** программ — автоматическая очистка нулевого часа (ZAP) приняла меры по сообщению электронной почты, обнаруженного с вредоносными программами после доставки.</span><span class="sxs-lookup"><span data-stu-id="21f1d-141">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="21f1d-142">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="21f1d-142">Related topics</span></span>
- [<span data-ttu-id="21f1d-143">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="21f1d-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="21f1d-144">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="21f1d-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="21f1d-145">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="21f1d-145">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="21f1d-146">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="21f1d-146">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="21f1d-147">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="21f1d-147">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="21f1d-148">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="21f1d-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
