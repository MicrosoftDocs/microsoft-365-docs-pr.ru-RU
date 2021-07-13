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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid: MET150
description: Узнайте, как управлять Office скриптами для пользователей в организации.
ms.openlocfilehash: fea50838cf1089b73a6af5bbf86d490293831085
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392675"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="a2e4e-103">Управление параметрами сценариев Office</span><span class="sxs-lookup"><span data-stu-id="a2e4e-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="a2e4e-104">[Office скрипты](/office/dev/scripts)позволяют пользователям автоматизировать задачи путем записи, редактирования и запуска сценариев в Excel в Интернете.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-104">[Office Scripts](/office/dev/scripts)‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="a2e4e-105">Office Скрипты работают с Power Automate, а пользователи запускают сценарии в книгах с помощью соединиттеля Excel Online (Бизнес).</span><span class="sxs-lookup"><span data-stu-id="a2e4e-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="a2e4e-106">Microsoft 365 администраторы могут управлять Office скриптами из Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a2e4e-107">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="a2e4e-107">Before you begin</span></span>

- <span data-ttu-id="a2e4e-108">Чтобы управлять Office скриптами, необходимо быть глобальным администратором. Дополнительные сведения см. в [дополнительных сведениях о ролях администратора.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="a2e4e-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="a2e4e-109">Убедитесь, что пользователи в вашей организации имеют допустимую лицензию для коммерческого Microsoft 365 или Office 365 или плана EDU, который включает доступ к Office настольным приложениям, например одному из следующих планов:</span><span class="sxs-lookup"><span data-stu-id="a2e4e-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="a2e4e-110">Microsoft 365 бизнес стандарт</span><span class="sxs-lookup"><span data-stu-id="a2e4e-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="a2e4e-111">Приложения Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a2e4e-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="a2e4e-112">Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="a2e4e-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="a2e4e-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="a2e4e-113">Office 365 E3</span></span>
    - <span data-ttu-id="a2e4e-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="a2e4e-114">Office 365 E5</span></span>
    - <span data-ttu-id="a2e4e-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="a2e4e-115">Office 365 A3</span></span>
    - <span data-ttu-id="a2e4e-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="a2e4e-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="a2e4e-117">Управление доступностью Office скриптов и обменом скриптами</span><span class="sxs-lookup"><span data-stu-id="a2e4e-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="a2e4e-118">В Центр администрирования Microsoft 365 перейдите на **вкладку Параметры** \> **параметров Org.** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="a2e4e-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="a2e4e-119">Выберите **Office скрипты**.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="a2e4e-120">Office Скрипты включены по умолчанию, и каждый в вашей организации может получить доступ и использовать функции и совместно использовать скрипты.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="a2e4e-121">Чтобы отключить Office скрипты для вашей организации, упустите функцию Let **users automate their tasks in Excel в Интернете** check box.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="a2e4e-122">Если вы ранее отключили Office скрипты для организации и хотите включить его, выберите Дайте пользователям автоматизировать свои задачи в **Excel в Интернете,** а затем укажите, кто может получить доступ к этой функции и использовать ее:</span><span class="sxs-lookup"><span data-stu-id="a2e4e-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="a2e4e-123">Чтобы разрешить всем пользователям в вашей организации доступ к Office скриптам, выберите **все** (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="a2e4e-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="a2e4e-124">Чтобы разрешить доступ и использование скриптов Office только членам определенной группы, выберите конкретную **группу,** а затем введите псевдоним или псевдоним электронной почты группы, чтобы добавить его в список разрешаний.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="a2e4e-125">В список разрешаний может быть добавлена только одна группа, которая должна быть одним из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="a2e4e-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="a2e4e-126">Microsoft 365 группы</span><span class="sxs-lookup"><span data-stu-id="a2e4e-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="a2e4e-127">Группа рассылки.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-127">Distribution group</span></span>
        - <span data-ttu-id="a2e4e-128">Группа безопасности</span><span class="sxs-lookup"><span data-stu-id="a2e4e-128">Security group</span></span>
        - <span data-ttu-id="a2e4e-129">Группа безопасности с поддержкой электронной почты</span><span class="sxs-lookup"><span data-stu-id="a2e4e-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="a2e4e-130">Дополнительные дополнительные данные о различных типах групп см. в см. [в "Сравнение групп".](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="a2e4e-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="a2e4e-131">Чтобы разрешить пользователям с доступом к Office скриптам делиться своими скриптами с другими пользователями в организации, выберите Разрешить пользователям с доступом к Office Скрипты поделиться своими сценариями с другими в **организации**.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="a2e4e-132">Совместное использование скриптов за пределами организации запрещено.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="a2e4e-133">Если позже отключите общий доступ к скриптам для организации, пользователи смогут запускать ранее общие скрипты.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="a2e4e-134">Укажите, какие пользователи с доступом к Office скриптам могут делиться своими скриптами:</span><span class="sxs-lookup"><span data-stu-id="a2e4e-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="a2e4e-135">Чтобы разрешить всем пользователям с доступом к Office скриптам делиться своими скриптами, оставьте выбранным **Все** (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="a2e4e-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="a2e4e-136">Чтобы разрешить только членам определенной группы с доступом к Office скриптам делиться своими скриптами, выберите конкретную **группу,** а затем введите имя или псевдоним электронной почты группы, чтобы добавить его в список разрешаний.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="a2e4e-137">В список разрешаний может быть добавлена только одна группа, которая должна быть одним из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="a2e4e-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="a2e4e-138">Microsoft 365 группы</span><span class="sxs-lookup"><span data-stu-id="a2e4e-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="a2e4e-139">Группа рассылки.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-139">Distribution group</span></span>
        - <span data-ttu-id="a2e4e-140">Группа безопасности</span><span class="sxs-lookup"><span data-stu-id="a2e4e-140">Security group</span></span>
        - <span data-ttu-id="a2e4e-141">Группа безопасности с поддержкой электронной почты</span><span class="sxs-lookup"><span data-stu-id="a2e4e-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="a2e4e-142">Дополнительные дополнительные данные о различных типах групп см. в см. [в "Сравнение групп".](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="a2e4e-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="a2e4e-143">Чтобы разрешить пользователям запускать Office скрипты внутри потоков Power Automate, выберите Разрешить пользователям с доступом к Office Скрипты запускать свои **скрипты с Power Automate**.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="a2e4e-144">Это позволяет пользователям добавлять шаги потока с [помощью параметра сценарий запуска Excel Online (Business) Connector.](/connectors/excelonlinebusiness) </span><span class="sxs-lookup"><span data-stu-id="a2e4e-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="a2e4e-145">Чтобы разрешить всем пользователям с доступом к Office скриптам использовать свои скрипты в потоках, оставьте все **(по** умолчанию) выбраны.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="a2e4e-146">Чтобы разрешить только членам определенной группы с доступом к Office скриптам использовать свои скрипты в потоках, выберите конкретную группу, а затем введите имя или псевдоним электронной почты группы, чтобы добавить его в список разрешаний.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="a2e4e-147">В список разрешаний может быть добавлена только одна группа, которая должна быть одним из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="a2e4e-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="a2e4e-148">Microsoft 365 группы</span><span class="sxs-lookup"><span data-stu-id="a2e4e-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="a2e4e-149">Группа рассылки.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-149">Distribution group</span></span>
        - <span data-ttu-id="a2e4e-150">Группа безопасности</span><span class="sxs-lookup"><span data-stu-id="a2e4e-150">Security group</span></span>
        - <span data-ttu-id="a2e4e-151">Группа безопасности с поддержкой электронной почты</span><span class="sxs-lookup"><span data-stu-id="a2e4e-151">Mail-enabled security group</span></span>

        <span data-ttu-id="a2e4e-152">Дополнительные дополнительные данные о различных типах групп см. в см. [в "Сравнение групп".](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="a2e4e-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="a2e4e-153">Дополнительные новости об использовании Office с Power Automate см. в Office [Run Power Automate.](/office/dev/scripts/develop/power-automate-integration)</span><span class="sxs-lookup"><span data-stu-id="a2e4e-153">To learn more about using Office Scripts with Power Automate, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="a2e4e-154">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-154">Select **Save**.</span></span>

    <span data-ttu-id="a2e4e-155">Изменение параметров сценариев Office может занять до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a2e4e-156">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="a2e4e-156">Next steps</span></span>

<span data-ttu-id="a2e4e-157">Поскольку Office скрипты работают с Power Automate, рекомендуется просмотреть существующие политики предотвращения потери данных (DLP), чтобы обеспечить защиту данных организации во время использования пользователями Office скриптов.</span><span class="sxs-lookup"><span data-stu-id="a2e4e-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="a2e4e-158">Дополнительные сведения см. в статье [Политики защиты от потери данных (DLP)](/power-automate/prevent-data-loss).</span><span class="sxs-lookup"><span data-stu-id="a2e4e-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="a2e4e-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2e4e-159">Related content</span></span>

<span data-ttu-id="a2e4e-160">[Office Скрипты техническая документация](/office/dev/scripts/) (страница ссылки)</span><span class="sxs-lookup"><span data-stu-id="a2e4e-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="a2e4e-161">[Введение в Office скрипты в Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (статья)</span><span class="sxs-lookup"><span data-stu-id="a2e4e-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="a2e4e-162">[Обмен Office скриптами в Excel веб-страницы](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (статья)</span><span class="sxs-lookup"><span data-stu-id="a2e4e-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="a2e4e-163">[Запись, редактирование](/office/dev/scripts/tutorials/excel-tutorial) и создание Office в Excel в Интернете (статья)</span><span class="sxs-lookup"><span data-stu-id="a2e4e-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
