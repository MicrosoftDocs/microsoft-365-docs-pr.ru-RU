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
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_licensing
description: Узнайте о новых функциях.
ms.date: 03/17/2021
ms.openlocfilehash: 0910673ce54f3f977ed8ecbc3d6c77ac2ebad0cc
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331698"
---
# <a name="allotment-basics"></a><span data-ttu-id="6a3af-103">Основы реализации</span><span class="sxs-lookup"><span data-stu-id="6a3af-103">Allotment basics</span></span>

<span data-ttu-id="6a3af-104">Присвоение лицензий позволит вам установить ограничения лицензии и делегировать управление назначением лицензии только на выбранные вами продукты и лицензии.</span><span class="sxs-lookup"><span data-stu-id="6a3af-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="6a3af-105">Для назначения лицензий пользователям используются групповые лицензии.</span><span class="sxs-lookup"><span data-stu-id="6a3af-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="6a3af-106">Ограничения лицензий обеспечивают дополнительный контроль над количеством лицензий, назначенных пользователям в группах.</span><span class="sxs-lookup"><span data-stu-id="6a3af-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="6a3af-107">Таким образом, даже по мере увеличения числа пользователей в группах можно обеспечить, чтобы вы оставались в пределах лимита лицензии, установленного для вашего отгружаемого.</span><span class="sxs-lookup"><span data-stu-id="6a3af-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="6a3af-108">Вы также можете делегировать управление своими ресурсами.</span><span class="sxs-lookup"><span data-stu-id="6a3af-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="6a3af-109">Владельцы делегирования получают доступ к центру администрирования, но могут видеть и управлять лицензиями только в своих собственных лицензиях.</span><span class="sxs-lookup"><span data-stu-id="6a3af-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="6a3af-110">Это обеспечивает более подробное делегированное управление лицензией в организации.</span><span class="sxs-lookup"><span data-stu-id="6a3af-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6a3af-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="6a3af-111">Prerequisites</span></span>

<span data-ttu-id="6a3af-112">Вы должны соответствовать требованиям лицензирования для [группового лицензирования.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="6a3af-112">You must meet the licensing requirements for [group-based licensing](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="6a3af-113">Вы можете использовать ссылки с любым продуктом, доступным для пользователей:</span><span class="sxs-lookup"><span data-stu-id="6a3af-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="6a3af-114">Пакеты Office и автономные продукты</span><span class="sxs-lookup"><span data-stu-id="6a3af-114">Office suites and standalone products</span></span>
- <span data-ttu-id="6a3af-115">Продукты enterprise и Mobility</span><span class="sxs-lookup"><span data-stu-id="6a3af-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="6a3af-116">Продукты Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="6a3af-116">Dynamics 365 products</span></span>

<span data-ttu-id="6a3af-117">Следующие продукты нельзя использовать со ссылками:</span><span class="sxs-lookup"><span data-stu-id="6a3af-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="6a3af-118">Приложения Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="6a3af-118">Microsoft Store apps</span></span>
- <span data-ttu-id="6a3af-119">Постоянное программное обеспечение или программное обеспечение, непосредственно назначенное пользователю, если лицензия не задействована.</span><span class="sxs-lookup"><span data-stu-id="6a3af-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="6a3af-120">Ресурсы Azure</span><span class="sxs-lookup"><span data-stu-id="6a3af-120">Azure resources</span></span>

<span data-ttu-id="6a3af-121">Вы должны быть глобальным администратором или администратором лицензий, чтобы начать работу с помощью этой ссылки.</span><span class="sxs-lookup"><span data-stu-id="6a3af-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="6a3af-122">Начало работы</span><span class="sxs-lookup"><span data-stu-id="6a3af-122">Getting started</span></span>

<span data-ttu-id="6a3af-123">Эта функция доступна в закрытом предварительном просмотре только небольшому числу клиентов.</span><span class="sxs-lookup"><span data-stu-id="6a3af-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="6a3af-124">Если вы заинтересованы в присоединении, заполните эту форму: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) .</span><span class="sxs-lookup"><span data-stu-id="6a3af-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>