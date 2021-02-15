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
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="900c8-103">Управление лицензиями для устройств</span><span class="sxs-lookup"><span data-stu-id="900c8-103">Manage licenses for devices</span></span>

<span data-ttu-id="900c8-104">Если у вас есть приложения Microsoft 365 для предприятий (устройство) или Приложения Microsoft 365 для образования (устройство), вы можете назначать лицензии устройствам с помощью групп Azure AD.</span><span class="sxs-lookup"><span data-stu-id="900c8-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="900c8-105">Если у устройства есть лицензия, любой, кто использует это устройство, может использовать приложения Microsoft 365 для предприятий (ранее он назывался Office 365 профессиональныйplus).</span><span class="sxs-lookup"><span data-stu-id="900c8-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="900c8-106">Например, предположим, что у вас есть 20 ноутбуков и планшетов, которые используют люди в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="900c8-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="900c8-107">При назначении лицензии каждому устройству каждый человек, который входит в систему на одном из устройств, использует приложения Microsoft 365 для предприятий без необходимости в собственной лицензии.</span><span class="sxs-lookup"><span data-stu-id="900c8-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="900c8-108">Лицензирование приложений Microsoft 365 для предприятий на основе устройств доступно только в качестве лицензии на надстройку для некоторых коммерческих и образовательных клиентов.</span><span class="sxs-lookup"><span data-stu-id="900c8-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="900c8-109">Для коммерческих клиентов лицензия — *приложения Microsoft 365* для предприятий (устройство) и доступна только через Соглашение Enterprise/Соглашение Enterprise Подписка.</span><span class="sxs-lookup"><span data-stu-id="900c8-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="900c8-110">Для образовательных клиентов лицензия — *приложения Microsoft 365* для образования (устройство) и доступна только в рамках программы регистрации для образовательных решений (EES).</span><span class="sxs-lookup"><span data-stu-id="900c8-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="900c8-111">Дополнительные сведения о доступности образования можно прочитать в [записи блога.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/)</span><span class="sxs-lookup"><span data-stu-id="900c8-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="900c8-112">Для коммерческой доступности обратитесь к представителю учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="900c8-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="900c8-113">Для начала создайте группу в Центре администрирования Azure Active Directory, а затем назначьте ее устройства.</span><span class="sxs-lookup"><span data-stu-id="900c8-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="900c8-114">Дополнительные информацию о лицензировании устройств, в том числе требованиях к устройствам, типах групп, которые можно использовать, а также о настройке приложений Microsoft 365 для предприятий на использование лицензирования устройств см. в подстроке "Лицензирование на основе устройств для [приложений Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2094216)для предприятий".</span><span class="sxs-lookup"><span data-stu-id="900c8-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="900c8-115">Для выполнения задач, которые необходимо выполнить в этой статье, необходимо быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="900c8-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="900c8-116">Назначение лицензий устройствам</span><span class="sxs-lookup"><span data-stu-id="900c8-116">Assign licenses to devices</span></span>

<span data-ttu-id="900c8-117">При назначении лицензий группе лицензии назначаются всем устройствам в группе.</span><span class="sxs-lookup"><span data-stu-id="900c8-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="900c8-118">Одной группе можно назначить только одну подписку.</span><span class="sxs-lookup"><span data-stu-id="900c8-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="900c8-119">В Центре администрирования Microsoft 365 перейдите на страницу **"Лицензии на**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">выставление</a> счета".</span><span class="sxs-lookup"><span data-stu-id="900c8-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="900c8-120">На странице **"Лицензии"** выберите **приложения Microsoft 365** для образования (устройство) или **Приложения Microsoft 365** для предприятий (устройство).</span><span class="sxs-lookup"><span data-stu-id="900c8-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="900c8-121">На следующей странице выберите подписку, а затем **выберите "Назначить лицензии".**</span><span class="sxs-lookup"><span data-stu-id="900c8-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="900c8-122">В области **"Назначение лицензий"** начните вводить имя группы, а затем выберите его в результатах, чтобы добавить его в список.</span><span class="sxs-lookup"><span data-stu-id="900c8-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="900c8-123">Choose **Assign**, then choose **Close**.</span><span class="sxs-lookup"><span data-stu-id="900c8-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="900c8-124">Unassign licenses from devices</span><span class="sxs-lookup"><span data-stu-id="900c8-124">Unassign licenses from devices</span></span>

<span data-ttu-id="900c8-125">При отомене лицензий для группы лицензии удаляются со всех устройств в группе.</span><span class="sxs-lookup"><span data-stu-id="900c8-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="900c8-126">После этого все приложения и связанные с ними данные будут доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="900c8-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="900c8-127">В Центре администрирования перейдите на страницу **"Лицензии**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">на выставление счета".</a></span><span class="sxs-lookup"><span data-stu-id="900c8-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="900c8-128">На странице **"Лицензии"** выберите **приложения Microsoft 365** для образования (устройство) или **Приложения Microsoft 365** для предприятий (устройство).</span><span class="sxs-lookup"><span data-stu-id="900c8-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="900c8-129">На следующей странице выберите подписку, выберите "Дополнительные **действия"** и выберите **"Отоименуть лицензии".**</span><span class="sxs-lookup"><span data-stu-id="900c8-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="900c8-130">В **диалоговом окне "Unassign licenses"** (Отоименуйте лицензии) выберите **"Unassign" (Отоименуйте лицензии).**</span><span class="sxs-lookup"><span data-stu-id="900c8-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>