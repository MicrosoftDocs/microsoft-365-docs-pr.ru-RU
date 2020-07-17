---
title: Устранение конфликтов лицензий
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Узнайте, как устранять конфликты лицензий с подпиской на Microsoft 365 для бизнеса.
ms.openlocfilehash: 2270fd3ad831ec0ad92ac4eddec5f08a1d07f8be
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015975"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="421d7-103">Устранение конфликтов лицензий</span><span class="sxs-lookup"><span data-stu-id="421d7-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="421d7-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="421d7-104">The admin center is changing.</span></span> <span data-ttu-id="421d7-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="421d7-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="421d7-106">Мы рекомендуем приобрести лицензии, необходимые для подписки, прежде чем создавать новых пользователей.</span><span class="sxs-lookup"><span data-stu-id="421d7-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="421d7-107">Таким образом, при создании учетных записей пользователей лицензия может быть назначена новым пользователям.</span><span class="sxs-lookup"><span data-stu-id="421d7-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="421d7-108">Если вы уже назначили все лицензии пользователям, но у них истек срок действия, или если вы попытаетесь удалить лицензию, которая уже назначена пользователю, возникнут конфликты лицензий.</span><span class="sxs-lookup"><span data-stu-id="421d7-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="421d7-109">Дополнительные сведения см. [в статье Удаление лицензий из подписки](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="421d7-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="421d7-110">Просмотр конфликтов лицензий</span><span class="sxs-lookup"><span data-stu-id="421d7-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="421d7-111">В центре администрирования перейдите на страницу лицензии **выставления счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> .</span><span class="sxs-lookup"><span data-stu-id="421d7-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="421d7-112">В центре администрирования перейдите на страницу лицензии **выставления счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> .</span><span class="sxs-lookup"><span data-stu-id="421d7-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="421d7-113">В центре администрирования перейдите на страницу лицензии **выставления счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> .</span><span class="sxs-lookup"><span data-stu-id="421d7-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="421d7-114">Чтобы узнать, нет ли конфликтов, проверьте столбец **Состояние**.</span><span class="sxs-lookup"><span data-stu-id="421d7-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="421d7-115">При возникновении конфликта отображается предупреждающее сообщение о том, что одному или нескольким пользователям требуется действительная лицензия.</span><span class="sxs-lookup"><span data-stu-id="421d7-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="421d7-116">Если конфликты отсутствуют, столбец **Состояние** не отображается.</span><span class="sxs-lookup"><span data-stu-id="421d7-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="421d7-117">Устранение конфликтов лицензий</span><span class="sxs-lookup"><span data-stu-id="421d7-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="421d7-118">Конфликты лицензий можно устранить, [приобретая дополнительные лицензии](../../commerce/licenses/buy-licenses.md) или [удалив лицензии от пользователей, которым они больше не нужны](remove-licenses-from-users.md).</span><span class="sxs-lookup"><span data-stu-id="421d7-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="421d7-119">Вы также можете [удалить учетную запись пользователя, чтобы высвободить лицензию](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="421d7-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="421d7-120">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="421d7-120">Related articles</span></span>

[<span data-ttu-id="421d7-121">Назначение лицензий пользователям</span><span class="sxs-lookup"><span data-stu-id="421d7-121">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="421d7-122">Удаление лицензий у пользователей</span><span class="sxs-lookup"><span data-stu-id="421d7-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)
