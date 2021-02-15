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
description: Узнайте, как позволить пользователям делиться своими календарями с внешними пользователями для собраний и встреч.
ms.openlocfilehash: 8204dc025f843953af13cba58fa0cf2e4d76de45
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760058"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="28279-103">Совместное использование календарей с внешними пользователями</span><span class="sxs-lookup"><span data-stu-id="28279-103">Share calendars with external users</span></span>

<span data-ttu-id="28279-104">Иногда пользователям необходимо планировать собрания с людьми за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="28279-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="28279-105">Чтобы упростить поиск общего времени собрания, Microsoft 365 позволяет сделать календари доступными для этих людей.</span><span class="sxs-lookup"><span data-stu-id="28279-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="28279-106">Это люди, которым нужно видеть свободное и занятое время для пользователей в вашей организации, но у них нет учетных записей пользователей для вашей организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="28279-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="28279-107">Вы можете включить общий доступ к календарю для всех пользователей в организации в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="28279-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="28279-108">После включения общего доступа пользователи могут использовать Outlook Web App для общего доступа к своим календарям любым пользователям внутри или за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="28279-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="28279-109">Люди в организации могут просматривать общий календарь вместе с собственным календарем.</span><span class="sxs-lookup"><span data-stu-id="28279-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="28279-110">Людям за пределами организации будет отправлен URL-адрес, который они могут использовать для просмотра календаря.</span><span class="sxs-lookup"><span data-stu-id="28279-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="28279-111">Пользователи в организации решают, когда и сколько делиться.</span><span class="sxs-lookup"><span data-stu-id="28279-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="28279-112">Если вы хотите поделиться календарями с организацией, использующей Exchange Server 2013 (локальное решение), администратору Exchange потребуется настроить отношение проверки подлинности с облаком.</span><span class="sxs-lookup"><span data-stu-id="28279-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="28279-113">Это называется федерацией и должно соответствовать минимальным требованиям к программному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="28279-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="28279-114">Дополнительные [сведения см.](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) в разделе "Общий доступ".</span><span class="sxs-lookup"><span data-stu-id="28279-114">See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="28279-115">Включить общий доступ к календарю с помощью Центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="28279-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="28279-116">В Центре администрирования перейдите в **"Параметры** \> **организации".**</span><span class="sxs-lookup"><span data-stu-id="28279-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="28279-117">На **вкладке "Службы"** выберите **"Календарь".**</span><span class="sxs-lookup"><span data-stu-id="28279-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="28279-118">На странице **"Календарь"** выберите, хотите ли вы позволить пользователям делиться своими календарями с пользователями за пределами вашей организации, у которых есть Microsoft 365 или Exchange.</span><span class="sxs-lookup"><span data-stu-id="28279-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="28279-119">Выберите, хотите ли вы разрешить анонимным пользователям (пользователям без учетных данных) доступ к календарям по приглашению по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="28279-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="28279-120">Выберите тип данных календаря, которые будут доступны пользователям.</span><span class="sxs-lookup"><span data-stu-id="28279-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="28279-121">Вы можете разрешить всю информацию или ограничить ее только временем или временем, темой и расположением.</span><span class="sxs-lookup"><span data-stu-id="28279-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="28279-122">Приглашение пользователей для доступа к календарям</span><span class="sxs-lookup"><span data-stu-id="28279-122">Invite people to access calendars</span></span>

<span data-ttu-id="28279-123">После включения общего доступа владельцы календаря могут расширять приглашения определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="28279-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="28279-124">Инструкции [см.](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) в Outlook Web App разделе "Общий доступ к календарю".</span><span class="sxs-lookup"><span data-stu-id="28279-124">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span>