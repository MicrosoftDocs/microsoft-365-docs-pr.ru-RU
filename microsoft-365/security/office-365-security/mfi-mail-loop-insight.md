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
description: Администраторы могут узнать, как использовать исправление возможных почтовых циклов почты в панели мониторинга "почтовый ящик" в центре безопасности & соответствия требованиям, чтобы определить и устранить почтовые циклы в Организации.
ms.openlocfilehash: 063906195488aa7d65093c538d9045002448e181
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358274"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="2309c-103">Исправление возможных почтовых циклов в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="2309c-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

<span data-ttu-id="2309c-104">Почтовый цикл является недопустимым, так как он создает неисправность системных ресурсов, использует квоту почтового ящика организации и отправляет исходным отправителям неправильные отчеты о недоставке (также называемые сообщениями NDR и Bounce).</span><span class="sxs-lookup"><span data-stu-id="2309c-104">A mail loop is bad because it wastes system resources, consumes your organization's mail volume quota, and sends confusing non-delivery reports (also known as NDRs or bounce messages) to the original senders.</span></span>

<span data-ttu-id="2309c-105">В [центре безопасности & соответствия требованиям](https://protection.office.com) уведомление о возможных возможностях почтовых **циклов** в области " **Рекомендуемые для вас** [" панели мониторинга "](mail-flow-insights-v2.md) безопасность соответствия" уведомляет об обнаружении почтового цикла в Организации.</span><span class="sxs-lookup"><span data-stu-id="2309c-105">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span> <span data-ttu-id="2309c-106">Эта информация отображается только после того, как будет обнаружено условие (если у вас нет почтовых циклов, вы не увидите сведения).</span><span class="sxs-lookup"><span data-stu-id="2309c-106">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Устранение медленных почтовых правил в области "Рекомендуемые для вас" панели мониторинга почтового процесса](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="2309c-108">При нажатии кнопки **Просмотреть сведения** на мини-приложение появляется раскрывающееся меню с дополнительными сведениями:</span><span class="sxs-lookup"><span data-stu-id="2309c-108">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="2309c-109">**Домен**</span><span class="sxs-lookup"><span data-stu-id="2309c-109">**Domain**</span></span>
- <span data-ttu-id="2309c-110">**Количество сообщений**: вы можете щелкнуть **Просмотреть примеры сообщений** , чтобы просмотреть результаты [трассировки сообщений](message-trace-scc.md) для примера сообщений, на которые повлиял цикл.</span><span class="sxs-lookup"><span data-stu-id="2309c-110">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="2309c-111">**Тип домена**"например, удостоверяющий или недостоверный.</span><span class="sxs-lookup"><span data-stu-id="2309c-111">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="2309c-112">**Запись MX**: узел (**почтовый сервер**) и значения **приоритета** записи MX для домена.</span><span class="sxs-lookup"><span data-stu-id="2309c-112">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="2309c-113">**Причина** и **способ исправления**: мы попытаемся определить наиболее распространенные сценарии почтового цикла и предоставить Рекомендуемые действия (если они доступны), чтобы исправить цикл.</span><span class="sxs-lookup"><span data-stu-id="2309c-113">**Loop reason** and **How to fix**: We'll try to identify the most common mail loop scenarios and provide the recommended actions (if available) to fix the loop.</span></span>

![Всплывающее окно со сведениями, которое появляется после нажатия кнопки Просмотр сведений в разделе Устранение возможных сообщений о возможных повторах](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a><span data-ttu-id="2309c-115">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2309c-115">Related topics</span></span>

<span data-ttu-id="2309c-116">Сведения о других аналитиках в панели мониторинга для почтового процесса приведены в статье сведения о [почтовых сообщениях в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="2309c-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
