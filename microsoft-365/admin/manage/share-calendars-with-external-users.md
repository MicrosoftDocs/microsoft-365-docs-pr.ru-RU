---
title: Совместное использование календарей с внешними пользователями
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: Включить общий доступ к календарю в центре администрирования Microsoft 365, чтобы пользователи могли делиться своими календарями с любыми пользователями в организации или за ее пределами.
ms.openlocfilehash: ee2b48182efec3e8bc22f47fd1657cd123ec65f8
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635814"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="d5d04-103">Совместное использование календарей с внешними пользователями</span><span class="sxs-lookup"><span data-stu-id="d5d04-103">Share calendars with external users</span></span>

<span data-ttu-id="d5d04-104">Иногда пользователям необходимо планировать встречи с людьми за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="d5d04-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="d5d04-105">Чтобы упростить процесс поиска общего времени собраний, Microsoft 365 позволяет сделать календари доступными для этих людей.</span><span class="sxs-lookup"><span data-stu-id="d5d04-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="d5d04-106">Это люди, которым необходимо видеть свободное и занятое время для пользователей в вашей организации, но у них нет учетных записей пользователей для Microsoft 365 организации.</span><span class="sxs-lookup"><span data-stu-id="d5d04-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="d5d04-107">Вы можете включить общий доступ к календарю для всех пользователей в организации в центре Microsoft 365 администрирования.</span><span class="sxs-lookup"><span data-stu-id="d5d04-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d5d04-108">После включения общего доступа пользователи могут использовать Outlook Web App, чтобы делиться своими календарями с любыми пользователями в организации или за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="d5d04-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="d5d04-109">Люди внутри организации могут просматривать общий календарь вместе с собственным календарем.</span><span class="sxs-lookup"><span data-stu-id="d5d04-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="d5d04-110">Людям за пределами организации будет отправлен URL-адрес, который они могут использовать для просмотра календаря.</span><span class="sxs-lookup"><span data-stu-id="d5d04-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="d5d04-111">Пользователи в организации решают, когда и сколько делиться.</span><span class="sxs-lookup"><span data-stu-id="d5d04-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="d5d04-112">Если вы хотите поделиться календарями с организацией, использующей Exchange Server 2013 (локальное решение), администратору Exchange необходимо настроить связь проверки подлинности с облаком.</span><span class="sxs-lookup"><span data-stu-id="d5d04-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="d5d04-113">Это называется федерацией и должно соответствовать минимальным требованиям к программному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="d5d04-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="d5d04-114">Дополнительные сведения см. в разделе [Общий](/exchange/sharing-exchange-2013-help) доступ.</span><span class="sxs-lookup"><span data-stu-id="d5d04-114">See [Sharing](/exchange/sharing-exchange-2013-help) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="d5d04-115">Включить общий доступ к календарю с Microsoft 365 центра администрирования</span><span class="sxs-lookup"><span data-stu-id="d5d04-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="d5d04-116">В центре администрирования перейдите **в Параметры** \> **Org Параметры**.</span><span class="sxs-lookup"><span data-stu-id="d5d04-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="d5d04-117">На **вкладке Services** выберите **Календарь**.</span><span class="sxs-lookup"><span data-stu-id="d5d04-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="d5d04-118">На странице **Календарь** выберите, хотите ли вы позволить пользователям делиться своими календарями с людьми за пределами организации, у которых есть Microsoft 365 или Exchange.</span><span class="sxs-lookup"><span data-stu-id="d5d04-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="d5d04-119">Выберите, хотите ли вы разрешить анонимным пользователям (пользователям без учетных данных) доступ к календарям по приглашению электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d5d04-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="d5d04-120">Выберите тип данных календаря, которые будут доступны пользователям.</span><span class="sxs-lookup"><span data-stu-id="d5d04-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="d5d04-121">Вы можете разрешить всю информацию или ограничить ее только временем или временем, субъектом и расположением.</span><span class="sxs-lookup"><span data-stu-id="d5d04-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="d5d04-122">Приглашение пользователей для доступа к календарям</span><span class="sxs-lookup"><span data-stu-id="d5d04-122">Invite people to access calendars</span></span>

<span data-ttu-id="d5d04-123">После включения общего доступа владельцы календарей могут распространять приглашения на определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5d04-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="d5d04-124">Инструкции см. [в разделе Общий доступ к календарю в Outlook Web App.](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5)</span><span class="sxs-lookup"><span data-stu-id="d5d04-124">For instructions, see [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5).</span></span>

## <a name="related-content"></a><span data-ttu-id="d5d04-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="d5d04-125">Related content</span></span>

<span data-ttu-id="d5d04-126">[Включите внешний общий доступ или отключите для сайта](/sharepoint/change-external-sharing-site) (статьи)</span><span class="sxs-lookup"><span data-stu-id="d5d04-126">[Turn external sharing on or off for a site](/sharepoint/change-external-sharing-site) (article)</span></span>\
<span data-ttu-id="d5d04-127">[Обзор центра администрирования Microsoft 365](../../business-video/admin-center-overview.md) (видео)</span><span class="sxs-lookup"><span data-stu-id="d5d04-127">[Overview of the Microsoft 365 admin center](../../business-video/admin-center-overview.md) (video)</span></span>\
<span data-ttu-id="d5d04-128">[Управление электронной почтой и календарями](../email/index.yml) (страница ссылки)</span><span class="sxs-lookup"><span data-stu-id="d5d04-128">[Manage email and calendars](../email/index.yml) (link page)</span></span>