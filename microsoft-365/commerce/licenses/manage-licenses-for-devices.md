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
ms.openlocfilehash: a316810e3e6ddb1373697dc56b2fccb5a32cf0b1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911486"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="03a51-103">Управление лицензиями для устройств</span><span class="sxs-lookup"><span data-stu-id="03a51-103">Manage licenses for devices</span></span>

<span data-ttu-id="03a51-104">Если у вас есть приложения Microsoft 365 для корпоративных (устройств) или Microsoft 365 Apps для образования (устройства), вы можете назначить лицензии устройствам с помощью групп Azure AD.</span><span class="sxs-lookup"><span data-stu-id="03a51-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="03a51-105">Если у устройства есть лицензия, любой, кто использует это устройство, может использовать Приложения Microsoft 365 для предприятия (ранее названный Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="03a51-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="03a51-106">Например, предположим, что у вас есть 20 ноутбуков и планшетов, которые используются людьми в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="03a51-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="03a51-107">При назначении лицензии каждому устройству каждый человек, войдите на одно из устройств, использует Microsoft 365 Apps для предприятия без необходимости иметь собственную лицензию.</span><span class="sxs-lookup"><span data-stu-id="03a51-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03a51-108">Лицензирование на основе устройств для Microsoft 365 Apps для предприятия доступно только в качестве надстройки для некоторых коммерческих клиентов и некоторых образовательных клиентов.</span><span class="sxs-lookup"><span data-stu-id="03a51-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="03a51-109">Для коммерческих клиентов лицензия *microsoft 365 Apps для предприятия (устройства)* доступна только Соглашение Enterprise/Соглашение Enterprise Подписка.</span><span class="sxs-lookup"><span data-stu-id="03a51-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="03a51-110">Для образовательных клиентов лицензия *является Microsoft 365 Apps for Education (device)* и доступна только через систему Регистрации для образовательных решений (EES).</span><span class="sxs-lookup"><span data-stu-id="03a51-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="03a51-111">Дополнительные сведения читайте в блоге о доступности [образования.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/)</span><span class="sxs-lookup"><span data-stu-id="03a51-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="03a51-112">Для коммерческой доступности обратитесь к представителю учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="03a51-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="03a51-113">Для начала создайте группу в центре администрирования Azure Active Directory и назначьте устройства группе.</span><span class="sxs-lookup"><span data-stu-id="03a51-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="03a51-114">Дополнительные информацию о лицензировании устройств, включая требования к устройствам, типах групп, которые можно использовать, и о настройке Microsoft 365 Apps для корпоративного использования лицензирования устройств см. в статью Лицензирование на основе устройств для [Microsoft 365 Apps для](/deployoffice/device-based-licensing)предприятия.</span><span class="sxs-lookup"><span data-stu-id="03a51-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](/deployoffice/device-based-licensing).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03a51-115">Вы должны быть глобальным администратором для выполнения задач в этой статье.</span><span class="sxs-lookup"><span data-stu-id="03a51-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="03a51-116">Назначение лицензий устройствам</span><span class="sxs-lookup"><span data-stu-id="03a51-116">Assign licenses to devices</span></span>

<span data-ttu-id="03a51-117">При назначении лицензий группе вы назначаете лицензии всем устройствам в группе.</span><span class="sxs-lookup"><span data-stu-id="03a51-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="03a51-118">Вы можете назначить только одну подписку для любой группы.</span><span class="sxs-lookup"><span data-stu-id="03a51-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="03a51-119">В центре администрирования Microsoft 365 перейдите на страницу **Биллинг**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии.</a></span><span class="sxs-lookup"><span data-stu-id="03a51-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="03a51-120">На странице **Лицензии** выберите **Microsoft 365 Apps for Education (device)** или **Microsoft 365 Apps для предприятия (устройства).**</span><span class="sxs-lookup"><span data-stu-id="03a51-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="03a51-121">На следующей странице выберите подписку, а затем **назначьте лицензии.**</span><span class="sxs-lookup"><span data-stu-id="03a51-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="03a51-122">В области **Назначение лицензий** групповой области приступить к вводить имя группы, а затем выбрать его из результатов, чтобы добавить его в список.</span><span class="sxs-lookup"><span data-stu-id="03a51-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="03a51-123">Выберите **Назначение,** а затем **выберите Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="03a51-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="03a51-124">Unassign licenses from devices</span><span class="sxs-lookup"><span data-stu-id="03a51-124">Unassign licenses from devices</span></span>

<span data-ttu-id="03a51-125">При отозвив лицензии из группы, вы удалите лицензии со всех устройств в группе.</span><span class="sxs-lookup"><span data-stu-id="03a51-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="03a51-126">Затем все приложения и связанные с ними данные доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="03a51-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="03a51-127">В центре администрирования перейдите на страницу **Биллинг**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии.</a></span><span class="sxs-lookup"><span data-stu-id="03a51-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="03a51-128">На странице **Лицензии** выберите **Microsoft 365 Apps for Education (device)** или **Microsoft 365 Apps для предприятия (устройства).**</span><span class="sxs-lookup"><span data-stu-id="03a51-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="03a51-129">На следующей странице выберите подписку, выберите **Дополнительные действия,** а затем выберите **лицензии Unassign**.</span><span class="sxs-lookup"><span data-stu-id="03a51-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="03a51-130">В **диалоговом окне Unassign licenses** выберите **Unassign**.</span><span class="sxs-lookup"><span data-stu-id="03a51-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>