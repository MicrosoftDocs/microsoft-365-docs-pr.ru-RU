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
description: Сведения о том, как перемещать пользователей между подписками.
ms.date: 07/01/2020
ms.openlocfilehash: 79f3e4636ff047c4d6f27d83e3644913a8fbb0b5
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48647799"
---
# <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="4eb10-103">Перевод пользователей на другую подписку</span><span class="sxs-lookup"><span data-stu-id="4eb10-103">Move users to a different subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4eb10-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="4eb10-104">The admin center is changing.</span></span> <span data-ttu-id="4eb10-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="4eb10-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="4eb10-106">Если у вас несколько подписок, попросите пользователей с лицензией на одну подписку, но хотите переместить их в другую подписку, вы можете заменить существующую лицензию на другой.</span><span class="sxs-lookup"><span data-stu-id="4eb10-106">If you have more than one subscription, have users with a license for one subscription, but want to move them to another subscription, you can replace their existing license with a different one.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4eb10-107">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="4eb10-107">Before you begin</span></span>

<span data-ttu-id="4eb10-108">Чтобы назначать лицензии необходимо быть глобальным администратором либо администратором лицензией или пользователей.</span><span class="sxs-lookup"><span data-stu-id="4eb10-108">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="4eb10-109">Дополнительные сведения см. в статье [Роли администраторов в Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="4eb10-109">For more information, see [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span>

## <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="4eb10-110">Перевод пользователей на другую подписку</span><span class="sxs-lookup"><span data-stu-id="4eb10-110">Move users to a different subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4eb10-111">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="4eb10-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="4eb10-112">Выберите кружки рядом с именами пользователей, для которых вы хотите заменить существующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="4eb10-112">Select the circles next to the names of the users that you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="4eb10-113">Нажмите вверху **Дополнительные параметры (...)** и выберите **Управление лицензиями на продукты**.</span><span class="sxs-lookup"><span data-stu-id="4eb10-113">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="4eb10-114">В области **Управление лицензиями на продукты** выберите **Заменить имеющиеся назначения лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4eb10-114">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="4eb10-115">Установите переключатель в положение **вкл** ., чтобы получить лицензии, которые вы хотите назначить этим пользователям. </span><span class="sxs-lookup"><span data-stu-id="4eb10-115">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="4eb10-116">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="4eb10-116">You can limit which services are available to the users.</span></span> <span data-ttu-id="4eb10-117">Для служб, которых не должно быть у этих пользователей, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="4eb10-117">Switch the toggles to the **Off** position for the services that you don't want those users to have.</span></span> <span data-ttu-id="4eb10-118">Все предыдущие назначения лицензий для выбранных пользователей удаляются.</span><span class="sxs-lookup"><span data-stu-id="4eb10-118">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="4eb10-119">В нижней части области **Заменить имеющиеся продукты** нажмите **Заменить** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="4eb10-119">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4eb10-120">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="4eb10-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="4eb10-121">Установите флажки рядом с именами пользователей, для которых необходимо заменить лицензии.</span><span class="sxs-lookup"><span data-stu-id="4eb10-121">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="4eb10-122">В области **Массовые действия** выберите **Изменить лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="4eb10-122">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="4eb10-123">В области **Назначить продукты** выберите **Заменить имеющиеся назначения лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4eb10-123">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="4eb10-124">Установите переключатель в положение **вкл** ., чтобы получить лицензии, которые вы хотите назначить этим пользователям. </span><span class="sxs-lookup"><span data-stu-id="4eb10-124">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="4eb10-125">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="4eb10-125">You can limit which services are available to the users.</span></span> <span data-ttu-id="4eb10-126">Для служб, которых не должно быть у пользователей, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="4eb10-126">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="4eb10-127">Все предыдущие назначения лицензий для выбранных пользователей удаляются.</span><span class="sxs-lookup"><span data-stu-id="4eb10-127">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="4eb10-128">В нижней части области **Заменить имеющиеся продукты** нажмите **Заменить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="4eb10-128">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4eb10-129">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="4eb10-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="4eb10-130">Установите флажки рядом с именами пользователей, для которых необходимо заменить лицензии.</span><span class="sxs-lookup"><span data-stu-id="4eb10-130">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="4eb10-131">В области **Массовые действия** выберите **Изменить лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="4eb10-131">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="4eb10-132">В области **Назначить продукты** выберите **Заменить имеющиеся назначения лицензий на продукты** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4eb10-132">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="4eb10-133">Установите переключатель в положение **вкл** ., чтобы получить лицензии, которые вы хотите назначить этим пользователям. </span><span class="sxs-lookup"><span data-stu-id="4eb10-133">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="4eb10-134">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="4eb10-134">You can limit which services are available to the users.</span></span> <span data-ttu-id="4eb10-135">Для служб, которых не должно быть у пользователей, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="4eb10-135">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="4eb10-136">Все предыдущие назначения лицензий для выбранных пользователей удаляются.</span><span class="sxs-lookup"><span data-stu-id="4eb10-136">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="4eb10-137">В нижней части области **Заменить имеющиеся продукты** нажмите **Заменить** \> **Закрыть** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="4eb10-137">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="next-steps"></a><span data-ttu-id="4eb10-138">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="4eb10-138">Next steps</span></span>

<span data-ttu-id="4eb10-139">Если вы не собираетесь [переназначить неиспользуемые лицензии другим пользователям](../../managed-desktop/get-started/assign-licenses.md), рекомендуем [Удалить лицензии из подписки](../../commerce/licenses/buy-licenses.md) , чтобы вы не оплачиваете больше лицензий, чем требуется.</span><span class="sxs-lookup"><span data-stu-id="4eb10-139">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="4eb10-140">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="4eb10-140">Related content</span></span>

<span data-ttu-id="4eb10-141">[Назначение лицензий пользователям](../../admin/manage/assign-licenses-to-users.md) (статья) </span><span class="sxs-lookup"><span data-stu-id="4eb10-141">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="4eb10-142">[Удаление лицензий из подписки](../../commerce/licenses/remove-licenses-from-subscription.md) (статья) </span><span class="sxs-lookup"><span data-stu-id="4eb10-142">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="4eb10-143">[Изменение планов вручную](change-plans-manually.md) (статья) </span><span class="sxs-lookup"><span data-stu-id="4eb10-143">[Change plans manually](change-plans-manually.md) (article)</span></span>\
<span data-ttu-id="4eb10-144">[Общие сведения о подписках и лицензиях в Microsoft 365 для бизнеса](../licenses/subscriptions-and-licenses.md) (статья) </span><span class="sxs-lookup"><span data-stu-id="4eb10-144">[Understand subscriptions and licenses in Microsoft 365 for business](../licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="4eb10-145">[Приобретение другой подписки на Microsoft 365 для бизнеса](../buy-another-subscription.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="4eb10-145">[Buy another Microsoft 365 for business subscription](../buy-another-subscription.md) (article)</span></span>