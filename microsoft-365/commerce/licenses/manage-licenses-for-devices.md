---
title: Управление лицензиями для устройств
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: c7c747d5f4d2408b717bf16068d23c7882c2d667
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246353"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="96814-103">Управление лицензиями для устройств</span><span class="sxs-lookup"><span data-stu-id="96814-103">Manage licenses for devices</span></span>

<span data-ttu-id="96814-104">Если у вас есть Office 365 профессиональный плюс для образовательных учреждений (Device), вы можете назначить лицензии устройствам с помощью групп Azure AD.</span><span class="sxs-lookup"><span data-stu-id="96814-104">If you have Office 365 ProPlus for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="96814-105">Когда устройство имеет лицензию, любой пользователь, который использует это устройство, может использовать Office 365.</span><span class="sxs-lookup"><span data-stu-id="96814-105">When a device has a license, anyone who uses that device can use Office 365.</span></span> <span data-ttu-id="96814-106">Например, предположим, что у вас есть 20 ноутбуков и планшетов, используемых людьми в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="96814-106">For example, let’s say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="96814-107">При назначении лицензии каждому устройству каждый пользователь, который входит в систему на одном из устройств, использует Office 365 без необходимости в собственной лицензии.</span><span class="sxs-lookup"><span data-stu-id="96814-107">When you assign a license to each device, each person who logs in to one of the devices uses Office 365 without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96814-108">Office 365 профессиональный плюс для образовательных учреждений (Device) доступен только для пользователей с корпоративным лицензированием a3 и A5.</span><span class="sxs-lookup"><span data-stu-id="96814-108">Office 365 ProPlus for Education (device) is only available to Education A3 and A5 volume licensing customers.</span></span>

<span data-ttu-id="96814-109">Для начала создайте группу в центре администрирования Azure Active Directory, а затем назначьте устройства группе.</span><span class="sxs-lookup"><span data-stu-id="96814-109">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="96814-110">Дополнительные сведения о лицензировании устройств, в том числе требования к устройствам, доступных типах групп и настройке Office 365 профессиональный плюс для использования лицензирования устройств, приведены в разделе [Лицензирование устройств для Office 365 профессиональный плюс для образовательных учреждений](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span><span class="sxs-lookup"><span data-stu-id="96814-110">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Office 365 ProPlus to use device licensing, see [Device licensing for Office 365 ProPlus for Education customers](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96814-111">Для выполнения задач, описанных в этой статье, необходимо быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="96814-111">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="96814-112">Назначение лицензий устройствам</span><span class="sxs-lookup"><span data-stu-id="96814-112">Assign licenses to devices</span></span>

<span data-ttu-id="96814-113">При назначении лицензий группе вы назначаете лицензии всем устройствам в группе.</span><span class="sxs-lookup"><span data-stu-id="96814-113">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="96814-114">Одну подписку можно назначить только одной группе.</span><span class="sxs-lookup"><span data-stu-id="96814-114">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="96814-115">В центре администрирования Microsoft 365 перейдите на страницу<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">лицензии</a> **выставления счетов** > .</span><span class="sxs-lookup"><span data-stu-id="96814-115">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="96814-116">На странице **лицензии** выберите **Office 365 профессиональный плюс для образовательных учреждений (Device)**.</span><span class="sxs-lookup"><span data-stu-id="96814-116">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="96814-117">На странице **Office 365 профессиональный плюс для образовательных учреждений (Device)** выберите подписку, а затем выберите **назначить лицензии**.</span><span class="sxs-lookup"><span data-stu-id="96814-117">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="96814-118">В области **назначить лицензии группе** введите имя группы, а затем выберите его из результатов, чтобы добавить его в список.</span><span class="sxs-lookup"><span data-stu-id="96814-118">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
6. <span data-ttu-id="96814-119">Нажмите кнопку **назначить**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="96814-119">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="96814-120">Отмена назначения лицензий для устройств</span><span class="sxs-lookup"><span data-stu-id="96814-120">Unassign licenses from devices</span></span>

<span data-ttu-id="96814-121">При отмене назначения лицензий группе вы удаляете лицензии со всех устройств в группе.</span><span class="sxs-lookup"><span data-stu-id="96814-121">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="96814-122">Все приложения и связанные с ними данные доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="96814-122">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="96814-123">В центре администрирования перейдите на страницу<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">лицензии</a> **выставления счетов** > .</span><span class="sxs-lookup"><span data-stu-id="96814-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="96814-124">На странице **лицензии** выберите **Office 365 профессиональный плюс для образовательных учреждений (Device)**.</span><span class="sxs-lookup"><span data-stu-id="96814-124">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="96814-125">На странице **Office 365 профессиональный плюс для образовательных учреждений (Device)** выберите подписку, нажмите **Дополнительные действия**, а затем выберите **Отменить назначение лицензий**.</span><span class="sxs-lookup"><span data-stu-id="96814-125">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
5. <span data-ttu-id="96814-126">В диалоговом окне **Отмена назначения лицензий** выберите **Отменить назначение**.</span><span class="sxs-lookup"><span data-stu-id="96814-126">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>