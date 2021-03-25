---
title: Таблица EmailEvents в схеме расширенного поиска
description: Узнайте о событиях, связанных с электронной почтой Microsoft 365 в таблице EmailEvents в продвинутой схеме охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, Microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailEvents, network message id, sender, recipient, attachment id, attachment name, malware verdict, phishing verdict, attachment count, link count, url count
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
ms.openlocfilehash: 086d3ef8777685d17fdcdfdcd937cb120810c78a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073957"
---
# <a name="emailevents"></a><span data-ttu-id="ff1c1-104">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="ff1c1-104">EmailEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ff1c1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ff1c1-105">**Applies to:**</span></span>

- <span data-ttu-id="ff1c1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff1c1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ff1c1-107">Таблица в продвинутой схеме охоты содержит сведения о событиях, связанных с обработкой электронных писем `EmailEvents` в Microsoft Defender для Office 365. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ff1c1-107">The `EmailEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about events involving the processing of emails on Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ff1c1-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="ff1c1-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="ff1c1-109">Подробные сведения о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в центре безопасности.</span><span class="sxs-lookup"><span data-stu-id="ff1c1-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="ff1c1-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ff1c1-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ff1c1-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="ff1c1-111">Column name</span></span> | <span data-ttu-id="ff1c1-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ff1c1-112">Data type</span></span> | <span data-ttu-id="ff1c1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ff1c1-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ff1c1-114">datetime</span><span class="sxs-lookup"><span data-stu-id="ff1c1-114">datetime</span></span> | <span data-ttu-id="ff1c1-115">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="ff1c1-115">Date and time when the event was recorded</span></span> |
| `NetworkMessageId` | <span data-ttu-id="ff1c1-116">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-116">string</span></span> | <span data-ttu-id="ff1c1-117">Уникальный идентификатор для электронной почты, созданный Корпорацией Майкрософт 365</span><span class="sxs-lookup"><span data-stu-id="ff1c1-117">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="ff1c1-118">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-118">string</span></span> | <span data-ttu-id="ff1c1-119">Общедоступный идентификатор сообщения электронной почты, устанавливаемый системой отправки электронной почты</span><span class="sxs-lookup"><span data-stu-id="ff1c1-119">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `SenderMailFromAddress` | <span data-ttu-id="ff1c1-120">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-120">string</span></span> | <span data-ttu-id="ff1c1-121">Адрес отправителя электронной почты в заголовке "MAIL FROM", также называемый "отправителем конверта" или "адресом Return-Path"</span><span class="sxs-lookup"><span data-stu-id="ff1c1-121">Sender email address in the MAIL FROM header, also known as the envelope sender or the Return-Path address</span></span> |
| `SenderFromAddress` | <span data-ttu-id="ff1c1-122">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-122">string</span></span> | <span data-ttu-id="ff1c1-123">Адрес электронной почты отправителя в заголовке "ОТ", который получатели электронной почты видят в своих почтовых клиентах</span><span class="sxs-lookup"><span data-stu-id="ff1c1-123">Sender email address in the FROM header, which is visible to email recipients on their email clients</span></span> |
| `SenderDisplayName` | <span data-ttu-id="ff1c1-124">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-124">string</span></span> | <span data-ttu-id="ff1c1-125">Имя отправитель, отображаемого в адресной книге, как правило, сочетание заданного или имени, среднего начального и фамилии</span><span class="sxs-lookup"><span data-stu-id="ff1c1-125">Name of the sender displayed in the address book, typically a combination of a given or first name, a middle initial, and a last name or surname</span></span> |
| `SenderObjectId` | <span data-ttu-id="ff1c1-126">строка</span><span class="sxs-lookup"><span data-stu-id="ff1c1-126">string</span></span> |<span data-ttu-id="ff1c1-127">Уникальный идентификатор учетной записи отправитель в Azure AD</span><span class="sxs-lookup"><span data-stu-id="ff1c1-127">Unique identifier for the sender’s account in Azure AD</span></span> |
| `SenderMailFromDomain` | <span data-ttu-id="ff1c1-128">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-128">string</span></span> | <span data-ttu-id="ff1c1-129">Домен отправителя в заголовке "MAIL FROM", также называемый "отправителем конверта" или "адресом Return-Path"</span><span class="sxs-lookup"><span data-stu-id="ff1c1-129">Sender domain in the MAIL FROM header, also known as the envelope sender or the Return-Path address</span></span> |
| `SenderFromDomain` | <span data-ttu-id="ff1c1-130">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-130">string</span></span> | <span data-ttu-id="ff1c1-131">Домен отправителя электронной почты в заголовке "FROM", который получатели электронной почты видят в своих почтовых клиентах</span><span class="sxs-lookup"><span data-stu-id="ff1c1-131">Sender domain in the FROM header, which is visible to email recipients on their email clients</span></span> |
| `SenderIPv4` | <span data-ttu-id="ff1c1-132">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-132">string</span></span> | <span data-ttu-id="ff1c1-133">IPv4-адрес последнего обнаруженного почтового сервера, который ретранслировал сообщение.</span><span class="sxs-lookup"><span data-stu-id="ff1c1-133">IPv4 address of the last detected mail server that relayed the message</span></span> |
| `SenderIPv6` | <span data-ttu-id="ff1c1-134">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-134">string</span></span> | <span data-ttu-id="ff1c1-135">IPv6-адрес последнего обнаруженного почтового сервера, который ретранслировал сообщение.</span><span class="sxs-lookup"><span data-stu-id="ff1c1-135">IPv6 address of the last detected mail server that relayed the message</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="ff1c1-136">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-136">string</span></span> | <span data-ttu-id="ff1c1-137">Адрес электронной почты получателя или адрес электронной почты получателя после расширения списка рассылки</span><span class="sxs-lookup"><span data-stu-id="ff1c1-137">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `RecipientObjectId` | <span data-ttu-id="ff1c1-138">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-138">string</span></span> | <span data-ttu-id="ff1c1-139">Уникальный идентификатор получателя электронной почты в Azure AD</span><span class="sxs-lookup"><span data-stu-id="ff1c1-139">Unique identifier for the email recipient in Azure AD</span></span> |
| `Subject` | <span data-ttu-id="ff1c1-140">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-140">string</span></span> | <span data-ttu-id="ff1c1-141">Тема письма</span><span class="sxs-lookup"><span data-stu-id="ff1c1-141">Subject of the email</span></span> |
| `EmailClusterId` | <span data-ttu-id="ff1c1-142">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-142">string</span></span> | <span data-ttu-id="ff1c1-143">Идентификатор группы схожих сообщений электронной почты, сгруппированных на основе эвристического анализа их содержания</span><span class="sxs-lookup"><span data-stu-id="ff1c1-143">Identifier for the group of similar emails clustered based on heuristic analysis of their contents</span></span> |
| `EmailDirection` | <span data-ttu-id="ff1c1-144">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-144">string</span></span> | <span data-ttu-id="ff1c1-145">Направление сообщения электронной почты по отношению к вашей сети: "Входящее", "Исходящее" или "Внутри организации"</span><span class="sxs-lookup"><span data-stu-id="ff1c1-145">Direction of the email relative to your network:  Inbound, Outbound, Intra-org</span></span> |
| `DeliveryAction` | <span data-ttu-id="ff1c1-146">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-146">string</span></span> | <span data-ttu-id="ff1c1-147">Действие доставки сообщения электронной почты: "Доставлено", "Спам", "Заблокировано" или "Заменено"</span><span class="sxs-lookup"><span data-stu-id="ff1c1-147">Delivery action of the email: Delivered, Junked, Blocked, or Replaced</span></span> |
| `DeliveryLocation` | <span data-ttu-id="ff1c1-148">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-148">string</span></span> | <span data-ttu-id="ff1c1-149">Место доставки сообщения: "Входящие" или другая папка, локальная или внешняя среда, "Спам", "Карантин", "Не выполнено", "Отброшенные" или "Удаленные"</span><span class="sxs-lookup"><span data-stu-id="ff1c1-149">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |
| `ThreatTypes` | <span data-ttu-id="ff1c1-150">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-150">string</span></span> | <span data-ttu-id="ff1c1-151">Вердикт из стека фильтрации электронной почты о том, содержит ли электронная почта вредоносные программы, фишинг или другие угрозы</span><span class="sxs-lookup"><span data-stu-id="ff1c1-151">Verdict from the email filtering stack on whether the email contains malware, phishing, or other threats</span></span> |
| `ThreatNames` | <span data-ttu-id="ff1c1-152">строка</span><span class="sxs-lookup"><span data-stu-id="ff1c1-152">string</span></span> |<span data-ttu-id="ff1c1-153">Обнаружено имя обнаружения вредоносных программ или других найденных угроз</span><span class="sxs-lookup"><span data-stu-id="ff1c1-153">Detection name for malware or other threats found</span></span> |
| `DetectionMethods` | <span data-ttu-id="ff1c1-154">строка</span><span class="sxs-lookup"><span data-stu-id="ff1c1-154">string</span></span> | <span data-ttu-id="ff1c1-155">Методы обнаружения вредоносных программ, фишинга или других угроз, обнаруженных в электронной почте</span><span class="sxs-lookup"><span data-stu-id="ff1c1-155">Methods used to detect malware, phishing, or other threats found in the email</span></span> |
| `ConfidenceLevel` | <span data-ttu-id="ff1c1-156">строка</span><span class="sxs-lookup"><span data-stu-id="ff1c1-156">string</span></span> | <span data-ttu-id="ff1c1-157">Список уровней доверия к любым решениям о нежелательной почте или фишинге.</span><span class="sxs-lookup"><span data-stu-id="ff1c1-157">List of confidence levels of any spam or phishing verdicts.</span></span> <span data-ttu-id="ff1c1-158">Для нежелательной почты в этом столбце показан уровень доверия к нежелательной почте (SCL), указывающий, что сообщение было пропущено (-1), не было нежелательной почты (0,1), было обнаружено, что нежелательной почты с умеренной уверенностью (5,6) или нежелательной почты с высокой степенью уверенности (9).</span><span class="sxs-lookup"><span data-stu-id="ff1c1-158">For spam, this column shows the spam confidence level (SCL), indicating if the email was skipped (-1), found to be not spam (0,1), found to be spam with moderate confidence (5,6), or found to be spam with high confidence (9).</span></span> <span data-ttu-id="ff1c1-159">Для фишинга в этом столбце отображается уровень доверия "High" или "Low".</span><span class="sxs-lookup"><span data-stu-id="ff1c1-159">For phishing, this column displays whether the confidence level is "High" or "Low".</span></span> |
| `EmailAction` | <span data-ttu-id="ff1c1-160">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-160">string</span></span> | <span data-ttu-id="ff1c1-161">Итоговое действие, выполненное с сообщением электронной почты на основании решений фильтров, политик и действий пользователя: перемещение сообщения в папку "Спам", добавление X-заголовка, изменение темы, перенаправление сообщения, удаление сообщения, отправка в карантин, никаких действий, отправка скрытой копии</span><span class="sxs-lookup"><span data-stu-id="ff1c1-161">Final action taken on the email based on filter verdict, policies, and user actions:  Move message to junk mail folder, Add X-header, Modify subject, Redirect message, Delete message, send to quarantine, No action taken, Bcc message</span></span> |
| `EmailActionPolicy` | <span data-ttu-id="ff1c1-162">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-162">string</span></span> | <span data-ttu-id="ff1c1-163">Примененная политика действий: защита от спама с высокой вероятностью, защита от спама, защита от спама для массовых рассылок, защита от спама фишинга, защита от фишинга — олицетворение доменов, защита от фишинга — олицетворение пользователей, защита от фишинга — спуфинг, защита от фишинга — олицетворение диаграмм, защита от вредоносных программ, безопасные вложения, корпоративные правила транспорта (ETR)</span><span class="sxs-lookup"><span data-stu-id="ff1c1-163">Action policy that took effect: Antispam high-confidence, Antispam, Antispam bulk mail, Antispam phishing, Anti-phishing domain impersonation, Anti-phishing user impersonation, Anti-phishing spoof, Anti-phishing graph impersonation, Antimalware, Safe Attachments, Enterprise Transport Rules (ETR)</span></span> |
| `EmailActionPolicyGuid` | <span data-ttu-id="ff1c1-164">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-164">string</span></span> | <span data-ttu-id="ff1c1-165">Уникальный идентификатор политики, определяющей итоговое действие для сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="ff1c1-165">Unique identifier for the policy that determined the final mail action</span></span> |
| `AttachmentCount` | <span data-ttu-id="ff1c1-166">int</span><span class="sxs-lookup"><span data-stu-id="ff1c1-166">int</span></span> | <span data-ttu-id="ff1c1-167">Количество вложений в сообщении электронной почты</span><span class="sxs-lookup"><span data-stu-id="ff1c1-167">Number of attachments in the email</span></span> |
| `UrlCount` | <span data-ttu-id="ff1c1-168">int</span><span class="sxs-lookup"><span data-stu-id="ff1c1-168">int</span></span> | <span data-ttu-id="ff1c1-169">Количество встроенных URL-адресов в сообщении электронной почты</span><span class="sxs-lookup"><span data-stu-id="ff1c1-169">Number of embedded URLs in the email</span></span> |
| `EmailLanguage` | <span data-ttu-id="ff1c1-170">string</span><span class="sxs-lookup"><span data-stu-id="ff1c1-170">string</span></span> | <span data-ttu-id="ff1c1-171">Обнаруженный язык сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="ff1c1-171">Detected language of the email content</span></span> |
| `Connectors` | <span data-ttu-id="ff1c1-172">строка</span><span class="sxs-lookup"><span data-stu-id="ff1c1-172">string</span></span> | <span data-ttu-id="ff1c1-173">Настраиваемые инструкции, определяемые организационным потоком почты и маршрутом отправки электронной почты</span><span class="sxs-lookup"><span data-stu-id="ff1c1-173">Custom instructions that define organizational mail flow and how the email was routed</span></span> |
| `OrgLevelAction` | <span data-ttu-id="ff1c1-174">строка</span><span class="sxs-lookup"><span data-stu-id="ff1c1-174">string</span></span> | <span data-ttu-id="ff1c1-175">Действия, принятые по электронной почте в ответ на совпадения с политикой, определенной на организационном уровне</span><span class="sxs-lookup"><span data-stu-id="ff1c1-175">Action taken on the email in response to matches to a policy defined at the organizational level</span></span> |
| `OrgLevelPolicy` | <span data-ttu-id="ff1c1-176">строка</span><span class="sxs-lookup"><span data-stu-id="ff1c1-176">string</span></span> | <span data-ttu-id="ff1c1-177">Организационная политика, которая вызвала действия, принятые в электронной почте</span><span class="sxs-lookup"><span data-stu-id="ff1c1-177">Organizational policy that triggered the action taken on the email</span></span> |
| `UserLevelAction` | <span data-ttu-id="ff1c1-178">строка</span><span class="sxs-lookup"><span data-stu-id="ff1c1-178">string</span></span> | <span data-ttu-id="ff1c1-179">Действия, принятые по электронной почте в ответ на совпадения с политикой почтовых ящиков, определенной получателем</span><span class="sxs-lookup"><span data-stu-id="ff1c1-179">Action taken on the email in response to matches to a mailbox policy defined by the recipient</span></span> |
| `UserLevelPolicy` | <span data-ttu-id="ff1c1-180">строка</span><span class="sxs-lookup"><span data-stu-id="ff1c1-180">string</span></span> | <span data-ttu-id="ff1c1-181">Политика почтовых ящиков конечных пользователей, которая вызвала действия, принятые в электронной почте</span><span class="sxs-lookup"><span data-stu-id="ff1c1-181">End-user mailbox policy that triggered the action taken on the email</span></span> |
| `ReportId` | <span data-ttu-id="ff1c1-182">long</span><span class="sxs-lookup"><span data-stu-id="ff1c1-182">long</span></span> | <span data-ttu-id="ff1c1-183">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="ff1c1-183">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="ff1c1-184">Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp.</span><span class="sxs-lookup"><span data-stu-id="ff1c1-184">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ff1c1-185">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ff1c1-185">Related topics</span></span>

- [<span data-ttu-id="ff1c1-186">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="ff1c1-186">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ff1c1-187">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="ff1c1-187">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ff1c1-188">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="ff1c1-188">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ff1c1-189">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="ff1c1-189">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ff1c1-190">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="ff1c1-190">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ff1c1-191">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="ff1c1-191">Apply query best practices</span></span>](advanced-hunting-best-practices.md)