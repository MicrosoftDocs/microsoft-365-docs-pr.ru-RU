---
title: Настройка пользователей и обращений в Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Сведения о настройке ролей пользователей, создании обращений и назначении пользователям обращений в Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: e53d304445aa7d171766d38496d95a0d6cb47792
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090715"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a><span data-ttu-id="2d8d4-103">Настройка пользователей и обращений в Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2d8d4-103">Set up users and cases in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="2d8d4-104">В этом разделе описывается, как настроить пользователей и обращения для Office 365 Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="2d8d4-104">This topic describes how to set up users and cases for Office 365 Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d8d4-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="2d8d4-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="2d8d4-107">Необходимые условия</span><span class="sxs-lookup"><span data-stu-id="2d8d4-107">Prerequisites</span></span>

<span data-ttu-id="2d8d4-108">Перед настройкой обращений и пользователей в Advanced eDiscovery необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="2d8d4-108">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="2d8d4-109">Чтобы проанализировать данные пользователя с помощью расширенного обнаружения электронных данных, пользователю (хранитель данных) должна быть назначена лицензия Office 365.</span><span class="sxs-lookup"><span data-stu-id="2d8d4-109">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="2d8d4-110">Кроме того, для пользователей с лицензией на Office 365 E1 или E3 может быть назначена Расширенная лицензия eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="2d8d4-110">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="2d8d4-111">Администраторам и должностным лицам, назначенным для обращений и использующим расширенные функции обнаружения электронных данных для анализа данных, не требуется лицензия "водо".</span><span class="sxs-lookup"><span data-stu-id="2d8d4-111">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="2d8d4-112">Чтобы создать дело обнаружения электронных данных и добавить в него участников, необходимо быть участником группы &amp; ролей диспетчера обнаружения электронных данных в центре безопасности Office 365.</span><span class="sxs-lookup"><span data-stu-id="2d8d4-112">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="2d8d4-113">Чтобы добавить себя в группу ролей "Диспетчер обнаружения электронных данных &amp; " в центре безопасности и соответствия требованиям, необходимо быть глобальным администратором в организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="2d8d4-113">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization.</span></span> <span data-ttu-id="2d8d4-114">Если вы не являетесь глобальным администратором, вам потребуется попросить глобального администратора добавить вас в группу ролей "Диспетчер обнаружения электронных данных".</span><span class="sxs-lookup"><span data-stu-id="2d8d4-114">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="2d8d4-115">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="2d8d4-115">For more information, see:</span></span>
    
  - [<span data-ttu-id="2d8d4-116">Разрешения в центре безопасности &amp; и соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2d8d4-116">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="2d8d4-117">Назначение разрешений на обнаружение электронных данных в центре &amp; безопасности и соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2d8d4-117">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="2d8d4-118">Шаг 1: Назначение пользователям разрешений на обнаружение электронных данных</span><span class="sxs-lookup"><span data-stu-id="2d8d4-118">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="2d8d4-119">Первым шагом является назначение пользователям требований к требованиям в центре обеспечения безопасности &amp; , чтобы они могли добавляться как участник дела eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="2d8d4-119">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="2d8d4-120">После добавления пользователя в качестве участника в центре безопасности &amp; и соответствия требованиям он сможет получить доступ к обращению в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="2d8d4-120">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="2d8d4-121">Чтобы назначить пользователю необходимые разрешения, чтобы их можно было добавить в качестве участника такого случая обнаружения электронных данных, ознакомьтесь со статьей "шаг 1 [" в вариантах &amp; обнаружения электронных данных в центре безопасности и соответствия требованиям Microsoft 365](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span><span class="sxs-lookup"><span data-stu-id="2d8d4-121">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="2d8d4-122">Шаг 2: создание дела обнаружения электронных данных и добавление участников</span><span class="sxs-lookup"><span data-stu-id="2d8d4-122">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="2d8d4-123">Следующий шаг — создание нового дела обнаружения электронных данных в центре безопасности &amp; и добавление участников.</span><span class="sxs-lookup"><span data-stu-id="2d8d4-123">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members.</span></span> <span data-ttu-id="2d8d4-124">В этом случае участники будут иметь доступ к обращению в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="2d8d4-124">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="2d8d4-125">Чтобы создать новое дело обнаружения электронных данных, ознакомьтесь со статьей шаг 2 в [вариантах обнаружения &amp; электронных данных в центре безопасности Майкрософт 365](ediscovery-cases.md#step-2-create-a-new-case).</span><span class="sxs-lookup"><span data-stu-id="2d8d4-125">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="2d8d4-126">Чтобы добавить участников в дело обнаружения электронных данных, просмотрите шаг 3 в [вариантах обнаружения электронных данных в &amp; центре безопасности Майкрософт 365](ediscovery-cases.md#step-3-add-members-to-a-case)</span><span class="sxs-lookup"><span data-stu-id="2d8d4-126">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="2d8d4-127">Шаг 3: переход на дело с дополнительным обнаружением электронных данных</span><span class="sxs-lookup"><span data-stu-id="2d8d4-127">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="2d8d4-128">После создания случая обнаружения электронных данных и добавления участников вы (или любой участник дела) могут получить доступ к соответствующему случаю в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="2d8d4-128">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="2d8d4-129">Чтобы получить доступ к обращению в Advanced eDiscovery, ознакомьтесь с шагом 8 в [вариантах обнаружения электронных &amp; данных в центре безопасности Майкрософт 365](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span><span class="sxs-lookup"><span data-stu-id="2d8d4-129">To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2d8d4-130">См. также</span><span class="sxs-lookup"><span data-stu-id="2d8d4-130">See also</span></span>

[<span data-ttu-id="2d8d4-131">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2d8d4-131">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2d8d4-132">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="2d8d4-132">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 
