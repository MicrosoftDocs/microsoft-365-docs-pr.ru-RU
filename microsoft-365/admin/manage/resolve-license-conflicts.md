---
title: Устранение конфликтов лицензий
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
description: Узнайте, как разрешить конфликт лицензий с microsoft 365 для бизнес-подписки.
ms.openlocfilehash: e2b5daa71164b41825282bd5652549347b8307c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915186"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="4c10c-103">Устранение конфликтов лицензий</span><span class="sxs-lookup"><span data-stu-id="4c10c-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4c10c-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="4c10c-104">The admin center is changing.</span></span> <span data-ttu-id="4c10c-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="4c10c-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="4c10c-106">Перед созданием новых пользователей рекомендуется приобрести лицензии, необходимые для подписки.</span><span class="sxs-lookup"><span data-stu-id="4c10c-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="4c10c-107">Таким образом, по мере создания учетных записей пользователей лицензия может быть назначена новым пользователям.</span><span class="sxs-lookup"><span data-stu-id="4c10c-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="4c10c-108">Если все лицензии уже назначены пользователям, но срок действия некоторых лицензий истек, или вы пытаетесь удалить лицензию, которая уже назначена пользователю, у вас будут конфликты лицензий.</span><span class="sxs-lookup"><span data-stu-id="4c10c-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="4c10c-109">Дополнительные сведения см. в [журнале Remove licenses from your subscription.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="4c10c-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="4c10c-110">Просмотр конфликтов лицензий</span><span class="sxs-lookup"><span data-stu-id="4c10c-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4c10c-111">В Центре администрирования выберите **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="4c10c-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4c10c-112">В Центре администрирования выберите **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="4c10c-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4c10c-113">В Центре администрирования выберите **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Лицензии</a>.</span><span class="sxs-lookup"><span data-stu-id="4c10c-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="4c10c-114">Чтобы узнать, нет ли конфликтов, проверьте столбец **Состояние**.</span><span class="sxs-lookup"><span data-stu-id="4c10c-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="4c10c-115">Если произошел конфликт, вы увидите предупреждающий сигнал, в нем говорится, что одному или более пользователям нужна действительная лицензия.</span><span class="sxs-lookup"><span data-stu-id="4c10c-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c10c-116">Если конфликты отсутствуют, столбец **Состояние** не отображается.</span><span class="sxs-lookup"><span data-stu-id="4c10c-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="4c10c-117">Устранение конфликтов лицензий</span><span class="sxs-lookup"><span data-stu-id="4c10c-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="4c10c-118">Конфликты лицензий можно разрешить путем [покупки](../../commerce/licenses/buy-licenses.md) дополнительных лицензий или удаления лицензий у [пользователей, которым они](remove-licenses-from-users.md)больше не нужны.</span><span class="sxs-lookup"><span data-stu-id="4c10c-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="4c10c-119">Вы также можете [удалить учетную запись пользователя, чтобы высвободить лицензию](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="4c10c-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="4c10c-120">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4c10c-120">Related articles</span></span>

[<span data-ttu-id="4c10c-121">Назначение лицензий пользователям</span><span class="sxs-lookup"><span data-stu-id="4c10c-121">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="4c10c-122">Удаление лицензий у пользователей</span><span class="sxs-lookup"><span data-stu-id="4c10c-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)