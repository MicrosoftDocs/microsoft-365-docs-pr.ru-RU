---
title: Основы реализации
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: ''
ms.custom:
- commerce_licensing
description: Узнайте о новых функциях.
ms.date: 03/17/2021
ms.openlocfilehash: 949e06d4bf54405e0045f8c7512a04b1b5cc22c0
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327134"
---
# <a name="allotment-basics"></a><span data-ttu-id="7b223-103">Основы реализации</span><span class="sxs-lookup"><span data-stu-id="7b223-103">Allotment basics</span></span>

<span data-ttu-id="7b223-104">Присвоение лицензий позволит вам установить ограничения лицензии и делегировать управление назначением лицензии только на выбранные вами продукты и лицензии.</span><span class="sxs-lookup"><span data-stu-id="7b223-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="7b223-105">Для назначения лицензий пользователям используются групповые лицензии.</span><span class="sxs-lookup"><span data-stu-id="7b223-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="7b223-106">Ограничения лицензий обеспечивают дополнительный контроль над количеством лицензий, назначенных пользователям в группах.</span><span class="sxs-lookup"><span data-stu-id="7b223-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="7b223-107">Таким образом, даже по мере увеличения числа пользователей в группах можно обеспечить, чтобы вы оставались в пределах лимита лицензии, установленного для вашего отгружаемого.</span><span class="sxs-lookup"><span data-stu-id="7b223-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="7b223-108">Вы также можете делегировать управление своими ресурсами.</span><span class="sxs-lookup"><span data-stu-id="7b223-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="7b223-109">Владельцы делегирования получают доступ к центру администрирования, но могут видеть и управлять лицензиями только в своих собственных лицензиях.</span><span class="sxs-lookup"><span data-stu-id="7b223-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="7b223-110">Это обеспечивает более подробное делегированное управление лицензией в организации.</span><span class="sxs-lookup"><span data-stu-id="7b223-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7b223-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7b223-111">Prerequisites</span></span>

<span data-ttu-id="7b223-112">Вы должны соответствовать требованиям лицензирования для [группового лицензирования.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="7b223-112">You must meet the licensing requirements for [group-based licensing](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="7b223-113">Вы можете использовать ссылки с любым продуктом, доступным для пользователей:</span><span class="sxs-lookup"><span data-stu-id="7b223-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="7b223-114">Office и автономные продукты</span><span class="sxs-lookup"><span data-stu-id="7b223-114">Office suites and standalone products</span></span>
- <span data-ttu-id="7b223-115">Enterprise и мобильные продукты</span><span class="sxs-lookup"><span data-stu-id="7b223-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="7b223-116">Продукты Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7b223-116">Dynamics 365 products</span></span>

<span data-ttu-id="7b223-117">Следующие продукты нельзя использовать со ссылками:</span><span class="sxs-lookup"><span data-stu-id="7b223-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="7b223-118">Microsoft Store приложения</span><span class="sxs-lookup"><span data-stu-id="7b223-118">Microsoft Store apps</span></span>
- <span data-ttu-id="7b223-119">Постоянное программное обеспечение или программное обеспечение, непосредственно назначенное пользователю, если лицензия не задействована.</span><span class="sxs-lookup"><span data-stu-id="7b223-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="7b223-120">Ресурсы Azure</span><span class="sxs-lookup"><span data-stu-id="7b223-120">Azure resources</span></span>

<span data-ttu-id="7b223-121">Вы должны быть глобальным администратором или администратором лицензий, чтобы начать работу с помощью этой ссылки.</span><span class="sxs-lookup"><span data-stu-id="7b223-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="7b223-122">Начало работы</span><span class="sxs-lookup"><span data-stu-id="7b223-122">Getting started</span></span>

<span data-ttu-id="7b223-123">Эта функция доступна в закрытом предварительном просмотре только небольшому числу клиентов.</span><span class="sxs-lookup"><span data-stu-id="7b223-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="7b223-124">Если вы заинтересованы в присоединении, заполните эту форму: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) .</span><span class="sxs-lookup"><span data-stu-id="7b223-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>