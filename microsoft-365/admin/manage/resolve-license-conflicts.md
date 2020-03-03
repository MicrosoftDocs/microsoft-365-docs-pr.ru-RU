---
title: Устранение конфликтов лицензий в Office 365 для бизнеса
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Узнайте, как устранять конфликты лицензий с подпиской на Office 365 для бизнеса.
ms.openlocfilehash: 63464951c4f1fd568248ca5c43da9f8c94347711
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361784"
---
# <a name="resolve-license-conflicts-in-office-365-for-business"></a><span data-ttu-id="50a56-103">Устранение конфликтов лицензий в Office 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="50a56-103">Resolve license conflicts in Office 365 for business</span></span>

<span data-ttu-id="50a56-104">Мы рекомендуем приобрести лицензии, необходимые для подписки, прежде чем создавать новых пользователей.</span><span class="sxs-lookup"><span data-stu-id="50a56-104">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="50a56-105">Таким образом, при создании учетных записей пользователей лицензия может быть назначена новым пользователям.</span><span class="sxs-lookup"><span data-stu-id="50a56-105">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="50a56-106">Если вы уже назначили все лицензии пользователям, но у них истек срок действия, или если вы попытаетесь удалить лицензию, которая уже назначена пользователю, возникнут конфликты лицензий.</span><span class="sxs-lookup"><span data-stu-id="50a56-106">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="50a56-107">Дополнительные сведения см. [в статье Удаление лицензий из подписки](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="50a56-107">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="50a56-108">Просмотр конфликтов лицензий</span><span class="sxs-lookup"><span data-stu-id="50a56-108">How do I view license conflicts?</span></span>

1. <span data-ttu-id="50a56-109">В центре администрирования перейдите на страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">лицензии</a> **выставления счетов** \> .</span><span class="sxs-lookup"><span data-stu-id="50a56-109">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

    <span data-ttu-id="50a56-110">Если вы используете Office 365 Германии, перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">лицензии</a> ".</span><span class="sxs-lookup"><span data-stu-id="50a56-110">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

    <span data-ttu-id="50a56-111">Если вы используете Office 365 под управлением 21Vianet, перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">лицензии</a> ".</span><span class="sxs-lookup"><span data-stu-id="50a56-111">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="50a56-112">Чтобы узнать, нет ли конфликтов, проверьте столбец **Состояние**.</span><span class="sxs-lookup"><span data-stu-id="50a56-112">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="50a56-113">При возникновении конфликта отображается предупреждающее сообщение о том, что одному или нескольким пользователям требуется действительная лицензия.</span><span class="sxs-lookup"><span data-stu-id="50a56-113">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="50a56-114">Если конфликты отсутствуют, столбец **Состояние** не отображается.</span><span class="sxs-lookup"><span data-stu-id="50a56-114">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="50a56-115">Устранение конфликтов лицензий</span><span class="sxs-lookup"><span data-stu-id="50a56-115">How do I resolve license conflicts?</span></span>

<span data-ttu-id="50a56-116">Конфликты лицензий можно устранить, [приобретая дополнительные лицензии](../../commerce/licenses/buy-licenses.md) или [удалив лицензии от пользователей, которым они больше не нужны](remove-licenses-from-users.md).</span><span class="sxs-lookup"><span data-stu-id="50a56-116">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="50a56-117">Вы также можете [удалить учетную запись пользователя, чтобы высвободить лицензию](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="50a56-117">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="50a56-118">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="50a56-118">Related articles</span></span> 

[<span data-ttu-id="50a56-119">Назначение лицензий пользователям</span><span class="sxs-lookup"><span data-stu-id="50a56-119">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="50a56-120">Удаление лицензий у пользователей</span><span class="sxs-lookup"><span data-stu-id="50a56-120">Remove licenses from users</span></span>](remove-licenses-from-users.md)
