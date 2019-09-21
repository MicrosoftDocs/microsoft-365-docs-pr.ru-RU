---
title: Использование уведомлений пользователей о спаме для освобождения сообщений из карантина и создания отчетов о них в Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: Если администратор включает уведомления для пользователей, вы получите сообщение с уведомлением о том, что сообщения, отправленные в ваш почтовый ящик, были идентифицированы как спам, массовые или фишинговые сообщения. Вы можете отпустить или отправить отчет о сообщениях после получения уведомления.
ms.openlocfilehash: 499af3ae2934eed19e421918af07a45b72fe2518
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090938"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="4e6b3-104">Использование уведомлений пользователей о спаме для освобождения сообщений из карантина и создания отчетов о них в Office 365</span><span class="sxs-lookup"><span data-stu-id="4e6b3-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="4e6b3-105">Если администратор включает уведомления о нежелательной почте для пользователей, вы получите сообщение с уведомлением, в котором перечисляются сообщения, адресованные почтовому ящику, которые были идентифицированы как спам и помещены в карантин.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="4e6b3-106">Если вы являетесь администратором и хотите включить эту функцию, вы можете выбрать параметр при [изменении политики защиты от нежелательной почты по умолчанию](https://go.microsoft.com/fwlink/?LinkId=800313).</span><span class="sxs-lookup"><span data-stu-id="4e6b3-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="4e6b3-107">Полученное сообщение включает в себя количество сообщений, помещенных в карантин нежелательной почты, а также дату и время (в формате UTC) последнего сообщения в списке.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="4e6b3-108">Список содержит следующие сведения для каждого сообщения:</span><span class="sxs-lookup"><span data-stu-id="4e6b3-108">The list includes the following for each message:</span></span>
  
- <span data-ttu-id="4e6b3-109">**Sender (отправитель** ) Имя отправителя и адрес электронной почты почтового сообщения, помещенного в карантин.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="4e6b3-110">**Тема.** Текст в строке темы помещенного в карантин сообщения.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="4e6b3-111">**Дата.** Дата и время (в формате UTC) помещения сообщения в карантин.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="4e6b3-112">**Size (размер** ) Размер сообщения в килобайтах (КБ).</span><span class="sxs-lookup"><span data-stu-id="4e6b3-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="4e6b3-113">Ниже приведены действия, которые можно выполнить с сообщением в карантине.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-113">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="4e6b3-114">**Просмотрите** сообщение, если вы хотите предварительно просмотреть содержимое или заголовок, прежде чем предпринимать действия.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-114">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

- <span data-ttu-id="4e6b3-115">**Скачайте** сообщение, если вы хотите просмотреть сообщение и вложения (если они есть) на устройстве, прежде чем предпринимать действия.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-115">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

- <span data-ttu-id="4e6b3-116">**Отпустите** , если сообщение не является спамом и вы хотите, чтобы Office 365 отправлял сообщение в ваш почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-116">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

- <span data-ttu-id="4e6b3-117">**Отпустите & разрешить отправителю** , если сообщение не является спамом и вы хотите, чтобы Office 365 добавить отправителя в список надежных отправителей и получателей для будущих сообщений.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-117">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails.</span></span> <span data-ttu-id="4e6b3-118">Имейте в виду, что у администратора могут быть другие конфигурации разрешений и блокировок в Организации, которые переопределяют список надежных отправителей.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-118">Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

- <span data-ttu-id="4e6b3-119">**Выпустите & отчет**, если сообщение не спама и вы хотите отправить его в свой почтовый ящик и сообщить в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-119">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

- <span data-ttu-id="4e6b3-120">**Блокировать отправителя** , если вы хотите, чтобы Office 365 добавить отправителя в список заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-120">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="4e6b3-121">Необходимо учитывать следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-121">Be aware of the following:</span></span>
  
- <span data-ttu-id="4e6b3-122">Сообщения, помещенные в карантин, так как они отвечают правилу обработки почты, не включаются в сообщения, помещенные в карантин пользователя.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-122">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="4e6b3-123">В список включаются только помещенные в карантин нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-123">Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="4e6b3-124">Освободить сообщение и сообщить о ложном срабатывании (о том, что сообщение не является нежелательным) можно только один раз.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-124">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

