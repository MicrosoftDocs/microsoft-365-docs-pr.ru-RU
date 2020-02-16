---
title: Настройка уведомлений пользователя о спаме в Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: Вы можете настроить уведомления о нежелательной почте для пользователей по умолчанию для политики фильтрации нежелательной почты по умолчанию или для настраиваемых политик фильтрации нежелательной почты, которые применяются к доменам.
ms.openlocfilehash: cc3054715fdc5cbe72bc6655462b61eb8a9db5d3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42086468"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="64c39-103">Настройка уведомлений пользователя о спаме в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="64c39-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64c39-104">Этот раздел предназначается клиентам Exchange Online, обеспечивающим защиту почтовых ящиков, размещенных в облаке.</span><span class="sxs-lookup"><span data-stu-id="64c39-104">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes.</span></span> <span data-ttu-id="64c39-105">Изолированные клиенты Exchange Online Protection (EOP), защищающие локальные почтовые ящики, должны прочитать следующий раздел: [Настройка уведомлений конечных пользователей о нежелательной почте в EOP](configure-end-user-spam-notifications-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="64c39-105">Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="64c39-106">Вы можете настроить уведомления о нежелательной почте для пользователей по умолчанию для политики фильтрации нежелательной почты по умолчанию или для настраиваемых политик фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="64c39-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies.</span></span> <span data-ttu-id="64c39-107">Включение оповещений о нежелательной почте пользователи могут управлять своими сообщениями о нежелательной почте, массовых и фишинговых сообщениях в карантине.</span><span class="sxs-lookup"><span data-stu-id="64c39-107">Enabling end-user spam notification messages lets your users manage their own quarantined spam, bulk, and phishing messages.</span></span>   
  
<span data-ttu-id="64c39-p103">Уведомления конечного пользователя о нежелательных сообщениях содержат список всех сообщений, помещенных на карантин нежелательной почты, которые получил пользователь в течение определенного вами периода (можно указать значение между 1 и 15 днями). Можно также настроить язык сообщения уведомления.</span><span class="sxs-lookup"><span data-stu-id="64c39-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="64c39-110">После получения сообщения с уведомлением пользователи могут выбрать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="64c39-110">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="64c39-111">**Блокировать отправителя** , если вы хотите, чтобы Office 365 добавить отправителя в список заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="64c39-111">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="64c39-112">**Отпустите** , если сообщение не является спамом и вы хотите, чтобы Office 365 отправлял сообщение в ваш почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="64c39-112">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="64c39-113">**Просмотрите** , чтобы перейти на портал карантина в центре безопасности & соответствия требованиям, если вы хотите выполнить другие действия, такие как предварительный просмотр или выпуск.</span><span class="sxs-lookup"><span data-stu-id="64c39-113">**Review** to navigate to the Quarantine Portal within the Security & Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="64c39-114">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="64c39-114">What do you need to know before you begin?</span></span>

<span data-ttu-id="64c39-115">Предполагаемое время выполнения: 2 минуты.</span><span class="sxs-lookup"><span data-stu-id="64c39-115">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="64c39-116">Для выполнения этой процедуры (процедур) необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="64c39-116">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="64c39-117">Чтобы просмотреть необходимые разрешения, обратитесь к разделу "Защита от нежелательной почты" в разделе [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) .</span><span class="sxs-lookup"><span data-stu-id="64c39-117">To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) topic.</span></span> 
  
<span data-ttu-id="64c39-118">Дополнительные сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в статье [сочетания клавиш для центра администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="64c39-118">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="64c39-119">Настройка уведомлений пользователя о нежелательной почте с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="64c39-119">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="64c39-120">В Центре администрирования Exchange перейдите в раздел **Защита** \> **Фильтр спама**.</span><span class="sxs-lookup"><span data-stu-id="64c39-120">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="64c39-121">Выберите политику фильтрации нежелательной почты, для которой нужно включить уведомления конечных пользователей о нежелательной почте (по умолчанию они отключены).</span><span class="sxs-lookup"><span data-stu-id="64c39-121">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="64c39-122">На правой панели, на которой отображается сводная информация о вашей политике, выберите ссылку **Включить уведомления пользователя о нежелательной почте**.</span><span class="sxs-lookup"><span data-stu-id="64c39-122">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="64c39-123">В следующем диалоговом окне можно настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="64c39-123">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="64c39-p105">**Включить уведомления пользователя о нежелательной почте** Установите этот флажок, если нужно включить уведомления для этой политики. (И наоборот: если эта политика включена, снимите этот флажок, если нужно отключить уведомления пользователя о нежелательной почте для этой политики.)</span><span class="sxs-lookup"><span data-stu-id="64c39-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="64c39-p106">**Отправлять уведомления пользователя о нежелательной почте каждые (дн.)** Укажите, как часто необходимо отправлять пользователям уведомления о нежелательной почте. Значение по умолчанию  3 дня. Допустимый интервал значений  от 1 до 15 дней. Например, если вы укажете 7 дней, уведомление будет включать список всех сообщений за последние 7 дней, которые предназначались этому пользователю, но были ошибочно поставлены на карантин нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="64c39-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="64c39-130">**Язык уведомлений** В раскрывающемся списке выберите язык, на котором пользователю будут отправляться уведомления о нежелательной почте для этой политики.</span><span class="sxs-lookup"><span data-stu-id="64c39-130">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="64c39-131">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="64c39-131">Click **Save**.</span></span> <span data-ttu-id="64c39-132">Сводка параметров политики фильтрации нежелательной почты, в том числе параметров уведомлений для конечных пользователей, отображается в правой области.</span><span class="sxs-lookup"><span data-stu-id="64c39-132">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="64c39-133">Уведомления конечных пользователей о нежелательной почте будут работать только с включенными политиками фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="64c39-133">End-user spam notifications will only be functional for spam filter policies that are enabled.</span></span> <span data-ttu-id="64c39-134">>  Уведомления о нежелательной почте отправляются конечному пользователю один раз в день.</span><span class="sxs-lookup"><span data-stu-id="64c39-134">>  End-user spam notifications are only sent once per day.</span></span> <span data-ttu-id="64c39-135">Время доставки уведомления не гарантируется для каждого конкретного пользователя, и его нельзя настроить.</span><span class="sxs-lookup"><span data-stu-id="64c39-135">The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="64c39-136">**Совет:** Если вы хотите протестировать уведомления о нежелательной почте пользователей, отправив их ограниченному набору пользователей, прежде чем приступать к их полному внедрению, создайте настраиваемую политику фильтрации нежелательной почты, позволяющую пользователям получать уведомления о нежелательной почте для доменов, в которых они находятся.</span><span class="sxs-lookup"><span data-stu-id="64c39-136">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="64c39-137">Затем в центре администрирования Exchange в разделе \*\* \> правила обработки почтового ящика\*\*создайте правило для обработки почтового ящика (также называемое правилом транспорта), чтобы заблокировать сообщения от Quarantine@messaging.microsoft.com (адрес электронной почты, который отправляет уведомления) с исключениями для пользователей, которые хотят получать уведомления.</span><span class="sxs-lookup"><span data-stu-id="64c39-137">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="64c39-138">На следующем рисунке показан пример создания исключения для двух пользователей (SaraD и AlexD) с домена Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="64c39-138">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Правило транспорта для тестирования уведомлений пользователей о нежелательной почте](../../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="use-the-scc-to-configure-end-user-spam-notifications"></a><span data-ttu-id="64c39-140">Использование SCC для настройки уведомлений конечных пользователей о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="64c39-140">Use the SCC to configure end-user spam notifications</span></span>

<span data-ttu-id="64c39-141">Вы также можете использовать центр безопасности и соответствия требованиям (SCC) для настройки уведомлений конечных пользователей о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="64c39-141">You can also use the Security and Compliance Center (SCC) to configure end-user spam notifications.</span></span> <span data-ttu-id="64c39-142">Выполните приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="64c39-142">Follow these steps:</span></span>

1. <span data-ttu-id="64c39-143">Откройте центр безопасности и соответствия требованиям, перейдите к разделу **Защита от** угроз для **политики** \> \> **управления угрозами** или https://protection.office.com/antispamиспользуйте прямую ссылку.</span><span class="sxs-lookup"><span data-stu-id="64c39-143">Open the Security and Compliance Center, navigate to **Threat management** \> **Policy** \> **Anti-spam** or use the direct link https://protection.office.com/antispam.</span></span>

2. <span data-ttu-id="64c39-144">Щелкните стрелку вниз рядом с политикой фильтрации нежелательной почты, для которой нужно включить уведомления конечных пользователей о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="64c39-144">Click the down arrow next to the spam filter policy for which you want to enable end-user spam notifications.</span></span>

3. <span data-ttu-id="64c39-145">Щелкните ссылку **настроить уведомления пользователя о нежелательной почте** .</span><span class="sxs-lookup"><span data-stu-id="64c39-145">Click on the **Configure End-user spam notifications** link.</span></span>

4. <span data-ttu-id="64c39-146">В следующем диалоговом окне можно настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="64c39-146">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="64c39-p111">**Включить уведомления пользователя о нежелательной почте** Установите этот флажок, если нужно включить уведомления для этой политики. (И наоборот: если эта политика включена, снимите этот флажок, если нужно отключить уведомления пользователя о нежелательной почте для этой политики.)</span><span class="sxs-lookup"><span data-stu-id="64c39-p111">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="64c39-p112">**Отправлять уведомления пользователя о нежелательной почте каждые (дн.)** Укажите, как часто необходимо отправлять пользователям уведомления о нежелательной почте. Значение по умолчанию  3 дня. Допустимый интервал значений  от 1 до 15 дней. Например, если вы укажете 7 дней, уведомление будет включать список всех сообщений за последние 7 дней, которые предназначались этому пользователю, но были ошибочно поставлены на карантин нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="64c39-p112">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="64c39-153">**Язык уведомлений** В раскрывающемся списке выберите язык, на котором пользователю будут отправляться уведомления о нежелательной почте для этой политики.</span><span class="sxs-lookup"><span data-stu-id="64c39-153">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="64c39-154">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="64c39-154">Click **Save**.</span></span> <span data-ttu-id="64c39-155">Сводка параметров политики фильтрации нежелательной почты, включая параметры уведомления о нежелательной почте пользователя, отображается в области.</span><span class="sxs-lookup"><span data-stu-id="64c39-155">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the pane.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="64c39-156">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="64c39-156">For more information</span></span>

[<span data-ttu-id="64c39-157">Настройка политик фильтрации нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="64c39-157">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
