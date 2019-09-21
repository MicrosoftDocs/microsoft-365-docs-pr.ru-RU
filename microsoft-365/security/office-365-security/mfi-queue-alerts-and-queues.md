---
title: Очереди и оповещения о них
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Администраторы могут узнать об оповещениях очереди и очередях в панели мониторинга "Управление почтовыми сообщениями" в центре безопасности & соответствия требованиям.
ms.openlocfilehash: ef8b4acd4008f3039030049893f83a5e49e1efc2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091276"
---
# <a name="queue-alerts-and-queues"></a><span data-ttu-id="94665-103">Очереди и оповещения о них</span><span class="sxs-lookup"><span data-stu-id="94665-103">Queue alerts and Queues</span></span>

## <a name="queue-alerts"></a><span data-ttu-id="94665-104">Оповещения в очереди</span><span class="sxs-lookup"><span data-stu-id="94665-104">Queue alerts</span></span>

<span data-ttu-id="94665-105">Если не удается отправить сообщения из организации Office 365 на локальные или партнерские почтовые серверы с помощью соединителей, сообщения помещаются в очередь в Office 365.</span><span class="sxs-lookup"><span data-stu-id="94665-105">When messages can't be sent from your Office 365 organization to your on-premises or partner email servers using connectors, the messages are queued in Office 365.</span></span> <span data-ttu-id="94665-106">Распространенные примеры, вызывающие это условие:</span><span class="sxs-lookup"><span data-stu-id="94665-106">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="94665-107">Соединитель неправильно настроен.</span><span class="sxs-lookup"><span data-stu-id="94665-107">The connector is incorrectly configured.</span></span>

- <span data-ttu-id="94665-108">В локальной среде есть изменения в сети или брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="94665-108">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="94665-109">Office 365 продолжит попытки доставки в течение 48 часов.</span><span class="sxs-lookup"><span data-stu-id="94665-109">Office 365 will continue to retry to delivery for 48 hours.</span></span> <span data-ttu-id="94665-110">Через 48 часов срок действия сообщений истечет и они будут возвращены отправителям в отчетах о недоставке (также известных как отчеты о недоставке или сообщения Bounce).</span><span class="sxs-lookup"><span data-stu-id="94665-110">After 48 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="94665-111">Если объем почтовых ящиков, помещенных в очередь, превышает предопределенный порог (значение по умолчанию — 2000 сообщений), оповещения будут доступны в панели мониторинга "поток обработки почты" при **последних оповещениях**, а администраторы получат уведомление по электронной почте (на свой альтернативный адрес электронной почты). .</span><span class="sxs-lookup"><span data-stu-id="94665-111">If the queued email volume exceeds the pre-defined threshold (the default value is 2000 messages), the alerts will be available in the mail flow dashboard at **Recent alerts**, and admins will receive an email notification (to their alternative email address).</span></span> <span data-ttu-id="94665-112">Чтобы настроить порог оповещений, ограничение ежедневного уведомления и/или получателей оповещения, ознакомьтесь с разделом **Настройка оповещений в очереди** .</span><span class="sxs-lookup"><span data-stu-id="94665-112">To configure the alert threshold, daily notification limit, and/or recipients of the alert, see the **Customize queue alerts** section below.</span></span>

![Поочередно отправлять оповещения в области "Недавние оповещения" панели мониторинга "Управление почтовыми сообщениями" в центре безопасности & соответствия требованиям](../media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a><span data-ttu-id="94665-114">Настройка оповещений из очереди</span><span class="sxs-lookup"><span data-stu-id="94665-114">Customize queue alerts</span></span>

<span data-ttu-id="94665-115">Аналитика обработки почты. Создание политики оповещений с именем **Messages откладывается** (флажок **отправлять уведомления по электронной почте** в приведенном ниже снимке экрана) найден в разделе **Alert** \> **Alert Alerts**.</span><span class="sxs-lookup"><span data-stu-id="94665-115">Mail flow insights create an alert policy named **Messages have been delayed** (the **Send email notifications** check box in the example screen shot below) found in **Alerts** \> **Alert Policies**.</span></span> <span data-ttu-id="94665-116">Вы можете изменить пороговое значение и получателей оповещений, щелкнув политику.</span><span class="sxs-lookup"><span data-stu-id="94665-116">You can modify the threshold and alert recipients by clicking on the policy.</span></span>

![Навигация по оповещениям](../media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

<span data-ttu-id="94665-118">Отобразится Новая колонка со сведениями о политике, теперь можно щелкнуть **изменить политику**.</span><span class="sxs-lookup"><span data-stu-id="94665-118">You'll see a new policy information blade, you can now click **Edit Policy**.</span></span>

![Политика изменений ](../media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

<span data-ttu-id="94665-120">Колонка сведений изменится на **политику редактирования**.</span><span class="sxs-lookup"><span data-stu-id="94665-120">The information blade will change to the **Edit Policy**.</span></span> <span data-ttu-id="94665-121">Теперь вы можете изменить получателей оповещения по электронной почте, предельное число отправляемых уведомлений в день и минимальное пороговое значение для запуска оповещения (200 или более).</span><span class="sxs-lookup"><span data-stu-id="94665-121">You can now change the recipients for the alert email, the limit on the number of notifications sent per day, and the minimum threshold to trigger the alert (200 or more).</span></span>

![Изменение Колонкы политики](../media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a><span data-ttu-id="94665-123">Сведения об оповещениях в очереди</span><span class="sxs-lookup"><span data-stu-id="94665-123">Queue alert details</span></span>

<span data-ttu-id="94665-124">При нажатии на оповещение в раскрывающейся области отображаются сведения об оповещении.</span><span class="sxs-lookup"><span data-stu-id="94665-124">When you click the alert, the alert details appear in a flyout pane.</span></span>

![Выберите оповещение из очереди в области "Недавние оповещения" панели мониторинга "Управление почтовыми сообщениями" в центре безопасности & соответствия требованиям](../media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![Всплывающее меню сведений о предупреждении очереди в центре безопасности & соответствия требованиям](../media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

<span data-ttu-id="94665-127">Чтобы просмотреть сведения об очереди, проблемы и ссылки на доступные исправления в новой всплывающей области, щелкните ссылку **просмотреть очередь** в сведениях оповещения.</span><span class="sxs-lookup"><span data-stu-id="94665-127">You can click **View queue** in the alert details to see the queue details, problems, and links to the available fixes in a new flyout pane.</span></span>

![Всплывающее меню сведений о предупреждении очереди в центре безопасности & соответствия требованиям](../media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Просмотр очереди в сведениях оповещения](../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a><span data-ttu-id="94665-130">Очереди</span><span class="sxs-lookup"><span data-stu-id="94665-130">Queues</span></span>

<span data-ttu-id="94665-131">Даже если объем сообщений, помещенных в очередь, не превысил пороговое значение, можно по-прежнему использовать область " **очереди** " панели мониторинга "поток обработки почты" для просмотра сообщений, помещенных в очередь более чем за один час.</span><span class="sxs-lookup"><span data-stu-id="94665-131">Even if the queued message volume hasn't exceeded the threshold, you can still use the **Queues** area of the mail flow dashboard to see messages that have been queued for more than one hour.</span></span> <span data-ttu-id="94665-132">Вы можете использовать область " **очереди** " для наблюдения за количеством сообщений в очереди (значение 0 означает, что почтовый ящик является допустимым) и предпринимать действия до того, как количество сообщений в очереди станет слишком большим.</span><span class="sxs-lookup"><span data-stu-id="94665-132">You can use the **Queues** area to monitor the number of queued messages (the value 0 indicates mail flow is OK) and take action before the number of queued messages becomes too large.</span></span>

![Очереди на панели мониторинга "почтовые потоки" в центре безопасности & соответствия требованиям](../media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

<span data-ttu-id="94665-134">Когда вы наводите число помещенных **в очередь сообщений в очереди, сведения**об очередях и инструкции по их устранению будут отображаться в раскрывающейся области (то же самое, что отображается после нажатия кнопки **просмотреть очередь** в разделе сведения о предупреждении очереди).</span><span class="sxs-lookup"><span data-stu-id="94665-134">When you click the number of queued messages in **Queues**, the queue details and guidance for how to fix the issue will appear in a flyout pane (the same flyout that appears after you click **View queue** in the details of a queue alert).</span></span>

![Сведения об очереди](../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="see-also"></a><span data-ttu-id="94665-136">См. также</span><span class="sxs-lookup"><span data-stu-id="94665-136">See also</span></span>

<span data-ttu-id="94665-137">Для получения дополнительных сведений о других аналитиках почтовых ящиков в панели мониторинга обработки почты ознакомьтесь с разрешениями [почтовых ящиков в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="94665-137">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
