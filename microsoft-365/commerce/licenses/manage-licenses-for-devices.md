---
title: Управление лицензиями для устройств
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Узнайте, как назначать лицензии группам для использования с устройствами.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: 29bd56ccff01d8c21cc67d1188fa21e338fb4b7e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638187"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="94412-103">Управление лицензиями для устройств</span><span class="sxs-lookup"><span data-stu-id="94412-103">Manage licenses for devices</span></span>

<span data-ttu-id="94412-104">Если у вас есть приложения Microsoft 365 для Enterprise (Device) или Microsoft 365 для образовательных учреждений (Device), вы можете назначить лицензии устройствам с помощью групп Azure AD.</span><span class="sxs-lookup"><span data-stu-id="94412-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="94412-105">Когда устройство имеет лицензию, любой пользователь, использующий это устройство, может использовать приложения Microsoft 365 для предприятия (ранее именуемые Office 365 профессиональный плюс).</span><span class="sxs-lookup"><span data-stu-id="94412-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="94412-106">Например, предположим, что у вас есть 20 ноутбуков и планшетов, используемых людьми в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="94412-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="94412-107">При назначении лицензии каждому устройству каждый пользователь, который входит в систему на одном из устройств, использует приложения Microsoft 365 для предприятий без необходимости в собственной лицензии.</span><span class="sxs-lookup"><span data-stu-id="94412-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94412-108">Лицензирование на основе устройств для приложений Microsoft 365 для предприятий доступно только в качестве лицензии на надстройку для некоторых коммерческих клиентов и клиентов для образования.</span><span class="sxs-lookup"><span data-stu-id="94412-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="94412-109">Для коммерческих клиентов лицензия — это *приложения Microsoft 365 для Enterprise (Device)* , доступные только через корпоративное соглашение/Корпоративное соглашение.</span><span class="sxs-lookup"><span data-stu-id="94412-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="94412-110">Для учебных заведений лицензия — это *приложения Microsoft 365 для образовательных учреждений (Device)* , доступные только через регистрацию для решений для образования (ИС).</span><span class="sxs-lookup"><span data-stu-id="94412-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="94412-111">Для получения дополнительных сведений прочитайте запись в блоге о [доступности для образования](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span><span class="sxs-lookup"><span data-stu-id="94412-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="94412-112">Чтобы получить коммерческую доступность, обратитесь к представителю учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="94412-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="94412-113">Для начала создайте группу в центре администрирования Azure Active Directory, а затем назначьте устройства группе.</span><span class="sxs-lookup"><span data-stu-id="94412-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="94412-114">Дополнительные сведения о лицензировании устройств, в том числе требования к устройствам, доступных типах групп и настройке приложений Microsoft 365 для предприятий для использования лицензирования устройств, представлены в разделе [Лицензирование на основе устройств для приложений microsoft 365 для предприятий](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span><span class="sxs-lookup"><span data-stu-id="94412-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94412-115">Для выполнения задач, описанных в этой статье, необходимо быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="94412-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="94412-116">Назначение лицензий устройствам</span><span class="sxs-lookup"><span data-stu-id="94412-116">Assign licenses to devices</span></span>

<span data-ttu-id="94412-117">При назначении лицензий группе вы назначаете лицензии всем устройствам в группе.</span><span class="sxs-lookup"><span data-stu-id="94412-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="94412-118">Одну подписку можно назначить только одной группе.</span><span class="sxs-lookup"><span data-stu-id="94412-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="94412-119">В центре администрирования Microsoft 365 перейдите на страницу лицензии **выставления счетов**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> .</span><span class="sxs-lookup"><span data-stu-id="94412-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="94412-120">На странице **лицензии** выберите **Microsoft 365 приложения для образовательных учреждений (устройство)** или **приложения Microsoft 365 для Enterprise (Device)**.</span><span class="sxs-lookup"><span data-stu-id="94412-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="94412-121">На следующей странице выберите подписку, а затем выберите **назначить лицензии**.</span><span class="sxs-lookup"><span data-stu-id="94412-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="94412-122">В области **назначить лицензии группе** введите имя группы, а затем выберите его из результатов, чтобы добавить его в список.</span><span class="sxs-lookup"><span data-stu-id="94412-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="94412-123">Нажмите кнопку **назначить**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="94412-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="94412-124">Отмена назначения лицензий для устройств</span><span class="sxs-lookup"><span data-stu-id="94412-124">Unassign licenses from devices</span></span>

<span data-ttu-id="94412-125">При отмене назначения лицензий группе вы удаляете лицензии со всех устройств в группе.</span><span class="sxs-lookup"><span data-stu-id="94412-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="94412-126">Все приложения и связанные с ними данные доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="94412-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="94412-127">В центре администрирования перейдите на страницу лицензии **выставления счетов**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> .</span><span class="sxs-lookup"><span data-stu-id="94412-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="94412-128">На странице **лицензии** выберите **Microsoft 365 приложения для образовательных учреждений (устройство)** или **приложения Microsoft 365 для Enterprise (Device)**.</span><span class="sxs-lookup"><span data-stu-id="94412-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="94412-129">На следующей странице выберите подписку, нажмите кнопку **Дополнительные действия**, а затем выберите пункт **Отменить назначение лицензий**.</span><span class="sxs-lookup"><span data-stu-id="94412-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="94412-130">В диалоговом окне **Отмена назначения лицензий** выберите **Отменить назначение**.</span><span class="sxs-lookup"><span data-stu-id="94412-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>