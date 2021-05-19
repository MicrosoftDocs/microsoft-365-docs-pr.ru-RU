---
title: Управление лицензиями для устройств
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: Узнайте, как назначать лицензии группам для использования с устройствами.
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 03/17/2021
ms.openlocfilehash: c590c2d47699c4c3cbea4b5145bea9e7c9fc79ec
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535666"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="56f30-103">Управление лицензиями для устройств</span><span class="sxs-lookup"><span data-stu-id="56f30-103">Manage licenses for devices</span></span>

<span data-ttu-id="56f30-104">Если у вас Приложения Microsoft 365 для предприятий (устройство) или Приложения Microsoft 365 для образования (устройства), можно назначить лицензии устройствам с помощью групп Azure AD.</span><span class="sxs-lookup"><span data-stu-id="56f30-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="56f30-105">Если у устройства есть лицензия, любой, кто использует это устройство, может использовать Приложения Microsoft 365 для предприятий (ранее именуемую Office 365 профессиональный плюс).</span><span class="sxs-lookup"><span data-stu-id="56f30-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="56f30-106">Например, предположим, что у вас есть 20 ноутбуков и планшетов, которые используются людьми в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="56f30-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="56f30-107">При назначении лицензии каждому устройству каждый человек, войдите на одно из устройств, использует Приложения Microsoft 365 для предприятий без необходимости в собственной лицензии.</span><span class="sxs-lookup"><span data-stu-id="56f30-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56f30-108">Лицензирование на основе устройств для Приложения Microsoft 365 для предприятий доступно только в качестве надстройки для некоторых коммерческих клиентов и некоторых образовательных клиентов.</span><span class="sxs-lookup"><span data-stu-id="56f30-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="56f30-109">Для коммерческих клиентов лицензия Приложения Microsoft 365 для предприятий *(устройство)* и доступна только Соглашение Enterprise/Соглашение Enterprise Подписка.</span><span class="sxs-lookup"><span data-stu-id="56f30-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="56f30-110">Для образовательных клиентов лицензия Приложения Microsoft 365 *для образовательных услуг (устройства)* и доступна только через Систему регистрации образовательных решений (EES).</span><span class="sxs-lookup"><span data-stu-id="56f30-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="56f30-111">Дополнительные сведения читайте в блоге о доступности [образования.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education)</span><span class="sxs-lookup"><span data-stu-id="56f30-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education).</span></span> <span data-ttu-id="56f30-112">Для коммерческой доступности обратитесь к представителю учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="56f30-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="56f30-113">Для начала создайте группу в центре администрирования Azure Active Directory, а затем назначьте устройства группе.</span><span class="sxs-lookup"><span data-stu-id="56f30-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="56f30-114">Дополнительные информацию о лицензировании устройств, включая требования к устройствам, типах групп, которые можно использовать, и о настройке Приложения Microsoft 365 для предприятий для использования лицензирования устройств см. в [Приложения Microsoft 365 для предприятий.](/deployoffice/device-based-licensing)</span><span class="sxs-lookup"><span data-stu-id="56f30-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](/deployoffice/device-based-licensing).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56f30-115">Вы должны быть глобальным администратором для выполнения задач в этой статье.</span><span class="sxs-lookup"><span data-stu-id="56f30-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="56f30-116">Назначение лицензий устройствам</span><span class="sxs-lookup"><span data-stu-id="56f30-116">Assign licenses to devices</span></span>

<span data-ttu-id="56f30-117">При назначении лицензий группе вы назначаете лицензии всем устройствам в группе.</span><span class="sxs-lookup"><span data-stu-id="56f30-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="56f30-118">Вы можете назначить только одну подписку для любой группы.</span><span class="sxs-lookup"><span data-stu-id="56f30-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="56f30-119">В центре Microsoft 365 администрирования перейдите на страницу  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">"Лицензии на выставление счета".</a></span><span class="sxs-lookup"><span data-stu-id="56f30-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="56f30-120">На странице **Лицензии** выберите Приложения Microsoft 365 **для образования (устройство)** **или Приложения Microsoft 365 для предприятий (устройство).**</span><span class="sxs-lookup"><span data-stu-id="56f30-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="56f30-121">На следующей странице выберите подписку, а затем **назначьте лицензии.**</span><span class="sxs-lookup"><span data-stu-id="56f30-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="56f30-122">В области **Назначение лицензий** групповой области приступить к вводить имя группы, а затем выбрать его из результатов, чтобы добавить его в список.</span><span class="sxs-lookup"><span data-stu-id="56f30-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="56f30-123">Выберите **Назначение,** а затем **выберите Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="56f30-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="56f30-124">Unassign licenses from devices</span><span class="sxs-lookup"><span data-stu-id="56f30-124">Unassign licenses from devices</span></span>

<span data-ttu-id="56f30-125">При отозвив лицензии из группы, вы удалите лицензии со всех устройств в группе.</span><span class="sxs-lookup"><span data-stu-id="56f30-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="56f30-126">Затем все приложения и связанные с ними данные доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="56f30-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="56f30-127">В центре администрирования перейдите на страницу **Биллинг**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии.</a></span><span class="sxs-lookup"><span data-stu-id="56f30-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="56f30-128">На странице **Лицензии** выберите Приложения Microsoft 365 **для образования (устройство)** **или Приложения Microsoft 365 для предприятий (устройство).**</span><span class="sxs-lookup"><span data-stu-id="56f30-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="56f30-129">На следующей странице выберите подписку, выберите три точки (больше действий), а затем выберите лицензии **Unassign**.</span><span class="sxs-lookup"><span data-stu-id="56f30-129">On the next page, choose a subscription, select the three dots (more actions), and then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="56f30-130">В **диалоговом окне Unassign licenses** выберите **Unassign**.</span><span class="sxs-lookup"><span data-stu-id="56f30-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>
