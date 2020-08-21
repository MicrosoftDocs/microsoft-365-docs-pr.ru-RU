---
title: Анализ исправления правил потока обработки почты при задержках
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут научиться использовать медленную аналитику правил потока обработки почты в Центре безопасности &, чтобы определять и исправлять неэффективные или неработающие правила потока обработки почты (также называемые правилами транспорта) в организации.
ms.openlocfilehash: 6319633c47e34d7b62c4f68bfbda7fe298c0deb3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826885"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="50152-103">Устранение медленных аналитических данных о правилах потока обработки почты в Центре соответствия требованиям & безопасности</span><span class="sxs-lookup"><span data-stu-id="50152-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

<span data-ttu-id="50152-104">Неэффективные правила потока обработки почты (также называемые правилами транспорта) могут привести к задержкам потока обработки почты в организации.</span><span class="sxs-lookup"><span data-stu-id="50152-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="50152-105">Она сообщает о правилах потока обработки почты организации.</span><span class="sxs-lookup"><span data-stu-id="50152-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="50152-106">Примеры этих типов правил:</span><span class="sxs-lookup"><span data-stu-id="50152-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="50152-107">Условия, в которых условия **применятся для больших** групп.</span><span class="sxs-lookup"><span data-stu-id="50152-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="50152-108">Условия, в которых используется сложное сопоставление шаблонов регулярных выражений (regex).</span><span class="sxs-lookup"><span data-stu-id="50152-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="50152-109">Условия, при которых используется проверка содержимого во вложениях.</span><span class="sxs-lookup"><span data-stu-id="50152-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="50152-110">**Замедление работы правил** потока обработки почты **(рекомендуемая** для вас области мониторинга потока обработки почты в Центре соответствия требованиям безопасности & уведомляет вас о завершении правила потока обработки почты). [Mail flow dashboard](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="50152-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center notifies you when a mail flow rule is taking too long to complete.</span></span> <span data-ttu-id="50152-111">Эта аналитика появляется только после определения условия (если у вас нет почтовых циклов, аналитика не будет отображаться).</span><span class="sxs-lookup"><span data-stu-id="50152-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="50152-112">Используйте его, чтобы выявлять и точно настроить правила потока обработки почты, чтобы уменьшить задержки потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="50152-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Устранение медленных результатов правил потока обработки почты в рекомендуемой области панели мониторинга потока обработки почты](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="50152-114">Когда вы **щелкаете** "Просмотр сведений" в мини-приложении, появится всплывающая область с дополнительной информацией:</span><span class="sxs-lookup"><span data-stu-id="50152-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="50152-115">**Правило**. Наведите указатель мыши на сводку, чтобы увидеть все условия, исключения и действия правила.</span><span class="sxs-lookup"><span data-stu-id="50152-115">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="50152-116">Можно щелкнуть сводку, чтобы изменить правило в Центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="50152-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="50152-117">**Количество оцениваемых сообщений.** Чтобы [message trace](message-trace-scc.md) просмотреть **примеры сообщений,** примеры которых были затронуты правилом, можно просмотреть образцы сообщений.</span><span class="sxs-lookup"><span data-stu-id="50152-117">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="50152-118">**Среднее время, затраченное на каждое сообщение**</span><span class="sxs-lookup"><span data-stu-id="50152-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="50152-119">**Медицинское время,** проведенное над сообщением: отчество разделяет верхнюю половину данных времени.</span><span class="sxs-lookup"><span data-stu-id="50152-119">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![Всплывающий элемент "Подробности", который отображается после нажатия кнопки "Просмотр сведений" в разделе "Замедление исправлений правил потока обработки почты"](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="50152-121">Дополнительные сведения об условиях и исключениях в правилах обработки почтового потока в Exchange Online см. в статье об условиях и исключениях [(предикатах) правил обработки почтового потока в Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</span><span class="sxs-lookup"><span data-stu-id="50152-121">For more information about conditions and exceptions in mail flow rules in Exchange Online, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="related-topics"></a><span data-ttu-id="50152-122">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="50152-122">Related topics</span></span>

<span data-ttu-id="50152-123">Сведения о других аналитических данных на панели мониторинга потока обработки почты см. в статье "Аналитика потока [обработки почты" в Центре безопасности & соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="50152-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
