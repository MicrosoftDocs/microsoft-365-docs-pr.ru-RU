---
title: Использование уведомлений пользователей о спаме для освобождения сообщений из карантина и создания отчетов о них в Office 365
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 51fcdefc08987b153d045994927f56df3b670fd0
ms.sourcegitcommit: 836bd8135cc49d6db37e78a7cfeb7d2cc4159e4e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722040"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="d63ab-104">Использование уведомлений пользователей о спаме для освобождения сообщений из карантина и создания отчетов о них в Office 365</span><span class="sxs-lookup"><span data-stu-id="d63ab-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="d63ab-105">Если администратор включает уведомления о нежелательной почте для пользователей, вы получите сообщение с уведомлением, в котором перечисляются сообщения, адресованные почтовому ящику, которые были идентифицированы как спам, массовый или фишинг и помещены в карантин.</span><span class="sxs-lookup"><span data-stu-id="d63ab-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam, bulk, or phish and quarantined instead.</span></span>

> [!TIP]
> <span data-ttu-id="d63ab-106">Если вы являетесь администратором и хотите включить эту функцию, вы можете выбрать параметр при [изменении политики защиты от нежелательной почты по умолчанию](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d63ab-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="d63ab-107">Полученное сообщение включает в себя количество сообщений, помещенных в карантин нежелательной почты, а также дату и время (в формате UTC) последнего сообщения в списке.</span><span class="sxs-lookup"><span data-stu-id="d63ab-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="d63ab-108">Список содержит следующие сведения для каждого сообщения:</span><span class="sxs-lookup"><span data-stu-id="d63ab-108">The list includes the following for each message:</span></span>

- <span data-ttu-id="d63ab-109">**Sender (отправитель** ) Имя отправителя и адрес электронной почты почтового сообщения, помещенного в карантин.</span><span class="sxs-lookup"><span data-stu-id="d63ab-109">**Sender** The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="d63ab-110">**Тема.** Текст в строке темы помещенного в карантин сообщения.</span><span class="sxs-lookup"><span data-stu-id="d63ab-110">**Subject** The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="d63ab-111">**Дата.** Дата и время (в формате UTC) помещения сообщения в карантин.</span><span class="sxs-lookup"><span data-stu-id="d63ab-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span>

<span data-ttu-id="d63ab-112">Ниже приведены действия, которые можно выполнить с сообщением в карантине.</span><span class="sxs-lookup"><span data-stu-id="d63ab-112">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="d63ab-113">**Блокировать отправителя** , если вы хотите, чтобы Office 365 добавить отправителя в список заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="d63ab-113">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

- <span data-ttu-id="d63ab-114">**Отпустите** , если сообщение не является спамом и вы хотите, чтобы Office 365 отправлял сообщение в ваш почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="d63ab-114">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

- <span data-ttu-id="d63ab-115">**Просмотрите** , чтобы перейти на портал карантина в центре безопасности и соответствия требованиям, если вы хотите выполнить другие действия, такие как предварительный просмотр или выпуск.</span><span class="sxs-lookup"><span data-stu-id="d63ab-115">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>

<span data-ttu-id="d63ab-116">Необходимо учитывать следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="d63ab-116">Be aware of the following:</span></span>

- <span data-ttu-id="d63ab-117">Конфиденциальные сообщения и сообщения с высокой достоверностью, помещенные в карантин, так как они отвечают правилу обработки почты пользователя, не включаются в уведомления о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="d63ab-117">Malware and high confidence phishing messages and messages that are quarantined because they matched a mail flow rule are not included in user spam notifications.</span></span> 

- <span data-ttu-id="d63ab-118">Освободить сообщение и сообщить о ложном срабатывании (о том, что сообщение не является нежелательным) можно только один раз.</span><span class="sxs-lookup"><span data-stu-id="d63ab-118">You can only release a message and report it as a false positive (not junk) once.</span></span>
