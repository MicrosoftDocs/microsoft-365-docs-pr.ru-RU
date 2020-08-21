---
title: Анализ исправления возможного почтового цикла
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут научиться использовать эту статистику "Исправление" почтового цикла на панели мониторинга потока обработки почты в Центре безопасности &, чтобы определять и исправлять почтовые циклы в организации.
ms.openlocfilehash: 162752ce6981e27d6ae2923aeb0fc33aec42bb0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826957"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="a8b2a-103">Устранение возможных статистики почтового цикла в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a8b2a-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

<span data-ttu-id="a8b2a-104">Почтовый цикл недопустим, поскольку он препятствует системным ресурсам, потребляет квоту на объем почтовых ресурсов организации и делает путаницу неудобств теми отправителями.</span><span class="sxs-lookup"><span data-stu-id="a8b2a-104">A mail loop is bad because it wastes system resources, consumes your organization's mail volume quota, and sends confusing non-delivery reports (also known as NDRs or bounce messages) to the original senders.</span></span>

<span data-ttu-id="a8b2a-105">Эта **информация о возможной проблеме** с почтовым циклом в **рекомендуемой** панели мониторинга [потока обработки](mail-flow-insights-v2.md) почты в Центре безопасности & уведомляет о обнаружении почтового цикла в организации.</span><span class="sxs-lookup"><span data-stu-id="a8b2a-105">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center notifies you when a mail loop is detected in your organization.</span></span> <span data-ttu-id="a8b2a-106">Эта аналитика появляется только после определения условия (если у вас нет почтовых циклов, аналитика не будет отображаться).</span><span class="sxs-lookup"><span data-stu-id="a8b2a-106">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Устранение медленных результатов правил потока обработки почты в рекомендуемой области панели мониторинга потока обработки почты](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="a8b2a-108">Когда вы **щелкаете** "Просмотр сведений" в мини-приложении, появится всплывающая область с дополнительной информацией:</span><span class="sxs-lookup"><span data-stu-id="a8b2a-108">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="a8b2a-109">**Домен**</span><span class="sxs-lookup"><span data-stu-id="a8b2a-109">**Domain**</span></span>
- <span data-ttu-id="a8b2a-110">**Количество сообщений:** можно нажать кнопку **«Просмотреть пример сообщений»,** чтобы просмотреть результаты трассировки для образца сообщений, затронутых циклом. [message trace](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="a8b2a-110">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="a8b2a-111">**Тип домена**" Например, "Доверенное" или "Незаслуживающие доверия".</span><span class="sxs-lookup"><span data-stu-id="a8b2a-111">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="a8b2a-112">**Запись MX:** узел **(почтовый сервер)** **и значения приоритета** для записи MX для домена.</span><span class="sxs-lookup"><span data-stu-id="a8b2a-112">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="a8b2a-113">**Причина цикла** и **рекомендации:** мы пытаемся определить наиболее распространенные сценарии почтового цикла и предоставить рекомендуемые действия (если они доступны).</span><span class="sxs-lookup"><span data-stu-id="a8b2a-113">**Loop reason** and **How to fix**: We'll try to identify the most common mail loop scenarios and provide the recommended actions (if available) to fix the loop.</span></span>

![Всплывающий элемент "Подробности", который отображается после нажатия элемента "Просмотр сведений" в разделе "Исправление проблемы" из почтового цикла](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a><span data-ttu-id="a8b2a-115">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="a8b2a-115">Related topics</span></span>

<span data-ttu-id="a8b2a-116">Сведения о других аналитических данных на панели мониторинга потока обработки почты см. в статье "Аналитика потока [обработки почты" в Центре безопасности & соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="a8b2a-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
