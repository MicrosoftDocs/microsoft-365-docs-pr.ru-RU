---
title: Устранение медленного анализа правил обработки почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать исправление правил обработки медленных почтовых ящиков в центре безопасности & соответствия требованиям, чтобы выявить и исправить неэффективные и нарушенные правила обработки почтовых ящиков (также называемые правилами транспорта) в Организации.
ms.openlocfilehash: bb1c09c2809260be8086059259a1aeec3f1fb3eb
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577164"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="23c38-103">Устранение медленных почтовых правил в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="23c38-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

<span data-ttu-id="23c38-104">Неэффективные правила для поток обработки почты (также называемые правилами транспорта) могут приводить к задержкам обработки почты для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="23c38-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="23c38-105">Этот отчет содержит правила обработки почты, которые влияют на процесс обработки почты в Организации.</span><span class="sxs-lookup"><span data-stu-id="23c38-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="23c38-106">Ниже приведены примеры этих типов правил.</span><span class="sxs-lookup"><span data-stu-id="23c38-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="23c38-107">Условия использования **— членство** в группах больших групп.</span><span class="sxs-lookup"><span data-stu-id="23c38-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="23c38-108">Условия, в которых используется сложное совпадение с шаблонами регулярных выражений (Regex).</span><span class="sxs-lookup"><span data-stu-id="23c38-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="23c38-109">Условия, в которых используется проверка содержимого во вложениях.</span><span class="sxs-lookup"><span data-stu-id="23c38-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="23c38-110">В разделе " **Устранение медленных почтовых ящиков** " в области " **Рекомендуемые для вас** [" панели мониторинга "](mail-flow-insights-v2.md) безопасность & соответствия требованиям" отображается уведомление о том, что выполнение правила обработки почтового процесса занимает слишком много времени.</span><span class="sxs-lookup"><span data-stu-id="23c38-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center notifies you when a mail flow rule is taking too long to complete.</span></span> <span data-ttu-id="23c38-111">Эта информация отображается только после того, как будет обнаружено условие (если у вас нет почтовых циклов, вы не увидите сведения).</span><span class="sxs-lookup"><span data-stu-id="23c38-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="23c38-112">С помощью этого уведомления вы можете определить и настроить правила для обработки почты, чтобы снизить задержку обработки почты.</span><span class="sxs-lookup"><span data-stu-id="23c38-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Устранение медленных почтовых правил в области "Рекомендуемые для вас" панели мониторинга почтового процесса](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="23c38-114">При нажатии кнопки **Просмотреть сведения** на мини-приложение появляется раскрывающееся меню с дополнительными сведениями:</span><span class="sxs-lookup"><span data-stu-id="23c38-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="23c38-115">**Правило**: вы можете навести указатель на сводную информацию, чтобы увидеть все условия, исключения и действия правила.</span><span class="sxs-lookup"><span data-stu-id="23c38-115">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="23c38-116">Чтобы изменить правило в центре администрирования Exchange, щелкните сводную информацию.</span><span class="sxs-lookup"><span data-stu-id="23c38-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="23c38-117">**Число оцененных сообщений**: вы можете щелкнуть **Просмотреть примеры сообщений** , чтобы просмотреть результаты [трассировки сообщений](message-trace-scc.md) для примера сообщений, на которые повлияло правило.</span><span class="sxs-lookup"><span data-stu-id="23c38-117">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="23c38-118">**Среднее время, затраченное на каждое сообщение**</span><span class="sxs-lookup"><span data-stu-id="23c38-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="23c38-119">**Среднее время, затраченное на сообщение**: среднее значение, которое отделяет верхнюю половину от нижней половины данных времени.</span><span class="sxs-lookup"><span data-stu-id="23c38-119">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![Всплывающее меню сведений, которое появляется после нажатия кнопки Просмотр сведений в разделе Устранение проблем с медленным почтовыми сообщениями](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="23c38-121">Дополнительные сведения об условиях и исключениях в правилах обработки почтового ящика в Exchange Online можно узнать в статье [условия и исключения правила обработки почтового процесса в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="23c38-121">For more information about conditions and exceptions in mail flow rules in Exchange Online, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="related-topics"></a><span data-ttu-id="23c38-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="23c38-122">Related topics</span></span>

<span data-ttu-id="23c38-123">Сведения о других аналитиках в панели мониторинга для почтового процесса приведены в статье сведения о [почтовых сообщениях в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="23c38-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
