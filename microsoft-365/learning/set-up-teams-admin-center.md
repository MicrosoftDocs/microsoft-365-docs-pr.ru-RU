---
title: Настройка microsoft Viva Learning (Preview) в центре администрирования Teams
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
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
ms.openlocfilehash: e5af676752064738e26f9b934a60973cb9b0200d
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625313"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="cb197-103">Настройка microsoft Viva Learning (Preview) в центре администрирования Teams</span><span class="sxs-lookup"><span data-stu-id="cb197-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="cb197-104">Сведения в этой статье относятся к продукту предварительного просмотра, который может быть существенно изменен до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="cb197-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="cb197-105">Администратор Teams Viva Learning (Preview) и применяет политики разрешений Teams центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="cb197-105">The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.</span></span>

1. <span data-ttu-id="cb197-106">Для просмотра общего просмотра сначала необходимо установить политику обновления.</span><span class="sxs-lookup"><span data-stu-id="cb197-106">For Public Preview, you must first set the Update policy.</span></span> <span data-ttu-id="cb197-107">Дополнительные сведения см. в Teams [веб-Microsoft Teams Public Preview.](/MicrosoftTeams/public-preview-doc-updates)</span><span class="sxs-lookup"><span data-stu-id="cb197-107">For more details, see the Teams site [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).</span></span>

    1. <span data-ttu-id="cb197-108">Во входе в Teams центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="cb197-108">Sign in to the Teams admin center.</span></span>

    2. <span data-ttu-id="cb197-109">Выберите **Teams**  >  **обновления**.</span><span class="sxs-lookup"><span data-stu-id="cb197-109">Select **Teams** > **Update policies**.</span></span>

    3. <span data-ttu-id="cb197-110">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="cb197-110">Select **Add**.</span></span> 

    4. <span data-ttu-id="cb197-111">Назови политику обновления, добавьте политику и включите **функции предварительного просмотра show.**</span><span class="sxs-lookup"><span data-stu-id="cb197-111">Name the update policy, add a policy, and turn on **Show preview features**.</span></span>

2. <span data-ttu-id="cb197-112">Администратор должен уведомить пользователей об обновлении политики, чтобы они перемещали сборку в общедоступный предварительный просмотр для Teams.</span><span class="sxs-lookup"><span data-stu-id="cb197-112">The admin must notify users of the policy update so that they move their build into Public Preview for Teams.</span></span> 

    1. <span data-ttu-id="cb197-113">Пользователь должен выбрать свое изображение профиля > о --> просмотр.</span><span class="sxs-lookup"><span data-stu-id="cb197-113">User must select their profile image --> About --> Public Preview.</span></span>
   
        ![Верхняя навигация в приложении Teams с профилем пользователя](../media/learning/learning-app-select-profile-teams.png)
    
    2. <span data-ttu-id="cb197-115">Пользователь должен принять условия общедоступных предварительных просмотров.</span><span class="sxs-lookup"><span data-stu-id="cb197-115">User must accept terms of Public Preview.</span></span>

        ![Переход на сборку общедоступных предварительных просмотров](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="cb197-117">Организации, которые имеют ограничительные политики и должны включить Viva Learning, выполните этот процесс в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="cb197-117">For organizations that have restrictive policies and need to enable Viva Learning, follow the process in the next section.</span></span>

## <a name="manage-settings-for-viva-learning-preview"></a><span data-ttu-id="cb197-118">Управление настройками для обучения Viva (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="cb197-118">Manage settings for Viva Learning (Preview)</span></span>

<span data-ttu-id="cb197-119">Для выполнения этих задач необходимо быть администратором Teams центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="cb197-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="cb197-120">Чтобы сделать Viva Learning (Preview) доступной для пользователей в организации, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cb197-120">To make Viva Learning (Preview) available for users in your organization, follow these steps:</span></span>

1. <span data-ttu-id="cb197-121">В левой навигации центра администрирования Teams перейдите к Teams   >  **приложениям Управление приложениями.**</span><span class="sxs-lookup"><span data-stu-id="cb197-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Левая навигация в центре администрирования Teams с Teams приложениями и разделом Управление приложениями.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="cb197-123">На странице **Управление приложениями** в поле поиска введите *обучение Viva* и выберите **Viva Learning (Preview).**</span><span class="sxs-lookup"><span data-stu-id="cb197-123">On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![Управление страницей приложений в центре администрирования Teams с полем поиска.](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="cb197-125">На странице **Обучение Viva (Предварительный просмотр):**</span><span class="sxs-lookup"><span data-stu-id="cb197-125">On the **Viva Learning (Preview)** page:</span></span>

   1. <span data-ttu-id="cb197-126">В **статье Состояние** выберите **Разрешено** включить Обучение Viva (Предварительная версия).</span><span class="sxs-lookup"><span data-stu-id="cb197-126">Under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   2. <span data-ttu-id="cb197-127">На **вкладке Параметры** в настройках **Приложения** перейдите в центр администрирования Microsoft 365 для настройки источников контента [для обучения.](content-sources-365-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="cb197-127">On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).</span></span>

   ![Страница обучения в центре администрирования Teams разделе Параметры состояния и приложения.](../media/learning/learning-app-teams-learning-page.png)

4. <span data-ttu-id="cb197-129">После **управления настройками** приложений  перейдите  к политикам разрешений и политикам установки, чтобы предоставить разрешения сотрудникам, которые должны иметь доступ к viva Learning (Preview) в рамках участия вашей организации в предварительном просмотре.</span><span class="sxs-lookup"><span data-stu-id="cb197-129">After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="cb197-130">Если ваша организация находится в кольце 4.0 в рамках Teams TAP100, может потребоваться включить утвержденных пользователей в Ring 3.0 для доступа к Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="cb197-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview).</span></span> <br><br><span data-ttu-id="cb197-131">В рамках предварительного просмотра в Ring 3.0 выпущена версия Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="cb197-131">As part of the preview, Viva Learning (Preview) is released in Ring 3.0.</span></span> <span data-ttu-id="cb197-132">Если ваша организация находится в кольце 4.0, вы не увидите Viva Learning (Preview) на странице **Управление приложениями.**</span><span class="sxs-lookup"><span data-stu-id="cb197-132">If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page.</span></span> <span data-ttu-id="cb197-133">Чтобы протестировать приложение, необходимо создать настраиваемую политику разрешений приложений, задать ее для всех приложений **и** назначить ее утвержденным пользователям Ring 3.0.</span><span class="sxs-lookup"><span data-stu-id="cb197-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span> <br><br>   <span data-ttu-id="cb197-134">![Страница TAP-AppsPermission-Plcy с указанием разрешить все выбранные приложения.](../media/learning/learning-app-tap-appspermission-plcy.png)</span><span class="sxs-lookup"><span data-stu-id="cb197-134">![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)</span></span>

## <a name="next-step"></a><span data-ttu-id="cb197-135">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="cb197-135">Next step</span></span>

[<span data-ttu-id="cb197-136">Настройка источников обучающего контента для Viva Learning (Preview) в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb197-136">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
