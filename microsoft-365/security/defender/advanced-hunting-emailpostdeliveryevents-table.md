---
title: Таблица EmailPostDeliveryEvents в продвинутой схеме охоты
description: Узнайте о действиях после доставки, принятых в электронной почте Microsoft 365 в таблице EmailPostDeliveryEvents в продвинутой схеме охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, Microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailPostDeliveryEvents, network message id, sender, recipient, attachment id, attachment name, malware verdict, phishing verdict, attachment count, link count, url count
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
ms.technology: m365d
ms.openlocfilehash: 25f1a177571862e92c502b584bbd51801141069a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076701"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="a5f71-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="a5f71-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a5f71-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a5f71-105">**Applies to:**</span></span>
- <span data-ttu-id="a5f71-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5f71-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a5f71-107">Таблица в продвинутой схеме охоты содержит сведения о действиях после доставки, принятых в сообщениях электронной `EmailPostDeliveryEvents` почты, обработанных Корпорацией Майкрософт [](advanced-hunting-overview.md) 365.</span><span class="sxs-lookup"><span data-stu-id="a5f71-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="a5f71-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="a5f71-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="a5f71-109">Подробные сведения о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в центре безопасности.</span><span class="sxs-lookup"><span data-stu-id="a5f71-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="a5f71-110">Чтобы получить дополнительные сведения об отдельных сообщениях электронной почты, вы также можете использовать [`EmailEvents`](advanced-hunting-emailevents-table.md) таблицы и [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) таблицы.</span><span class="sxs-lookup"><span data-stu-id="a5f71-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="a5f71-111">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a5f71-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a5f71-112">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="a5f71-112">Column name</span></span> | <span data-ttu-id="a5f71-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="a5f71-113">Data type</span></span> | <span data-ttu-id="a5f71-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a5f71-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a5f71-115">datetime</span><span class="sxs-lookup"><span data-stu-id="a5f71-115">datetime</span></span> | <span data-ttu-id="a5f71-116">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="a5f71-116">Date and time when the event was recorded</span></span> |
| `NetworkMessageId` | <span data-ttu-id="a5f71-117">string</span><span class="sxs-lookup"><span data-stu-id="a5f71-117">string</span></span> | <span data-ttu-id="a5f71-118">Уникальный идентификатор для электронной почты, созданный Корпорацией Майкрософт 365</span><span class="sxs-lookup"><span data-stu-id="a5f71-118">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="a5f71-119">string</span><span class="sxs-lookup"><span data-stu-id="a5f71-119">string</span></span> | <span data-ttu-id="a5f71-120">Общедоступный идентификатор сообщения электронной почты, устанавливаемый системой отправки электронной почты</span><span class="sxs-lookup"><span data-stu-id="a5f71-120">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="a5f71-121">string</span><span class="sxs-lookup"><span data-stu-id="a5f71-121">string</span></span> | <span data-ttu-id="a5f71-122">Действия, принятые в отношении объекта</span><span class="sxs-lookup"><span data-stu-id="a5f71-122">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="a5f71-123">строка</span><span class="sxs-lookup"><span data-stu-id="a5f71-123">string</span></span> | <span data-ttu-id="a5f71-124">Тип действий, которые вызвали событие: исправление вручную, Фишинг ZAP, ZAP вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="a5f71-124">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="a5f71-125">строка</span><span class="sxs-lookup"><span data-stu-id="a5f71-125">string</span></span> | <span data-ttu-id="a5f71-126">Указывает, было ли вызвано действие администратором (вручную или путем утверждения ожидающих автоматического действия) или каким-либо специальным механизмом, например ZAP или динамической доставкой.</span><span class="sxs-lookup"><span data-stu-id="a5f71-126">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="a5f71-127">строка</span><span class="sxs-lookup"><span data-stu-id="a5f71-127">string</span></span> | <span data-ttu-id="a5f71-128">Результат действия</span><span class="sxs-lookup"><span data-stu-id="a5f71-128">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="a5f71-129">string</span><span class="sxs-lookup"><span data-stu-id="a5f71-129">string</span></span> | <span data-ttu-id="a5f71-130">Адрес электронной почты получателя или адрес электронной почты получателя после расширения списка рассылки</span><span class="sxs-lookup"><span data-stu-id="a5f71-130">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="a5f71-131">string</span><span class="sxs-lookup"><span data-stu-id="a5f71-131">string</span></span> | <span data-ttu-id="a5f71-132">Место доставки сообщения: "Входящие" или другая папка, локальная или внешняя среда, "Спам", "Карантин", "Не выполнено", "Отброшенные" или "Удаленные"</span><span class="sxs-lookup"><span data-stu-id="a5f71-132">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |
| `ReportId` | <span data-ttu-id="a5f71-133">long</span><span class="sxs-lookup"><span data-stu-id="a5f71-133">long</span></span> | <span data-ttu-id="a5f71-134">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="a5f71-134">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="a5f71-135">Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp.</span><span class="sxs-lookup"><span data-stu-id="a5f71-135">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="a5f71-136">Поддерживаемые типы событий</span><span class="sxs-lookup"><span data-stu-id="a5f71-136">Supported event types</span></span>
<span data-ttu-id="a5f71-137">В этой таблице запечатлены события со `ActionType` следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="a5f71-137">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="a5f71-138">**Исправление вручную** — администратор вручную принял меры по сообщению электронной почты после его доставки в почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="a5f71-138">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="a5f71-139">Это включает действия, принятые вручную с помощью [обозревателя угроз](../defender-365-security/threat-explorer.md) или утверждения действий автоматического расследования [и реагирования (AIR).](m365d-autoir-actions.md)</span><span class="sxs-lookup"><span data-stu-id="a5f71-139">This includes actions taken manually through [Threat Explorer](../defender-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](m365d-autoir-actions.md).</span></span>
- <span data-ttu-id="a5f71-140">**Phish ZAP** — автоматическая очистка нулевого часа [(ZAP)](../defender-365-security/zero-hour-auto-purge.md) приняла меры по фишинговой электронной почте после доставки.</span><span class="sxs-lookup"><span data-stu-id="a5f71-140">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../defender-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="a5f71-141">**ZaP вредоносных** программ — автоматическая очистка нулевого часа (ZAP) приняла меры по сообщению электронной почты, обнаруженного с вредоносными программами после доставки.</span><span class="sxs-lookup"><span data-stu-id="a5f71-141">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a5f71-142">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a5f71-142">Related topics</span></span>
- [<span data-ttu-id="a5f71-143">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="a5f71-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a5f71-144">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="a5f71-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a5f71-145">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="a5f71-145">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a5f71-146">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="a5f71-146">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a5f71-147">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="a5f71-147">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a5f71-148">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="a5f71-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
