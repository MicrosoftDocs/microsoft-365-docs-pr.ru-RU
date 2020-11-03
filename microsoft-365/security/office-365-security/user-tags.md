---
title: Теги пользователя в защитнике Майкрософт для Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как определить определенные группы пользователей с помощью тегов пользователя в защитнике Майкрософт для Office 365 (план 2). Фильтрация тегов доступна для всех оповещений, отчетов и исследований в защитнике Майкрософт для Office 365, чтобы быстро определить пользователей с тегами.
ms.openlocfilehash: fcc13a04ed603712bb2a45ccaadbaf161702c502
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842884"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="7248e-104">Теги пользователя в защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="7248e-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="7248e-105">Функция "Теги пользователей" Предварительная версия, недоступна всем и может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="7248e-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="7248e-106">За сведениями о расписании выпуска, ознакомьтесь с [планом Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="7248e-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="7248e-107">Теги пользователя — это идентификаторы для определенных групп пользователей в [защитнике для Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="7248e-107">User tags are identifiers for specific groups of users in [Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="7248e-108">Существует два типа тегов пользователя:</span><span class="sxs-lookup"><span data-stu-id="7248e-108">There are two types of user tags:</span></span>

- <span data-ttu-id="7248e-109">**Системные теги** : в настоящее время [учетные записи приоритета](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) являются единственным типом системного тега.</span><span class="sxs-lookup"><span data-stu-id="7248e-109">**System tags** : Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="7248e-110">**Настраиваемые теги** : вы можете самостоятельно создавать эти теги.</span><span class="sxs-lookup"><span data-stu-id="7248e-110">**Custom tags** : You create these user tags yourself.</span></span>

<span data-ttu-id="7248e-111">Если в Организации есть защитник для Office 365 Plan 2 (включенный в вашу подписку или как надстройку), можно создать настраиваемые теги пользователя в дополнение к использованию тега приоритетов учетных записей.</span><span class="sxs-lookup"><span data-stu-id="7248e-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="7248e-112">После применения системных тегов или настраиваемых тегов к пользователям эти теги можно использовать как фильтры в оповещениях, отчетах и исследованиях.</span><span class="sxs-lookup"><span data-stu-id="7248e-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="7248e-113">Оповещения в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="7248e-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="7248e-114">Обозреватель угроз и обнаружение в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="7248e-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- <span data-ttu-id="7248e-115">[отчет о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report);</span><span class="sxs-lookup"><span data-stu-id="7248e-115">[Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="7248e-116">Представления кампании</span><span class="sxs-lookup"><span data-stu-id="7248e-116">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="7248e-117">В этой статье объясняется, как настроить Теги пользователя в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="7248e-117">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="7248e-118">В центре безопасности & нет командлетов для управления пользовательскими тегами.</span><span class="sxs-lookup"><span data-stu-id="7248e-118">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7248e-119">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="7248e-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7248e-120">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="7248e-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7248e-121">Чтобы перейти непосредственно к странице " **теги пользователей** ", откройте ее <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="7248e-121">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="7248e-122">Чтобы создать, изменить или удалить **настраиваемые теги пользователей** , необходимо быть членом группы ролей " **Управление организацией** " или " **администратор безопасности** " в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="7248e-122">To create, modify, or remove **custom user tags** , you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="7248e-123">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7248e-123">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="7248e-124">Чтобы настроить учетные записи приоритетов (системные теги), необходимо быть [глобальным администратором](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) или [администратором Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span><span class="sxs-lookup"><span data-stu-id="7248e-124">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="7248e-125">Вы также можете управлять учетными записями приоритетов и отслеживать их в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7248e-125">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7248e-126">Инструкции см в разделе [Управление учетными записями приоритетов](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="7248e-126">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="7248e-127">Использование центра обеспечения безопасности для создания тегов пользователя</span><span class="sxs-lookup"><span data-stu-id="7248e-127">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="7248e-128">В центре безопасности перейдите к разделу **Пользователи управления угрозами** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="7248e-128">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="7248e-129">На открывшейся странице " **теги пользователей** " нажмите кнопку **создать тег**.</span><span class="sxs-lookup"><span data-stu-id="7248e-129">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="7248e-130">Мастер **создания тегов** открывается в новом полете. На странице **определение тега** настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="7248e-130">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="7248e-131">**Name** : введите уникальное описательное имя тега.</span><span class="sxs-lookup"><span data-stu-id="7248e-131">**Name** : Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="7248e-132">Это значение, которое вы увидите и будете использовать.</span><span class="sxs-lookup"><span data-stu-id="7248e-132">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="7248e-133">**Описание** : введите необязательное описание для тега.</span><span class="sxs-lookup"><span data-stu-id="7248e-133">**Description** : Enter an optional description for the tag.</span></span>

   <span data-ttu-id="7248e-134">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7248e-134">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="7248e-135">На странице **назначить почтовые ящики** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="7248e-135">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="7248e-136">Нажмите кнопку **добавить почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="7248e-136">Click **Add mailboxes**.</span></span> <span data-ttu-id="7248e-137">В появившемся окне выполните одно из следующих действий, чтобы добавить отдельных пользователей или группы:</span><span class="sxs-lookup"><span data-stu-id="7248e-137">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="7248e-138">Щелкните поле и прокрутите список, чтобы выбрать пользователя или группу.</span><span class="sxs-lookup"><span data-stu-id="7248e-138">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="7248e-139">Щелкните поле и начните ввод текста, чтобы отфильтровать список и выбрать пользователя или группу.</span><span class="sxs-lookup"><span data-stu-id="7248e-139">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="7248e-140">Чтобы добавить дополнительные значения, щелкните пустую область в поле.</span><span class="sxs-lookup"><span data-stu-id="7248e-140">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="7248e-141">Чтобы удалить отдельные записи из поля, нажмите кнопку **Удалить** ![ значок "удалить ](../../media/scc-remove-icon.png) " в поле пользователя или группы.</span><span class="sxs-lookup"><span data-stu-id="7248e-141">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="7248e-142">Чтобы удалить существующие записи из списка под полем, нажмите кнопку **Удалить** ![ значок "удалить ](../../media/scc-remove-icon.png) ".</span><span class="sxs-lookup"><span data-stu-id="7248e-142">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="7248e-143">По завершении нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7248e-143">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="7248e-144">Нажмите кнопку **Импорт** , чтобы выбрать текстовый файл, содержащий адреса электронной почты пользователей или групп.</span><span class="sxs-lookup"><span data-stu-id="7248e-144">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="7248e-145">Убедитесь, что текстовый файл содержит одну запись в строке.</span><span class="sxs-lookup"><span data-stu-id="7248e-145">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="7248e-146">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7248e-146">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="7248e-147">На странице **тег рассмотрения** проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="7248e-147">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="7248e-148">Для внесения изменений можно нажать кнопку **изменить** в определенном разделе.</span><span class="sxs-lookup"><span data-stu-id="7248e-148">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="7248e-149">По завершении нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7248e-149">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="7248e-150">Использование центра обеспечения безопасности для просмотра тегов пользователей</span><span class="sxs-lookup"><span data-stu-id="7248e-150">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="7248e-151">В центре безопасности перейдите к разделу **Пользователи управления угрозами** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="7248e-151">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="7248e-152">На открывшейся странице " **теги пользователей** " выберите тег пользователя, который нужно просмотреть (не щелкая флажок).</span><span class="sxs-lookup"><span data-stu-id="7248e-152">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="7248e-153">При выпадающем на экран сведений, предназначенных только для чтения, проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="7248e-153">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="7248e-154">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7248e-154">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="7248e-155">Использование центра обеспечения безопасности для изменения тегов пользователя</span><span class="sxs-lookup"><span data-stu-id="7248e-155">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="7248e-156">В центре безопасности перейдите к разделу **Пользователи управления угрозами** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="7248e-156">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="7248e-157">На открывшейся странице " **теги пользователей** " выберите тег пользователя, который нужно просмотреть, и нажмите кнопку **изменить тег**.</span><span class="sxs-lookup"><span data-stu-id="7248e-157">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="7248e-158">Мастер политики откроется в **теге редактирования** . Нажмите кнопку **Далее** , чтобы просмотреть и изменить параметры.</span><span class="sxs-lookup"><span data-stu-id="7248e-158">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="7248e-159">По завершении нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7248e-159">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="7248e-160">Использование центра обеспечения безопасности для удаления тегов пользователей</span><span class="sxs-lookup"><span data-stu-id="7248e-160">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="7248e-161">**Note** : невозможно удалить встроенный тег **учетной записи приоритета** .</span><span class="sxs-lookup"><span data-stu-id="7248e-161">**Note** : You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="7248e-162">В центре безопасности перейдите к разделу **Пользователи управления угрозами** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="7248e-162">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="7248e-163">На открывшейся странице " **теги пользователей** " выберите тег пользователя, которого нужно удалить, нажмите кнопку **Удалить тег** , а затем выберите **Да, удалить** в появившемся предупреждении.</span><span class="sxs-lookup"><span data-stu-id="7248e-163">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag** , and then select **Yes, remove** in the warning that appears.</span></span>
