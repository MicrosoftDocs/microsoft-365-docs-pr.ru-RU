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
description: Удалите группы или политики, чтобы отключить базовую мобильность и безопасность.
ms.openlocfilehash: 1d81aed01193fb2ba821ebc055958ac6cd8ac382
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023873"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="01cab-103">Отключение Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="01cab-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="01cab-104">Чтобы эффективно отключить базовую мобильность и безопасность, вы удалите группы людей, определенных группами безопасности, из политик управления устройствами или удалите сами политики.</span><span class="sxs-lookup"><span data-stu-id="01cab-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="01cab-105">Удалите группы пользователей, удалите группы безопасности пользователей из созданных политик устройства.</span><span class="sxs-lookup"><span data-stu-id="01cab-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="01cab-106">Отключить базовую мобильность и безопасность для всех, удалив все политики устройств Basic Mobility и Security.</span><span class="sxs-lookup"><span data-stu-id="01cab-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="01cab-107">Эти параметры удаляют правоприменители Basic Mobility и Security для устройств в организации.</span><span class="sxs-lookup"><span data-stu-id="01cab-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="01cab-108">К сожалению, нельзя просто "отсутвить" базовую мобильность и безопасность после ее настройка.</span><span class="sxs-lookup"><span data-stu-id="01cab-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="01cab-109">Будьте в курсе влияния на устройства пользователей при удалите группы безопасности пользователей из политик или удалите сами политики.</span><span class="sxs-lookup"><span data-stu-id="01cab-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="01cab-110">Например, профили электронной почты и кэшные сообщения могут быть удалены в зависимости от устройства.</span><span class="sxs-lookup"><span data-stu-id="01cab-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="01cab-111">Дополнительные сведения см.  [в публикации What happens when you delete a policy or remove a user from the policy?](../../admin/basic-mobility-security/create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="01cab-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](../../admin/basic-mobility-security/create-device-security-policies.md)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="01cab-112">Удаление групп безопасности пользователей из политик устройств Basic Mobility и Security</span><span class="sxs-lookup"><span data-stu-id="01cab-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="01cab-113">В типе браузера:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="01cab-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="01cab-114">Выберите политику устройства и выберите политику **редактирования.**</span><span class="sxs-lookup"><span data-stu-id="01cab-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="01cab-115">На странице  **Развертывание**   выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="01cab-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="01cab-116">В  **группах** выберите группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="01cab-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="01cab-117">Выберите  **Удалить** и **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="01cab-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="01cab-118">Удаление политик устройств с базовой мобильностью и безопасностью</span><span class="sxs-lookup"><span data-stu-id="01cab-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="01cab-119">В типе браузера:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="01cab-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="01cab-120">Выберите политику устройства, а затем выберите  **политику Удаления.**</span><span class="sxs-lookup"><span data-stu-id="01cab-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="01cab-121">В диалоговом окне Предупреждение выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="01cab-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE]
><span data-ttu-id="01cab-122">Дополнительные действия по разблокировать устройства, если устройства организации по-прежнему находятся в заблокированном состоянии, см. в блоге"Удаление управления доступом из управления мобильными устройствами для [Office 365.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)</span><span class="sxs-lookup"><span data-stu-id="01cab-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
