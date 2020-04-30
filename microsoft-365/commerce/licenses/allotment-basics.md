---
title: Основы объема услуг
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: ''
description: Сведения о новых функциях.
ms.openlocfilehash: e6fe91ee2c0e2de58b54e40eddba6d3066999e6d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942179"
---
# <a name="allotment-basics"></a><span data-ttu-id="cb7f6-103">Основы объема услуг</span><span class="sxs-lookup"><span data-stu-id="cb7f6-103">Allotment basics</span></span>

<span data-ttu-id="cb7f6-104">Использование лицензий позволяет устанавливать пределы лицензий и делегировать управление назначением лицензий только выбранным продуктам и лицензиям.</span><span class="sxs-lookup"><span data-stu-id="cb7f6-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="cb7f6-105">Для назначения лицензий пользователям используется лицензирование на основе групп.</span><span class="sxs-lookup"><span data-stu-id="cb7f6-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="cb7f6-106">Лицензионные пределы предоставляют возможность управления количеством лицензий, назначенных пользователям в группах.</span><span class="sxs-lookup"><span data-stu-id="cb7f6-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="cb7f6-107">Таким образом, даже при увеличении числа пользователей в группах вы можете убедиться, что вы следите за предельным числом лицензий, заданным для вашего объема.</span><span class="sxs-lookup"><span data-stu-id="cb7f6-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="cb7f6-108">Вы также можете делегировать управление вашими отправкой.</span><span class="sxs-lookup"><span data-stu-id="cb7f6-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="cb7f6-109">Делегированные владельцы услуг, которые получают доступ к центру администрирования, но могут просматривать и управлять лицензиями только в тех случаях, когда они владеют.</span><span class="sxs-lookup"><span data-stu-id="cb7f6-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="cb7f6-110">Это обеспечивает более детальное делегирование управления лицензиями в пределах организации.</span><span class="sxs-lookup"><span data-stu-id="cb7f6-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cb7f6-111">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="cb7f6-111">Prerequisites</span></span>

<span data-ttu-id="cb7f6-112">Необходимо соблюдение требований лицензирования для [лицензирования на основе групп](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="cb7f6-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="cb7f6-113">Вы можете использовать доступ к любому продукту, доступному пользователям:</span><span class="sxs-lookup"><span data-stu-id="cb7f6-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="cb7f6-114">Пакеты Office и отдельные продукты</span><span class="sxs-lookup"><span data-stu-id="cb7f6-114">Office suites and standalone products</span></span>
- <span data-ttu-id="cb7f6-115">Продукты для предприятий и мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="cb7f6-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="cb7f6-116">Продукты Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="cb7f6-116">Dynamics 365 products</span></span>

<span data-ttu-id="cb7f6-117">Следующие продукты невозможно использовать с объемом услуг:</span><span class="sxs-lookup"><span data-stu-id="cb7f6-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="cb7f6-118">Приложения Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="cb7f6-118">Microsoft Store apps</span></span>
- <span data-ttu-id="cb7f6-119">Нелицензионное программное обеспечение или программное обеспечение, непосредственно назначенное пользователю при отсутствии лицензии.</span><span class="sxs-lookup"><span data-stu-id="cb7f6-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="cb7f6-120">Ресурсы Azure</span><span class="sxs-lookup"><span data-stu-id="cb7f6-120">Azure resources</span></span>

<span data-ttu-id="cb7f6-121">Чтобы приступить к работе, вам необходимо быть глобальным администратором или администратором лицензий.</span><span class="sxs-lookup"><span data-stu-id="cb7f6-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="cb7f6-122">Начало работы</span><span class="sxs-lookup"><span data-stu-id="cb7f6-122">Getting started</span></span>

<span data-ttu-id="cb7f6-123">Функция "предоставление услуг" доступна в частном предварительном просмотре только для небольшого числа клиентов.</span><span class="sxs-lookup"><span data-stu-id="cb7f6-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="cb7f6-124">Если вы хотите присоединиться, заполните эту форму [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup):.</span><span class="sxs-lookup"><span data-stu-id="cb7f6-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
