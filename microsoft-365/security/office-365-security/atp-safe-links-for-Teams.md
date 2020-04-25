---
title: Безопасные ссылки ATP для Teams, сафелинкс, безопасные ссылки, блокировать вредоносные ссылки, Office 365 ATP, безопасные ссылки, остановить пользователей щелкать неправильные ссылки, вредоносные ссылки
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
ms.openlocfilehash: 07f20f0adf503e4592d2bd3f3bc9857d08a1e433
ms.sourcegitcommit: 481fb95d8b80cf2102a9c73b21e7effa79e594e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2020
ms.locfileid: "43809004"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a><span data-ttu-id="452eb-104">Безопасные ссылки в Teams</span><span class="sxs-lookup"><span data-stu-id="452eb-104">Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="452eb-105">Эта функция доступна в **общедоступной предварительной версии** для клиентов в программе внедрения технологий Microsoft Teams (TAP) на 28 февраля 2020 г.</span><span class="sxs-lookup"><span data-stu-id="452eb-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="452eb-106">Это примечание будет удалено из статьи, когда безопасные ссылки для Teams более широко доступны.</span><span class="sxs-lookup"><span data-stu-id="452eb-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="452eb-107">Microsoft Teams — приложение на основе Microsoft Cloud для управления работой, уже использует безопасные вложения (для Office 365), но теперь у него есть доступ к безопасным каналам на момент щелчка.</span><span class="sxs-lookup"><span data-stu-id="452eb-107">Microsoft Teams, a Microsoft cloud-based application for managing your work, already uses Safe Attachments (for Office 365), but it will now have access to Safe Links at the time of your click.</span></span> <span data-ttu-id="452eb-108">Независимо от того, используете ли вы сеансы бесед, групповых чатов, каналы или вкладки, если у вас есть подписка на Office 365 ATP, вы сможете включить и использовать этот показатель безопасности.</span><span class="sxs-lookup"><span data-stu-id="452eb-108">Whether you're using Chats, Group Chats, Channels, or Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span> <span data-ttu-id="452eb-109">Дополнительные сведения о требованиях к лицензированию см. в статье [Рекомендации по лицензированию служб на уровне клиента Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="452eb-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

<span data-ttu-id="452eb-110">Вот как это работает:</span><span class="sxs-lookup"><span data-stu-id="452eb-110">Here's how it works:</span></span> 

1. <span data-ttu-id="452eb-111">Когда вы запускаете приложение Teams, Microsoft 365 проверит, принадлежит ли пользователь к Организации, имеющей Office 365 ATP, и что пользователь входит в активную политику безопасных ссылок с включенной защитой для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="452eb-111">When you start the Teams application, Microsoft 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="452eb-112">Если вышеприведенные условия верны, URL-адреса будут проверяться во время щелчков в беседах, групповых чатов, каналов и на вкладках для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="452eb-112">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>
 
## <a name="what-will-users-experience"></a><span data-ttu-id="452eb-113">Что будет работать пользователям?</span><span class="sxs-lookup"><span data-stu-id="452eb-113">What will users experience?</span></span> 

<span data-ttu-id="452eb-114">Все защищенные пользователи будут иметь такой интерфейс с URL-адресами опасного:</span><span class="sxs-lookup"><span data-stu-id="452eb-114">All protected users will have this experience with hazardous URLs:</span></span> 

- <span data-ttu-id="452eb-115">Если ссылка была выбрана из беседы Teams, группового чата или из каналов, страница будет отображаться в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="452eb-115">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="452eb-116">Если ссылка была выбрана из закрепленной вкладки, эта страница появится в графическом интерфейсе Teams на этой вкладке, а параметр Открыть в браузере будет отключен в целях обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="452eb-116">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="452eb-117">Этот пользователь не будет переходить на сайт URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="452eb-117">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="452eb-118">Если пользователь, который отправил ссылку, не защищен Office 365 ATP, он может щелкнуть его URL-адрес на своем компьютере и устранить неполадку на сайте.</span><span class="sxs-lookup"><span data-stu-id="452eb-118">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="452eb-119">Это позволяет администраторам знать о том, кто из них имеет доступ к своим защищенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="452eb-119">This makes it doubly important for administrators to be aware of who their protected users are and should be.</span></span>

![Страница безопасных ссылок для Teams, сообщающая о вредоносной ссылке и блокирующей транзит к странице.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="452eb-121">Нажатие кнопки *"вернуться* " на этой странице в Teams закрывает ее (или может привести к закрытию пустой страницы).</span><span class="sxs-lookup"><span data-stu-id="452eb-121">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="452eb-122">Однако повторное нажатие этой ссылки приведет к повторной оценке репутации сайта, чтобы эта страница снова появилась.</span><span class="sxs-lookup"><span data-stu-id="452eb-122">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
> <span data-ttu-id="452eb-123">Некоторые администраторы Microsoft 365 будут включать сообщение **"продолжить все все** " на странице "Блокировка".</span><span class="sxs-lookup"><span data-stu-id="452eb-123">Some Microsoft 365 admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="452eb-124">Тем не менее, если безопасные ссылки измеряют репутацию сайта и не могут найти его, дальнейшая дальнейшая переход не выполняется.</span><span class="sxs-lookup"><span data-stu-id="452eb-124">However, if Safe Links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="452eb-125">Не рекомендуется, чтобы пользователи обходили показатели безопасности.</span><span class="sxs-lookup"><span data-stu-id="452eb-125">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="452eb-126">Перед тем как приступить к работе, взвесьте это в своих рекомендациях.</span><span class="sxs-lookup"><span data-stu-id="452eb-126">Please weigh this into your considerations before enabling Continue Anyway.</span></span> 
