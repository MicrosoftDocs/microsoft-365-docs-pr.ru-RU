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
description: Администраторы могут узнать, как использовать анализ правил медленного потока обработки почты в Центре безопасности и соответствия требованиям &, чтобы выявлять и исправлять неэффективные или неработоспособные правила потока обработки почты (также известные как правила транспорта) в своей организации.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ef9f26994f563a5f9dad411f2276fd42c28496f9
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029130"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="de33f-103">Исправление анализа медленных правил потока обработки почты в Центре & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="de33f-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="de33f-104">Неэффективные правила потока почты (также известные как правила транспорта) могут привести к задержкам потока почты в организации.</span><span class="sxs-lookup"><span data-stu-id="de33f-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="de33f-105">Эта информация сообщает о правилах потока почты, которые влияют на поток почты организации.</span><span class="sxs-lookup"><span data-stu-id="de33f-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="de33f-106">Примеры таких типов правил:</span><span class="sxs-lookup"><span data-stu-id="de33f-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="de33f-107">Условия, в которых **используется is member для** больших групп.</span><span class="sxs-lookup"><span data-stu-id="de33f-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="de33f-108">Условия, в которых используются сложные шаблоны регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="de33f-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="de33f-109">Условия, в которых используется проверка содержимого во вложениях.</span><span class="sxs-lookup"><span data-stu-id="de33f-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="de33f-110">Анализ **правил** медленного потока  обработки почты в [](mail-flow-insights-v2.md) области "Рекомендуемый для вас" панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям [&](https://protection.office.com) сообщает, что выполнение правила потока обработки почты слишком длинное.</span><span class="sxs-lookup"><span data-stu-id="de33f-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="de33f-111">Эта информация отображается только после обнаружения условия (если у вас нет почтовых циклов, вы не увидите эти данные).</span><span class="sxs-lookup"><span data-stu-id="de33f-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="de33f-112">Это уведомление можно использовать для определения и точной настройки правил потока почты, чтобы уменьшить задержки потока почты.</span><span class="sxs-lookup"><span data-stu-id="de33f-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Исправление статистики о медленных правилах потока почты в области "Рекомендуемые для вас" панели мониторинга потока почты](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="de33f-114">При **нажатии кнопки "Просмотреть сведения о** виджете" появится элемент с дополнительными сведениями:</span><span class="sxs-lookup"><span data-stu-id="de33f-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="de33f-115">**Правило:** вы можете наведя курсор на сводку, чтобы увидеть все условия, исключения и действия правила.</span><span class="sxs-lookup"><span data-stu-id="de33f-115">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="de33f-116">Вы можете щелкнуть сводку, чтобы изменить правило в Центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="de33f-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="de33f-117">**Количество вычисляемого** количества сообщений: можно щелкнуть [](message-trace-scc.md) "Просмотреть образцы сообщений", чтобы просмотреть результаты трассировки сообщений для примера сообщений, на которые повлияло правило. </span><span class="sxs-lookup"><span data-stu-id="de33f-117">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="de33f-118">**Среднее время, затраченное на каждое сообщение**</span><span class="sxs-lookup"><span data-stu-id="de33f-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="de33f-119">**Среднее время, затраченное на сообщение:** среднее значение, отделяя верхнюю половину от данных нижней половины времени.</span><span class="sxs-lookup"><span data-stu-id="de33f-119">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![Flyout Details that appears after clicking View details on the Fix slow mail flow rules insight](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="de33f-121">Дополнительные сведения об условиях и исключениях в правилах потока почты см. в сведениях об условиях и исключениях правил потока почты [(предикатах) в Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</span><span class="sxs-lookup"><span data-stu-id="de33f-121">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="de33f-122">См. также</span><span class="sxs-lookup"><span data-stu-id="de33f-122">See also</span></span>

<span data-ttu-id="de33f-123">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="de33f-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
