---
title: Представление очередей в панели мониторинга потока почты
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Администраторы могут узнать, как использовать виджет Queues в панели мониторинга потока почты в Центре соответствия требованиям & безопасности для отслеживания неуспешного потока почты в локальной или партнерских организациях над исходящие соединители.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65452b0ad7c31673c910ba48c9c6709995e563ce
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599987"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="ab727-103">Анализ очередей в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="ab727-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ab727-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="ab727-104">**Applies to**</span></span>
- [<span data-ttu-id="ab727-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ab727-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ab727-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="ab727-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ab727-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab727-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ab727-108">Когда сообщения не могут отправляться из организации на локальном или партнером серверах электронной почты с помощью соединителок, эти сообщения выстрояются в очередь в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ab727-108">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="ab727-109">Распространенные примеры, которые вызывают это условие:</span><span class="sxs-lookup"><span data-stu-id="ab727-109">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="ab727-110">Соединителю некорректно настроен.</span><span class="sxs-lookup"><span data-stu-id="ab727-110">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="ab727-111">В локальной среде произошли изменения сетевого или брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="ab727-111">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="ab727-112">Microsoft 365 будет продолжать повторить доставку в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="ab727-112">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="ab727-113">По истечении 24 часов срок действия сообщений истекает, и они будут возвращены отправителям в отчетах о невывозе (также известных как NDRs или отказов).</span><span class="sxs-lookup"><span data-stu-id="ab727-113">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="ab727-114">Если объем электронной почты в очереди превышает заранее определенный порог (значение по умолчанию составляет 200 сообщений), сведения доступны в следующих расположениях:</span><span class="sxs-lookup"><span data-stu-id="ab727-114">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="ab727-115">Представление **о очередях** в [панели](mail-flow-insights-v2.md) мониторинга потока почты в Центре [& безопасности.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="ab727-115">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="ab727-116">Дополнительные сведения см. в разделе ["Очереди" в разделе Панель](#queues-insight-in-the-mail-flow-dashboard) мониторинга потока почты в этой статье.</span><span class="sxs-lookup"><span data-stu-id="ab727-116">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="ab727-117">Оповещение отображается в **последних** оповещениях панели оповещений в Центре [&](https://protection.office.com) безопасности **(Панель** оповещений \>  или <https://protection.office.com/alertsdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="ab727-117">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Последние оповещения на панели оповещений в Центре & соответствия требованиям](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="ab727-119">Администраторы получат уведомление по электронной почте в зависимости от конфигурации политики оповещения по умолчанию с именем **Сообщения были отложены**.</span><span class="sxs-lookup"><span data-stu-id="ab727-119">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="ab727-120">Чтобы настроить параметры уведомлений для этого оповещения, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="ab727-120">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="ab727-121">Дополнительные сведения о политиках оповещений см. в центре оповещения в центре [& безопасности.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ab727-121">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="ab727-122">Настройка оповещений очереди</span><span class="sxs-lookup"><span data-stu-id="ab727-122">Customize queue alerts</span></span>

1. <span data-ttu-id="ab727-123">В Центре [& безопасности](https://protection.office.com)перейдите к политикам **оповещения** оповещений или \>  откройте <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="ab727-123">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="ab727-124">На странице **Политики оповещения** поиск и выбор политики с именем **Сообщения отложены.**</span><span class="sxs-lookup"><span data-stu-id="ab727-124">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="ab727-125">В **открываемом** вылете Сообщение было отложено, можно включить или отключить оповещение и настроить параметры уведомлений.</span><span class="sxs-lookup"><span data-stu-id="ab727-125">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![Сообщения были задержаны сведения о политике оповещения Центра & соответствия требованиям](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="ab727-127">**Состояние.** Вы можете отключить или отключить оповещение.</span><span class="sxs-lookup"><span data-stu-id="ab727-127">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="ab727-128">**Получатели электронной почты** и ограничение ежедневных **уведомлений:** нажмите **кнопку Изменить,** чтобы настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ab727-128">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="ab727-129">Чтобы настроить параметры уведомлений, нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="ab727-129">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="ab727-130">В **вылете политики** редактирования, которая появится, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ab727-130">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ab727-131">**Отправка уведомлений электронной** почты: значение по умолчанию в режиме.</span><span class="sxs-lookup"><span data-stu-id="ab727-131">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="ab727-132">**Получатели электронной почты:** по умолчанию значение **TenantAdmins**.</span><span class="sxs-lookup"><span data-stu-id="ab727-132">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="ab727-133">**Ежедневное ограничение** уведомлений. Значение по умолчанию **не является ограничением**.</span><span class="sxs-lookup"><span data-stu-id="ab727-133">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="ab727-134">**Пороговое** значение: значение по умолчанию — 200.</span><span class="sxs-lookup"><span data-stu-id="ab727-134">**Threshold**: The default value is 200.</span></span>

   ![Параметры уведомлений в "Сообщениях" отложены сведения о политике оповещения центра & соответствия требованиям](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="ab727-136">По завершению нажмите кнопку **Сохранить и** **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="ab727-136">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="ab727-137">Представление очередей в панели мониторинга потока почты</span><span class="sxs-lookup"><span data-stu-id="ab727-137">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="ab727-138">Даже если объем сообщений в очереди не превысил пороговое значение и  не вызвал [](mail-flow-insights-v2.md) оповещений, вы можете использовать представление очередей в панели мониторинга потока почты, чтобы увидеть сообщения, которые были в очереди более одного часа, и принять меры до того, как число очередных сообщений станет слишком большим.</span><span class="sxs-lookup"><span data-stu-id="ab727-138">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Виджет очередей в панели мониторинга потока почты в центре & соответствия требованиям](../../media/mfi-queues-widget.png)

<span data-ttu-id="ab727-140">Если щелкнуть число сообщений в  виджете, вылет сообщений в очереди появится со следующей информацией:</span><span class="sxs-lookup"><span data-stu-id="ab727-140">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="ab727-141">**Количество сообщений в очереди**</span><span class="sxs-lookup"><span data-stu-id="ab727-141">**Number of queued messages**</span></span>
- <span data-ttu-id="ab727-142">**Имя соединителя.** Щелкните имя соединителя, чтобы управлять соединитетелем в центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="ab727-142">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="ab727-143">**Время начала очереди**</span><span class="sxs-lookup"><span data-stu-id="ab727-143">**Queue started time**</span></span>
- <span data-ttu-id="ab727-144">**Срок действия самых старых сообщений**</span><span class="sxs-lookup"><span data-stu-id="ab727-144">**Oldest messages expired**</span></span>
- <span data-ttu-id="ab727-145">**Сервер назначения**</span><span class="sxs-lookup"><span data-stu-id="ab727-145">**Destination server**</span></span>
- <span data-ttu-id="ab727-146">**Последний IP-адрес**</span><span class="sxs-lookup"><span data-stu-id="ab727-146">**Last IP address**</span></span>
- <span data-ttu-id="ab727-147">**Последняя ошибка**</span><span class="sxs-lookup"><span data-stu-id="ab727-147">**Last error**</span></span>
- <span data-ttu-id="ab727-148">**Исправление.** Общие проблемы и решения доступны.</span><span class="sxs-lookup"><span data-stu-id="ab727-148">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="ab727-149">Если теперь **доступна** ссылка Исправление, щелкните ее, чтобы устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="ab727-149">If a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="ab727-150">В противном случае щелкните все доступные ссылки, чтобы получить дополнительные сведения об ошибке и возможных решениях.</span><span class="sxs-lookup"><span data-stu-id="ab727-150">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Сведения после нажатия на представление очередей в панели мониторинга потока почты](../../media/mfi-queues-details.png)

<span data-ttu-id="ab727-152">Такая же вылетная информация отображается после нажатия очереди **Просмотр** в сведениях о задержке оповещения о **сообщениях.**</span><span class="sxs-lookup"><span data-stu-id="ab727-152">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Сообщения были отложены сведения о оповещениях в Центре & соответствия требованиям](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="ab727-154">См. также</span><span class="sxs-lookup"><span data-stu-id="ab727-154">See also</span></span>

<span data-ttu-id="ab727-155">Сведения о других сведениях в панели мониторинга потока почты см. в странице Анализ потока почты в Центре [& соответствия](mail-flow-insights-v2.md)требованиям.</span><span class="sxs-lookup"><span data-stu-id="ab727-155">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
