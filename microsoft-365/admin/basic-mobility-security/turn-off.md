---
title: Отключение базовых функций мобильной связи и безопасности
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
description: Удалите группы или политики, чтобы отключить основные функции мобильной работы и обеспечения безопасности.
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430270"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="e8d81-103">Отключение базовых функций мобильной связи и безопасности</span><span class="sxs-lookup"><span data-stu-id="e8d81-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="e8d81-104">Чтобы эффективно отключить базовую мобильность и безопасность, удалите группы людей, определенные группами безопасности в политиках управления устройствами, или удалите сами политики.</span><span class="sxs-lookup"><span data-stu-id="e8d81-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="e8d81-105">Удалите группы пользователей, удалив группы безопасности пользователей из созданных политик устройств.</span><span class="sxs-lookup"><span data-stu-id="e8d81-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>
    
- <span data-ttu-id="e8d81-106">Отключите базовые мобильность и безопасность для всех, удалив все базовые политики устройств для мобильных устройств и безопасности.</span><span class="sxs-lookup"><span data-stu-id="e8d81-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>
    
<span data-ttu-id="e8d81-107">Эти параметры изменяют базовую поддержку мобильных устройств и обеспечение безопасности для устройств в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e8d81-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="e8d81-108">К сожалению, после настройки вы не можете просто отписаться на базовые мобильные решения и безопасность.</span><span class="sxs-lookup"><span data-stu-id="e8d81-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="e8d81-109">Учитывайте влияние на устройства пользователей при удалении групп безопасности пользователей из политик или удалении самих политик.</span><span class="sxs-lookup"><span data-stu-id="e8d81-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="e8d81-110">Например, профили электронной почты и кэшированные сообщения электронной почты могут быть удалены в зависимости от устройства.</span><span class="sxs-lookup"><span data-stu-id="e8d81-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="e8d81-111">Для получения дополнительных сведений о  [том, что происходит при удалении политики или удалении пользователя из политики?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span><span class="sxs-lookup"><span data-stu-id="e8d81-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="e8d81-112">Удаление групп безопасности пользователей из базовых политик мобильных устройств и устройств безопасности</span><span class="sxs-lookup"><span data-stu-id="e8d81-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="e8d81-113">В браузере введите:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="e8d81-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="e8d81-114">Выберите политику устройства и нажмите **изменить политику**.</span><span class="sxs-lookup"><span data-stu-id="e8d81-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="e8d81-115">На странице  **развертывание** нажмите   кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="e8d81-115">On the  **Deployment**  page, select **Remove**.</span></span>
    
4. <span data-ttu-id="e8d81-116">В разделе  **группы**выберите группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="e8d81-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="e8d81-117">Нажмите кнопку  **Удалить**, а затем выберите **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e8d81-117">Select  **Remove**, and select **Save**.</span></span>
    

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="e8d81-118">Удаление основных политик мобильных устройств и устройств безопасности</span><span class="sxs-lookup"><span data-stu-id="e8d81-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="e8d81-119">В браузере введите:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="e8d81-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="e8d81-120">Выберите политику устройства, а затем выберите команду  **удалить политику**.</span><span class="sxs-lookup"><span data-stu-id="e8d81-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="e8d81-121">В диалоговом окне предупреждения нажмите **кнопку Да**.</span><span class="sxs-lookup"><span data-stu-id="e8d81-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE] 
><span data-ttu-id="e8d81-122">Дополнительные действия, которые необходимо выполнить, чтобы разблокировать устройства, если их устройства находятся в заблокированном состоянии, обратитесь к разделу запись блога [Удаление управления доступом с мобильного устройства для Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span><span class="sxs-lookup"><span data-stu-id="e8d81-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
