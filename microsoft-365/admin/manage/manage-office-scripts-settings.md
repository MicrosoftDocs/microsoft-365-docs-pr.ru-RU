---
title: Управление параметрами сценариев Office
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Узнайте, как управлять Office скриптами для пользователей в вашей организации.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572313"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="7ad2e-103">Управление параметрами сценариев Office</span><span class="sxs-lookup"><span data-stu-id="7ad2e-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="7ad2e-104">[Office скрипты](/office/dev/scripts)позволяет пользователям автоматизировать задачи, записывая, редактируя и запуская скрипты в Excel в Интернете.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-104">[Office Scripts](/office/dev/scripts)‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="7ad2e-105">Office Скрипты работают с Power Automate, и пользователи заходят в рабочие книги с помощью разъема Excel Online (Business).</span><span class="sxs-lookup"><span data-stu-id="7ad2e-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="7ad2e-106">Microsoft 365 администраторы могут управлять Office скриптами из Microsoft 365 центра.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7ad2e-107">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="7ad2e-107">Before you begin</span></span>

- <span data-ttu-id="7ad2e-108">Для управления Office скриптов необходимо быть глобальным администратором. Для получения дополнительной информации [см.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="7ad2e-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="7ad2e-109">Убедитесь, что пользователи в вашей организации имеют действительную лицензию на Microsoft 365 или Office 365 коммерческий или EDU план, который включает в себя доступ к настольным приложениям Office, например, один из следующих планов:</span><span class="sxs-lookup"><span data-stu-id="7ad2e-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="7ad2e-110">Microsoft 365 бизнес стандарт</span><span class="sxs-lookup"><span data-stu-id="7ad2e-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="7ad2e-111">Приложения Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7ad2e-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="7ad2e-112">Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="7ad2e-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="7ad2e-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="7ad2e-113">Office 365 E3</span></span>
    - <span data-ttu-id="7ad2e-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="7ad2e-114">Office 365 E5</span></span>
    - <span data-ttu-id="7ad2e-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="7ad2e-115">Office 365 A3</span></span>
    - <span data-ttu-id="7ad2e-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="7ad2e-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="7ad2e-117">Управление доступностью Office скриптов и совместное использование скриптов</span><span class="sxs-lookup"><span data-stu-id="7ad2e-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="7ad2e-118">В Microsoft 365 администратора перейдите на вкладку **Параметры** \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">org.</a></span><span class="sxs-lookup"><span data-stu-id="7ad2e-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="7ad2e-119">Выберите **Office скрипты**.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="7ad2e-120">Office Сценарии включены по умолчанию, и каждый в вашей организации может получить доступ и использовать функцию и обмениваться сценариями.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="7ad2e-121">Чтобы отключить Office скрипты для вашей организации, **очистите от позволяйте пользователям автоматизировать свои задачи Excel в Интернете поле.**</span><span class="sxs-lookup"><span data-stu-id="7ad2e-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="7ad2e-122">Если вы ранее выключили Office Scripts для вашей организации и хотите включить его обратно, выберите **Пусть пользователи автоматизируют свои задачи в Excel в Интернете** году, а затем указать, кто может получить доступ и использовать эту функцию:</span><span class="sxs-lookup"><span data-stu-id="7ad2e-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="7ad2e-123">Чтобы разрешить всем пользователям в вашей организации доступ и использование Office скриптов, оставьте **все** (по умолчанию) выбраны.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="7ad2e-124">Чтобы разрешить доступ и использование скриптов Office только членам определенной группы, выберите **конкретную группу,** а затем введите псевдоним имени или электронной почты группы, чтобы добавить его в список допустимых.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="7ad2e-125">Вы можете добавить только одну группу в список допустимых, и она должна быть одним из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="7ad2e-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="7ad2e-126">Microsoft 365 группа</span><span class="sxs-lookup"><span data-stu-id="7ad2e-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="7ad2e-127">Группа рассылки.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-127">Distribution group</span></span>
        - <span data-ttu-id="7ad2e-128">Группа безопасности</span><span class="sxs-lookup"><span data-stu-id="7ad2e-128">Security group</span></span>
        - <span data-ttu-id="7ad2e-129">Группа безопасности с поддержкой электронной почты</span><span class="sxs-lookup"><span data-stu-id="7ad2e-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="7ad2e-130">Чтобы узнать больше о различных типах групп, см [Сравните группы](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="7ad2e-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="7ad2e-131">Чтобы пользователи, у которого есть доступ к скриптам Office, поделиться своими скриптами с другими пользователями вашей организации, выберите Let users с **доступом к Office Scripts, чтобы поделиться своими скриптами с другими в организации.**</span><span class="sxs-lookup"><span data-stu-id="7ad2e-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="7ad2e-132">Обмен скриптами за пределами организации не допускается.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="7ad2e-133">Если позже вы выключите совместное использование скриптов для вашей организации, пользователи все равно смогут запускать ранее совместно общие скрипты.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="7ad2e-134">Укажите, какие пользователи, Office скриптам, могут поделиться своими скриптами:</span><span class="sxs-lookup"><span data-stu-id="7ad2e-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="7ad2e-135">Чтобы все пользователи, у кого есть доступ Office скрипты, поделиться своими скриптами, **оставьте всех** (по умолчанию) выбранными.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="7ad2e-136">Разрешить только членам определенной группы, у которого есть доступ к скриптам Office, поделиться своими сценариями, **выберите конкретную** группу, а затем введите псевдоним имени или электронной почты группы, чтобы добавить его в список допустимых.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="7ad2e-137">Вы можете добавить только одну группу в список допустимых, и она должна быть одним из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="7ad2e-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="7ad2e-138">Microsoft 365 группа</span><span class="sxs-lookup"><span data-stu-id="7ad2e-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="7ad2e-139">Группа рассылки.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-139">Distribution group</span></span>
        - <span data-ttu-id="7ad2e-140">Группа безопасности</span><span class="sxs-lookup"><span data-stu-id="7ad2e-140">Security group</span></span>
        - <span data-ttu-id="7ad2e-141">Группа безопасности с поддержкой электронной почты</span><span class="sxs-lookup"><span data-stu-id="7ad2e-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="7ad2e-142">Чтобы узнать больше о различных типах групп, см [Сравните группы](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="7ad2e-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="7ad2e-143">Чтобы пользователи могут запускать свои Office скрипты внутри Power Automate потоков, **выберите Пусть пользователи с доступом к Office Скрипты** запустить свои скрипты с Power Automate .</span><span class="sxs-lookup"><span data-stu-id="7ad2e-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="7ad2e-144">Это позволяет пользователям добавлять шаги потока с [Excel (Бизнес) Разъем Run](/connectors/excelonlinebusiness) скрипт **вариант.**</span><span class="sxs-lookup"><span data-stu-id="7ad2e-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="7ad2e-145">Чтобы все пользователи, у кого есть Office скрипты, использовать свои скрипты в потоках, **оставьте всех** (по умолчанию) выбранными.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="7ad2e-146">Чтобы разрешить только членам определенной группы, у которого есть доступ к скриптам Office, использовать свои скрипты в потоках, **выберите конкретную группу,** а затем введите имя или псевдоним группы по электронной почте, чтобы добавить его в список допустимых.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="7ad2e-147">Вы можете добавить только одну группу в список допустимых, и она должна быть одним из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="7ad2e-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="7ad2e-148">Microsoft 365 группа</span><span class="sxs-lookup"><span data-stu-id="7ad2e-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="7ad2e-149">Группа рассылки.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-149">Distribution group</span></span>
        - <span data-ttu-id="7ad2e-150">Группа безопасности</span><span class="sxs-lookup"><span data-stu-id="7ad2e-150">Security group</span></span>
        - <span data-ttu-id="7ad2e-151">Группа безопасности с поддержкой электронной почты</span><span class="sxs-lookup"><span data-stu-id="7ad2e-151">Mail-enabled security group</span></span>

        <span data-ttu-id="7ad2e-152">Чтобы узнать больше о различных типах групп, см [Сравните группы](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="7ad2e-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="7ad2e-153">Чтобы узнать больше об использовании Office скриптов с Power Automate, [с Power Automate Office м.](/office/dev/scripts/develop/power-automate-integration)</span><span class="sxs-lookup"><span data-stu-id="7ad2e-153">To learn more about using Office Scripts with Power Automate, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="7ad2e-154">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-154">Select **Save**.</span></span>

    <span data-ttu-id="7ad2e-155">Изменение настроек скриптов может занять до 48 часов Office скриптов.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7ad2e-156">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="7ad2e-156">Next steps</span></span>

<span data-ttu-id="7ad2e-157">Поскольку Office Scripts работает с Power Automate, мы рекомендуем пересмотреть существующие политики предотвращения потери данных (DLP), чтобы обеспечить защиту данных организации в то время как пользователи используют Office скрипты.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="7ad2e-158">Для получения дополнительной информации [см.](/power-automate/prevent-data-loss)</span><span class="sxs-lookup"><span data-stu-id="7ad2e-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="7ad2e-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="7ad2e-159">Related content</span></span>

<span data-ttu-id="7ad2e-160">[Office сценариев (ссылка](/office/dev/scripts/) на страницу)</span><span class="sxs-lookup"><span data-stu-id="7ad2e-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)\</span></span>
<span data-ttu-id="7ad2e-161">[Введение в Office в Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (статья)</span><span class="sxs-lookup"><span data-stu-id="7ad2e-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)\</span></span>
<span data-ttu-id="7ad2e-162">[Обмен Office скриптами в Excel для Интернета](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (статья)</span><span class="sxs-lookup"><span data-stu-id="7ad2e-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)\</span></span>
<span data-ttu-id="7ad2e-163">[Запись, редактирование и создание Office скриптов в Excel в Интернете](/office/dev/scripts/tutorials/excel-tutorial) (статья)</span><span class="sxs-lookup"><span data-stu-id="7ad2e-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
