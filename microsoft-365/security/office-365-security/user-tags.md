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
description: Администраторы могут узнать, как определить определенные группы пользователей с тегами пользователей в Microsoft Defender для Office 365 Plan 2. Фильтрация тегов доступна для оповещений, отчетов и расследований в Microsoft Defender для Office 365, чтобы быстро идентифицировать помеченных пользователей.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e9bb6a233f21268df860974549ecffbfd7154045
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916410"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6dd77-104">Теги пользователей в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="6dd77-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="6dd77-105">Функция тегов пользователя находится в предварительной версии, доступна не всем и подлежит изменениям.</span><span class="sxs-lookup"><span data-stu-id="6dd77-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="6dd77-106">Сведения о расписании выпуска ознакомьтесь с дорожной картой [Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="6dd77-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="6dd77-107">Теги пользователей являются идентификаторами для определенных групп пользователей [в Microsoft Defender для Office 365.](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="6dd77-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="6dd77-108">Существует два типа тегов пользователей:</span><span class="sxs-lookup"><span data-stu-id="6dd77-108">There are two types of user tags:</span></span>

- <span data-ttu-id="6dd77-109">**Теги системы.** В настоящее [время учетные записи Priority](../../admin/setup/priority-accounts.md) — это единственный тип системного тега.</span><span class="sxs-lookup"><span data-stu-id="6dd77-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="6dd77-110">**Настраиваемые теги.** Вы создаете эти теги пользователя самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="6dd77-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="6dd77-111">Если в вашей организации есть Defender для Office 365 Plan 2 (включен в подписку или в качестве надстройки), можно создать пользовательские теги в дополнение к использованию тега учетных записей приоритета.</span><span class="sxs-lookup"><span data-stu-id="6dd77-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="6dd77-112">После применения системных тегов или пользовательских тегов для пользователей эти теги можно использовать в качестве фильтров в оповещениях, отчетах и исследованиях:</span><span class="sxs-lookup"><span data-stu-id="6dd77-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="6dd77-113">Оповещений в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="6dd77-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="6dd77-114">Обозреватель угроз и обнаружения в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="6dd77-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- <span data-ttu-id="6dd77-115">[отчет о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report);</span><span class="sxs-lookup"><span data-stu-id="6dd77-115">[Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="6dd77-116">Представления кампании</span><span class="sxs-lookup"><span data-stu-id="6dd77-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="6dd77-117">Для учетных записей приоритетов [](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) можно использовать проблемы электронной почты для отчета о приоритетных учетных записях в центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="6dd77-117">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="6dd77-118">В этой статье рассказывается о настройке тегов пользователей в Центре & безопасности.</span><span class="sxs-lookup"><span data-stu-id="6dd77-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="6dd77-119">В Центре обеспечения безопасности не & командлетов для управления тегами пользователей.</span><span class="sxs-lookup"><span data-stu-id="6dd77-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

<span data-ttu-id="6dd77-120">Чтобы узнать, как теги пользователей являются частью стратегии защиты учетных записей пользователей с высокими последствиями, см. в рекомендациях по безопасности для учетных записей приоритетов [в Microsoft 365.](security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="6dd77-120">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6dd77-121">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="6dd77-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6dd77-122">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="6dd77-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="6dd77-123">Чтобы перейти непосредственно на **страницу Теги пользователя,** откройте <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="6dd77-123">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="6dd77-124">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="6dd77-124">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="6dd77-125">Чтобы создать, изменить и удалить теги пользователей, необходимо быть членом групп ролей **администратора** организации или **администратора** безопасности.</span><span class="sxs-lookup"><span data-stu-id="6dd77-125">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="6dd77-126">Чтобы добавить и удалить участников из существующих тегов пользователей, необходимо быть членом групп ролей **"Управление** организацией", "Администратор безопасности" или **"Оператор** безопасности".</span><span class="sxs-lookup"><span data-stu-id="6dd77-126">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="6dd77-127">Для доступа только для чтения к тегам пользователей необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="6dd77-127">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="6dd77-128">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6dd77-128">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="6dd77-129">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="6dd77-129">**Notes**:</span></span>

  - <span data-ttu-id="6dd77-130">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6dd77-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="6dd77-131">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="6dd77-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="6dd77-132">Управление тегами пользователя контролируется ролями **Reader и** **Tag Manager.**</span><span class="sxs-lookup"><span data-stu-id="6dd77-132">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="6dd77-133">Вы также можете управлять и отслеживать учетные записи приоритетов в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6dd77-133">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6dd77-134">Инструкции см. в [инструкции Управление и мониторинг учетных записей приоритетов.](../../admin/setup/priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="6dd77-134">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-user-tags"></a><span data-ttu-id="6dd77-135">Используйте Центр & безопасности для создания тегов пользователей</span><span class="sxs-lookup"><span data-stu-id="6dd77-135">Use the Security & Compliance Center to create user tags</span></span>

1. <span data-ttu-id="6dd77-136">В Центре & безопасности перейдите к **тегам пользователя управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="6dd77-136">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="6dd77-137">На **открываемой странице Теги** пользователя нажмите **кнопку Создать тег**.</span><span class="sxs-lookup"><span data-stu-id="6dd77-137">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="6dd77-138">Мастер **создания тегов** открывается в новой вылет. На странице **Определение тегов** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="6dd77-138">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="6dd77-139">**Имя.** Введите уникальное описательное имя тега.</span><span class="sxs-lookup"><span data-stu-id="6dd77-139">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="6dd77-140">Это значение, которое вы увидите и используете.</span><span class="sxs-lookup"><span data-stu-id="6dd77-140">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="6dd77-141">**Описание.** Введите необязательное описание тега.</span><span class="sxs-lookup"><span data-stu-id="6dd77-141">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="6dd77-142">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6dd77-142">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6dd77-143">На странице **Назначение пользователей** сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="6dd77-143">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="6dd77-144">Нажмите **кнопку Добавить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="6dd77-144">Click **Add users**.</span></span> <span data-ttu-id="6dd77-145">В вылете, который появляется, сделайте любой из следующих действий, чтобы добавить отдельных пользователей или групп:</span><span class="sxs-lookup"><span data-stu-id="6dd77-145">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="6dd77-146">Щелкните в поле и прокрутите список, чтобы выбрать пользователя или группу.</span><span class="sxs-lookup"><span data-stu-id="6dd77-146">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="6dd77-147">Щелкните в поле и начните печатать, чтобы отфильтровать список и выбрать пользователя или группу.</span><span class="sxs-lookup"><span data-stu-id="6dd77-147">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="6dd77-148">Чтобы добавить дополнительные значения, щелкните в пустой области в поле.</span><span class="sxs-lookup"><span data-stu-id="6dd77-148">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="6dd77-149">Чтобы удалить отдельные записи из окна, нажмите **кнопку Удалить** значок Удалить пользователя или ![ ](../../media/scc-remove-icon.png) группу в поле.</span><span class="sxs-lookup"><span data-stu-id="6dd77-149">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="6dd77-150">Чтобы удалить существующие записи из списка под полем, нажмите **кнопку Удалить** ![ значок Удалить ](../../media/scc-remove-icon.png) запись.</span><span class="sxs-lookup"><span data-stu-id="6dd77-150">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="6dd77-151">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="6dd77-151">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="6dd77-152">Щелкните **Импорт,** чтобы выбрать текстовый файл, содержащий адреса электронной почты пользователей или групп.</span><span class="sxs-lookup"><span data-stu-id="6dd77-152">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="6dd77-153">Убедитесь, что текстовый файл содержит одну запись на строку.</span><span class="sxs-lookup"><span data-stu-id="6dd77-153">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="6dd77-154">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6dd77-154">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6dd77-155">На странице **Тег Обзор** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="6dd77-155">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="6dd77-156">Чтобы внести изменения, нажмите **кнопку Изменить** в определенном разделе.</span><span class="sxs-lookup"><span data-stu-id="6dd77-156">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="6dd77-157">По завершению нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="6dd77-157">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-view-user-tags"></a><span data-ttu-id="6dd77-158">Используйте Центр & безопасности для просмотра тегов пользователей</span><span class="sxs-lookup"><span data-stu-id="6dd77-158">Use the Security & Compliance Center to view user tags</span></span>

1. <span data-ttu-id="6dd77-159">В Центре & безопасности перейдите к **тегам пользователя управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="6dd77-159">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="6dd77-160">На **открываемой** странице Теги пользователя выберите тег пользователя, который необходимо просмотреть (не нажимайте на почтовый ящик).</span><span class="sxs-lookup"><span data-stu-id="6dd77-160">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="6dd77-161">В сведениях, которые только для чтения вылет, которые появляются, просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="6dd77-161">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="6dd77-162">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="6dd77-162">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a><span data-ttu-id="6dd77-163">Используйте Центр & безопасности для изменения тегов пользователей</span><span class="sxs-lookup"><span data-stu-id="6dd77-163">Use the Security & Compliance Center to modify user tags</span></span>

1. <span data-ttu-id="6dd77-164">В Центре & безопасности перейдите к **тегам пользователя управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="6dd77-164">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="6dd77-165">На **открываемой** странице Теги пользователя выберите тег пользователя, который необходимо просмотреть, а затем нажмите **кнопку Изменить тег**.</span><span class="sxs-lookup"><span data-stu-id="6dd77-165">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="6dd77-166">Мастер политики откроется в метке **Изменить.** Нажмите **кнопку Далее,** чтобы просмотреть и изменить параметры.</span><span class="sxs-lookup"><span data-stu-id="6dd77-166">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="6dd77-167">По завершению нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="6dd77-167">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a><span data-ttu-id="6dd77-168">Используйте Центр & безопасности для удаления тегов пользователей</span><span class="sxs-lookup"><span data-stu-id="6dd77-168">Use the Security & Compliance Center to remove user tags</span></span>

<span data-ttu-id="6dd77-169">**Примечание.** Нельзя удалить встроенный тег учетной **записи Priority.**</span><span class="sxs-lookup"><span data-stu-id="6dd77-169">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="6dd77-170">В Центре & безопасности перейдите к **тегам пользователя управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="6dd77-170">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="6dd77-171">На **открываемой** странице Теги пользователя выберите тег пользователя, который необходимо удалить, нажмите кнопку **Удалить** тег, а затем выберите **Да,** удалите в предостережение, которое появится.</span><span class="sxs-lookup"><span data-stu-id="6dd77-171">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>