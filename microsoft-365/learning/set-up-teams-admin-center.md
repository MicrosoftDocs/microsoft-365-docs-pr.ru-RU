---
title: Настройка microsoft Viva Learning (Preview) в центре администрирования Teams
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: ''
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Узнайте, как настроить Microsoft Viva Learning (Preview) в центре Teams администрирования.
ms.openlocfilehash: 860f16bee7d93f2212072c5d738263402704272f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789235"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="b5df6-103">Настройка microsoft Viva Learning (Preview) в центре администрирования Teams</span><span class="sxs-lookup"><span data-stu-id="b5df6-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="b5df6-104">Сведения в этой статье относятся к продукту предварительного просмотра, который может быть существенно изменен до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="b5df6-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="b5df6-105">Администратору Teams выполнить определенные действия, чтобы включить Viva Learning (Preview) для своих пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="b5df6-105">The Teams administrator needs to perform certain steps to enable Viva Learning (Preview) for their users in the tenant.</span></span> <span data-ttu-id="b5df6-106">Эти действия зависят от того, как включен клиент: [*public Preview*](set-up-teams-admin-center.md#public-preview-tenants) или [ *Private Preview* (или бета-версия).](set-up-teams-admin-center.md#private-preview-tenants)</span><span class="sxs-lookup"><span data-stu-id="b5df6-106">These steps vary based on how the tenant is enabled:  [*Public Preview*](set-up-teams-admin-center.md#public-preview-tenants) or [*Private Preview* (or Beta)](set-up-teams-admin-center.md#private-preview-tenants).</span></span>

## <a name="public-preview-tenants"></a><span data-ttu-id="b5df6-107">Клиенты public Preview</span><span class="sxs-lookup"><span data-stu-id="b5df6-107">Public Preview tenants</span></span>

### <a name="administrator-steps-for-public-preview-tenants"></a><span data-ttu-id="b5df6-108">Действия администратора для клиентов public Preview</span><span class="sxs-lookup"><span data-stu-id="b5df6-108">Administrator steps for Public Preview tenants</span></span>

<span data-ttu-id="b5df6-109">Поскольку обучение Viva (Preview) еще не доступно, необходимы определенные действия, чтобы включить функции и установить разрешения для определенных пользователей или групп.</span><span class="sxs-lookup"><span data-stu-id="b5df6-109">Because the Viva Learning (Preview) is not yet generally available, certain steps are required to enable the features and set permissions for specific users or groups.</span></span> 

1. <span data-ttu-id="b5df6-110">Включить общедоступные функции предварительного просмотра для пользователей Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="b5df6-110">Enable Public Preview features for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="b5df6-111">а.</span><span class="sxs-lookup"><span data-stu-id="b5df6-111">a.</span></span> <span data-ttu-id="b5df6-112">Измените Teams обновления, чтобы включить функции public Preview.</span><span class="sxs-lookup"><span data-stu-id="b5df6-112">Modify Teams update policy to enable Public Preview features.</span></span> <span data-ttu-id="b5df6-113">Просмотреть [Microsoft Teams просмотра.](/microsoftteams/public-preview-doc-updates)</span><span class="sxs-lookup"><span data-stu-id="b5df6-113">See [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).</span></span>

    <span data-ttu-id="b5df6-114">б.</span><span class="sxs-lookup"><span data-stu-id="b5df6-114">b.</span></span> <span data-ttu-id="b5df6-115">Включить политику обновления для пользователей или групп, которые будут выполнять тестирование Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="b5df6-115">Enable the update policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="b5df6-116">См. [назначение политик пользователям и группам.](/microsoftteams/assign-policies-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="b5df6-116">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

2. <span data-ttu-id="b5df6-117">Измените политику разрешений приложений для пользователей Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="b5df6-117">Modify the app permission policy for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="b5df6-118">а.</span><span class="sxs-lookup"><span data-stu-id="b5df6-118">a.</span></span> <span data-ttu-id="b5df6-119">Если в настоящее время она не является частью глобальной политики, разрешить все приложения Майкрософт в политике разрешений приложений.</span><span class="sxs-lookup"><span data-stu-id="b5df6-119">Unless it's currently part of the global policy, allow all Microsoft apps in the app permission policy.</span></span> <span data-ttu-id="b5df6-120">Управление [политиками разрешений приложений см.](/microsoftteams/teams-app-permission-policies)в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b5df6-120">See [Manage app permission policies in Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span></span> 

    <span data-ttu-id="b5df6-121">б.</span><span class="sxs-lookup"><span data-stu-id="b5df6-121">b.</span></span> <span data-ttu-id="b5df6-122">Включить политику разрешений приложений для пользователей или групп, которые будут выполнять тестирование Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="b5df6-122">Enable the app permission policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="b5df6-123">См. [назначение политик пользователям и группам.](/microsoftteams/assign-policies-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="b5df6-123">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

3.  <span data-ttu-id="b5df6-124">Уведомите пользователей, которые будут тестировать Viva Learning (Preview), чтобы переключить их клиент [сборки](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants)на общедоступный предварительный просмотр для Teams .</span><span class="sxs-lookup"><span data-stu-id="b5df6-124">Notify users who will test Viva Learning (Preview) to [switch their build client to Public Preview for Teams](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5df6-125">Для клиентов предварительного просмотра Viva Learning (Preview)  не будет отображаться в управляемых приложениях в центре администрирования Teams до окончательного выпуска продукта.</span><span class="sxs-lookup"><span data-stu-id="b5df6-125">For Public Preview tenants, Viva Learning (Preview) will not be displayed in **Managed apps** in the Teams admin center until final product release.</span></span> <span data-ttu-id="b5df6-126">Однако пользователи с включенным общедоступным предварительным просмотром могут найти Viva Learning (Preview) в Teams магазине приложений и использовать его после того, как будут настроены правильные политики и разрешения.</span><span class="sxs-lookup"><span data-stu-id="b5df6-126">However, enabled Public Preview users can find Viva Learning (Preview) in the Teams app store and use it, once the correct policies and permissions have been set up.</span></span>

### <a name="user-steps-for-public-preview-tenants"></a><span data-ttu-id="b5df6-127">Действия пользователей для клиентов предварительного просмотра общего просмотра</span><span class="sxs-lookup"><span data-stu-id="b5df6-127">User steps for Public Preview tenants</span></span>

<span data-ttu-id="b5df6-128">Пользователям, которые были включены для тестирования общедоступных предварительных просмотров, [](/microsoftteams/public-preview-doc-updates#enable-public-preview) включив описанные ранее [политики,](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) необходимо перейти на общедоступный предварительный просмотр в Teams клиенте.</span><span class="sxs-lookup"><span data-stu-id="b5df6-128">Users who have been enabled for Public Preview testing — by enabling the [policies previously described](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) — need to [switch to Public Preview](/microsoftteams/public-preview-doc-updates#enable-public-preview) in their Teams client.</span></span>

1. <span data-ttu-id="b5df6-129">Пользователи должны выбрать свое изображение профиля > **о просмотре**  >  **общего просмотра**.</span><span class="sxs-lookup"><span data-stu-id="b5df6-129">Users must select their profile image > **About** > **Public Preview**.</span></span>
   
    ![Верхняя навигация в приложении Teams с профилем пользователя](../media/learning/learning-app-select-profile-teams.png)
    
2. <span data-ttu-id="b5df6-131">Пользователи должны принимать общедоступные условия предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="b5df6-131">Users must accept the Public Preview terms and conditions.</span></span>

    ![Переход на сборку общедоступных предварительных просмотров](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="b5df6-133">Теперь пользователи могут найти Viva Learning (Preview) в Teams и начать использовать его.</span><span class="sxs-lookup"><span data-stu-id="b5df6-133">Users can now find Viva Learning (Preview) in the Teams app store and start using it.</span></span>

## <a name="private-preview-tenants"></a><span data-ttu-id="b5df6-134">Частные клиенты предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="b5df6-134">Private Preview tenants</span></span>

### <a name="administrator-steps-for-private-preview-or-beta-tenants"></a><span data-ttu-id="b5df6-135">Действия администратора для частных клиентов предварительного просмотра (или бета-версии)</span><span class="sxs-lookup"><span data-stu-id="b5df6-135">Administrator steps for Private Preview (or Beta) tenants</span></span>

<span data-ttu-id="b5df6-136">Для частных клиентов предварительного просмотра дополнительные политики, которые необходимо включить, не требуется.</span><span class="sxs-lookup"><span data-stu-id="b5df6-136">For Private Preview tenants, there are no additional policies that need to be enabled.</span></span> <span data-ttu-id="b5df6-137">Однако viva Learning (Preview) должен быть доступен пользователям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b5df6-137">However, Viva Learning (Preview) must be made available for users in your organization.</span></span>

1. <span data-ttu-id="b5df6-138">В левой навигации центра администрирования Teams перейдите к Teams   >  **приложениям Управление приложениями.**</span><span class="sxs-lookup"><span data-stu-id="b5df6-138">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Левая навигация в центре администрирования Teams с Teams приложениями и разделом Управление приложениями.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="b5df6-140">На странице **Управление приложениями** в поле поиска введите *Viva Learning* и выберите **Viva Learning (Preview).**</span><span class="sxs-lookup"><span data-stu-id="b5df6-140">On the **Manage apps** page, in the search box, type *Viva Learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![Управление страницей приложений в центре администрирования Teams с полем поиска.](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="b5df6-142">На странице **Обучение Viva (Предварительный просмотр)** в статье **Состояние** выберите Разрешено включить Обучение Viva (Предварительная версия). </span><span class="sxs-lookup"><span data-stu-id="b5df6-142">On the **Viva Learning (Preview)** page, under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   ![Страница обучения в центре администрирования Teams разделе Параметры состояния и приложения.](../media/learning/learning-app-teams-learning-page.png)


<!---
The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.

1. For Viva Learning (Preview), you must first set the Update policy in Teams. For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).

    1. Sign in to the Teams admin center.

    2. Select **Teams** > **Update policies**.

    3. Select **Add**. 

    4. Name the update policy, add a policy, and turn on **Show preview features**.

2. The admin must notify users of the policy update so that they move their build into the Public Preview for Teams. 

    1. Users must select their profile image > **About** > **Public Preview**.
   
        ![Upper navigation in the Teams application showing user's profile](../media/learning/learning-app-select-profile-teams.png)
    
    2. Users must accept the **Public preview** terms and conditions.

        ![Switch to public preview build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.

## Manage settings for Viva Learning (Preview)

You must be an administrator in the Teams admin center to perform these tasks.

To make Viva Learning (Preview) available for users in your organization, follow these steps:

1. In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.

   ![Left navigation in the Teams admin center showing Teams apps and Manage apps section.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.

   ![Manage apps page in the Teams admin center showing the search box.](../media/learning/learning-app-teams-manage-apps-page.png)

3. On the **Viva Learning (Preview)** page:

   1. Under **Status**, select **Allowed** to turn on Viva Learning (Preview).

   2. On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).

   ![Learning page in the Teams admin center showing Status and App settings section.](../media/learning/learning-app-teams-learning-page.png)

4. After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.

> [!NOTE]
>  If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview). <br><br>As part of the preview, Viva Learning (Preview) is released in Ring 3.0. If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page. To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users. <br><br>   ![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)

--->

## <a name="next-step"></a><span data-ttu-id="b5df6-144">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="b5df6-144">Next step</span></span>

[<span data-ttu-id="b5df6-145">Настройка источников обучающего контента для Viva Learning (Preview) в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b5df6-145">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
