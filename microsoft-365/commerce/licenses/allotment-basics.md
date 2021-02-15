---
title: Основы реализации
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
description: Узнайте о новых функциях.
ms.openlocfilehash: 2ab8efd637bb278faf6065559cab26cb7016975b
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638235"
---
# <a name="allotment-basics"></a><span data-ttu-id="1b801-103">Основы реализации</span><span class="sxs-lookup"><span data-stu-id="1b801-103">Allotment basics</span></span>

<span data-ttu-id="1b801-104">Назначения лицензий могут устанавливать ограничения лицензий и делегировать управление назначением лицензий только выбранным продуктам и лицензиям.</span><span class="sxs-lookup"><span data-stu-id="1b801-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="1b801-105">Для назначения лицензий пользователям используются групповые лицензии.</span><span class="sxs-lookup"><span data-stu-id="1b801-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="1b801-106">Ограничения лицензий обеспечивают дополнительный контроль над количеством лицензий, которые назначены пользователям в группах.</span><span class="sxs-lookup"><span data-stu-id="1b801-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="1b801-107">Поэтому даже по мере увеличения количества пользователей в группах вы можете следить за тем, чтобы вы оставались в пределах лимита лицензий, установленного для вашего лимита.</span><span class="sxs-lookup"><span data-stu-id="1b801-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="1b801-108">Вы также можете делегировать управление своими ресурсами.</span><span class="sxs-lookup"><span data-stu-id="1b801-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="1b801-109">Владельцы делегирования получают доступ к Центру администрирования, но могут видеть и управлять лицензиями только в своих собственных лицензиях.</span><span class="sxs-lookup"><span data-stu-id="1b801-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="1b801-110">Это обеспечивает более детальное делегирования управления лицензией в организации.</span><span class="sxs-lookup"><span data-stu-id="1b801-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1b801-111">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="1b801-111">Prerequisites</span></span>

<span data-ttu-id="1b801-112">Необходимо соответствовать требованиям лицензирования для [группового лицензирования.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="1b801-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="1b801-113">Вы можете использовать средства для любого продукта, доступного пользователям:</span><span class="sxs-lookup"><span data-stu-id="1b801-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="1b801-114">Наборы Office и автономные продукты</span><span class="sxs-lookup"><span data-stu-id="1b801-114">Office suites and standalone products</span></span>
- <span data-ttu-id="1b801-115">Корпоративные и мобильные продукты</span><span class="sxs-lookup"><span data-stu-id="1b801-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="1b801-116">Продукты Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="1b801-116">Dynamics 365 products</span></span>

<span data-ttu-id="1b801-117">С назначениями нельзя использовать следующие продукты:</span><span class="sxs-lookup"><span data-stu-id="1b801-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="1b801-118">Приложения Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="1b801-118">Microsoft Store apps</span></span>
- <span data-ttu-id="1b801-119">Бессрочные программы или программное обеспечение, которое напрямую назначено пользователю, если лицензия не задействована.</span><span class="sxs-lookup"><span data-stu-id="1b801-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="1b801-120">Ресурсы Azure</span><span class="sxs-lookup"><span data-stu-id="1b801-120">Azure resources</span></span>

<span data-ttu-id="1b801-121">Для начала работы с этим процессом необходимо быть глобальным администратором или администратором лицензии.</span><span class="sxs-lookup"><span data-stu-id="1b801-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="1b801-122">Начало работы</span><span class="sxs-lookup"><span data-stu-id="1b801-122">Getting started</span></span>

<span data-ttu-id="1b801-123">Эта функция доступна в закрытой предварительной версии только небольшому количеству пользователей.</span><span class="sxs-lookup"><span data-stu-id="1b801-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="1b801-124">Если вы хотите присоединиться, заполните эту [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) форму:</span><span class="sxs-lookup"><span data-stu-id="1b801-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
