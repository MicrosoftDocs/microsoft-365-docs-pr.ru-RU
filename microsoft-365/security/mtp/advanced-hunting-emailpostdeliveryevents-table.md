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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: f4b34abdbfcbd6c3a2f142001a3d486485c86fcd
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515937"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="6b50f-104">емаилпостделиверевентс</span><span class="sxs-lookup"><span data-stu-id="6b50f-104">EmailPostDeliveryEvents</span></span>

<span data-ttu-id="6b50f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6b50f-105">**Applies to:**</span></span>
- <span data-ttu-id="6b50f-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="6b50f-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="6b50f-107">`EmailPostDeliveryEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о действиях после доставки, выполняемых в сообщениях электронной почты, обработанных Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6b50f-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="6b50f-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="6b50f-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="6b50f-109">Для получения дополнительных сведений об отдельных сообщениях электронной почты можно также использовать [`EmailEvents`](advanced-hunting-emailevents-table.md) таблицы, [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) и [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) .</span><span class="sxs-lookup"><span data-stu-id="6b50f-109">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="6b50f-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="6b50f-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6b50f-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="6b50f-111">Column name</span></span> | <span data-ttu-id="6b50f-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6b50f-112">Data type</span></span> | <span data-ttu-id="6b50f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6b50f-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6b50f-114">datetime</span><span class="sxs-lookup"><span data-stu-id="6b50f-114">datetime</span></span> | <span data-ttu-id="6b50f-115">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="6b50f-115">Date and time when the event was recorded</span></span> |
| `EventId` | <span data-ttu-id="6b50f-116">string</span><span class="sxs-lookup"><span data-stu-id="6b50f-116">string</span></span> | <span data-ttu-id="6b50f-117">Уникальный идентификатор для события</span><span class="sxs-lookup"><span data-stu-id="6b50f-117">Unique identifier for the event</span></span> |
| `NetworkMessageId` | <span data-ttu-id="6b50f-118">string</span><span class="sxs-lookup"><span data-stu-id="6b50f-118">string</span></span> | <span data-ttu-id="6b50f-119">Уникальный идентификатор электронного сообщения, созданного Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6b50f-119">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="6b50f-120">string</span><span class="sxs-lookup"><span data-stu-id="6b50f-120">string</span></span> | <span data-ttu-id="6b50f-121">Общедоступный идентификатор сообщения электронной почты, устанавливаемый системой отправки электронной почты</span><span class="sxs-lookup"><span data-stu-id="6b50f-121">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="6b50f-122">string</span><span class="sxs-lookup"><span data-stu-id="6b50f-122">string</span></span> | <span data-ttu-id="6b50f-123">Действие, выполняемое с объектом</span><span class="sxs-lookup"><span data-stu-id="6b50f-123">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="6b50f-124">string</span><span class="sxs-lookup"><span data-stu-id="6b50f-124">string</span></span> | <span data-ttu-id="6b50f-125">Тип действия, вызвавшего событие: ручное исправление, фишинг ZAP, вредоносный ZAP</span><span class="sxs-lookup"><span data-stu-id="6b50f-125">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="6b50f-126">string</span><span class="sxs-lookup"><span data-stu-id="6b50f-126">string</span></span> | <span data-ttu-id="6b50f-127">Указывает, было ли действие инициировано администратором (вручную или с помощью утверждения ожидающего автоматического действия) или с помощью какого-либо специального механизма, такого как ZAP или динамическая доставка.</span><span class="sxs-lookup"><span data-stu-id="6b50f-127">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="6b50f-128">string</span><span class="sxs-lookup"><span data-stu-id="6b50f-128">string</span></span> | <span data-ttu-id="6b50f-129">Результат действия</span><span class="sxs-lookup"><span data-stu-id="6b50f-129">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="6b50f-130">string</span><span class="sxs-lookup"><span data-stu-id="6b50f-130">string</span></span> | <span data-ttu-id="6b50f-131">Адрес электронной почты получателя или адрес электронной почты получателя после расширения списка рассылки</span><span class="sxs-lookup"><span data-stu-id="6b50f-131">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="6b50f-132">string</span><span class="sxs-lookup"><span data-stu-id="6b50f-132">string</span></span> | <span data-ttu-id="6b50f-133">Место доставки сообщения: "Входящие" или другая папка, локальная или внешняя среда, "Спам", "Карантин", "Не выполнено", "Отброшенные" или "Удаленные"</span><span class="sxs-lookup"><span data-stu-id="6b50f-133">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="6b50f-134">Поддерживаемые типы событий</span><span class="sxs-lookup"><span data-stu-id="6b50f-134">Supported event types</span></span>
<span data-ttu-id="6b50f-135">В этой таблице регистрируются события со следующими `ActionType` значениями:</span><span class="sxs-lookup"><span data-stu-id="6b50f-135">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="6b50f-136">**Ручное исправление** — администратор вручную предпринимает действия над электронным сообщением после его доставки в почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="6b50f-136">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="6b50f-137">Сюда входят действия, выполняемые вручную с помощью [проводника по угрозам](../office-365-security/threat-explorer.md) или утверждения [автоматизированных расследований и действий](mtp-autoir-actions.md), выполняемых в среде.</span><span class="sxs-lookup"><span data-stu-id="6b50f-137">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="6b50f-138">**ФИШИНГ ZAP** — [Автоматическая очистка с нулевой ставкой (ZAP)](../office-365-security/zero-hour-auto-purge.md) выполнила действие по фишинговой почте после доставки.</span><span class="sxs-lookup"><span data-stu-id="6b50f-138">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="6b50f-139">**Вредоносный ZAP** — автоматическая очистка с нулевой нагрузкой (ZAP) заняла бы какое-либо сообщение электронной почты, содержащее вредоносную программу после доставки.</span><span class="sxs-lookup"><span data-stu-id="6b50f-139">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6b50f-140">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6b50f-140">Related topics</span></span>
- [<span data-ttu-id="6b50f-141">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="6b50f-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6b50f-142">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="6b50f-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6b50f-143">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="6b50f-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6b50f-144">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="6b50f-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6b50f-145">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="6b50f-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6b50f-146">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="6b50f-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)