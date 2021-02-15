---
title: Отключение Basic Mobility + Security
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: Удалите группы или политики, чтобы отключить базовые функции мобильности и безопасности.
ms.openlocfilehash: 0786ac8ebd190b9af3211c211cc6db2ea9e0ea48
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876844"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="d6a6d-103">Отключение Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="d6a6d-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="d6a6d-104">Чтобы эффективно отключить функцию Basic Mobility and Security, вы удаляете группы людей, определенные группами безопасности, из политик управления устройствами или сами политики.</span><span class="sxs-lookup"><span data-stu-id="d6a6d-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="d6a6d-105">Удалите группы пользователей, удалите группы безопасности пользователей из созданных вами политик устройств.</span><span class="sxs-lookup"><span data-stu-id="d6a6d-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="d6a6d-106">Отключать базовую мобильность и безопасность для всех, удалив все политики устройств Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="d6a6d-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="d6a6d-107">Эти параметры удаляют базовое обеспечение мобильности и безопасности для устройств в организации.</span><span class="sxs-lookup"><span data-stu-id="d6a6d-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="d6a6d-108">К сожалению, вы не можете просто "отопрестить" базовую мобильность и безопасность после ее настроки.</span><span class="sxs-lookup"><span data-stu-id="d6a6d-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="d6a6d-109">Следует помнить о влиянии на устройства пользователей, когда вы удаляете группы безопасности пользователей из политик или сами политики.</span><span class="sxs-lookup"><span data-stu-id="d6a6d-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="d6a6d-110">Например, профили электронной почты и кэшные сообщения электронной почты могут быть удалены в зависимости от устройства.</span><span class="sxs-lookup"><span data-stu-id="d6a6d-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="d6a6d-111">Дополнительные сведения см. в сведениях о том, что происходит при удалении политики или  [удалении пользователя из политики?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span><span class="sxs-lookup"><span data-stu-id="d6a6d-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="d6a6d-112">Удаление групп безопасности пользователей из политик базовой мобильности и безопасности устройств</span><span class="sxs-lookup"><span data-stu-id="d6a6d-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="d6a6d-113">В браузере:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="d6a6d-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="d6a6d-114">Выберите политику устройств и выберите политику **редактирования.**</span><span class="sxs-lookup"><span data-stu-id="d6a6d-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="d6a6d-115">На  \*\*\*\* странице   "Развертывание" выберите **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="d6a6d-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="d6a6d-116">В  **группе** выберите группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="d6a6d-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="d6a6d-117">Выберите  **"Удалить"** и **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="d6a6d-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="d6a6d-118">Удаление базовых политик мобильных устройств и устройств безопасности</span><span class="sxs-lookup"><span data-stu-id="d6a6d-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="d6a6d-119">В браузере:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="d6a6d-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="d6a6d-120">Выберите политику устройств, а затем выберите  **"Удалить политику".**</span><span class="sxs-lookup"><span data-stu-id="d6a6d-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="d6a6d-121">В диалоговом окне предупреждения выберите **"Да".**</span><span class="sxs-lookup"><span data-stu-id="d6a6d-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE]
><span data-ttu-id="d6a6d-122">Дополнительные действия по разблокировать устройства, если устройства организации по-прежнему находятся в заблокированном состоянии, см. в записи блога "Удаление контроля доступа из управления мобильными устройствами [для Office 365".](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)</span><span class="sxs-lookup"><span data-stu-id="d6a6d-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
