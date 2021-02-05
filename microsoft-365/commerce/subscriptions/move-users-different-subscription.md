---
title: Перевод пользователей на другую подписку
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Узнайте, как перемещать пользователей между подписками.
ms.date: 07/01/2020
ms.openlocfilehash: ec9385d10cc1799509c6f1d2fa88059eecf3bd8c
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114673"
---
# <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="f606f-103">Перевод пользователей на другую подписку</span><span class="sxs-lookup"><span data-stu-id="f606f-103">Move users to a different subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f606f-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="f606f-104">The admin center is changing.</span></span> <span data-ttu-id="f606f-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="f606f-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="f606f-106">Если у вас несколько подписок, есть пользователи с лицензией на одну подписку, но вы хотите переместить их в другую, вы можете заменить их существующую лицензию другой.</span><span class="sxs-lookup"><span data-stu-id="f606f-106">If you have more than one subscription, have users with a license for one subscription, but want to move them to another subscription, you can replace their existing license with a different one.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f606f-107">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="f606f-107">Before you begin</span></span>

<span data-ttu-id="f606f-108">Чтобы назначать лицензии необходимо быть глобальным администратором либо администратором лицензией или пользователей.</span><span class="sxs-lookup"><span data-stu-id="f606f-108">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="f606f-109">Дополнительные сведения см. в статье [Роли администраторов в Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="f606f-109">For more information, see [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span>

## <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="f606f-110">Перевод пользователей на другую подписку</span><span class="sxs-lookup"><span data-stu-id="f606f-110">Move users to a different subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f606f-111">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="f606f-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f606f-112">Выберите круги рядом с именами пользователей, для которых необходимо заменить существующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="f606f-112">Select the circles next to the names of the users that you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="f606f-113">Нажмите вверху **Дополнительные параметры (...)** и выберите **Управление лицензиями на продукты**.</span><span class="sxs-lookup"><span data-stu-id="f606f-113">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="f606f-114">В области **Управление лицензиями на продукты** выберите **Заменить имеющиеся назначения лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f606f-114">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="f606f-115">Переключить переключатель в положение **"Вкл."** для лицензий, которые вы хотите назначить этим пользователям.</span><span class="sxs-lookup"><span data-stu-id="f606f-115">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="f606f-116">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="f606f-116">You can limit which services are available to the users.</span></span> <span data-ttu-id="f606f-117">Для служб, которых не должно быть у этих пользователей, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="f606f-117">Switch the toggles to the **Off** position for the services that you don't want those users to have.</span></span> <span data-ttu-id="f606f-118">Все предыдущие назначения лицензий для выбранных пользователей удаляются.</span><span class="sxs-lookup"><span data-stu-id="f606f-118">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="f606f-119">В нижней части области **Заменить имеющиеся продукты** нажмите **Заменить** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f606f-119">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="f606f-120">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="f606f-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f606f-121">Установите флажки рядом с именами пользователей, для которых необходимо заменить лицензии.</span><span class="sxs-lookup"><span data-stu-id="f606f-121">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="f606f-122">В области **Массовые действия** выберите **Изменить лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="f606f-122">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="f606f-123">В области **Назначить продукты** выберите **Заменить имеющиеся назначения лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f606f-123">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="f606f-124">Переключить переключатель в положение **"Вкл."** для лицензий, которые вы хотите назначить этим пользователям.</span><span class="sxs-lookup"><span data-stu-id="f606f-124">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="f606f-125">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="f606f-125">You can limit which services are available to the users.</span></span> <span data-ttu-id="f606f-126">Для служб, которых не должно быть у пользователей, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="f606f-126">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="f606f-127">Все предыдущие назначения лицензий для выбранных пользователей удаляются.</span><span class="sxs-lookup"><span data-stu-id="f606f-127">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="f606f-128">В нижней части области **Заменить имеющиеся продукты** нажмите **Заменить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f606f-128">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f606f-129">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="f606f-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f606f-130">Установите флажки рядом с именами пользователей, для которых необходимо заменить лицензии.</span><span class="sxs-lookup"><span data-stu-id="f606f-130">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="f606f-131">В области **Массовые действия** выберите **Изменить лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="f606f-131">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="f606f-132">В области **Назначить продукты** выберите **Заменить имеющиеся назначения лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f606f-132">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="f606f-133">Переключить переключатель в положение **"Вкл."** для лицензий, которые вы хотите назначить этим пользователям.</span><span class="sxs-lookup"><span data-stu-id="f606f-133">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="f606f-134">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="f606f-134">You can limit which services are available to the users.</span></span> <span data-ttu-id="f606f-135">Для служб, которых не должно быть у пользователей, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="f606f-135">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="f606f-136">Все предыдущие назначения лицензий для выбранных пользователей удаляются.</span><span class="sxs-lookup"><span data-stu-id="f606f-136">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="f606f-137">В нижней части области **Заменить имеющиеся продукты** нажмите **Заменить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f606f-137">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="next-steps"></a><span data-ttu-id="f606f-138">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="f606f-138">Next steps</span></span>

<span data-ttu-id="f606f-139">Если вы не собираетесь переначивать неиспользование лицензий другим [](../../commerce/licenses/buy-licenses.md) [пользователям,](../../managed-desktop/get-started/assign-licenses.md)рассмотрите возможность удаления лицензий из подписки, чтобы не платить за дополнительные лицензии, чем нужно.</span><span class="sxs-lookup"><span data-stu-id="f606f-139">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="f606f-140">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="f606f-140">Related content</span></span>

<span data-ttu-id="f606f-141">[Назначение лицензий пользователям](../../admin/manage/assign-licenses-to-users.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="f606f-141">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="f606f-142">[Удаление лицензий из подписки](../../commerce/licenses/remove-licenses-from-subscription.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="f606f-142">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="f606f-143">[Изменение планов вручную](change-plans-manually.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="f606f-143">[Change plans manually](change-plans-manually.md) (article)</span></span>\
<span data-ttu-id="f606f-144">[Подписки и лицензии в Microsoft 365 для бизнеса](../licenses/subscriptions-and-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="f606f-144">[Understand subscriptions and licenses in Microsoft 365 for business](../licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="f606f-145">[Покупка другой подписки на Microsoft 365 для бизнеса](../buy-another-subscription.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="f606f-145">[Buy another Microsoft 365 for business subscription](../buy-another-subscription.md) (article)</span></span>