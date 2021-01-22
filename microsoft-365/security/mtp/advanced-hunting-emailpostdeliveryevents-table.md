---
title: Таблица EmailPostDeliveryEvents в схеме advanced hunting
description: Узнайте о действиях после доставки сообщений электронной почты Microsoft 365 в таблице EmailPostDeliveryEvents схемы advanced hunting
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailPostDeliveryEvents, network message id, sender, recipient, attachment id, attachment name, malware verdict, phishing verdict, attachment count, link count, url count
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
ms.openlocfilehash: d7920be05156320411f3907cbcdae88d315b5136
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929713"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="75429-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="75429-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="75429-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="75429-105">**Applies to:**</span></span>
- <span data-ttu-id="75429-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75429-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="75429-107">Таблица в схеме advanced hunting содержит сведения о действиях после доставки сообщений электронной почты, обрабатываемых `EmailPostDeliveryEvents` Microsoft 365. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="75429-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="75429-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="75429-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="75429-109">Для получения подробных сведений о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в Центре безопасности. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="75429-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="75429-110">Чтобы получить дополнительные сведения об отдельных сообщениях электронной почты, можно также использовать таблицы [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) и [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) таблицы.</span><span class="sxs-lookup"><span data-stu-id="75429-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="75429-111">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="75429-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="75429-112">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="75429-112">Column name</span></span> | <span data-ttu-id="75429-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="75429-113">Data type</span></span> | <span data-ttu-id="75429-114">Описание</span><span class="sxs-lookup"><span data-stu-id="75429-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="75429-115">datetime</span><span class="sxs-lookup"><span data-stu-id="75429-115">datetime</span></span> | <span data-ttu-id="75429-116">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="75429-116">Date and time when the event was recorded</span></span> |
| `EventId` | <span data-ttu-id="75429-117">string</span><span class="sxs-lookup"><span data-stu-id="75429-117">string</span></span> | <span data-ttu-id="75429-118">Уникальный идентификатор события</span><span class="sxs-lookup"><span data-stu-id="75429-118">Unique identifier for the event</span></span> |
| `NetworkMessageId` | <span data-ttu-id="75429-119">string</span><span class="sxs-lookup"><span data-stu-id="75429-119">string</span></span> | <span data-ttu-id="75429-120">Уникальный идентификатор электронной почты, созданный Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75429-120">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="75429-121">string</span><span class="sxs-lookup"><span data-stu-id="75429-121">string</span></span> | <span data-ttu-id="75429-122">Общедоступный идентификатор сообщения электронной почты, устанавливаемый системой отправки электронной почты</span><span class="sxs-lookup"><span data-stu-id="75429-122">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="75429-123">string</span><span class="sxs-lookup"><span data-stu-id="75429-123">string</span></span> | <span data-ttu-id="75429-124">Действие, которое было предприняты с объектом</span><span class="sxs-lookup"><span data-stu-id="75429-124">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="75429-125">string</span><span class="sxs-lookup"><span data-stu-id="75429-125">string</span></span> | <span data-ttu-id="75429-126">Тип действия, которое вызвало событие: исправление вручную, фишинговая zap, zap вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="75429-126">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="75429-127">string</span><span class="sxs-lookup"><span data-stu-id="75429-127">string</span></span> | <span data-ttu-id="75429-128">Указывает, было ли действие инициировано администратором (вручную или путем утверждения ожидающих автоматизированных действий) или каким-либо специальным механизмом, таким как автоматическая доставка или автоматическая доставка</span><span class="sxs-lookup"><span data-stu-id="75429-128">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="75429-129">string</span><span class="sxs-lookup"><span data-stu-id="75429-129">string</span></span> | <span data-ttu-id="75429-130">Результат действия</span><span class="sxs-lookup"><span data-stu-id="75429-130">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="75429-131">string</span><span class="sxs-lookup"><span data-stu-id="75429-131">string</span></span> | <span data-ttu-id="75429-132">Адрес электронной почты получателя или адрес электронной почты получателя после расширения списка рассылки</span><span class="sxs-lookup"><span data-stu-id="75429-132">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="75429-133">string</span><span class="sxs-lookup"><span data-stu-id="75429-133">string</span></span> | <span data-ttu-id="75429-134">Место доставки сообщения: "Входящие" или другая папка, локальная или внешняя среда, "Спам", "Карантин", "Не выполнено", "Отброшенные" или "Удаленные"</span><span class="sxs-lookup"><span data-stu-id="75429-134">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="75429-135">Поддерживаемые типы событий</span><span class="sxs-lookup"><span data-stu-id="75429-135">Supported event types</span></span>
<span data-ttu-id="75429-136">В этой таблице фиксировать события со `ActionType` следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="75429-136">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="75429-137">**Исправление вручную** — администратор вручную принял действие над сообщением электронной почты после его доставки в почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="75429-137">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="75429-138">К ним относятся действия, вручную предпринятые с помощью [обозревателя угроз](../office-365-security/threat-explorer.md) или одобрения автоматизированных действий по расследованию и [реагированию на них (AIR).](mtp-autoir-actions.md)</span><span class="sxs-lookup"><span data-stu-id="75429-138">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="75429-139">**Очистка фишинга** — автоматическая очистка [(ZAP)](../office-365-security/zero-hour-auto-purge.md) после доставки фишингового сообщения.</span><span class="sxs-lookup"><span data-stu-id="75429-139">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="75429-140">**ZaP вредоносных** программ — автоматическая очистка (ZAP) в течение нулевого часа приняла действие с сообщением электронной почты, содержащим вредоносную программу после доставки.</span><span class="sxs-lookup"><span data-stu-id="75429-140">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="75429-141">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="75429-141">Related topics</span></span>
- [<span data-ttu-id="75429-142">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="75429-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="75429-143">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="75429-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="75429-144">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="75429-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="75429-145">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="75429-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="75429-146">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="75429-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="75429-147">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="75429-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
