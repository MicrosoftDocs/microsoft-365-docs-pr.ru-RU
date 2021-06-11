---
title: Теги пользователей в Microsoft Defender для Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как определить определенные группы пользователей с тегами пользователей в Microsoft Defender для Office 365 Plan 2. Фильтрация тегов доступна для оповещений, отчетов и расследований в Microsoft Defender для Office 365 для быстрого определения помеченных пользователей.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 105e927e50f7b1d1217587587b8d7ee3b7d6bd4c
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904108"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fc611-104">Теги пользователей в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="fc611-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="fc611-105">Функция тегов пользователя находится в предварительной версии, доступна не всем и подлежит изменениям.</span><span class="sxs-lookup"><span data-stu-id="fc611-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="fc611-106">Сведения о расписании выпуска ознакомьтесь с Microsoft 365 [плана](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="fc611-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="fc611-107">Теги пользователей являются идентификаторами для определенных групп пользователей [в Microsoft Defender для Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="fc611-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="fc611-108">Существует два типа тегов пользователей:</span><span class="sxs-lookup"><span data-stu-id="fc611-108">There are two types of user tags:</span></span>

- <span data-ttu-id="fc611-109">**Теги системы.** В настоящее [время учетные записи Priority](../../admin/setup/priority-accounts.md) — это единственный тип системного тега.</span><span class="sxs-lookup"><span data-stu-id="fc611-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="fc611-110">**Настраиваемые теги.** Вы создаете эти теги пользователя самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="fc611-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="fc611-111">Если в вашей организации имеется defender for Office 365 Plan 2 (включен в подписку или в качестве надстройки), вы можете создать пользовательские теги пользователей в дополнение к использованию тега учетных записей приоритета.</span><span class="sxs-lookup"><span data-stu-id="fc611-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="fc611-112">В настоящее время теги пользователей можно применять только к пользователям почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="fc611-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="fc611-113">После применения системных тегов или пользовательских тегов для пользователей эти теги можно использовать в качестве фильтров в оповещениях, отчетах и исследованиях:</span><span class="sxs-lookup"><span data-stu-id="fc611-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="fc611-114">Alerts</span><span class="sxs-lookup"><span data-stu-id="fc611-114">Alerts</span></span>](alerts.md)
- [<span data-ttu-id="fc611-115">Настраиваемые политики оповещения</span><span class="sxs-lookup"><span data-stu-id="fc611-115">Custom alert policies</span></span>](../../compliance/alert-policies.md#viewing-alerts)
- [<span data-ttu-id="fc611-116">Обозреватель угроз и обнаружения в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="fc611-116">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="fc611-117">Страница сущности электронной почты</span><span class="sxs-lookup"><span data-stu-id="fc611-117">Email entity page</span></span>](mdo-email-entity-page.md#other-innovations)
- <span data-ttu-id="fc611-118">[отчет о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report);</span><span class="sxs-lookup"><span data-stu-id="fc611-118">[Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="fc611-119">Представления кампании</span><span class="sxs-lookup"><span data-stu-id="fc611-119">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="fc611-120">Для учетных записей приоритета [](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) можно использовать проблемы электронной почты для отчета о приоритетных учетных записях в центре администрирования Exchange администратора (EAC).</span><span class="sxs-lookup"><span data-stu-id="fc611-120">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="fc611-121">В этой статье рассказывается о настройке тегов пользователей на портале Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="fc611-121">This article explains how to configure user tags in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="fc611-122">На портале Defender Microsoft 365 командлетов для управления тегами пользователей.</span><span class="sxs-lookup"><span data-stu-id="fc611-122">There are no cmdlets in Microsoft 365 Defender portal to manage user tags.</span></span>

<span data-ttu-id="fc611-123">Чтобы узнать, как теги пользователей являются частью стратегии защиты учетных записей пользователей с высокими последствиями, см. в рекомендациях по безопасности для приоритетных учетных записей [в Microsoft 365.](security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="fc611-123">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fc611-124">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="fc611-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fc611-125">Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="fc611-125">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="fc611-126">Чтобы перейти непосредственно на **страницу Теги пользователя,** откройте <https://security.microsoft.com/securitysettings/userTags> .</span><span class="sxs-lookup"><span data-stu-id="fc611-126">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="fc611-127">Вам необходимо получить разрешения на портале Microsoft 365 Defender, прежде чем вы сможете сделать процедуры в этой статье:</span><span class="sxs-lookup"><span data-stu-id="fc611-127">You need to be assigned permissions in the Microsoft 365 Defender portal before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="fc611-128">Чтобы создать, изменить и удалить теги пользователей, необходимо быть членом групп ролей **администратора** организации или **администратора** безопасности.</span><span class="sxs-lookup"><span data-stu-id="fc611-128">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="fc611-129">Чтобы добавить и удалить участников из существующих тегов пользователей, необходимо быть членом групп ролей **"Управление** организацией", "Администратор безопасности" или **"Оператор** безопасности".</span><span class="sxs-lookup"><span data-stu-id="fc611-129">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="fc611-130">Для доступа только для чтения к тегам пользователей необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="fc611-130">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="fc611-131">Дополнительные сведения см. [в сайте Permissions in the Microsoft 365 Defender.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="fc611-131">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="fc611-132">Добавление пользователей к соответствующей роли Azure Active Directory в центре администрирования Microsoft 365 предоставляет пользователям необходимые разрешения на  портале Microsoft 365 Defender и разрешения на другие функции в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fc611-132">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="fc611-133">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="fc611-133">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="fc611-134">Управление тегами пользователя контролируется ролями **Reader и** **Tag Manager.**</span><span class="sxs-lookup"><span data-stu-id="fc611-134">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="fc611-135">Вы также можете управлять и отслеживать учетные записи приоритетов в центре Microsoft 365 администрирования.</span><span class="sxs-lookup"><span data-stu-id="fc611-135">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="fc611-136">Инструкции см. в [инструкции Управление и мониторинг учетных записей приоритетов.](../../admin/setup/priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="fc611-136">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="fc611-137">Сведения о защите привилегированных _учетных записей_ (учетных записей администратора) см. [в этом разделе.](/azure/architecture/framework/security/critical-impact-accounts)</span><span class="sxs-lookup"><span data-stu-id="fc611-137">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a><span data-ttu-id="fc611-138">Используйте портал Microsoft 365 Defender для создания тегов пользователей</span><span class="sxs-lookup"><span data-stu-id="fc611-138">Use the Microsoft 365 Defender portal to create user tags</span></span>

1. <span data-ttu-id="fc611-139">На портале Microsoft 365 Defender перейдите **на Параметры** email & \>  \> **теги для совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="fc611-139">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="fc611-140">На странице **Теги пользователя** нажмите ![ кнопку Создать значок ](../../media/m365-cc-sc-create-icon.png) **тега Создание тега**.</span><span class="sxs-lookup"><span data-stu-id="fc611-140">On the **User tags** page, click ![Create tag icon](../../media/m365-cc-sc-create-icon.png) **Create tag**.</span></span>

3. <span data-ttu-id="fc611-141">Мастер **создания тегов** открывается в новой вылете.</span><span class="sxs-lookup"><span data-stu-id="fc611-141">The **Create tag** wizard opens in a new flyout.</span></span> <span data-ttu-id="fc611-142">На странице **Определение тегов** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fc611-142">On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="fc611-143">**Имя.** Введите уникальное описательное имя тега.</span><span class="sxs-lookup"><span data-stu-id="fc611-143">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="fc611-144">Это значение, которое вы увидите и используете.</span><span class="sxs-lookup"><span data-stu-id="fc611-144">This is the value that you'll see and use.</span></span> <span data-ttu-id="fc611-145">Обратите внимание, что после создания тега переименовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="fc611-145">Note that you can't rename a tag after you create it.</span></span>
   - <span data-ttu-id="fc611-146">**Описание.** Введите необязательное описание тега.</span><span class="sxs-lookup"><span data-stu-id="fc611-146">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="fc611-147">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fc611-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="fc611-148">На странице **Назначение участников** сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="fc611-148">On the **Assign members** page, do either of the following steps:</span></span>
   - <span data-ttu-id="fc611-149">Нажмите ![ кнопку Добавить значок ](../../media/m365-cc-sc-create-icon.png) **Добавить членов** Добавить членов .</span><span class="sxs-lookup"><span data-stu-id="fc611-149">Click ![Add members icon](../../media/m365-cc-sc-create-icon.png) **Add members**.</span></span> <span data-ttu-id="fc611-150">В вылете, который появляется, сделайте любой из следующих действий, чтобы добавить отдельных пользователей или групп:</span><span class="sxs-lookup"><span data-stu-id="fc611-150">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="fc611-151">Щелкните в поле и прокрутите список, чтобы выбрать пользователя или группу.</span><span class="sxs-lookup"><span data-stu-id="fc611-151">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="fc611-152">Щелкните в поле и начните печатать, чтобы отфильтровать список и выбрать пользователя или группу.</span><span class="sxs-lookup"><span data-stu-id="fc611-152">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="fc611-153">Чтобы добавить дополнительные значения, щелкните в пустой области в поле.</span><span class="sxs-lookup"><span data-stu-id="fc611-153">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="fc611-154">Чтобы удалить отдельные записи, нажмите кнопку</span><span class="sxs-lookup"><span data-stu-id="fc611-154">To remove individual entries, click</span></span> ![Удаление значка записи](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="fc611-156">рядом с записью в поле.</span><span class="sxs-lookup"><span data-stu-id="fc611-156">next to the entry in the box.</span></span>
     - <span data-ttu-id="fc611-157">Чтобы удалить все записи, нажмите кнопку Удалить значок входа на ![ ](../../media/m365-cc-sc-remove-selection-icon.png) **элементе Выбранные пользователи nn** и группы nn под полем.</span><span class="sxs-lookup"><span data-stu-id="fc611-157">To remove all entries, click ![Remove entry icon](../../media/m365-cc-sc-remove-selection-icon.png) on the **Selected nn users and nn groups** item below the box.</span></span>

     <span data-ttu-id="fc611-158">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="fc611-158">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="fc611-159">Возвращаясь на **страницу Назначение участников,** вы также можете удалить записи, щелкнув значок ![ Delete рядом с ](../../media/m365-cc-sc-delete-icon.png) записью.</span><span class="sxs-lookup"><span data-stu-id="fc611-159">Back on the **Assign members** page, you can also remove entries by clicking ![Delete icon](../../media/m365-cc-sc-delete-icon.png) next to the entry.</span></span>

   - <span data-ttu-id="fc611-160">Щелкните **Импорт,** чтобы выбрать текстовый файл, содержащий адреса электронной почты пользователей или групп.</span><span class="sxs-lookup"><span data-stu-id="fc611-160">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="fc611-161">Убедитесь, что текстовый файл содержит одну запись на строку.</span><span class="sxs-lookup"><span data-stu-id="fc611-161">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="fc611-162">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fc611-162">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="fc611-163">На странице **Тег Обзор,** которая отображается, просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="fc611-163">On the **Review tag** page that appears, review your settings.</span></span> <span data-ttu-id="fc611-164">Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="fc611-164">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="fc611-165">Вы также можете щелкнуть **Назад** или выбрать определенную страницу в мастере.</span><span class="sxs-lookup"><span data-stu-id="fc611-165">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="fc611-166">Когда вы закончите, щелкните **Отправить**, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="fc611-166">When you're finished, click **Submit**, and then click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a><span data-ttu-id="fc611-167">Используйте портал Microsoft 365 Defender для просмотра тегов пользователей</span><span class="sxs-lookup"><span data-stu-id="fc611-167">Use the Microsoft 365 Defender portal to view user tags</span></span>

1. <span data-ttu-id="fc611-168">На портале Microsoft 365 Defender перейдите **на Параметры** email & \>  \> **теги для совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="fc611-168">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="fc611-169">На странице **Теги пользователя** в списке тегов пользователя отображаются следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="fc611-169">On the **User tags** page, the following properties are displayed in the list of user tags:</span></span>

   - <span data-ttu-id="fc611-170">**Тег.** Имя тега пользователя.</span><span class="sxs-lookup"><span data-stu-id="fc611-170">**Tag**: The name of the user tag.</span></span> <span data-ttu-id="fc611-171">Обратите внимание, что это включает встроенный тег **системы учетных записей Priority.**</span><span class="sxs-lookup"><span data-stu-id="fc611-171">Note that this includes the built-in **Priority account** system tag.</span></span>
   - <span data-ttu-id="fc611-172">**Применяется к**: Количество участников</span><span class="sxs-lookup"><span data-stu-id="fc611-172">**Applied to**: The number of members</span></span>
   - <span data-ttu-id="fc611-173">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="fc611-173">**Last modified**</span></span>
   - <span data-ttu-id="fc611-174">**Создан на**</span><span class="sxs-lookup"><span data-stu-id="fc611-174">**Created on**</span></span>

3. <span data-ttu-id="fc611-175">При выборе тега пользователя, нажав на имя, сведения отображаются в вылете.</span><span class="sxs-lookup"><span data-stu-id="fc611-175">When you select a user tag by clicking on the name, the details are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a><span data-ttu-id="fc611-176">Используйте портал Microsoft 365 Defender для изменения тегов пользователей</span><span class="sxs-lookup"><span data-stu-id="fc611-176">Use the Microsoft 365 Defender portal to modify user tags</span></span>

1. <span data-ttu-id="fc611-177">На портале Microsoft 365 Defender перейдите **на Параметры** email & \>  \> **теги для совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="fc611-177">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="fc611-178">На странице **Теги пользователя** выберите тег пользователя из списка, а затем нажмите кнопку Изменить значок ![ ](../../media/m365-cc-sc-edit-icon.png) **тега Изменить**.</span><span class="sxs-lookup"><span data-stu-id="fc611-178">On the **User tags** page, select the user tag from the list, and then click ![Edit tag icon](../../media/m365-cc-sc-edit-icon.png) **Edit tag**.</span></span>

3. <span data-ttu-id="fc611-179">В подробной вылете, которая появится, один и тот же мастер и параметры доступны, как описано на портале [Use the Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-user-tags) для создания раздела тегов пользователей ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="fc611-179">In the details flyout that appears, the same wizard and settings are available as described in the [Use the Microsoft 365 Defender portal to create user tags](#use-the-microsoft-365-defender-portal-to-create-user-tags) section earlier in this article.</span></span>

   <span data-ttu-id="fc611-180">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="fc611-180">**Notes**:</span></span>

   - <span data-ttu-id="fc611-181">Страница **тега Define** недоступна для встроенного системного тега учетной записи **Priority,** поэтому нельзя переименовать этот тег или изменить описание.</span><span class="sxs-lookup"><span data-stu-id="fc611-181">The **Define tag** page is not available for the built-in **Priority account** system tag, so you can't rename this tag or change the description.</span></span>
   - <span data-ttu-id="fc611-182">Настраиваемый тег переименовать нельзя, но можно изменить описание.</span><span class="sxs-lookup"><span data-stu-id="fc611-182">You can't rename a custom tag, but you can change the description.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a><span data-ttu-id="fc611-183">Использование портала Microsoft 365 Defender для удаления тегов пользователей</span><span class="sxs-lookup"><span data-stu-id="fc611-183">Use the Microsoft 365 Defender portal to remove user tags</span></span>

> [!NOTE]
> <span data-ttu-id="fc611-184">Нельзя удалить встроенный тег системы учетной **записи Priority.**</span><span class="sxs-lookup"><span data-stu-id="fc611-184">You can't remove the built-in **Priority account** system tag.</span></span>

1. <span data-ttu-id="fc611-185">На портале Microsoft 365 Defender перейдите **на Параметры** email & \>  \> **теги для совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="fc611-185">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="fc611-186">На странице **Теги пользователя** выберите тег пользователя из списка, а затем нажмите ![ кнопку Удалить значок ](../../media/m365-cc-sc-delete-icon.png) **тега Удаление**.</span><span class="sxs-lookup"><span data-stu-id="fc611-186">On the **User tags** page, select the user tag from the list, and then click ![Delete tag icon](../../media/m365-cc-sc-delete-icon.png) **Delete tag**.</span></span>

3. <span data-ttu-id="fc611-187">Прочитайте предупреждение в диалоговом окте подтверждения, который появится, а затем нажмите **кнопку Да, удалите**.</span><span class="sxs-lookup"><span data-stu-id="fc611-187">Read the warning in the confirmation dialog that appears, and then click **Yes, remove**.</span></span>
