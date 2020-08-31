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
description: Узнайте, как управлять параметрами сценариев Office для пользователей в Организации.
ms.openlocfilehash: 12a80f277f6d17a8e7f5228f6948e70b7a93be11
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300841"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="834bf-103">Управление параметрами сценариев Office</span><span class="sxs-lookup"><span data-stu-id="834bf-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="834bf-104">Сценарии Office позволяют пользователям автоматизировать задачи, записывая, редактируя и запуская скрипты в Excel в Интернете.</span><span class="sxs-lookup"><span data-stu-id="834bf-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="834bf-105">Сценарии Office работают с автоматизацией управления питанием, а пользователи выполняют сценарии с книгами с помощью соединителя Excel Online (Business).</span><span class="sxs-lookup"><span data-stu-id="834bf-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="834bf-106">Администраторы Microsoft 365 могут управлять параметрами сценариев Office в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="834bf-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="834bf-107">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="834bf-107">Before you begin</span></span>

- <span data-ttu-id="834bf-108">Для управления параметрами сценариев Office необходимо быть глобальным администратором. Более подробную информацию можно узнать в статье [сведения о ролях администратора](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="834bf-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="834bf-109">Убедитесь, что у пользователей в вашей организации есть действительная лицензия на Microsoft 365 или Office 365 Профессиональная или EDU, которая включает доступ к классическим приложениям Office, таким как один из следующих планов:</span><span class="sxs-lookup"><span data-stu-id="834bf-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="834bf-110">Microsoft 365 бизнес стандарт</span><span class="sxs-lookup"><span data-stu-id="834bf-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="834bf-111">Приложения Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="834bf-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="834bf-112">Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="834bf-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="834bf-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="834bf-113">Office 365 E3</span></span>
    - <span data-ttu-id="834bf-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="834bf-114">Office 365 E5</span></span>
    - <span data-ttu-id="834bf-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="834bf-115">Office 365 A3</span></span>
    - <span data-ttu-id="834bf-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="834bf-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="834bf-117">Управление доступом к сценариям Office и совместному использованию сценариев</span><span class="sxs-lookup"><span data-stu-id="834bf-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="834bf-118">В центре администрирования Microsoft 365 **перейдите на** \> вкладку службы **параметров Организации** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> .</span><span class="sxs-lookup"><span data-stu-id="834bf-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="834bf-119">Выберите пункт **сценарии Office**.</span><span class="sxs-lookup"><span data-stu-id="834bf-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="834bf-120">Сценарии Office включены по умолчанию, а все в организации могут использовать эту функцию и совместно использовать сценарии.</span><span class="sxs-lookup"><span data-stu-id="834bf-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="834bf-121">Чтобы отключить сценарии Office для Организации, снимите флажок **Разрешить пользователям автоматизировать свои задачи в Excel в Интернете** .</span><span class="sxs-lookup"><span data-stu-id="834bf-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="834bf-122">Если вы ранее отключили сценарии Office для Организации и хотите включить его снова, выберите **Разрешить пользователям автоматизировать свои задачи в Excel в Интернете**, а затем укажите, кто может использовать эту функцию:</span><span class="sxs-lookup"><span data-stu-id="834bf-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="834bf-123">Чтобы разрешить всем пользователям в организации доступ к сценариям Office и использовать их, оставьте **все** (по умолчанию) выбранным.</span><span class="sxs-lookup"><span data-stu-id="834bf-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span> 

    - <span data-ttu-id="834bf-124">Чтобы разрешить доступ и использование скриптов Office только членам определенной группы, выберите **определенная группа**, а затем введите имя или псевдоним электронной почты группы, чтобы добавить ее в список разрешений.</span><span class="sxs-lookup"><span data-stu-id="834bf-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="834bf-125">Вы можете добавить только одну группу в список разрешений, а также один из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="834bf-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="834bf-126">Группа Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="834bf-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="834bf-127">Группа рассылки.</span><span class="sxs-lookup"><span data-stu-id="834bf-127">Distribution group</span></span>
        - <span data-ttu-id="834bf-128">Группа безопасности</span><span class="sxs-lookup"><span data-stu-id="834bf-128">Security group</span></span>
        - <span data-ttu-id="834bf-129">Группа безопасности с поддержкой электронной почты</span><span class="sxs-lookup"><span data-stu-id="834bf-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="834bf-130">Дополнительные сведения о различных типах групп приведены в разделе [Сравнение групп](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="834bf-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="834bf-131">Чтобы предоставить пользователям доступ к сценариям Office для совместного использования своих сценариев с другими сотрудниками Организации, установите флажок **Разрешить пользователям с доступом к сценариям Office совместно использовать свои сценарии с другими пользователями в Организации**.</span><span class="sxs-lookup"><span data-stu-id="834bf-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="834bf-132">Сценарии общего доступа вне Организации не разрешены.</span><span class="sxs-lookup"><span data-stu-id="834bf-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="834bf-133">Если позже вы отключите общий доступ к сценариям для вашей организации, пользователи по-прежнему смогут выполнять сценарии, для которых вы выполняли ранее общие сценарии.</span><span class="sxs-lookup"><span data-stu-id="834bf-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="834bf-134">Укажите, каким пользователям с доступом к сценариям Office могут обмениваться свои сценарии:</span><span class="sxs-lookup"><span data-stu-id="834bf-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="834bf-135">Чтобы разрешить всем пользователям, у которых есть доступ к сценариям Office, совместно использовать свои сценарии, оставьте **все** (по умолчанию) выбранным.</span><span class="sxs-lookup"><span data-stu-id="834bf-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="834bf-136">Чтобы разрешить доступ к сценариям только членам определенной группы, имеющими доступ к сценариям Office, выберите **определенную группу**, а затем введите имя или псевдоним электронной почты группы, чтобы добавить ее в список разрешений.</span><span class="sxs-lookup"><span data-stu-id="834bf-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="834bf-137">Вы можете добавить только одну группу в список разрешений, а также один из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="834bf-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="834bf-138">Группа Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="834bf-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="834bf-139">Группа рассылки.</span><span class="sxs-lookup"><span data-stu-id="834bf-139">Distribution group</span></span>
        - <span data-ttu-id="834bf-140">Группа безопасности</span><span class="sxs-lookup"><span data-stu-id="834bf-140">Security group</span></span>
        - <span data-ttu-id="834bf-141">Группа безопасности с поддержкой электронной почты</span><span class="sxs-lookup"><span data-stu-id="834bf-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="834bf-142">Дополнительные сведения о различных типах групп приведены в разделе [Сравнение групп](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="834bf-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="834bf-143">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="834bf-143">Select **Save**.</span></span>

    <span data-ttu-id="834bf-144">Чтобы изменения параметров сценариев Office вступили в силу, может потребоваться до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="834bf-144">It can take up to 48 hours for changes to Office Script settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="834bf-145">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="834bf-145">Next steps</span></span>

<span data-ttu-id="834bf-146">Так как сценарии Office работают с автоматизированной автоматизацией, рекомендуется проанализировать существующие политики защиты от потери данных (DLP), чтобы обеспечить защиту данных вашей организации, пока пользователи используют сценарии Office.</span><span class="sxs-lookup"><span data-stu-id="834bf-146">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="834bf-147">Более подробную информацию можно узнать в статье [политики защиты от потери данных (DLP)](/power-automate/prevent-data-loss).</span><span class="sxs-lookup"><span data-stu-id="834bf-147">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="834bf-148">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="834bf-148">Related content</span></span>

<span data-ttu-id="834bf-149">[Техническая документация по сценариям Office](/office/dev/scripts/) (страница ссылки) </span><span class="sxs-lookup"><span data-stu-id="834bf-149">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="834bf-150">[Общие сведения о сценариях Office в Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (статья) </span><span class="sxs-lookup"><span data-stu-id="834bf-150">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="834bf-151">[Совместное использование сценариев Office в Excel для Интернета](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (статья) </span><span class="sxs-lookup"><span data-stu-id="834bf-151">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="834bf-152">[Запись, редактирование и создание сценариев Office в Excel в Интернете](/office/dev/scripts/tutorials/excel-tutorial) (статья)</span><span class="sxs-lookup"><span data-stu-id="834bf-152">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>