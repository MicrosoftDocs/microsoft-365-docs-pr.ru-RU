---
title: Очереди в панели мониторинга почтового процесса
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Администраторы могут узнать, как использовать мини-приложение "очереди" в панели мониторинга "почта" в центре безопасности & соответствия требованиям для отслеживания неудачных почтовых сообщений в локальных или партнерских организациях через исходящие соединители.
ms.openlocfilehash: c582a7f459d89fa1515713c4f55dea14b619a6ec
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616396"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="f25ef-103">Очереди в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="f25ef-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f25ef-104">Если не удается отправить сообщения из вашей организации на локальные или партнерские почтовые серверы с помощью соединителей, сообщения помещаются в очередь Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f25ef-104">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="f25ef-105">Распространенные примеры, вызывающие это условие:</span><span class="sxs-lookup"><span data-stu-id="f25ef-105">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="f25ef-106">Соединитель неправильно настроен.</span><span class="sxs-lookup"><span data-stu-id="f25ef-106">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="f25ef-107">В локальной среде есть изменения в сети или брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="f25ef-107">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="f25ef-108">Microsoft 365 продолжит попытки доставки в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="f25ef-108">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="f25ef-109">Через 24 часа срок действия сообщений истечет и они будут возвращены отправителям в отчетах о недоставке (также известных как отчеты о недоставке или сообщения Bounce).</span><span class="sxs-lookup"><span data-stu-id="f25ef-109">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="f25ef-110">Если объем почтовых сообщений в очереди превышает предопределенный порог (значение по умолчанию — 200 сообщений), сведения доступны в следующих расположениях:</span><span class="sxs-lookup"><span data-stu-id="f25ef-110">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="f25ef-111">**Очереди** в [панели мониторинга почтовых ящиков](mail-flow-insights-v2.md) в [центре безопасности & соответствия требованиям](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="f25ef-111">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="f25ef-112">Для получения дополнительных сведений ознакомьтесь с разделом ["очереди" в разделе Панель мониторинга почтовых ящиков](#queues-insight-in-the-mail-flow-dashboard) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f25ef-112">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this topic.</span></span>

- <span data-ttu-id="f25ef-113">В разделе " **недавние оповещения** " отображается оповещение панель мониторинга оповещений в [центре безопасности & соответствия требованиям](https://protection.office.com) (панель мониторинга **оповещений** \>  или <https://protection.office.com/alertsdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="f25ef-113">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Последние оповещения в панели мониторинга оповещений в центре безопасности & соответствия требованиям](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="f25ef-115">Администраторы получат уведомление по электронной почте на основе конфигурации политики оповещений по умолчанию с именем **Messages DELAYED**.</span><span class="sxs-lookup"><span data-stu-id="f25ef-115">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="f25ef-116">Чтобы настроить параметры уведомлений для этого оповещения, ознакомьтесь со статьей в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="f25ef-116">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="f25ef-117">Дополнительные сведения о политиках оповещений можно узнать [в статье Security Alerts in the Security & Security Center](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f25ef-117">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="f25ef-118">Настройка оповещений из очереди</span><span class="sxs-lookup"><span data-stu-id="f25ef-118">Customize queue alerts</span></span>

1. <span data-ttu-id="f25ef-119">В [центре безопасности & соответствия требованиям](https://protection.office.com)перейдите к разделу **оповещения** о \> **политиках оповещений** или откройте окно "оповещения" <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="f25ef-119">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="f25ef-120">На странице " **политики оповещений** " найдите и выберите политику с именем " **сообщения задержаны**".</span><span class="sxs-lookup"><span data-stu-id="f25ef-120">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="f25ef-121">В сообщении открыто всплывающее окно с **задержкой** , и вы можете включить или отключить оповещение и настроить параметры уведомлений.</span><span class="sxs-lookup"><span data-stu-id="f25ef-121">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![Сообщения о политике предупреждений о задержке в сообщениях центр безопасности & соответствия требованиям](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="f25ef-123">**Состояние**: вы можете включить или отключить оповещение.</span><span class="sxs-lookup"><span data-stu-id="f25ef-123">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="f25ef-124">**Получателей электронной почты** и **Максимальное количество ежедневных уведомлений**: нажмите кнопку **изменить** , чтобы настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f25ef-124">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="f25ef-125">Чтобы настроить параметры уведомлений, нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="f25ef-125">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="f25ef-126">В открывшемся всплывающем окне **изменение политики** настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="f25ef-126">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f25ef-127">**Отправлять уведомления по электронной почте**: значение по умолчанию — включено.</span><span class="sxs-lookup"><span data-stu-id="f25ef-127">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="f25ef-128">**Получатели электронной почты**: значение по умолчанию — **тенантадминс**.</span><span class="sxs-lookup"><span data-stu-id="f25ef-128">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="f25ef-129">**Число ежедневных уведомлений**: значение по умолчанию не **ограничено**.</span><span class="sxs-lookup"><span data-stu-id="f25ef-129">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="f25ef-130">**Пороговое** значение: значение по умолчанию — 200.</span><span class="sxs-lookup"><span data-stu-id="f25ef-130">**Threshold**: The default value is 200.</span></span>

   ![Параметры уведомлений в сообщениях. Задержка политики оповещений центр безопасности & соответствия требованиям](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="f25ef-132">По завершении нажмите кнопку **сохранить** и **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f25ef-132">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="f25ef-133">Очереди в панели мониторинга почтового процесса</span><span class="sxs-lookup"><span data-stu-id="f25ef-133">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="f25ef-134">Даже если объем сообщений, помещенных в очередь, не превысил пороговое значение и создал оповещение, вы по-прежнему можете использовать **очереди** в [панели мониторинга потоков обработки почты](mail-flow-insights-v2.md) для просмотра сообщений, помещенных в очередь более чем за один час, и предпринимать действия до того, как количество сообщений в очереди станет слишком большим.</span><span class="sxs-lookup"><span data-stu-id="f25ef-134">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Мини-приложение Queues в панели мониторинга "Управление почтовыми сообщениями" в центре безопасности & соответствия требованиям](../../media/mfi-queues-widget.png)

<span data-ttu-id="f25ef-136">Если щелкнуть число сообщений в мини-приложении, появится раскрывающееся меню **сообщения** со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="f25ef-136">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="f25ef-137">**Количество сообщений в очереди**</span><span class="sxs-lookup"><span data-stu-id="f25ef-137">**Number of queued messages**</span></span>
- <span data-ttu-id="f25ef-138">**Имя соединителя**: щелкните имя соединителя, чтобы управлять соединителем в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="f25ef-138">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="f25ef-139">**Время начала очереди**</span><span class="sxs-lookup"><span data-stu-id="f25ef-139">**Queue started time**</span></span>
- <span data-ttu-id="f25ef-140">**Самые старые сообщения с истекшим сроком действия**</span><span class="sxs-lookup"><span data-stu-id="f25ef-140">**Oldest messages expired**</span></span>
- <span data-ttu-id="f25ef-141">**Целевой сервер**</span><span class="sxs-lookup"><span data-stu-id="f25ef-141">**Destination server**</span></span>
- <span data-ttu-id="f25ef-142">**Последний IP-адрес**</span><span class="sxs-lookup"><span data-stu-id="f25ef-142">**Last IP address**</span></span>
- <span data-ttu-id="f25ef-143">**Последняя ошибка**</span><span class="sxs-lookup"><span data-stu-id="f25ef-143">**Last error**</span></span>
- <span data-ttu-id="f25ef-144">**Исправление**: распространенные проблемы и решения.</span><span class="sxs-lookup"><span data-stu-id="f25ef-144">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="f25ef-145">Если **это так, нажмите эту ссылку,** чтобы устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="f25ef-145">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="f25ef-146">В противном случае щелкните любую из доступных ссылок, чтобы получить дополнительные сведения об ошибке и возможных решениях.</span><span class="sxs-lookup"><span data-stu-id="f25ef-146">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Сведения после того, как вы нажимаете кнопку "очереди" в панели мониторинга почтового процесса](../../media/mfi-queues-details.png)

<span data-ttu-id="f25ef-148">Одно и то же всплывающее окно отображается после нажатия кнопки **Просмотр очереди** в сведениях о **задержке сообщений** .</span><span class="sxs-lookup"><span data-stu-id="f25ef-148">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Сообщения с предупреждениями о задержке в центре безопасности & соответствия требованиям](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="f25ef-150">См. также</span><span class="sxs-lookup"><span data-stu-id="f25ef-150">See also</span></span>

<span data-ttu-id="f25ef-151">Сведения о других аналитиках в панели мониторинга для почтового процесса приведены в статье сведения о [почтовых сообщениях в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="f25ef-151">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
