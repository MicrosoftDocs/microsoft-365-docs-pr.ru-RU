---
title: Анализ исправления правил потока обработки почты при задержках
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать сведения о правилах медленного потока почты в Центре & безопасности для выявления и устранения неэффективных или нарушенных правил потока почты (также известных как правила транспорта) в своей организации.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 22ce3549077ad9b358165245159393d3e25e61c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924110"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="f5982-103">Исправление анализа правил медленного потока почты в центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="f5982-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f5982-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="f5982-104">**Applies to**</span></span>
- [<span data-ttu-id="f5982-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f5982-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f5982-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="f5982-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f5982-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5982-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="f5982-108">Неэффективные правила потока почты (также известные как правила транспорта) могут привести к задержкам потока почты для организации.</span><span class="sxs-lookup"><span data-stu-id="f5982-108">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="f5982-109">В этом анализе отчеты о правилах потока почты, которые влияют на поток почты организации.</span><span class="sxs-lookup"><span data-stu-id="f5982-109">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="f5982-110">Примеры этих типов правил:</span><span class="sxs-lookup"><span data-stu-id="f5982-110">Examples of these types of rules include:</span></span>

- <span data-ttu-id="f5982-111">Условия, которые **используют Is member для** больших групп.</span><span class="sxs-lookup"><span data-stu-id="f5982-111">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="f5982-112">Условия, в которых используется сложный шаблон регулярного выражения (regex).</span><span class="sxs-lookup"><span data-stu-id="f5982-112">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="f5982-113">Условия, в которых используется проверка контента в вложениях.</span><span class="sxs-lookup"><span data-stu-id="f5982-113">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="f5982-114">Сведения  о правилах медленного потока почты в [](mail-flow-insights-v2.md) рекомендуемой для [](https://protection.office.com) вас области панели мониторинга потока почты в Центре соответствия требованиям безопасности &, когда правило потока почты завершается слишком долго. </span><span class="sxs-lookup"><span data-stu-id="f5982-114">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="f5982-115">Это представление появляется только после обнаружения условия (если у вас нет каких-либо циклов почты, вы не увидите представление).</span><span class="sxs-lookup"><span data-stu-id="f5982-115">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="f5982-116">Вы можете использовать это уведомление, чтобы помочь вам определить и настроить правила потока почты, чтобы уменьшить задержки потока почты.</span><span class="sxs-lookup"><span data-stu-id="f5982-116">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Исправлено представление правил медленного потока почты в рекомендуемой для вас области панели мониторинга потока почты](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="f5982-118">При **нажатии сведений о** просмотре на виджете появляется флажок с дополнительными сведениями:</span><span class="sxs-lookup"><span data-stu-id="f5982-118">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="f5982-119">**Правило.** Вы можете наведите курсор на сводку, чтобы увидеть все условия, исключения и действия правила.</span><span class="sxs-lookup"><span data-stu-id="f5982-119">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="f5982-120">Вы можете нажать на сводку, чтобы изменить правило в центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="f5982-120">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="f5982-121">**Количество оцениваемого** количества сообщений. Вы можете нажать просмотреть примеры сообщений, чтобы просмотреть результаты трассировки сообщений для примера сообщений, затронутых правилом.  [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="f5982-121">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="f5982-122">**Среднее время, затраченное на каждое сообщение**</span><span class="sxs-lookup"><span data-stu-id="f5982-122">**Average time spent on each message**</span></span>
- <span data-ttu-id="f5982-123">**Среднее время, затраченное на сообщение:** среднее значение, которое отделяет верхнюю половину от нижней половины данных времени.</span><span class="sxs-lookup"><span data-stu-id="f5982-123">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![Подробные сведения, которые появляются после нажатия сведений о просмотре сведений о том, как исправить медленное представление правил потока почты](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="f5982-125">Дополнительные сведения об условиях и исключениях в правилах потока почты см. в рубрике Условия и исключения правил потока почты [(предикаты)](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f5982-125">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="f5982-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f5982-126">See also</span></span>

<span data-ttu-id="f5982-127">Сведения о других сведениях в панели мониторинга потока почты см. в странице Анализ потока почты в Центре [& соответствия](mail-flow-insights-v2.md)требованиям.</span><span class="sxs-lookup"><span data-stu-id="f5982-127">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>