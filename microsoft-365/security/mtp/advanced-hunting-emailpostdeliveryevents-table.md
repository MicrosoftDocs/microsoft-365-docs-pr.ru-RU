---
title: Таблица емаилпостделиверевентс в схеме расширенного поискового окна
description: Сведения о действиях после доставки, выполняемых в сообщениях электронной почты Microsoft 365 в таблице Емаилпостделиверевентс расширенной схемы подхождения
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справочник по схемам, Кусто, таблица, столбец, тип данных, описание, Емаилпостделиверевентс, идентификатор сетевого сообщения, отправитель, получатель, идентификатор вложения, имя вложения, идентификатор сообщения, отправитель, фишинг вредоносности
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 59e5d0d51997812689c7382d6a27af6f66a27d25
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842612"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="00962-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="00962-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="00962-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="00962-105">**Applies to:**</span></span>
- <span data-ttu-id="00962-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="00962-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="00962-107">`EmailPostDeliveryEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о действиях после доставки, выполняемых в сообщениях электронной почты, обработанных Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="00962-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="00962-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="00962-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="00962-109">Для получения подробных сведений о типах событий ( `ActionType` значений), поддерживаемых таблицей, используйте [встроенную справочную](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) информацию о схеме, доступную в центре обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="00962-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="00962-110">Для получения дополнительных сведений об отдельных сообщениях электронной почты можно также использовать [`EmailEvents`](advanced-hunting-emailevents-table.md) таблицы, [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) и [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) .</span><span class="sxs-lookup"><span data-stu-id="00962-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="00962-111">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="00962-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="00962-112">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="00962-112">Column name</span></span> | <span data-ttu-id="00962-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="00962-113">Data type</span></span> | <span data-ttu-id="00962-114">Описание</span><span class="sxs-lookup"><span data-stu-id="00962-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="00962-115">datetime</span><span class="sxs-lookup"><span data-stu-id="00962-115">datetime</span></span> | <span data-ttu-id="00962-116">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="00962-116">Date and time when the event was recorded</span></span> |
| `EventId` | <span data-ttu-id="00962-117">string</span><span class="sxs-lookup"><span data-stu-id="00962-117">string</span></span> | <span data-ttu-id="00962-118">Уникальный идентификатор для события</span><span class="sxs-lookup"><span data-stu-id="00962-118">Unique identifier for the event</span></span> |
| `NetworkMessageId` | <span data-ttu-id="00962-119">string</span><span class="sxs-lookup"><span data-stu-id="00962-119">string</span></span> | <span data-ttu-id="00962-120">Уникальный идентификатор электронного сообщения, созданного Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="00962-120">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="00962-121">string</span><span class="sxs-lookup"><span data-stu-id="00962-121">string</span></span> | <span data-ttu-id="00962-122">Общедоступный идентификатор сообщения электронной почты, устанавливаемый системой отправки электронной почты</span><span class="sxs-lookup"><span data-stu-id="00962-122">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="00962-123">string</span><span class="sxs-lookup"><span data-stu-id="00962-123">string</span></span> | <span data-ttu-id="00962-124">Действие, выполняемое с объектом</span><span class="sxs-lookup"><span data-stu-id="00962-124">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="00962-125">string</span><span class="sxs-lookup"><span data-stu-id="00962-125">string</span></span> | <span data-ttu-id="00962-126">Тип действия, вызвавшего событие: ручное исправление, фишинг ZAP, вредоносный ZAP</span><span class="sxs-lookup"><span data-stu-id="00962-126">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="00962-127">string</span><span class="sxs-lookup"><span data-stu-id="00962-127">string</span></span> | <span data-ttu-id="00962-128">Указывает, было ли действие инициировано администратором (вручную или с помощью утверждения ожидающего автоматического действия) или с помощью какого-либо специального механизма, такого как ZAP или динамическая доставка.</span><span class="sxs-lookup"><span data-stu-id="00962-128">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="00962-129">string</span><span class="sxs-lookup"><span data-stu-id="00962-129">string</span></span> | <span data-ttu-id="00962-130">Результат действия</span><span class="sxs-lookup"><span data-stu-id="00962-130">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="00962-131">string</span><span class="sxs-lookup"><span data-stu-id="00962-131">string</span></span> | <span data-ttu-id="00962-132">Адрес электронной почты получателя или адрес электронной почты получателя после расширения списка рассылки</span><span class="sxs-lookup"><span data-stu-id="00962-132">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="00962-133">string</span><span class="sxs-lookup"><span data-stu-id="00962-133">string</span></span> | <span data-ttu-id="00962-134">Место доставки сообщения: "Входящие" или другая папка, локальная или внешняя среда, "Спам", "Карантин", "Не выполнено", "Отброшенные" или "Удаленные"</span><span class="sxs-lookup"><span data-stu-id="00962-134">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="00962-135">Поддерживаемые типы событий</span><span class="sxs-lookup"><span data-stu-id="00962-135">Supported event types</span></span>
<span data-ttu-id="00962-136">В этой таблице регистрируются события со следующими `ActionType` значениями:</span><span class="sxs-lookup"><span data-stu-id="00962-136">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="00962-137">**Ручное исправление** — администратор вручную предпринимает действия над электронным сообщением после его доставки в почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="00962-137">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="00962-138">Сюда входят действия, выполняемые вручную с помощью [проводника по угрозам](../office-365-security/threat-explorer.md) или утверждения [автоматизированных расследований и действий](mtp-autoir-actions.md), выполняемых в среде.</span><span class="sxs-lookup"><span data-stu-id="00962-138">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="00962-139">**ФИШИНГ ZAP** — [Автоматическая очистка с нулевой ставкой (ZAP)](../office-365-security/zero-hour-auto-purge.md) выполнила действие по фишинговой почте после доставки.</span><span class="sxs-lookup"><span data-stu-id="00962-139">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="00962-140">**Вредоносный ZAP** — автоматическая очистка с нулевой нагрузкой (ZAP) заняла бы какое-либо сообщение электронной почты, содержащее вредоносную программу после доставки.</span><span class="sxs-lookup"><span data-stu-id="00962-140">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="00962-141">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="00962-141">Related topics</span></span>
- [<span data-ttu-id="00962-142">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="00962-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="00962-143">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="00962-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="00962-144">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="00962-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="00962-145">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="00962-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="00962-146">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="00962-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="00962-147">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="00962-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
