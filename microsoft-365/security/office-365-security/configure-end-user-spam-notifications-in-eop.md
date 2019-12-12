---
title: Настройка уведомлений пользователей о спаме в службе EOP
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
ms.collection:
- M365-security-compliance
description: Вы можете настроить уведомления пользователя о нежелательной почте для используемой по умолчанию политики фильтрации содержимого в компании или для настраиваемых политик фильтрации содержимого, которые применяются к доменам.
ms.openlocfilehash: 626d24b3a828ef90200c105bc2d4f5dd8572efe3
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2019
ms.locfileid: "39909859"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a><span data-ttu-id="3dc61-103">Настройка уведомлений пользователей о спаме в службе EOP</span><span class="sxs-lookup"><span data-stu-id="3dc61-103">Configure end-user spam notifications in EOP</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3dc61-104">Эта статья предназначена для клиентов изолированной службы Exchange Online Protection (EOP), которые обеспечивают защиту своих локальных почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="3dc61-104">This topic is for Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes.</span></span> <span data-ttu-id="3dc61-105">Пользователи Exchange Online, которые защищают размещенные в облаке почтовые ящики, должны прочитать следующий раздел: [Настройка уведомлений о нежелательной почте для конечных пользователей в Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="3dc61-105">Exchange Online customers who are protecting cloud-hosted mailboxes should read the following topic instead: [Configure end-user spam notifications in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span></span> 
  
<span data-ttu-id="3dc61-p102">Вы можете настроить уведомления пользователя о нежелательной почте для используемой по умолчанию политики фильтрации содержимого в компании или для настраиваемых политик фильтрации содержимого, которые применяются к доменам. Если включены уведомления пользователя о спаме, конечные пользователи смогут самостоятельно управлять своими сообщениями, которые находятся на карантине нежелательной почты. Уведомления конечного пользователя о нежелательных сообщениях нельзя использовать с политиками, которые применяются к пользователям, группам или к политике с исключениями.</span><span class="sxs-lookup"><span data-stu-id="3dc61-p102">You can configure end-user spam notifications for the default company-wide content filter policy or for custom content filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="3dc61-p103">Уведомления конечного пользователя о нежелательных сообщениях содержат список всех сообщений, помещенных на карантин нежелательной почты, которые получил пользователь в течение определенного вами периода (можно указать значение между 1 и 15 днями). Можно также настроить язык сообщения уведомления.</span><span class="sxs-lookup"><span data-stu-id="3dc61-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="3dc61-111">После получения сообщения с уведомлением пользователи могут выбрать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="3dc61-111">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="3dc61-112">**Блокировать отправителя** , если вы хотите, чтобы Office 365 добавить отправителя в список заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="3dc61-112">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="3dc61-113">**Отпустите** , если сообщение не является спамом и вы хотите, чтобы Office 365 отправлял сообщение в ваш почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="3dc61-113">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="3dc61-114">**Просмотрите** , чтобы перейти на портал карантина в центре безопасности и соответствия требованиям, если вы хотите выполнить другие действия, такие как предварительный просмотр или выпуск.</span><span class="sxs-lookup"><span data-stu-id="3dc61-114">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3dc61-115">Что нужно знать перед началом работы?</span><span class="sxs-lookup"><span data-stu-id="3dc61-115">What do you need to know before you begin?</span></span>
<span data-ttu-id="3dc61-116"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="3dc61-116"></span></span>

<span data-ttu-id="3dc61-117">Предполагаемое время для завершения: 5 минут.</span><span class="sxs-lookup"><span data-stu-id="3dc61-117">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="3dc61-p104">Для выполнения этих процедур необходимы соответствующие разрешения. Сведения о необходимых разрешениях см. в статье Запись "Защита от нежелательной почты" в разделе [Разрешения на функции в службе EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="3dc61-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
  
<span data-ttu-id="3dc61-120">Дополнительные сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в статье [сочетания клавиш для центра администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="3dc61-120">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="3dc61-121">Настройка уведомлений пользователя о нежелательной почте с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="3dc61-121">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="3dc61-122">В центре администрирования Exchange перейдите в раздел **Защита от** > **нежелательной почты**.</span><span class="sxs-lookup"><span data-stu-id="3dc61-122">In the Exchange Admin Center (EAC), navigate to **Protection** > **Spam filter**.</span></span>
    
2. <span data-ttu-id="3dc61-123">Выберите политику фильтрации содержимого, для которой нужно включить уведомления пользователя о спаме (по умолчанию они отключены).</span><span class="sxs-lookup"><span data-stu-id="3dc61-123">Select the content filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="3dc61-124">На правой панели, на которой отображается сводная информация о вашей политике, выберите ссылку **Включить уведомления пользователя о нежелательной почте**.</span><span class="sxs-lookup"><span data-stu-id="3dc61-124">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="3dc61-125">В следующем диалоговом окне можно настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="3dc61-125">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="3dc61-p105">**Включить уведомления пользователя о нежелательной почте** Установите этот флажок, если нужно включить уведомления для этой политики. (И наоборот: если эта политика включена, снимите этот флажок, если нужно отключить уведомления пользователя о нежелательной почте для этой политики.)</span><span class="sxs-lookup"><span data-stu-id="3dc61-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="3dc61-p106">**Отправлять уведомления пользователя о нежелательной почте каждые (дн.)** Укажите, как часто необходимо отправлять пользователям уведомления о нежелательной почте. Значение по умолчанию  3 дня. Допустимый интервал значений  от 1 до 15 дней. Например, если вы укажете 7 дней, уведомление будет включать список всех сообщений за последние 7 дней, которые предназначались этому пользователю, но были ошибочно поставлены на карантин нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="3dc61-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="3dc61-132">**Язык уведомлений** В раскрывающемся списке выберите язык, на котором пользователю будут отправляться уведомления о нежелательной почте для этой политики.</span><span class="sxs-lookup"><span data-stu-id="3dc61-132">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="3dc61-p107">Нажмите кнопку **Сохранить**. Сводка ваших текущих параметров политики фильтрации содержимого, включая параметры уведомлений пользователя о нежелательной почте, отображается на правой панели.</span><span class="sxs-lookup"><span data-stu-id="3dc61-p107">Click **save**. A summary of your content filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="3dc61-p108">Уведомления пользователя о спаме будут работать только для включенных политик фильтрации содержимого. >  Уведомления о нежелательной почте отправляются конечному пользователю один раз в день. Время доставки уведомления не гарантируется для каждого конкретного пользователя, и его нельзя настроить.</span><span class="sxs-lookup"><span data-stu-id="3dc61-p108">End-user spam notifications will only be functional for content filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="3dc61-138">**Совет:** Если вы хотите протестировать уведомления о нежелательной почте пользователей, отправив их ограниченному набору пользователей, прежде чем приступать к их полному внедрению, создайте настраиваемую политику фильтрации содержимого, позволяющую пользователям получать уведомления о нежелательной почте для доменов, в которых они находятся.</span><span class="sxs-lookup"><span data-stu-id="3dc61-138">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom content filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="3dc61-139">Затем в центре администрирования Exchange в разделе \*\* \> правила обработки почтового ящика\*\*создайте правило для обработки почтового ящика (также называемое правилом транспорта), чтобы заблокировать сообщения от Quarantine@messaging.microsoft.com (адрес электронной почты, который отправляет уведомления) с исключениями для пользователей, которые хотят получать уведомления.</span><span class="sxs-lookup"><span data-stu-id="3dc61-139">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="3dc61-140">На следующем рисунке показан пример создания исключения для двух пользователей (SaraD и AlexD) с домена Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="3dc61-140">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Правило транспорта для тестирования уведомлений пользователей о нежелательной почте](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="3dc61-142">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3dc61-142">For more information</span></span>

[<span data-ttu-id="3dc61-143">Настройка политик фильтрации нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="3dc61-143">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
