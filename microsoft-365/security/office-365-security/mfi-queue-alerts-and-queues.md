---
title: Аналитика очередей на панели мониторинга потока обработки почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Администраторы могут научиться использовать мини-приложение "Очереди" на панели мониторинга потока обработки почты в Центре безопасности & Для отслеживания неудачной передачи почты в свои локальные или партнерские организации через исходящие соединители.
ms.openlocfilehash: 79523533306e847988fa0d4e2dd70eca22f7c76c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826909"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="bf330-103">Статистика очередей в Центре безопасности & требованиям</span><span class="sxs-lookup"><span data-stu-id="bf330-103">Queues insight in the Security & Compliance Center</span></span>

<span data-ttu-id="bf330-104">Если сообщения невозможно отправлять из вашей организации на локальные или партнерские почтовые серверы, используя соединители, они помещаются в очередь Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bf330-104">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="bf330-105">Наиболее распространенные примеры, вызывающие это условие:</span><span class="sxs-lookup"><span data-stu-id="bf330-105">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="bf330-106">Соединитель настроен неправильно.</span><span class="sxs-lookup"><span data-stu-id="bf330-106">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="bf330-107">В локальной среде были изменены сетевые изменения или брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="bf330-107">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="bf330-108">Попытки Microsoft 365 будут пытаться доставить через 24 часа.</span><span class="sxs-lookup"><span data-stu-id="bf330-108">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="bf330-109">По просьбе 24 часа срок действия сообщений будет истекать, а отправители будут возвращаться отправителям в отчетах о недоставке (сообщений о недоставке).</span><span class="sxs-lookup"><span data-stu-id="bf330-109">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="bf330-110">Если объем почты в очереди превышает предопределенное пороговое значение (по умолчанию 200 сообщений), эта информация доступна в следующих местах:</span><span class="sxs-lookup"><span data-stu-id="bf330-110">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="bf330-111">Сведения **об очередях** на панели мониторинга [потока обработки почты](mail-flow-insights-v2.md) в Центре безопасности & требованиям.</span><span class="sxs-lookup"><span data-stu-id="bf330-111">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center.</span></span> <span data-ttu-id="bf330-112">Дополнительные сведения см. в [подразделе "Мониторинг"](#queues-insight-in-the-mail-flow-dashboard) панели мониторинга для потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="bf330-112">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this topic.</span></span>
  
- <span data-ttu-id="bf330-113">Оповещения отображаются в панели **мониторинга** оповещений на информационной [панели "Оповещения" в Центре безопасности &](https://protection.office.com) соответствия требованиям **(информационная панель оповещений** или панель \> **мониторинга** <https://protection.office.com/alertsdashboard> оповещений).</span><span class="sxs-lookup"><span data-stu-id="bf330-113">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Оповещения на информационной панели оповещений в Центре безопасности & требованиям](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="bf330-115">Администраторы будут получать уведомления по электронной почте с учетом конфигурации стандартной политики предупреждений **"Сообщения была задержана задержка".**</span><span class="sxs-lookup"><span data-stu-id="bf330-115">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="bf330-116">Сведения о настройке параметров уведомлений для этого предупреждения см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="bf330-116">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="bf330-117">Дополнительные сведения о политиках оповещений см. в статье ["Политики оповещений" в Центре безопасности & соответствия требованиям.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="bf330-117">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="bf330-118">Настройка оповещений очереди</span><span class="sxs-lookup"><span data-stu-id="bf330-118">Customize queue alerts</span></span>

1. <span data-ttu-id="bf330-119">В Центре [безопасности & соответствия требованиям выберите](https://protection.office.com) **"Политики** \> **оповещений" или откройте.** <https://protection.office.com/alertpolicies></span><span class="sxs-lookup"><span data-stu-id="bf330-119">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="bf330-120">На странице **"Политики оповещений"** найдите и выберите политику с **именем "Сообщения была задержана".**</span><span class="sxs-lookup"><span data-stu-id="bf330-120">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="bf330-121">В **открывшемся всплывающем** элементе сообщения можно включить или отключить оповещение, а также настроить параметры уведомлений.</span><span class="sxs-lookup"><span data-stu-id="bf330-121">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![Сообщения были задержаны в подробных сведениях о политике безопасности & центра соответствия требованиям](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="bf330-123">**Status:** оповещение можно включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="bf330-123">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="bf330-124">**Получатели электронной почты и** **ограничение на ежедневные уведомления.** Нажмите **кнопку "Изменить",** чтобы настроить указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="bf330-124">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="bf330-125">Чтобы настроить параметры уведомлений, нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="bf330-125">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="bf330-126">В **появившемся** окне "Изменение политики" настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="bf330-126">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="bf330-127">**Отправка уведомлений по**электронной почте: по умолчанию значение включено.</span><span class="sxs-lookup"><span data-stu-id="bf330-127">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="bf330-128">**Получатели электронной**почты: по умолчанию используется **значение TenantAdmins.**</span><span class="sxs-lookup"><span data-stu-id="bf330-128">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="bf330-129">**Ежедневный предел уведомлений.** Значение по умолчанию — **"Нет ограничения на отсутствует".**</span><span class="sxs-lookup"><span data-stu-id="bf330-129">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="bf330-130">**Порог**— значение по умолчанию — 200.</span><span class="sxs-lookup"><span data-stu-id="bf330-130">**Threshold**: The default value is 200.</span></span>

   ![Параметры уведомлений в политиках сообщений были задержана в подробных сведениях о политике безопасности & соответствия требованиям](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="bf330-132">Когда закончите, нажмите кнопку **"Сохранить"** и **закройте.**</span><span class="sxs-lookup"><span data-stu-id="bf330-132">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="bf330-133">Аналитика очередей на панели мониторинга потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="bf330-133">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="bf330-134">Даже если том сообщения в очереди не превысил пороговое значение и сгенерировано оповещение, вы все равно можете использовать аналитику очередей на панели мониторинга потока обработки почты, чтобы просматривать сообщения, которые были поставлены в очередь более одного часа, и выполнить действие, прежде чем слишком большое число сообщений в очереди станет слишком большим. **Queues** [Mail flow dashboard](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="bf330-134">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Мини-приложение очередей на панели мониторинга потока обработки почты в Центре безопасности & требованиям](../../media/mfi-queues-widget.png)

<span data-ttu-id="bf330-136">Если вы щелкнете количество сообщений на мини-приложении, **появится** всплывающую папку "Сообщения в очереди" со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="bf330-136">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="bf330-137">**Количество сообщений в очереди**</span><span class="sxs-lookup"><span data-stu-id="bf330-137">**Number of queued messages**</span></span>
- <span data-ttu-id="bf330-138">**Имя соединителя:** Щелкните имя соединителя, чтобы управлять соединителем в Центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="bf330-138">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="bf330-139">**Время начала очереди**</span><span class="sxs-lookup"><span data-stu-id="bf330-139">**Queue started time**</span></span>
- <span data-ttu-id="bf330-140">**Срок действия наиболее старых сообщений истек**</span><span class="sxs-lookup"><span data-stu-id="bf330-140">**Oldest messages expired**</span></span>
- <span data-ttu-id="bf330-141">**Конечный сервер**</span><span class="sxs-lookup"><span data-stu-id="bf330-141">**Destination server**</span></span>
- <span data-ttu-id="bf330-142">**Последний IP-адрес**</span><span class="sxs-lookup"><span data-stu-id="bf330-142">**Last IP address**</span></span>
- <span data-ttu-id="bf330-143">**Последняя ошибка**</span><span class="sxs-lookup"><span data-stu-id="bf330-143">**Last error**</span></span>
- <span data-ttu-id="bf330-144">**Способы решения:** доступны распространенные проблемы и решения.</span><span class="sxs-lookup"><span data-stu-id="bf330-144">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="bf330-145">Если ссылка **"Исправление" теперь** доступна, щелкните ее, чтобы устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="bf330-145">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="bf330-146">В противном случае щелкните любую доступную ссылку для получения дополнительных сведений об ошибке и возможных решениях.</span><span class="sxs-lookup"><span data-stu-id="bf330-146">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Сведения после нажатия на сведения об очередях на панели мониторинга потока обработки почты](../../media/mfi-queues-details.png)

<span data-ttu-id="bf330-148">Тот же всплывающий элемент отображается после нажатия кнопки **"Просмотреть очередь"** в сведениях **об задержке сообщений.**</span><span class="sxs-lookup"><span data-stu-id="bf330-148">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Сведения об задержке сообщений в Центре безопасности & соответствия требованиям](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="bf330-150">См. также</span><span class="sxs-lookup"><span data-stu-id="bf330-150">See also</span></span>

<span data-ttu-id="bf330-151">Сведения о других аналитических данных на панели мониторинга потока обработки почты см. в статье "Аналитика потока [обработки почты" в Центре безопасности & соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="bf330-151">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
