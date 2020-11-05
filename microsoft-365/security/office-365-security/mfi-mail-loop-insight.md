---
title: Анализ исправления возможного почтового цикла
f1.keywords:
- NOCSH
ms.author: siosulli
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
ms.openlocfilehash: 1d49fd93b2ea068986e003b36077672215a2dd57
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920573"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="712eb-103">Исправление возможных почтовых циклов в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="712eb-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="712eb-104">Неправильные циклы почты, так как:</span><span class="sxs-lookup"><span data-stu-id="712eb-104">Mail loops are bad because:</span></span>

- <span data-ttu-id="712eb-105">Они занимают ресурсы системы.</span><span class="sxs-lookup"><span data-stu-id="712eb-105">They waste system resources.</span></span>
- <span data-ttu-id="712eb-106">Они потребляют квоту объемного почтового ящика Организации.</span><span class="sxs-lookup"><span data-stu-id="712eb-106">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="712eb-107">Они могут отправлять сообщения о недоставке (также называемые сообщениями NDR и Bounce) отправителям исходного сообщения.</span><span class="sxs-lookup"><span data-stu-id="712eb-107">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="712eb-108">В [центре безопасности & соответствия требованиям](https://protection.office.com) уведомление о возможных возможностях почтовых **циклов** в области " **Рекомендуемые для вас** [" панели мониторинга "](mail-flow-insights-v2.md) безопасность соответствия" уведомляет об обнаружении почтового цикла в Организации.</span><span class="sxs-lookup"><span data-stu-id="712eb-108">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="712eb-109">Эта информация отображается только после того, как будет обнаружено условие (если у вас нет почтовых циклов, вы не увидите сведения).</span><span class="sxs-lookup"><span data-stu-id="712eb-109">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Устранение медленных почтовых правил в области "Рекомендуемые для вас" панели мониторинга почтового процесса](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="712eb-111">При нажатии кнопки **Просмотреть сведения** на мини-приложение появляется раскрывающееся меню с дополнительными сведениями:</span><span class="sxs-lookup"><span data-stu-id="712eb-111">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="712eb-112">**Домен**</span><span class="sxs-lookup"><span data-stu-id="712eb-112">**Domain**</span></span>
- <span data-ttu-id="712eb-113">**Количество сообщений** : вы можете щелкнуть **Просмотреть примеры сообщений** , чтобы просмотреть результаты [трассировки сообщений](message-trace-scc.md) для примера сообщений, на которые повлиял цикл.</span><span class="sxs-lookup"><span data-stu-id="712eb-113">**Number of messages** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="712eb-114">**Тип домена** "например, удостоверяющий или недостоверный.</span><span class="sxs-lookup"><span data-stu-id="712eb-114">**Domain type** " For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="712eb-115">**Запись MX** : узел ( **почтовый сервер** ) и значения **приоритета** записи MX для домена.</span><span class="sxs-lookup"><span data-stu-id="712eb-115">**MX record** : The host ( **Mail server** ) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="712eb-116">**Причина цикла** и **способ исправления** : мы будем определять наиболее распространенные сценарии циклов обработки почты и предоставлять Рекомендуемые действия по исправлению цикла.</span><span class="sxs-lookup"><span data-stu-id="712eb-116">**Loop reason** and **How to fix** : We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Всплывающее окно со сведениями, которое появляется после нажатия кнопки Просмотр сведений в разделе Устранение возможных сообщений о возможных повторах](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="712eb-118">См. также</span><span class="sxs-lookup"><span data-stu-id="712eb-118">See also</span></span>

<span data-ttu-id="712eb-119">Сведения о других аналитиках в панели мониторинга для почтового процесса приведены в статье сведения о [почтовых сообщениях в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="712eb-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
