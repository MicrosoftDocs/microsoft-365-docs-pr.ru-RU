---
title: Теги пользователя
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
description: Администраторы могут узнать, как идентифицировать определенные группы пользователей с помощью тегов пользователя в Оиффце 365 ATP (план 2). Фильтрация тегов доступна для оповещений, отчетов и исследований в Office 365 ATP, чтобы быстро определить пользователей с тегами.
ms.openlocfilehash: d47c5c00e3cf0362c44aebc18d11db4bba68a149
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48210034"
---
# <a name="user-tags-in-the-microsoft-security-center"></a><span data-ttu-id="fb48d-104">Теги пользователя в центре безопасности Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fb48d-104">User tags in the Microsoft Security Center</span></span>

<span data-ttu-id="fb48d-105">Теги пользователя — это идентификаторы для определенных групп пользователей в [Office 365 Advanced Threat protection (ATP)](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="fb48d-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="fb48d-106">[Учетные записи приоритета](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) — это тип тега пользователя.</span><span class="sxs-lookup"><span data-stu-id="fb48d-106">[Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) are a type of user tag.</span></span> <span data-ttu-id="fb48d-107">Если в вашей организации используется Office 365 ATP (план 2) (входит в вашу подписку или как надстройку), можно создать настраиваемые теги пользователя в дополнение к использованию тега приоритетов учетных записей.</span><span class="sxs-lookup"><span data-stu-id="fb48d-107">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="fb48d-108">После применения тегов к определенным пользователям можно использовать эти теги в качестве фильтров в оповещениях, отчетах и исследованиях.</span><span class="sxs-lookup"><span data-stu-id="fb48d-108">After you apply tags to specific users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="fb48d-109">Оповещения в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="fb48d-109">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="fb48d-110">Обозреватель угроз и обнаружение в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="fb48d-110">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- <span data-ttu-id="fb48d-111">[отчет о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report);</span><span class="sxs-lookup"><span data-stu-id="fb48d-111">[Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="fb48d-112">Представления кампании</span><span class="sxs-lookup"><span data-stu-id="fb48d-112">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="fb48d-113">В этой статье объясняется, как настроить Теги пользователя в центре обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="fb48d-113">This article explains how to configure user tags in the Security Center.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fb48d-114">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="fb48d-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fb48d-115">Вы открываете центр безопасности по адресу <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="fb48d-115">You open the Security Center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="fb48d-116">Чтобы перейти непосредственно к странице " **теги пользователей** ", откройте ее <https://security.microsoft.com/securitysettings/userTags> .</span><span class="sxs-lookup"><span data-stu-id="fb48d-116">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="fb48d-117">Для создания, изменения или удаления тегов пользователя необходимо быть членом группы ролей " **Управление организацией** " или " **администратор безопасности** " в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fb48d-117">To create, modify, or remove user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="fb48d-118">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fb48d-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="fb48d-119">Вы также можете управлять учетными записями приоритетов и отслеживать их в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb48d-119">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="fb48d-120">Инструкции см в разделе [Управление учетными записями приоритетов](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="fb48d-120">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="fb48d-121">Использование центра обеспечения безопасности для создания тегов пользователя</span><span class="sxs-lookup"><span data-stu-id="fb48d-121">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="fb48d-122">В центре безопасности перейдите в раздел **Параметры** \> **электронной почты &** " \> **Теги пользователя**совместной работы".</span><span class="sxs-lookup"><span data-stu-id="fb48d-122">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="fb48d-123">На открывшейся странице " **теги пользователей** " нажмите кнопку **создать тег**.</span><span class="sxs-lookup"><span data-stu-id="fb48d-123">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="fb48d-124">Мастер **создания тегов** открывается в новом полете. На странице **определение тега** настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="fb48d-124">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="fb48d-125">**Name**: введите уникальное описательное имя тега.</span><span class="sxs-lookup"><span data-stu-id="fb48d-125">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="fb48d-126">Это значение, которое вы увидите и будете использовать.</span><span class="sxs-lookup"><span data-stu-id="fb48d-126">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="fb48d-127">**Описание**: введите необязательное описание для тега.</span><span class="sxs-lookup"><span data-stu-id="fb48d-127">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="fb48d-128">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fb48d-128">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="fb48d-129">На странице **назначить почтовые ящики** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="fb48d-129">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="fb48d-130">Нажмите кнопку **добавить почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="fb48d-130">Click **Add mailboxes**.</span></span> <span data-ttu-id="fb48d-131">В появившемся окне выполните одно из следующих действий, чтобы добавить отдельных пользователей или группы:</span><span class="sxs-lookup"><span data-stu-id="fb48d-131">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="fb48d-132">Щелкните поле и прокрутите список, чтобы выбрать пользователя или группу.</span><span class="sxs-lookup"><span data-stu-id="fb48d-132">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="fb48d-133">Щелкните поле и начните ввод текста, чтобы отфильтровать список и выбрать пользователя или группу.</span><span class="sxs-lookup"><span data-stu-id="fb48d-133">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="fb48d-134">Чтобы добавить дополнительные значения, щелкните пустую область в поле.</span><span class="sxs-lookup"><span data-stu-id="fb48d-134">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="fb48d-135">Чтобы удалить отдельные записи из поля, нажмите кнопку **Удалить** ![ значок "удалить ](../../media/scc-remove-icon.png) " в поле пользователя или группы.</span><span class="sxs-lookup"><span data-stu-id="fb48d-135">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="fb48d-136">Чтобы удалить существующие записи из списка под полем, нажмите кнопку **Удалить** ![ значок "удалить ](../../media/scc-remove-icon.png) ".</span><span class="sxs-lookup"><span data-stu-id="fb48d-136">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="fb48d-137">По завершении нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="fb48d-137">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="fb48d-138">Нажмите кнопку **Импорт** , чтобы выбрать текстовый файл, содержащий адреса электронной почты пользователей или групп.</span><span class="sxs-lookup"><span data-stu-id="fb48d-138">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="fb48d-139">Убедитесь, что текстовый файл содержит одну запись в строке.</span><span class="sxs-lookup"><span data-stu-id="fb48d-139">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="fb48d-140">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fb48d-140">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="fb48d-141">На странице **тег рассмотрения** проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="fb48d-141">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="fb48d-142">Для внесения изменений можно нажать кнопку **изменить** в определенном разделе.</span><span class="sxs-lookup"><span data-stu-id="fb48d-142">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="fb48d-143">По завершении нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fb48d-143">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="fb48d-144">Использование центра обеспечения безопасности для просмотра тегов пользователей</span><span class="sxs-lookup"><span data-stu-id="fb48d-144">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="fb48d-145">В центре безопасности перейдите в раздел **Параметры** \> **электронной почты &** " \> **Теги пользователя**совместной работы".</span><span class="sxs-lookup"><span data-stu-id="fb48d-145">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="fb48d-146">На открывшейся странице " **теги пользователей** " выберите тег пользователя, который нужно просмотреть (не щелкая флажок).</span><span class="sxs-lookup"><span data-stu-id="fb48d-146">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="fb48d-147">При выпадающем на экран сведений, предназначенных только для чтения, проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="fb48d-147">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="fb48d-148">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="fb48d-148">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="fb48d-149">Использование центра обеспечения безопасности для изменения тегов пользователя</span><span class="sxs-lookup"><span data-stu-id="fb48d-149">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="fb48d-150">В центре безопасности перейдите в раздел **Параметры** \> **электронной почты &** " \> **Теги пользователя**совместной работы".</span><span class="sxs-lookup"><span data-stu-id="fb48d-150">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="fb48d-151">На открывшейся странице " **теги пользователей** " выберите тег пользователя, который нужно просмотреть, и нажмите кнопку **изменить тег**.</span><span class="sxs-lookup"><span data-stu-id="fb48d-151">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="fb48d-152">Мастер политики откроется в **теге редактирования** . Нажмите кнопку **Далее** , чтобы просмотреть и изменить параметры.</span><span class="sxs-lookup"><span data-stu-id="fb48d-152">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="fb48d-153">По завершении нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fb48d-153">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="fb48d-154">Использование центра обеспечения безопасности для удаления тегов пользователей</span><span class="sxs-lookup"><span data-stu-id="fb48d-154">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="fb48d-155">**Note**: невозможно удалить встроенный тег **учетной записи приоритета** .</span><span class="sxs-lookup"><span data-stu-id="fb48d-155">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="fb48d-156">В центре безопасности перейдите в раздел **Параметры** \> **электронной почты &** " \> **Теги пользователя**совместной работы".</span><span class="sxs-lookup"><span data-stu-id="fb48d-156">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="fb48d-157">На открывшейся странице " **теги пользователей** " выберите тег пользователя, которого нужно удалить, нажмите кнопку **Удалить тег**, а затем выберите **Да, удалить** в появившемся предупреждении.</span><span class="sxs-lookup"><span data-stu-id="fb48d-157">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
