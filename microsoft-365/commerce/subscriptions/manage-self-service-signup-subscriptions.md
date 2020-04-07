---
title: Управление подписками на самостоятельную регистрацию
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
- commerce
- Adm_NonTOC
search.appverid:
- MET150
description: Сведения о том, как управлять бесплатными самостоятельными подписками на услуги для Организации.
ms.openlocfilehash: 056ae95f9f5067ea3fa86164b620c72c84e3aad4
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "43154140"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="92174-103">Управление подписками на самостоятельную регистрацию</span><span class="sxs-lookup"><span data-stu-id="92174-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="92174-104">Что такое подписки на самостоятельную регистрацию.</span><span class="sxs-lookup"><span data-stu-id="92174-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="92174-105">Существует ограниченное число самостоятельных подписок для самообслуживания, для которых пользователи в вашей организации могут подписаться.</span><span class="sxs-lookup"><span data-stu-id="92174-105">There are a limited number of free self-service sign-up subscriptions that users in your organization can sign up for.</span></span> <span data-ttu-id="92174-106">Пользователь может только зарегистрироваться и использовать самостоятельную подписку на службу регистрации.</span><span class="sxs-lookup"><span data-stu-id="92174-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="92174-107">Эти подписки отображаются на странице " **продукты & услуг** ", помечены как **свободные**и имеют заметку "это бесплатная подписка, активируемая пользователями в вашей компании".</span><span class="sxs-lookup"><span data-stu-id="92174-107">These subscriptions appear on the **Products & services** page, are marked as **Free**, and have a note that says, "This is a free subscription activated by users in your company."</span></span> <span data-ttu-id="92174-108">Вы можете управлять подписками на самостоятельную регистрацию, блокируя регистрацию пользователей и удаляя Бесплатные подписки, на которые пользователи зарегистрировались.</span><span class="sxs-lookup"><span data-stu-id="92174-108">You can manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="92174-109">Для получения дополнительных сведений о самостоятельной регистрации и доступных подписках [в разделе Использование самостоятельной регистрации в вашей организации](../../admin/misc/self-service-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="92174-109">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="92174-110">Чем отличаются эти подписки от самостоятельной подписки на покупку?</span><span class="sxs-lookup"><span data-stu-id="92174-110">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="92174-111">Самостоятельная подписка на подписку предоставляется бесплатно и доступна для более крупного списка продуктов, чем самостоятельных подписок на покупку.</span><span class="sxs-lookup"><span data-stu-id="92174-111">Self-service sign-up subscriptions are free, and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="92174-112">Когда пользователь подписывается на самостоятельную подписку на покупку, она отвечает за ее оплату.</span><span class="sxs-lookup"><span data-stu-id="92174-112">When a user signs up for a self-service purchase subscription, they are responsible for paying for it.</span></span> <span data-ttu-id="92174-113">Кроме того, самостоятельные подписки на покупку доступны только для продуктов Power Platform (Power BI, Power Apps и Power Автоматизация).</span><span class="sxs-lookup"><span data-stu-id="92174-113">Also, self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate).</span></span> <span data-ttu-id="92174-114">Дополнительные сведения можно найти в статье [вопросы и ответы по самостоятельной покупке](self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="92174-114">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.md).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="92174-115">Запретить пользователям подписываться</span><span class="sxs-lookup"><span data-stu-id="92174-115">Block users from signing up</span></span>

<span data-ttu-id="92174-116">Используйте командлет [**Set – мсолкомпанисеттингс**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) с параметром **алловадхоксубскриптионс** , чтобы указать, могут ли пользователи подписываться на самостоятельную подписку на службу регистрации.</span><span class="sxs-lookup"><span data-stu-id="92174-116">You use the [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="92174-117">Дополнительные сведения можно найти в [статье как управлять параметрами самообслуживания?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="92174-117">For more information, see [How do I control self-service settings?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="92174-118">Удаление подписки на самостоятельную службу регистрации</span><span class="sxs-lookup"><span data-stu-id="92174-118">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="92174-119">При удалении подписки на самостоятельную службу подписки все пользователи блокируются для доступа к данным и электронной почте, а также удаляют все данные и электронную почту.</span><span class="sxs-lookup"><span data-stu-id="92174-119">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="92174-120">В центре администрирования откройте страницу "Услуги по **выставлению счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">& услуг</a> ".</span><span class="sxs-lookup"><span data-stu-id="92174-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>
2. <span data-ttu-id="92174-121">Найдите подписку на самостоятельную регистрацию, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="92174-121">Find the self-service sign-up subscription that you want to delete.</span></span> <span data-ttu-id="92174-122">В разделе **параметры & действий** выберите **удалить подписку**.</span><span class="sxs-lookup"><span data-stu-id="92174-122">In the **Settings & Actions** section, select **Delete subscription**.</span></span>
3. <span data-ttu-id="92174-123">В области **удалить подписку** установите флажок, а затем выберите **удалить подписку**.</span><span class="sxs-lookup"><span data-stu-id="92174-123">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="92174-124">У меня есть подписка на самостоятельную регистрацию, которая блокирует удаление каталога</span><span class="sxs-lookup"><span data-stu-id="92174-124">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="92174-125">Продукты для самостоятельной регистрации, которые могут зарегистрироваться для отдельных пользователей, также создают гостей для проверки подлинности в каталоге Azure AD.</span><span class="sxs-lookup"><span data-stu-id="92174-125">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="92174-126">Чтобы избежать потери данных, эти продукты самообслуживания блокируют Удаление каталога, пока они не будут полностью удалены из каталога.</span><span class="sxs-lookup"><span data-stu-id="92174-126">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="92174-127">Их можно удалить только администратором Azure AD. Дополнительные сведения см. [в статье Удаление каталога в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span><span class="sxs-lookup"><span data-stu-id="92174-127">They can be deleted only by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>