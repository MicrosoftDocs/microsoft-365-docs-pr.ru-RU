---
title: Анализ очередей на панели мониторинга потока почты
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Администраторы могут узнать, как использовать мини-виджет "Очереди" на панели мониторинга потока обработки почты в Центре безопасности & соответствия требованиям для отслеживания неудачного потока обработки почты в свои локальной или партнерской организации по исходящие соединители.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 94e8a1f3b54c3738c21e94ba85ae4f1d3f953498
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150175"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="fa76e-103">Анализ очередей в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="fa76e-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fa76e-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="fa76e-104">**Applies to**</span></span>
- [<span data-ttu-id="fa76e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fa76e-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="fa76e-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="fa76e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="fa76e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fa76e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="fa76e-108">Если сообщения не могут быть отправлены из вашей организации на ваши серверы электронной почты или серверы электронной почты партнеров с помощью соединителок, они будут в очереди в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa76e-108">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="fa76e-109">Распространенные примеры, которые вызывают это условие:</span><span class="sxs-lookup"><span data-stu-id="fa76e-109">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="fa76e-110">Соединительная связь настроена неправильно.</span><span class="sxs-lookup"><span data-stu-id="fa76e-110">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="fa76e-111">В локальной среде были внесены изменения в сети или брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="fa76e-111">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="fa76e-112">Microsoft 365 продолжит попытку доставки в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="fa76e-112">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="fa76e-113">По истечении 24 часов срок действия сообщений истекает, и они будут возвращены отправителям в отчетах о не доставке (также известных как отчеты о возврате).</span><span class="sxs-lookup"><span data-stu-id="fa76e-113">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="fa76e-114">Если объем электронной почты в очереди превышает заранее определенное пороговое значение (значение по умолчанию — 200 сообщений), сведения доступны в следующих расположениях:</span><span class="sxs-lookup"><span data-stu-id="fa76e-114">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="fa76e-115">Анализ **очередей** на панели мониторинга [потока](mail-flow-insights-v2.md) обработки почты в Центре & [соответствия требованиям.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="fa76e-115">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="fa76e-116">Дополнительные сведения см. в разделе ["Очереди"](#queues-insight-in-the-mail-flow-dashboard) в разделе панели мониторинга потока почты в этой статье.</span><span class="sxs-lookup"><span data-stu-id="fa76e-116">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="fa76e-117">Оповещение отображается  в последних оповещениях панели мониторинга оповещений в Центре [безопасности & соответствия](https://protection.office.com) требованиям ( панель мониторинга оповещений \>  или <https://protection.office.com/alertsdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="fa76e-117">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Последние оповещения на панели мониторинга оповещений в Центре безопасности & соответствия требованиям](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="fa76e-119">Администраторы получат уведомление по электронной почте в зависимости от конфигурации политики оповещений по умолчанию с именем **"Сообщения, которые были отложены".**</span><span class="sxs-lookup"><span data-stu-id="fa76e-119">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="fa76e-120">Чтобы настроить параметры уведомлений для этого оповещения, см. следующий раздел.</span><span class="sxs-lookup"><span data-stu-id="fa76e-120">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="fa76e-121">Дополнительные сведения о политиках оповещений см. в центре [безопасности & соответствия требованиям.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="fa76e-121">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="fa76e-122">Настройка оповещений очереди</span><span class="sxs-lookup"><span data-stu-id="fa76e-122">Customize queue alerts</span></span>

1. <span data-ttu-id="fa76e-123">В Центре [безопасности & соответствия](https://protection.office.com)требованиям  перейдите к политикам оповещений \> **или** откройте <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="fa76e-123">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="fa76e-124">На странице **"Политики оповещений"** найдите и выберите политику **"Сообщения" с задержкой.**</span><span class="sxs-lookup"><span data-stu-id="fa76e-124">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="fa76e-125">В **открываемом окте "Сообщение"** можно включить или отключить оповещение и настроить параметры уведомлений.</span><span class="sxs-lookup"><span data-stu-id="fa76e-125">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![Сведения о политике оповещений о сообщениях с задержкой в Центре & соответствия требованиям](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="fa76e-127">**Состояние:** вы можете отключить или отключить оповещение.</span><span class="sxs-lookup"><span data-stu-id="fa76e-127">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="fa76e-128">**Получатели электронной почты** и ограничение на количество уведомлений за **день:** нажмите **кнопку** "Изменить", чтобы настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fa76e-128">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="fa76e-129">Чтобы настроить параметры уведомлений, нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="fa76e-129">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="fa76e-130">Во появляется **во flyout политики** редактирования, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fa76e-130">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="fa76e-131">**Отправка уведомлений по электронной** почте: значение по умолчанию : "On".</span><span class="sxs-lookup"><span data-stu-id="fa76e-131">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="fa76e-132">**Получатели электронной** почты: значение по умолчанию **— TenantAdmins.**</span><span class="sxs-lookup"><span data-stu-id="fa76e-132">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="fa76e-133">**Ограничение на количество уведомлений по** дням: значение по умолчанию **— No limit**.</span><span class="sxs-lookup"><span data-stu-id="fa76e-133">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="fa76e-134">**Пороговое** значение: значение по умолчанию — 200.</span><span class="sxs-lookup"><span data-stu-id="fa76e-134">**Threshold**: The default value is 200.</span></span>

   ![Сведения о параметрах уведомлен & ий в Центре безопасности и соответствия требованиям](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="fa76e-136">По завершению нажмите кнопку **"Сохранить** и **закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fa76e-136">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="fa76e-137">Анализ очередей на панели мониторинга потока почты</span><span class="sxs-lookup"><span data-stu-id="fa76e-137">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="fa76e-138">Даже если объем сообщений в очереди не превысил пороговое значение и  вызвал оповещение, вы можете использовать анализ очередей на панели мониторинга потока почты, чтобы увидеть сообщения, которые были в очереди более одного часа, и принять меры до того, как количество сообщений в очереди станет слишком большим. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="fa76e-138">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Мини-приложения "Очереди" на панели мониторинга потока обработки почты в Центре & соответствия требованиям](../../media/mfi-queues-widget.png)

<span data-ttu-id="fa76e-140">Если щелкнуть количество сообщений в виджете, появится флажок **"Сообщения** в очереди" со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="fa76e-140">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="fa76e-141">**Количество сообщений в очереди**</span><span class="sxs-lookup"><span data-stu-id="fa76e-141">**Number of queued messages**</span></span>
- <span data-ttu-id="fa76e-142">**Имя соединителя:** щелкните имя соединителя, чтобы управлять соединитетелем в Центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="fa76e-142">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="fa76e-143">**Время начала работы очереди**</span><span class="sxs-lookup"><span data-stu-id="fa76e-143">**Queue started time**</span></span>
- <span data-ttu-id="fa76e-144">**Срок действия самых старых сообщений истек**</span><span class="sxs-lookup"><span data-stu-id="fa76e-144">**Oldest messages expired**</span></span>
- <span data-ttu-id="fa76e-145">**Сервер назначения**</span><span class="sxs-lookup"><span data-stu-id="fa76e-145">**Destination server**</span></span>
- <span data-ttu-id="fa76e-146">**Последний IP-адрес**</span><span class="sxs-lookup"><span data-stu-id="fa76e-146">**Last IP address**</span></span>
- <span data-ttu-id="fa76e-147">**Последняя ошибка**</span><span class="sxs-lookup"><span data-stu-id="fa76e-147">**Last error**</span></span>
- <span data-ttu-id="fa76e-148">**Как устранить:** доступны распространенные проблемы и решения.</span><span class="sxs-lookup"><span data-stu-id="fa76e-148">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="fa76e-149">Если теперь доступна **ссылка "Исправить",** щелкните ее, чтобы устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="fa76e-149">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="fa76e-150">В противном случае щелкните все доступные ссылки, чтобы получить дополнительные сведения об ошибке и возможных решениях.</span><span class="sxs-lookup"><span data-stu-id="fa76e-150">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Сведения после нажатия на анализ очередей на панели мониторинга потока почты](../../media/mfi-queues-details.png)

<span data-ttu-id="fa76e-152">Тот же самый флажок  отображается после нажатия кнопки "Просмотр очереди" в сведениях о отложенных **оповещениях** сообщений.</span><span class="sxs-lookup"><span data-stu-id="fa76e-152">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Сообщения с задержкой оповещений в Центре безопасности & соответствия требованиям](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="fa76e-154">См. также</span><span class="sxs-lookup"><span data-stu-id="fa76e-154">See also</span></span>

<span data-ttu-id="fa76e-155">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="fa76e-155">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
