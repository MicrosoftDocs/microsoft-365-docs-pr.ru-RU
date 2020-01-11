---
title: Карантин сообщений электронной почты в Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: Вы можете настроить карантин для входящих сообщений электронной почты в Office 365, где входящие сообщения электронной почты, которые были отфильтрованы как спам, массовые, фишинговую почту и вредоносные программы, можно хранить для последующего просмотра.
ms.openlocfilehash: f7669f69abb711d71362057f2019b0dd7e30443b
ms.sourcegitcommit: 40e83b22b74db8e37d65e0988d4c11de3aa541b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2020
ms.locfileid: "41021855"
---
# <a name="quarantine-email-messages-in-office-365"></a><span data-ttu-id="df783-103">Карантин сообщений электронной почты в Office 365</span><span class="sxs-lookup"><span data-stu-id="df783-103">Quarantine email messages in Office 365</span></span>

<span data-ttu-id="df783-104">Вы можете настроить карантин для входящих сообщений электронной почты в Office 365, где сообщения, которые были отфильтрованы как спам, массовая рассылка, Фишинговая почта, почта, содержащая вредоносные программы, и почта, соответствующая правилу обработки почты (также известной как правило ТРАСПОРТ), можно сохранить для последующего использования. Смотрите.</span><span class="sxs-lookup"><span data-stu-id="df783-104">You can set up quarantine for incoming email messages in Office 365 where messages that have been filtered as spam, bulk mail, phishing mail, mail that contains malware, and mail that matched a specified mail flow rule (also known as a trasport rule) can be kept for later review.</span></span>
  
<span data-ttu-id="df783-105">По умолчанию сообщения, которые были отфильтрованы для правил фишинга, вредоносных программ и почтовых ящиков, отправляются в карантин, а сообщения, которые были отфильтрованы как спам и массовая почта, отправляются в папку нежелательной почты получателей.</span><span class="sxs-lookup"><span data-stu-id="df783-105">By default, messages that were filtered for phishing, malware, and mail flow rules are sent to quarantine, while messages that were filtered as spam and bulk mail are sent to the recipients' Junk Email folder.</span></span> <span data-ttu-id="df783-106">Как администратор вы можете настроить политики фильтрации нежелательной почты (также называемые политиками фильтрации содержимого), чтобы отправлять нежелательные сообщения электронной почты и массовые сообщения в карантин.</span><span class="sxs-lookup"><span data-stu-id="df783-106">As an admin, you can set up spam filter policies (also known as content filter policies) to send spam and bulk mail messages to quarantine instead.</span></span> <span data-ttu-id="df783-107">Дополнительные сведения см. в статье [Настройка политик фильтрации спама](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="df783-107">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="df783-108">Пользователи и администраторы могут работать с сообщениями, помещенными в карантин.</span><span class="sxs-lookup"><span data-stu-id="df783-108">Both users and admins can work with quarantined messages.</span></span> <span data-ttu-id="df783-109">Пользователи могут работать только с собственными отфильтрованными сообщениями в карантине.</span><span class="sxs-lookup"><span data-stu-id="df783-109">Users can work with just their own filtered messages in quarantine.</span></span> <span data-ttu-id="df783-110">Администраторы могут искать сообщения, помещенные в карантин, и управлять ими для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="df783-110">Admins can search for and manage quarantined messages for all users.</span></span>

> [!NOTE]
> <span data-ttu-id="df783-111">Сообщения с высоким уровнем достоверности и сообщения, помещенные в карантин с помощью действий правил обработки почтового ящика, доступны только в карантине администратора.</span><span class="sxs-lookup"><span data-stu-id="df783-111">High confidence phish messages and messages quarantined by mail flow rule actions are only available in the admin quarantine.</span></span> <span data-ttu-id="df783-112">Пользователи могут получать доступ к собственным phishing-сообщениям, нежелательной почте и пакетным сообщениям.</span><span class="sxs-lookup"><span data-stu-id="df783-112">Users can access their own phish, spam, and bulk mail messages.</span></span> 
  
<span data-ttu-id="df783-113">Дополнительные сведения о работе с сообщениями, помещенными в карантин:</span><span class="sxs-lookup"><span data-stu-id="df783-113">Learn more about working with quarantined messages:</span></span>
  
- [<span data-ttu-id="df783-114">Управление сообщениями, помещенными в карантин, от имени администратора</span><span class="sxs-lookup"><span data-stu-id="df783-114">Manage quarantined messages as an administrator</span></span>](manage-quarantined-messages-and-files.md)

- [<span data-ttu-id="df783-115">Поиск и освобождение сообщений из карантина от имени пользователя</span><span class="sxs-lookup"><span data-stu-id="df783-115">Find and release quarantined messages as a user</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- [<span data-ttu-id="df783-116">Использование уведомлений о нежелательной почте для освобождения и отправки отчетов о сообщениях, помещенных в карантин</span><span class="sxs-lookup"><span data-stu-id="df783-116">Use user spam notifications to release and report spam-quarantined messages</span></span>](use-spam-notifications-to-release-and-report-quarantined-messages.md)

- [<span data-ttu-id="df783-117">Вопросы и ответы, посвященные карантину</span><span class="sxs-lookup"><span data-stu-id="df783-117">Quarantine FAQ</span></span>](quarantine-faq.md)
