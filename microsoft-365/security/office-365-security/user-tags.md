---
title: Теги пользователей в Microsoft Defender для Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как определить определенные группы пользователей с помощью тегов пользователей в Microsoft Defender для Office 365 (план 2). Фильтрация тегов доступна для оповещений, отчетов и расследований в Microsoft Defender для Office 365, чтобы быстро определить помеченных пользователей.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ed91492e652773b3a48373df49b20d97887df6ee
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931438"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="63353-104">Теги пользователей в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="63353-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="63353-105">Функция тегов пользователей доступна в режиме предварительного просмотра, доступна не всем и может быть внося изменения.</span><span class="sxs-lookup"><span data-stu-id="63353-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="63353-106">Сведения о расписании выпусков можно узнать в [плане развития Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="63353-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="63353-107">Теги пользователей — это идентификаторы определенных групп пользователей в [Microsoft Defender для Office 365.](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="63353-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="63353-108">Существует два типа тегов пользователей:</span><span class="sxs-lookup"><span data-stu-id="63353-108">There are two types of user tags:</span></span>

- <span data-ttu-id="63353-109">**Системные теги**: в [настоящее время учетные записи priority](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) — единственный тип системного тега.</span><span class="sxs-lookup"><span data-stu-id="63353-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="63353-110">**Настраиваемые теги:** вы создаете эти теги пользователей самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="63353-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="63353-111">Если в вашей организации есть Защитник для Office 365 (план 2), включенный в вашу подписку или в качестве надстройки, вы можете создавать настраиваемые теги пользователей в дополнение к тегу учетных записей приоритета.</span><span class="sxs-lookup"><span data-stu-id="63353-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="63353-112">После применения системных тегов или пользовательских тегов к пользователям эти теги можно использовать в качестве фильтров в оповещениях, отчетах и исследованиях:</span><span class="sxs-lookup"><span data-stu-id="63353-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="63353-113">Оповещения в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="63353-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="63353-114">Обозреватель угроз и обнаружение угроз в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="63353-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- <span data-ttu-id="63353-115">[отчет о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report);</span><span class="sxs-lookup"><span data-stu-id="63353-115">[Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="63353-116">Представления кампании</span><span class="sxs-lookup"><span data-stu-id="63353-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="63353-117">Для учетных записей с учетными данными приоритета можно использовать отчет [о](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) проблемах электронной почты для отчета об учетных записях приоритетов в Центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="63353-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="63353-118">В этой статье объясняется, как настроить теги пользователей в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="63353-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="63353-119">В Центре безопасности и соответствия & нет командлетов для управления тегами пользователей.</span><span class="sxs-lookup"><span data-stu-id="63353-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="63353-120">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="63353-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="63353-121">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="63353-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="63353-122">Чтобы перейти непосредственно на **страницу "Теги пользователя",** откройте <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="63353-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="63353-123">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="63353-123">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="63353-124">Чтобы создавать, изменять и удалять теги пользователей, необходимо  быть членом группы ролей "Управление организацией" или "Администратор **безопасности".**</span><span class="sxs-lookup"><span data-stu-id="63353-124">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="63353-125">Чтобы добавлять и удалять участников из существующих тегов пользователей, необходимо быть членом группы ролей "Управление организацией", "Администратор безопасности" или **"Оператор** безопасности".</span><span class="sxs-lookup"><span data-stu-id="63353-125">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="63353-126">Для доступа только для чтения к тегам пользователей необходимо быть  членом группы ролей **"Глобальное** читатель" или "Читатель безопасности".</span><span class="sxs-lookup"><span data-stu-id="63353-126">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="63353-127">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="63353-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="63353-128">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="63353-128">**Notes**:</span></span>

  - <span data-ttu-id="63353-129">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="63353-129">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="63353-130">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="63353-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="63353-131">Управление тегами пользователей контролируется ролями **"Читатель** тегов", **"Участник тегов"** и **"Диспетчер** тегов".</span><span class="sxs-lookup"><span data-stu-id="63353-131">User tag management is controlled by the **Tag Reader**, **Tag Contributor**, and **Tag Manager** roles.</span></span>

- <span data-ttu-id="63353-132">Вы также можете управлять учетной записью приоритета и отслеживать ее в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="63353-132">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="63353-133">Инструкции см. в под [управлением и отслеживании учетных записей приоритетов.](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)</span><span class="sxs-lookup"><span data-stu-id="63353-133">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="63353-134">Создание тегов пользователей с помощью Центра безопасности</span><span class="sxs-lookup"><span data-stu-id="63353-134">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="63353-135">В Центре безопасности перейдите к **тегам пользователя управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="63353-135">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="63353-136">На **открываемой странице "Теги** пользователя" нажмите кнопку **"Создать тег".**</span><span class="sxs-lookup"><span data-stu-id="63353-136">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="63353-137">Мастер **создания тегов** откроется в новом вылете. На странице **"Определение тегов"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="63353-137">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="63353-138">**Name**: Enter a unique, descriptive name for the tag.</span><span class="sxs-lookup"><span data-stu-id="63353-138">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="63353-139">Это значение, которое вы увидите и используете.</span><span class="sxs-lookup"><span data-stu-id="63353-139">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="63353-140">**Описание:** введите необязательное описание тега.</span><span class="sxs-lookup"><span data-stu-id="63353-140">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="63353-141">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="63353-141">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="63353-142">На странице **"Назначение пользователей"** сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="63353-142">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="63353-143">Нажмите **кнопку "Добавить пользователей".**</span><span class="sxs-lookup"><span data-stu-id="63353-143">Click **Add users**.</span></span> <span data-ttu-id="63353-144">Чтобы добавить отдельных пользователей или группы, в окнах вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="63353-144">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="63353-145">Щелкните поле и прокрутите список, чтобы выбрать пользователя или группу.</span><span class="sxs-lookup"><span data-stu-id="63353-145">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="63353-146">Щелкните это поле и начните вводить текст, чтобы отфильтровать список и выбрать пользователя или группу.</span><span class="sxs-lookup"><span data-stu-id="63353-146">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="63353-147">Чтобы добавить дополнительные значения, щелкните пустую область в поле.</span><span class="sxs-lookup"><span data-stu-id="63353-147">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="63353-148">Чтобы удалить отдельные записи из этого окна, щелкните значок **"Удалить"** для пользователя или группы ![ в этом ](../../media/scc-remove-icon.png) поле.</span><span class="sxs-lookup"><span data-stu-id="63353-148">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="63353-149">Чтобы удалить существующие записи из списка под полем, нажмите кнопку **"Удалить** ![ значок удаления". ](../../media/scc-remove-icon.png)</span><span class="sxs-lookup"><span data-stu-id="63353-149">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="63353-150">По завершению нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="63353-150">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="63353-151">Нажмите **кнопку** "Импорт", чтобы выбрать текстовый файл, содержащий адреса электронной почты пользователей или групп.</span><span class="sxs-lookup"><span data-stu-id="63353-151">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="63353-152">Убедитесь, что текстовый файл содержит по одной записи в строке.</span><span class="sxs-lookup"><span data-stu-id="63353-152">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="63353-153">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="63353-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="63353-154">На странице **тегов "Проверка"** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="63353-154">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="63353-155">Чтобы внести **изменения,** можно нажать кнопку "Изменить" в определенном разделе.</span><span class="sxs-lookup"><span data-stu-id="63353-155">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="63353-156">После завершения нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="63353-156">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="63353-157">Просмотр тегов пользователей с помощью Центра безопасности</span><span class="sxs-lookup"><span data-stu-id="63353-157">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="63353-158">В Центре безопасности перейдите к **тегам пользователя управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="63353-158">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="63353-159">На **открываемой** странице "Теги пользователя" выберите тег пользователя, который нужно просмотреть (не нажимайте на этот контрольный ящик).</span><span class="sxs-lookup"><span data-stu-id="63353-159">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="63353-160">В появились сведения только для чтения, которые появляются, просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="63353-160">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="63353-161">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="63353-161">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="63353-162">Использование центра безопасности для изменения тегов пользователей</span><span class="sxs-lookup"><span data-stu-id="63353-162">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="63353-163">В Центре безопасности перейдите к **тегам пользователя управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="63353-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="63353-164">На **открываемой странице** "Теги пользователя" выберите тег пользователя, который нужно просмотреть, и нажмите кнопку **"Изменить тег".**</span><span class="sxs-lookup"><span data-stu-id="63353-164">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="63353-165">Мастер политики откроется в открываемом **теге редактирования.** Нажмите **кнопку** "Далее", чтобы просмотреть и изменить параметры.</span><span class="sxs-lookup"><span data-stu-id="63353-165">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="63353-166">После завершения нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="63353-166">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="63353-167">Удаление тегов пользователей с помощью Центра безопасности</span><span class="sxs-lookup"><span data-stu-id="63353-167">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="63353-168">**Примечание.** Вы не можете удалить встроенный тег учетной **записи Priority.**</span><span class="sxs-lookup"><span data-stu-id="63353-168">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="63353-169">В Центре безопасности перейдите к **тегам пользователя управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="63353-169">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="63353-170">На **открываемой** странице "Теги пользователя" выберите тег пользователя, который нужно удалить, нажмите кнопку **"Удалить",** а затем выберите "Да", а затем удалите в отображаемом предупреждении. </span><span class="sxs-lookup"><span data-stu-id="63353-170">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
