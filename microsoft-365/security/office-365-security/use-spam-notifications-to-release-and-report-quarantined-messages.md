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
ms.openlocfilehash: fbe8a09f7da5df2df4b3b68bd524fa3ef2ed18b8
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "41572665"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="8dcfa-104">Использование уведомлений пользователей о спаме для освобождения сообщений из карантина и создания отчетов о них в Office 365</span><span class="sxs-lookup"><span data-stu-id="8dcfa-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="8dcfa-105">Если администратор включает уведомления о нежелательной почте для пользователей, вы получите сообщение с уведомлением, в котором перечисляются сообщения, адресованные почтовому ящику, которые были идентифицированы как спам и помещены в карантин.</span><span class="sxs-lookup"><span data-stu-id="8dcfa-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>

> [!TIP]
> <span data-ttu-id="8dcfa-106">Если вы являетесь администратором и хотите включить эту функцию, вы можете выбрать параметр при [изменении политики защиты от нежелательной почты по умолчанию](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8dcfa-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="8dcfa-107">Полученное сообщение включает в себя количество сообщений, помещенных в карантин нежелательной почты, а также дату и время (в формате UTC) последнего сообщения в списке.</span><span class="sxs-lookup"><span data-stu-id="8dcfa-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="8dcfa-108">Список содержит следующие сведения для каждого сообщения:</span><span class="sxs-lookup"><span data-stu-id="8dcfa-108">The list includes the following for each message:</span></span>

- <span data-ttu-id="8dcfa-109">**Sender (отправитель** ) Имя отправителя и адрес электронной почты почтового сообщения, помещенного в карантин.</span><span class="sxs-lookup"><span data-stu-id="8dcfa-109">**Sender** The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="8dcfa-110">**Тема.** Текст в строке темы помещенного в карантин сообщения.</span><span class="sxs-lookup"><span data-stu-id="8dcfa-110">**Subject** The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="8dcfa-111">**Дата.** Дата и время (в формате UTC) помещения сообщения в карантин.</span><span class="sxs-lookup"><span data-stu-id="8dcfa-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span>

<span data-ttu-id="8dcfa-112">Ниже приведены действия, которые можно выполнить с сообщением в карантине.</span><span class="sxs-lookup"><span data-stu-id="8dcfa-112">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="8dcfa-113">**Блокировать отправителя** , если вы хотите, чтобы Office 365 добавить отправителя в список заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="8dcfa-113">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

- <span data-ttu-id="8dcfa-114">**Отпустите** , если сообщение не является спамом и вы хотите, чтобы Office 365 отправлял сообщение в ваш почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="8dcfa-114">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

- <span data-ttu-id="8dcfa-115">**Просмотрите** , чтобы перейти на портал карантина в центре безопасности и соответствия требованиям, если вы хотите выполнить другие действия, такие как предварительный просмотр или выпуск.</span><span class="sxs-lookup"><span data-stu-id="8dcfa-115">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>

<span data-ttu-id="8dcfa-116">Необходимо учитывать следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="8dcfa-116">Be aware of the following:</span></span>

- <span data-ttu-id="8dcfa-117">Сообщения, помещенные в карантин, так как они отвечают правилу обработки почты, не включаются в сообщения, помещенные в карантин пользователя.</span><span class="sxs-lookup"><span data-stu-id="8dcfa-117">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="8dcfa-118">В список включаются только помещенные в карантин нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="8dcfa-118">Only spam-quarantined messages are listed.</span></span>

- <span data-ttu-id="8dcfa-119">Освободить сообщение и сообщить о ложном срабатывании (о том, что сообщение не является нежелательным) можно только один раз.</span><span class="sxs-lookup"><span data-stu-id="8dcfa-119">You can only release a message and report it as a false positive (not junk) once.</span></span>
