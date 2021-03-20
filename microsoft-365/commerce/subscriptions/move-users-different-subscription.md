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
ms.openlocfilehash: 7eb07bda4fd1a558a8126f11ef3a1fbc4ceb0389
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907884"
---
# <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="34524-103">Перевод пользователей на другую подписку</span><span class="sxs-lookup"><span data-stu-id="34524-103">Move users to a different subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="34524-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="34524-104">The admin center is changing.</span></span> <span data-ttu-id="34524-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="34524-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="34524-106">Если у вас несколько подписок, есть пользователи с лицензией на одну подписку, но вы хотите переместить их в другую подписку, вы можете заменить существующую лицензию другой.</span><span class="sxs-lookup"><span data-stu-id="34524-106">If you have more than one subscription, have users with a license for one subscription, but want to move them to another subscription, you can replace their existing license with a different one.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="34524-107">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="34524-107">Before you begin</span></span>

<span data-ttu-id="34524-108">Чтобы назначать лицензии необходимо быть глобальным администратором либо администратором лицензией или пользователей.</span><span class="sxs-lookup"><span data-stu-id="34524-108">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="34524-109">Дополнительные сведения см. в статье [Роли администраторов в Microsoft 365](../../admin/add-users/about-admin-roles.md?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="34524-109">For more information, see [About Microsoft 365 admin roles](../../admin/add-users/about-admin-roles.md?view=o365-worldwide).</span></span>

## <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="34524-110">Перевод пользователей на другую подписку</span><span class="sxs-lookup"><span data-stu-id="34524-110">Move users to a different subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="34524-111">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="34524-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="34524-112">Выберите круги рядом с именами пользователей, для которых необходимо заменить существующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="34524-112">Select the circles next to the names of the users that you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="34524-113">Нажмите вверху **Дополнительные параметры (...)** и выберите **Управление лицензиями на продукты**.</span><span class="sxs-lookup"><span data-stu-id="34524-113">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="34524-114">В области **Управление лицензиями на продукты** выберите **Заменить имеющиеся назначения лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="34524-114">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="34524-115">Переключить переключатель на положение **On** для лицензий, которые необходимо назначить этим пользователям.</span><span class="sxs-lookup"><span data-stu-id="34524-115">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="34524-116">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="34524-116">You can limit which services are available to the users.</span></span> <span data-ttu-id="34524-117">Для служб, которых не должно быть у этих пользователей, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="34524-117">Switch the toggles to the **Off** position for the services that you don't want those users to have.</span></span> <span data-ttu-id="34524-118">Все предыдущие назначения лицензий для выбранных пользователей удаляются.</span><span class="sxs-lookup"><span data-stu-id="34524-118">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="34524-119">В нижней части области **Заменить имеющиеся продукты** нажмите **Заменить** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="34524-119">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="34524-120">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="34524-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="34524-121">Установите флажки рядом с именами пользователей, для которых необходимо заменить лицензии.</span><span class="sxs-lookup"><span data-stu-id="34524-121">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="34524-122">В области **Массовые действия** выберите **Изменить лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="34524-122">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="34524-123">В области **Назначить продукты** выберите **Заменить имеющиеся назначения лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="34524-123">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="34524-124">Переключить переключатель на положение **On** для лицензий, которые необходимо назначить этим пользователям.</span><span class="sxs-lookup"><span data-stu-id="34524-124">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="34524-125">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="34524-125">You can limit which services are available to the users.</span></span> <span data-ttu-id="34524-126">Для служб, которых не должно быть у пользователей, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="34524-126">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="34524-127">Все предыдущие назначения лицензий для выбранных пользователей удаляются.</span><span class="sxs-lookup"><span data-stu-id="34524-127">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="34524-128">В нижней части области **Заменить имеющиеся продукты** нажмите **Заменить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="34524-128">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="34524-129">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="34524-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="34524-130">Установите флажки рядом с именами пользователей, для которых необходимо заменить лицензии.</span><span class="sxs-lookup"><span data-stu-id="34524-130">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="34524-131">В области **Массовые действия** выберите **Изменить лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="34524-131">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="34524-132">В области **Назначить продукты** выберите **Заменить имеющиеся назначения лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="34524-132">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="34524-133">Переключить переключатель на положение **On** для лицензий, которые необходимо назначить этим пользователям.</span><span class="sxs-lookup"><span data-stu-id="34524-133">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="34524-134">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="34524-134">You can limit which services are available to the users.</span></span> <span data-ttu-id="34524-135">Для служб, которых не должно быть у пользователей, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="34524-135">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="34524-136">Все предыдущие назначения лицензий для выбранных пользователей удаляются.</span><span class="sxs-lookup"><span data-stu-id="34524-136">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="34524-137">В нижней части области **Заменить имеющиеся продукты** нажмите **Заменить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="34524-137">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="next-steps"></a><span data-ttu-id="34524-138">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="34524-138">Next steps</span></span>

<span data-ttu-id="34524-139">Если вы не собираетесь перенаходить неиспользование лицензий другим [](../../commerce/licenses/buy-licenses.md) [пользователям,](../../managed-desktop/get-started/assign-licenses.md)рассмотрите возможность удаления лицензий из подписки, чтобы не платить за больше лицензий, чем нужно.</span><span class="sxs-lookup"><span data-stu-id="34524-139">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="34524-140">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="34524-140">Related content</span></span>

<span data-ttu-id="34524-141">[Назначение лицензий пользователям](../../admin/manage/assign-licenses-to-users.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="34524-141">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="34524-142">[Удаление лицензий из подписки](../licenses/buy-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="34524-142">[Remove licenses from your subscription](../licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="34524-143">[Изменение планов вручную](change-plans-manually.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="34524-143">[Change plans manually](change-plans-manually.md) (article)</span></span>\
<span data-ttu-id="34524-144">[Понимание подписок и лицензий в Microsoft 365 для бизнеса](../licenses/subscriptions-and-licenses.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="34524-144">[Understand subscriptions and licenses in Microsoft 365 for business](../licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="34524-145">[Купить другой Microsoft 365 для подписки на бизнес](../try-or-buy-microsoft-365.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="34524-145">[Buy another Microsoft 365 for business subscription](../try-or-buy-microsoft-365.md) (article)</span></span>