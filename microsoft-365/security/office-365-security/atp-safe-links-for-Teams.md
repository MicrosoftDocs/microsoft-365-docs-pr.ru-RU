---
title: Безопасные ссылки на Office 365 ATP для Teams, сафелинкс, безопасные ссылки, блокировать вредоносные ссылки, Office 365 ATP, безопасные ссылки Teams, остановить пользователей щелкать неправильные ссылки, вредоносные ссылки
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Теперь Teams будет иметь доступ к безопасным ссылкам во время щелчка. Если вы используете сеансы разговора 1 — от 1, между группами, в каналах и на вкладках, если у вас есть подписка на Office 365 ATP, вы сможете включить и использовать эту функцию безопасности.
ms.openlocfilehash: 864b211a1f007a0f6bde83da12b61362b53bf041
ms.sourcegitcommit: ce6121a8e3ca7438071d73b0c76e2b6f33ac1cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "43030146"
---
<!--06/21/2019-->

# <a name="office-365-safe-links-in-teams"></a><span data-ttu-id="02bd0-104">Безопасные ссылки на Office 365 в Teams</span><span class="sxs-lookup"><span data-stu-id="02bd0-104">Office 365 Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02bd0-105">Эта функция доступна в **общедоступной предварительной версии** для клиентов в программе внедрения технологий Microsoft Teams (TAP) на 28 февраля 2020 г.</span><span class="sxs-lookup"><span data-stu-id="02bd0-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="02bd0-106">Это примечание будет удалено из статьи, когда безопасные ссылки для Teams более широко доступны.</span><span class="sxs-lookup"><span data-stu-id="02bd0-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="02bd0-107">Microsoft Teams — облачное приложение Office 365 для управления работой, уже использующее безопасные вложения (для Office 365), но теперь у него есть доступ к безопасным каналам на момент щелчка.</span><span class="sxs-lookup"><span data-stu-id="02bd0-107">Microsoft Teams, an Office 365 Cloud-based application for managing your work, already uses safe attachments (for Office 365), but it will now have access to safe links at the time of your click.</span></span> <span data-ttu-id="02bd0-108">Независимо от того, используете ли сеансы разговора 1 — в одной группе, в каналах и на вкладках, если у вас есть подписка на Office 365 ATP, вы сможете включить и использовать этот показатель безопасности.</span><span class="sxs-lookup"><span data-stu-id="02bd0-108">Whether you're using chats 1-on-1 Chats, between Groups, or in Channels, and Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span>

<span data-ttu-id="02bd0-109">Вот как это работает:</span><span class="sxs-lookup"><span data-stu-id="02bd0-109">Here's how it works:</span></span> 

1. <span data-ttu-id="02bd0-110">Когда вы запускаете приложение Teams, Office 365 проверит, входит ли пользователь в организацию, имеющую Office 365 ATP, и что пользователь входит в активную политику безопасных ссылок с включенной защитой для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="02bd0-110">When you start the Teams application, Office 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="02bd0-111">Если вышеприведенные условия верны, URL-адреса будут проверяться во время щелчков в беседах, групповых чатов, каналов и на вкладках для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="02bd0-111">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>
 
## <a name="what-will-users-experience"></a><span data-ttu-id="02bd0-112">Что будет работать пользователям?</span><span class="sxs-lookup"><span data-stu-id="02bd0-112">What will users experience?</span></span> 

<span data-ttu-id="02bd0-113">Все защищенные пользователи будут иметь такой интерфейс с URL-адресами опасного:</span><span class="sxs-lookup"><span data-stu-id="02bd0-113">All protected users will have this experience with hazardous URLs:</span></span> 

- <span data-ttu-id="02bd0-114">Если ссылка была выбрана из беседы Teams, группового чата или из каналов, страница будет отображаться в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="02bd0-114">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="02bd0-115">Если ссылка была выбрана из закрепленной вкладки, эта страница появится в графическом интерфейсе Teams на этой вкладке, а параметр Открыть в браузере будет отключен в целях обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="02bd0-115">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="02bd0-116">Этот пользователь не будет переходить на сайт URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="02bd0-116">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="02bd0-117">Если пользователь, который отправил ссылку, не защищен Office 365 ATP, он может щелкнуть его URL-адрес на своем компьютере и устранить неполадку на сайте.</span><span class="sxs-lookup"><span data-stu-id="02bd0-117">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="02bd0-118">Это существенно важно для администраторов Office 365, которые должны знать о том, кто из них имеет свои защищенные пользователи.</span><span class="sxs-lookup"><span data-stu-id="02bd0-118">This makes it doubly important for Office 365 Administrators to be aware of who their protected users are and should be.</span></span>

![Страница безопасных ссылок для Teams, сообщающая о вредоносной ссылке и блокирующей транзит к странице.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="02bd0-120">Нажатие кнопки *"вернуться* " на этой странице в Teams закрывает ее (или может привести к закрытию пустой страницы).</span><span class="sxs-lookup"><span data-stu-id="02bd0-120">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="02bd0-121">Однако повторное нажатие этой ссылки приведет к повторной оценке репутации сайта, чтобы эта страница снова появилась.</span><span class="sxs-lookup"><span data-stu-id="02bd0-121">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
><span data-ttu-id="02bd0-122">Некоторые администраторы Office 365 будут включать сообщение **"продолжить все все** " на странице "Блокировка".</span><span class="sxs-lookup"><span data-stu-id="02bd0-122">Some Office 365 Admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="02bd0-123">Тем не менее, если безопасные ссылки измеряют репутацию сайта и не могут найти его, дальнейшая дальнейшая переход не выполняется.</span><span class="sxs-lookup"><span data-stu-id="02bd0-123">However, if safe links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="02bd0-124">Не рекомендуется, чтобы пользователи обходили показатели безопасности.</span><span class="sxs-lookup"><span data-stu-id="02bd0-124">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="02bd0-125">Перед тем как приступить к работе, взвесьте это в своих рекомендациях.</span><span class="sxs-lookup"><span data-stu-id="02bd0-125">Please weigh this into your considerations before enabling Continue Anyway.</span></span> 

