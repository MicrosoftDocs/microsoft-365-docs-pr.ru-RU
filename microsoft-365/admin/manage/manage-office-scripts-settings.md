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
description: Узнайте, как управлять настройками сценариев Office для пользователей в организации.
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058427"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="7d258-103">Управление параметрами сценариев Office</span><span class="sxs-lookup"><span data-stu-id="7d258-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="7d258-104">Сценарии Office позволяют пользователям автоматизировать задачи, записывая, редактывая и запуская сценарии в Excel в Интернете.</span><span class="sxs-lookup"><span data-stu-id="7d258-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="7d258-105">Сценарии Office работают с Power Automate, а пользователи запускают сценарии в книгах с помощью соединители Excel Online (для бизнеса).</span><span class="sxs-lookup"><span data-stu-id="7d258-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="7d258-106">Администраторы Microsoft 365 могут управлять настройками сценариев Office в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d258-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7d258-107">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="7d258-107">Before you begin</span></span>

- <span data-ttu-id="7d258-108">Для управления настройками сценариев Office необходимо быть глобальным администратором. Дополнительные сведения см. [в сведениях о ролях администраторов.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="7d258-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="7d258-109">Убедитесь, что у пользователей в вашей организации есть действующая лицензия на коммерческий план Microsoft 365 или Office 365 или план для EDU, который включает доступ к классическим приложениям Office, например одному из следующих планов:</span><span class="sxs-lookup"><span data-stu-id="7d258-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="7d258-110">Microsoft 365 бизнес стандарт</span><span class="sxs-lookup"><span data-stu-id="7d258-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="7d258-111">Приложения Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7d258-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="7d258-112">Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="7d258-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="7d258-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="7d258-113">Office 365 E3</span></span>
    - <span data-ttu-id="7d258-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="7d258-114">Office 365 E5</span></span>
    - <span data-ttu-id="7d258-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="7d258-115">Office 365 A3</span></span>
    - <span data-ttu-id="7d258-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="7d258-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="7d258-117">Управление доступностью сценариев Office и совместное использование сценариев</span><span class="sxs-lookup"><span data-stu-id="7d258-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="7d258-118">В Центре администрирования Microsoft 365  перейдите на вкладку "Службы \> **параметров** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank"></a> организации".</span><span class="sxs-lookup"><span data-stu-id="7d258-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="7d258-119">Выберите **сценарии Office.**</span><span class="sxs-lookup"><span data-stu-id="7d258-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="7d258-120">Сценарии Office по умолчанию включены, и все в вашей организации могут получать доступ к этим сценариям и использовать их.</span><span class="sxs-lookup"><span data-stu-id="7d258-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="7d258-121">Чтобы отключить сценарии Office для вашей организации, сверните для пользователей возможность автоматизировать свои задачи **в Excel в** Интернете.</span><span class="sxs-lookup"><span data-stu-id="7d258-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="7d258-122">Если вы ранее отключили сценарии Office для своей организации и хотите включить их, выберите "Позволить пользователям автоматизировать свои задачи в **Excel** в Интернете", а затем укажите, кто может получить доступ к этой функции и использовать ее:</span><span class="sxs-lookup"><span data-stu-id="7d258-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="7d258-123">Чтобы разрешить всем пользователям в организации доступ к сценариям Office и использовать их, оставьте выбранным "Все" **(по** умолчанию).</span><span class="sxs-lookup"><span data-stu-id="7d258-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="7d258-124">Чтобы разрешить доступ и использование сценариев Office только участникам определенной группы, выберите "Определенная группа" и введите имя или псевдоним электронной почты группы, чтобы добавить ее в список.</span><span class="sxs-lookup"><span data-stu-id="7d258-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="7d258-125">В список разрешается добавить только одну группу, которая должна иметь один из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="7d258-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="7d258-126">Группа Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d258-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="7d258-127">Группа рассылки.</span><span class="sxs-lookup"><span data-stu-id="7d258-127">Distribution group</span></span>
        - <span data-ttu-id="7d258-128">Группа безопасности</span><span class="sxs-lookup"><span data-stu-id="7d258-128">Security group</span></span>
        - <span data-ttu-id="7d258-129">Группа безопасности с поддержкой электронной почты</span><span class="sxs-lookup"><span data-stu-id="7d258-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="7d258-130">Дополнительные данные о различных типах групп см. в этой [теме.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="7d258-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="7d258-131">Чтобы разрешить пользователям с доступом к сценариям Office делиться своими сценариями с другими пользователями в организации, выберите "Разрешить пользователям с доступом к сценариям Office делиться своими сценариями с другими пользователями в **организации".**</span><span class="sxs-lookup"><span data-stu-id="7d258-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="7d258-132">Совместное использование сценариев за пределами организации запрещено.</span><span class="sxs-lookup"><span data-stu-id="7d258-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="7d258-133">Если позже вы отключите общий доступ к сценариям для вашей организации, пользователи смогут запускать ранее общие сценарии.</span><span class="sxs-lookup"><span data-stu-id="7d258-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="7d258-134">Укажите, какие пользователи с доступом к скриптам Office могут делиться своими сценариями:</span><span class="sxs-lookup"><span data-stu-id="7d258-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="7d258-135">Чтобы разрешить всем пользователям с доступом к сценариям Office делиться своими сценариями, оставьте выбранным "Все" **(по** умолчанию).</span><span class="sxs-lookup"><span data-stu-id="7d258-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="7d258-136">Чтобы разрешить только участникам определенной группы с доступом к скриптам Office делиться своими сценариями, выберите "Определенная группа" и введите имя или псевдоним электронной почты группы, чтобы добавить его в список запрещенных. </span><span class="sxs-lookup"><span data-stu-id="7d258-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="7d258-137">В список разрешается добавить только одну группу, которая должна иметь один из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="7d258-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="7d258-138">Группа Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d258-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="7d258-139">Группа рассылки.</span><span class="sxs-lookup"><span data-stu-id="7d258-139">Distribution group</span></span>
        - <span data-ttu-id="7d258-140">Группа безопасности</span><span class="sxs-lookup"><span data-stu-id="7d258-140">Security group</span></span>
        - <span data-ttu-id="7d258-141">Группа безопасности с поддержкой электронной почты</span><span class="sxs-lookup"><span data-stu-id="7d258-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="7d258-142">Дополнительные данные о различных типах групп см. в этой [теме.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="7d258-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="7d258-143">Чтобы разрешить пользователям запускать сценарии Office в потоках Power Automate, выберите "Разрешить пользователям с доступом к сценариям Office запускать свои сценарии с помощью **Power Automate".**</span><span class="sxs-lookup"><span data-stu-id="7d258-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="7d258-144">Это позволяет пользователям добавлять действия потока с помощью сценария запуска соединителю [Excel Online (business).](/connectors/excelonlinebusiness) </span><span class="sxs-lookup"><span data-stu-id="7d258-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="7d258-145">Чтобы разрешить всем пользователям с доступом к сценариям Office использовать свои сценарии в потоках, оставьте выбранным "Все" **(по** умолчанию).</span><span class="sxs-lookup"><span data-stu-id="7d258-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="7d258-146">Чтобы разрешить только членам определенной группы с доступом к сценариям Office использовать свои сценарии в потоках, выберите "Определенная группа" и введите имя или псевдоним электронной почты группы, чтобы добавить его в список разрешаний.</span><span class="sxs-lookup"><span data-stu-id="7d258-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="7d258-147">В список разрешается добавить только одну группу, которая должна иметь один из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="7d258-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="7d258-148">Группа Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d258-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="7d258-149">Группа рассылки.</span><span class="sxs-lookup"><span data-stu-id="7d258-149">Distribution group</span></span>
        - <span data-ttu-id="7d258-150">Группа безопасности</span><span class="sxs-lookup"><span data-stu-id="7d258-150">Security group</span></span>
        - <span data-ttu-id="7d258-151">Группа безопасности с поддержкой электронной почты</span><span class="sxs-lookup"><span data-stu-id="7d258-151">Mail-enabled security group</span></span>

        <span data-ttu-id="7d258-152">Дополнительные данные о различных типах групп см. в этой [теме.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="7d258-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="7d258-153">Дополнительные сведения об использовании сценариев Office с Power Automate, включая влияние политик защиты от потери данных, см. в под управлением сценариев Office с [помощью Power Automate.](/office/dev/scripts/develop/power-automate-integration)</span><span class="sxs-lookup"><span data-stu-id="7d258-153">To learn more about using Office Scripts with Power Automate, including how your data loss prevention policies may be impacted, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="7d258-154">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7d258-154">Select **Save**.</span></span>

    <span data-ttu-id="7d258-155">Изменение параметров сценариев Office может занять до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="7d258-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7d258-156">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="7d258-156">Next steps</span></span>

<span data-ttu-id="7d258-157">Так как сценарии Office работают вместе с Power Automate, мы рекомендуем вам просмотреть существующие политики защиты от потери данных (DLP), чтобы убедиться, что данные вашей организации остаются защищенными, пока пользователи используют сценарии Office.</span><span class="sxs-lookup"><span data-stu-id="7d258-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="7d258-158">Дополнительные сведения см. в политиках защиты от потери [данных (DLP).](/power-automate/prevent-data-loss)</span><span class="sxs-lookup"><span data-stu-id="7d258-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="7d258-159">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="7d258-159">Related content</span></span>

<span data-ttu-id="7d258-160">[Техническая документация по сценариям Office](/office/dev/scripts/) (страница ссылки)</span><span class="sxs-lookup"><span data-stu-id="7d258-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="7d258-161">[Введение в сценарии Office в Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (статья)</span><span class="sxs-lookup"><span data-stu-id="7d258-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="7d258-162">[Общий доступ к сценариям Office в Excel для Интернета](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (статья)</span><span class="sxs-lookup"><span data-stu-id="7d258-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="7d258-163">[Запись, редактирование и создание сценариев Office в Excel в Интернете](/office/dev/scripts/tutorials/excel-tutorial) (статья)</span><span class="sxs-lookup"><span data-stu-id="7d258-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
