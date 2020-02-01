---
title: Настройка пользователей и обращений в Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Сведения о настройке ролей пользователей, создании обращений и назначении пользователям обращений в Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: 754cc7d73fc3325c2525e3101d1378d55afea4de
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601456"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a><span data-ttu-id="7bedb-103">Настройка пользователей и обращений в Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7bedb-103">Set up users and cases in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="7bedb-104">В этом разделе описывается, как настроить пользователей и обращения для Office 365 Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="7bedb-104">This topic describes how to set up users and cases for Office 365 Advanced eDiscovery.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7bedb-105">Так как мы продолжим вкладывать новые версии расширенного обнаружения электронных данных, мы сообщаем выбытие Office 365 Advanced eDiscovery (также известное как *Advanced eDiscovery версии 1.0*).</span><span class="sxs-lookup"><span data-stu-id="7bedb-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Office 365 Advanced eDiscovery (also known as *Advanced eDiscovery v1.0*).</span></span> <span data-ttu-id="7bedb-106">Если вы по-прежнему используете Расширенное обнаружение электронных данных версии 1.0, переходите к [расширенному элементу обнаружения электронных данных версии 2.0](overview-ediscovery-20.md) (также известному как " *Расширенное решение обнаружения электронных данных в Microsoft 365*) как можно скорее.</span><span class="sxs-lookup"><span data-stu-id="7bedb-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="7bedb-107">Advanced eDiscovery 2,0 содержит похожие функции, обнаруженные в Advanced eDiscovery версии 1.0, но также предлагает множество новых функций, таких как управление хранитель, Управление связью и наборы проверки.</span><span class="sxs-lookup"><span data-stu-id="7bedb-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="7bedb-108">Чтобы узнать больше о выбытие расширенного обнаружения электронных данных версии 1.0, ознакомьтесь с разделом [упразднения устаревших средств обнаружения электронных данных](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span><span class="sxs-lookup"><span data-stu-id="7bedb-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="7bedb-109">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="7bedb-109">Prerequisites</span></span>

<span data-ttu-id="7bedb-110">Перед настройкой обращений и пользователей в Advanced eDiscovery необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="7bedb-110">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="7bedb-111">Чтобы проанализировать данные пользователя с помощью расширенного обнаружения электронных данных, пользователю (хранитель данных) должна быть назначена лицензия Office 365.</span><span class="sxs-lookup"><span data-stu-id="7bedb-111">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="7bedb-112">Кроме того, для пользователей с лицензией на Office 365 E1 или E3 может быть назначена Расширенная лицензия eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="7bedb-112">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="7bedb-113">Администраторам и должностным лицам, назначенным для обращений и использующим расширенные функции обнаружения электронных данных для анализа данных, не требуется лицензия "водо".</span><span class="sxs-lookup"><span data-stu-id="7bedb-113">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="7bedb-114">Чтобы создать дело обнаружения электронных данных и добавить в него участников, необходимо быть участником группы &amp; ролей диспетчера обнаружения электронных данных в центре безопасности Office 365.</span><span class="sxs-lookup"><span data-stu-id="7bedb-114">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="7bedb-115">Чтобы добавить себя в группу ролей "Диспетчер обнаружения электронных данных &amp; " в центре безопасности и соответствия требованиям, необходимо быть глобальным администратором в организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="7bedb-115">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization.</span></span> <span data-ttu-id="7bedb-116">Если вы не являетесь глобальным администратором, вам потребуется попросить глобального администратора добавить вас в группу ролей "Диспетчер обнаружения электронных данных".</span><span class="sxs-lookup"><span data-stu-id="7bedb-116">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="7bedb-117">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="7bedb-117">For more information, see:</span></span>
    
  - [<span data-ttu-id="7bedb-118">Разрешения в центре безопасности &amp; и соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7bedb-118">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](~/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="7bedb-119">Назначение разрешений на обнаружение электронных данных в центре &amp; безопасности и соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7bedb-119">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="7bedb-120">Шаг 1: Назначение пользователям разрешений на обнаружение электронных данных</span><span class="sxs-lookup"><span data-stu-id="7bedb-120">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="7bedb-121">Первым шагом является назначение пользователям требований к требованиям в центре обеспечения безопасности &amp; , чтобы они могли добавляться как участник дела eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="7bedb-121">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="7bedb-122">После добавления пользователя в качестве участника в центре безопасности &amp; и соответствия требованиям он сможет получить доступ к обращению в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="7bedb-122">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="7bedb-123">Чтобы назначить пользователю необходимые разрешения, чтобы их можно было добавить в качестве участника такого случая обнаружения электронных данных, ознакомьтесь со статьей "шаг 1 [" в вариантах &amp; обнаружения электронных данных в центре безопасности и соответствия требованиям Microsoft 365](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span><span class="sxs-lookup"><span data-stu-id="7bedb-123">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="7bedb-124">Шаг 2: создание дела обнаружения электронных данных и добавление участников</span><span class="sxs-lookup"><span data-stu-id="7bedb-124">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="7bedb-125">Следующий шаг — создание нового дела обнаружения электронных данных в центре безопасности &amp; и добавление участников.</span><span class="sxs-lookup"><span data-stu-id="7bedb-125">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members.</span></span> <span data-ttu-id="7bedb-126">В этом случае участники будут иметь доступ к обращению в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="7bedb-126">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="7bedb-127">Чтобы создать новое дело обнаружения электронных данных, ознакомьтесь со статьей шаг 2 в [вариантах обнаружения &amp; электронных данных в центре безопасности Майкрософт 365](ediscovery-cases.md#step-2-create-a-new-case).</span><span class="sxs-lookup"><span data-stu-id="7bedb-127">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="7bedb-128">Чтобы добавить участников в дело обнаружения электронных данных, просмотрите шаг 3 в [вариантах обнаружения электронных данных в &amp; центре безопасности Майкрософт 365](ediscovery-cases.md#step-3-add-members-to-a-case)</span><span class="sxs-lookup"><span data-stu-id="7bedb-128">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="7bedb-129">Шаг 3: переход на дело с дополнительным обнаружением электронных данных</span><span class="sxs-lookup"><span data-stu-id="7bedb-129">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="7bedb-130">После создания случая обнаружения электронных данных и добавления участников вы (или любой участник дела) могут получить доступ к соответствующему случаю в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="7bedb-130">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="7bedb-131">Чтобы получить доступ к обращению в Advanced eDiscovery, ознакомьтесь с шагом 8 в [вариантах обнаружения электронных &amp; данных в центре безопасности Майкрософт 365](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span><span class="sxs-lookup"><span data-stu-id="7bedb-131">To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7bedb-132">См. также</span><span class="sxs-lookup"><span data-stu-id="7bedb-132">See also</span></span>

[<span data-ttu-id="7bedb-133">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7bedb-133">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="7bedb-134">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="7bedb-134">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 
