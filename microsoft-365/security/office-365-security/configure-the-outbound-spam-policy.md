---
title: Настройка правил защиты от спама для исходящих сообщений
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/10/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: Фильтрация исходящей нежелательной почты всегда включена, если эта служба используется для отправки исходящей почты, тем самым помогая защищать организации, использующие эту службу, и их получателей.
ms.openlocfilehash: 9c8c2f7e9ff0be02f11fa66409690cbb854d8c56
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090447"
---
# <a name="configure-the-outbound-spam-policy"></a><span data-ttu-id="b067f-103">Настройка правил защиты от спама для исходящих сообщений</span><span class="sxs-lookup"><span data-stu-id="b067f-103">Configure the outbound spam policy</span></span>

<span data-ttu-id="b067f-p101">Фильтрация исходящей нежелательной почты всегда включена, если эта служба используется для отправки исходящей почты, тем самым помогая защищать организации, использующие эту службу, и их получателей. Как и в случае входящих сообщений, процесс фильтрации исходящих сообщений состоит из фильтрации подключений и фильтрации содержимого, однако настройки исходящей фильтрации не настраиваются. Если исходящее сообщение определено как нежелательное, оно маршрутизируется через пул доставки более высокого риска, что снижает вероятность добавления в список блокировок обычного пула исходящих IP-адресов. Если клиент продолжит отправлять через службу нежелательную почту, отправка сообщений для него будет заблокирована. Хотя фильтрация исходящих сообщений не может быть отключена или настроена, в рамках компании можно настроить некоторые параметры для исходящей нежелательной почты с помощью политики защиты от нежелательной почты для исходящих сообщений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b067f-p101">Outbound spam filtering is always enabled if you use the service for sending outbound email, thereby protecting organizations using the service and their intended recipients. Similar to inbound filtering, outbound spam filtering is comprised of connection filtering and content filtering, however the outbound filter settings are not configurable. If an outbound message is determined to be spam, it is routed through the higher risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list. If a customer continues to send outbound spam through the service, they will be blocked from sending messages. Although outbound spam filtering cannot be disabled or changed, you can configure several company-wide outbound spam settings via the default outbound spam policy.</span></span> 
  
<span data-ttu-id="b067f-109">На следующем видео показан процесс настройки правил защиты от нежелательной почты для исходящих сообщений:</span><span class="sxs-lookup"><span data-stu-id="b067f-109">The following video shows how to configure the outbound spam policy:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1f20d655-0d3d-4141-9cae-e57f5a6cffe8?autoplay=false]
  
> [!NOTE]
> <span data-ttu-id="b067f-110">Чтобы получить лучшие результаты фильтрации, содержимое видео, приведенное выше, должно использоваться с правильной настройкой, а также знакомство с [элементами управления нежелательной почтой в Office 365](https://docs.microsoft.com/office365/securitycompliance/outbound-spam-controls).</span><span class="sxs-lookup"><span data-stu-id="b067f-110">For the best filtering results, the content in the video above should used with a proper setup, and familiarity with [Outbound spam controls in Office 365](https://docs.microsoft.com/office365/securitycompliance/outbound-spam-controls).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b067f-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="b067f-111">What do you need to know before you begin?</span></span>
<span data-ttu-id="b067f-112"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="b067f-112"></span></span>

<span data-ttu-id="b067f-113">Предполагаемое время для завершения: 5 минут.</span><span class="sxs-lookup"><span data-stu-id="b067f-113">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="b067f-114">Для выполнения этих процедур необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="b067f-114">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="b067f-115">Чтобы просмотреть необходимые разрешения, обратитесь к разделу "Защита от нежелательной почты" в разделе [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b067f-115">To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="b067f-116">Дополнительные сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в статье [сочетания клавиш для центра администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="b067f-116">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
<span data-ttu-id="b067f-117">Следующую процедуру также можно выполнить в удаленном сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b067f-117">The following procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="b067f-118">Используйте командлет [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) для просмотра параметров, а командлет [Set-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) — для изменения параметров политики исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="b067f-118">Use the [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) cmdlet to review your settings, and the [Set-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) to edit your outbound spam policy settings.</span></span> <span data-ttu-id="b067f-119">Чтобы узнать, как использовать Windows PowerShell для подключения к Exchange Online Protection, ознакомьтесь [со статьей подключение к PowerShell для Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=627290).</span><span class="sxs-lookup"><span data-stu-id="b067f-119">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span> <span data-ttu-id="b067f-120">Сведения о том, как с помощью Оболочка Windows PowerShell подключаться к Exchange Online, см. в статье [Подключение к PowerShell для Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="b067f-120">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
  
## <a name="use-the-eac-to-edit-the-default-outbound-spam-policy"></a><span data-ttu-id="b067f-121">Использование Центра администрирования Exchange для редактирования правил защиты от нежелательной почты для исходящих сообщений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b067f-121">Use the EAC to edit the default outbound spam policy</span></span>
<span data-ttu-id="b067f-122"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="b067f-122"></span></span>

<span data-ttu-id="b067f-123">Для редактирования правил защиты от нежелательной почты для исходящих сообщений по умолчанию следуйте указанной ниже процедуре.</span><span class="sxs-lookup"><span data-stu-id="b067f-123">Use the following procedure to edit the default outbound spam policy:</span></span>
  
### <a name="to-configure-the-default-outbound-spam-policy"></a><span data-ttu-id="b067f-124">Настройка правил защиты от нежелательной почты для исходящих сообщений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b067f-124">To configure the default outbound spam policy</span></span>

1. <span data-ttu-id="b067f-125">В Центре администрирования Exchange перейдите на вкладку **Защита** \> **Нежелательная почта для исходящих сообщений** и дважды щелкните ссылку политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b067f-125">In the Exchange admin center (EAC), navigate to **Protection** \> **Outbound spam**, and then double-click the default policy.</span></span>
    
2. <span data-ttu-id="b067f-126">Выберите в меню пункт **Настройки нежелательной почты для исходящих сообщений**.</span><span class="sxs-lookup"><span data-stu-id="b067f-126">Select the **Outbound spam preferences** menu option.</span></span> 
    
3. <span data-ttu-id="b067f-127">Установите флажки для исходящих сообщений, затем в дополнительном поле ввода укажите один или несколько связанных адресов электронной почты (это могут быть списки рассылки, если они разрешены в допустимые адреса назначения сервера SMTP).</span><span class="sxs-lookup"><span data-stu-id="b067f-127">Select the following check boxes pertaining to outbound messages, and then specify an associated email address or addresses in the accompanying input box (these can be distribution lists if they resolve as valid SMTP destinations):</span></span>
    
1. <span data-ttu-id="b067f-p104">**Отправить копию всех подозрительных почтовых сообщений на следующий почтовый адрес или почтовые адреса**. Здесь находятся сообщения, которые отмечены фильтром как нежелательные (независимо от показателя вероятности нежелательной почты). Они не отклоняются фильтром, но направляются через пул доставки сообщений с более высокой степенью опасности. Несколько отдельных адресов, разделенных точкой с запятой. Обратите внимание, что указанные получатели получат сообщения с адреса получателя скрытой копии (в полях "От" и "Кому" указываются исходные отправитель и получатель).</span><span class="sxs-lookup"><span data-stu-id="b067f-p104">**Send a copy of all suspicious outbound email messages to the following email address or addresses**. These are messages that are marked as spam by the filter (regardless of the SCL rating). They are not rejected by the filter but are routed through the higher risk delivery pool. Separate multiple addresses with a semicolon. Note that the recipients specified will receive the messages as a Blind carbon copy (Bcc) address (the From and To fields are the original sender and recipient).</span></span>
    
2. <span data-ttu-id="b067f-p105">**Отправить уведомление на следующий почтовый адрес при блокировании нежелательной исходящей почты отправителя**. Несколько отдельных адресов, разделенных точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="b067f-p105">**Send a notification to the following email address when a sender is blocked sending outbound spam**. Separate multiple addresses with a semicolon.</span></span>
    
    <span data-ttu-id="b067f-p106">Если определенный пользователь отправляет значительный объем нежелательной почты, отключается возможность отправки электронных сообщений от этого пользователя. Назначенный с помощью данного параметра администратор домена получит уведомление о блокировании исходящих сообщений для этого пользователя. Внешний вид этого уведомление см. в статье [Пример уведомления, отправляемого в случае блокирования отправки спама для отправителя](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md). Сведения о том, как повторно включить пользователю отправку сообщений, см. в статье [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span><span class="sxs-lookup"><span data-stu-id="b067f-p106">When a significant amount of spam is originating from a particular user, the user is disabled from sending email messages. The administrator for the domain, who is specified using this setting, will be informed that outbound messages are blocked for this user. To see what this notification looks like, see [Sample notification when a sender is blocked sending outbound spam](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md). For information about getting re-enabled, see [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span></span>
    
4. <span data-ttu-id="b067f-p107">Нажмите кнопку **Сохранить**. Сводка параметров политики по умолчанию отображается на правой панели.</span><span class="sxs-lookup"><span data-stu-id="b067f-p107">Click **save**. A summary of your default policy settings appears in the right pane.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="b067f-141">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="b067f-141">For more information</span></span>
<span data-ttu-id="b067f-142"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="b067f-142"></span></span>

[<span data-ttu-id="b067f-143">Пул доставки сообщений с высоким уровнем опасности</span><span class="sxs-lookup"><span data-stu-id="b067f-143">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)
  
[<span data-ttu-id="b067f-144">Вопросы и ответы по защите от нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="b067f-144">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

