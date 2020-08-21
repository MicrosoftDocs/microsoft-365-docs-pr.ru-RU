---
title: Включение надстройки "Пожаловаться на сообщение"
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Узнайте, как включить надстройку Report Message для Outlook и Outlook в Интернете для отдельных пользователей или всей организации.
ms.openlocfilehash: 45f67e4c88d311254a0d922baed66178c3f672a5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826641"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="dc392-103">Включение надстройки "Пожаловаться на сообщение"</span><span class="sxs-lookup"><span data-stu-id="dc392-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="dc392-104">Администраторы организации Microsoft 365, имеющей почтовые ящики Exchange Online, рекомендуем использовать портал отправки в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="dc392-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="dc392-105">Дополнительные сведения см. в статье ["Использование функции отправки администратора" для отправки подозрительного спама, фишинга, URL-адресов и файлов в корпорацию Майкрософт.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="dc392-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="dc392-106">Надстройка Report Message для Outlook и Outlook в Интернете (предыдущее название Outlook Web App) позволяет пользователям легко сообщать о ложных срабатываниях (таких сообщениях оно отмечено как недопустимые) или отрицательные отрицательные результаты (разрешены недопустимые электронные письма) в корпорацию Майкрософт и ее аффилированных лиц для анализа.</span><span class="sxs-lookup"><span data-stu-id="dc392-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="dc392-107">Корпорация Майкрософт использует эти средства отправки для повышения эффективности технологий защиты электронной почты.</span><span class="sxs-lookup"><span data-stu-id="dc392-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="dc392-108">Например, предположим, что пользователи сообщают о многое количество сообщений как о фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="dc392-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="dc392-109">Эта информация доступна в панели [мониторинга безопасности и](security-dashboard.md) других отчетах.</span><span class="sxs-lookup"><span data-stu-id="dc392-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="dc392-110">Группы безопасности в вашей организации могут использовать эту информацию в качестве данных о том, что могут возникнуть требования политик защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="dc392-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="dc392-111">Или, если пользователи сообщают о нежелательных сообщениях как нежелательных с помощью надстройки Report Message, группе безопасности вашей организации, возможно, потребуется настроить политики [защиты от нежелательной почты.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="dc392-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="dc392-112">Кроме того, если ваша организация использует [Office 365 Advanced Threat Protection (план 1)](office-365-atp.md) или [план 2,](office-365-ti.md)надстройка Report Message предоставляет команде безопасности вашей организации полезные сведения, которые можно использовать для просмотра и обновления политик безопасности.</span><span class="sxs-lookup"><span data-stu-id="dc392-112">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="dc392-113">Администраторы могут включить надстройку Report Message для организации, а отдельные пользователи могут ее установить самим в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dc392-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="dc392-114">Если вы являетесь отдельным пользователем, вы можете самостоятельно включить [надстройку Report Message.](#get-the-report-message-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="dc392-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="dc392-115">Если вы являетесь глобальным администратором или администратором Exchange Online, а в Exchange настроено использование проверки подлинности OAuth, вы можете включить [надстройку Report Message в своей организации.](#get-and-enable-the-report-message-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="dc392-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="dc392-116">Теперь надстройка Report Message теперь доступна в [централизованном развертывании.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="dc392-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="dc392-117">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="dc392-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="dc392-118">Надстройка Report Message работает с большинством подписок Microsoft 365 и следующими продуктами:</span><span class="sxs-lookup"><span data-stu-id="dc392-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="dc392-119">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="dc392-119">Outlook on the web</span></span>
  - <span data-ttu-id="dc392-120">Outlook 2013 с пакетом обновления 1 (SP1) или более поздних версий</span><span class="sxs-lookup"><span data-stu-id="dc392-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="dc392-121">Outlook 2016 для Mac;</span><span class="sxs-lookup"><span data-stu-id="dc392-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="dc392-122">Outlook включен в приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="dc392-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="dc392-123">Надстройка Report Message недоступна для почтовых ящиков в локальных организациях Exchange.</span><span class="sxs-lookup"><span data-stu-id="dc392-123">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="dc392-124">Вы можете настроить отправленные сообщения для копирования или перенаправления в заданный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="dc392-124">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="dc392-125">Дополнительные сведения см. в статье , посвященном почтовому ящику, для отправки нежелательных [и фишинговых сообщений в Exchange Online.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="dc392-125">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="dc392-126">Существующий веб-браузер должен работать с надстройкой Report Message.</span><span class="sxs-lookup"><span data-stu-id="dc392-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="dc392-127">Но если вы заметите, что надстройка недоступна или не работает должным образом, попробуйте использовать другой браузер.</span><span class="sxs-lookup"><span data-stu-id="dc392-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="dc392-128">Организационная установка требуется для использования проверки подлинности OAuth.</span><span class="sxs-lookup"><span data-stu-id="dc392-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="dc392-129">Дополнительные сведения см. в разделе ["Определение способа ли для вашей организации" централизованного развертывания надстроек.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="dc392-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="dc392-130">Администраторы должны быть членом группы ролей глобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="dc392-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="dc392-131">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="dc392-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="dc392-132">Получение надстройки Report Message для себя</span><span class="sxs-lookup"><span data-stu-id="dc392-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="dc392-133">Перейдите в Microsoft AppSource и <https://appsource.microsoft.com/marketplace/apps> найдите надстройку Report Message.</span><span class="sxs-lookup"><span data-stu-id="dc392-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="dc392-134">Чтобы перейти непосредственно к надстройке Report Message, перейдите к <https://appsource.microsoft.com/product/office/wa104381180> разделу.</span><span class="sxs-lookup"><span data-stu-id="dc392-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="dc392-135">Нажмите **КНОПКУ GET IT NOW.**</span><span class="sxs-lookup"><span data-stu-id="dc392-135">Click **GET IT NOW**.</span></span>

   ![Report Message — Get It Now](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="dc392-137">В появившемся диалоговом окне просмотрите условия **Continue**использования и политику конфиденциальности, а затем нажмите кнопку "Продолжить".</span><span class="sxs-lookup"><span data-stu-id="dc392-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="dc392-138">Войдите с помощью рабочей или учебной учетной записи (для деловых пользователей) или учетной записи Майкрософт (для личного использования).</span><span class="sxs-lookup"><span data-stu-id="dc392-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="dc392-139">После установки и включения надстройки вы увидите следующие значки:</span><span class="sxs-lookup"><span data-stu-id="dc392-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="dc392-140">В Outlook значок выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dc392-140">In Outlook, the icon looks like this:</span></span>

  ![Значок надстройки Report Message для Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="dc392-142">В Outlook в Интернете значок выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dc392-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Значок надстройки "Отчет о сообщении" в Outlook в Интернете](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="dc392-144">Чтобы узнать, как использовать надстройку, см. [статью Использование надстройки Report Message.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="dc392-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="dc392-145">Получение и включение надстройки Report Message в организации</span><span class="sxs-lookup"><span data-stu-id="dc392-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="dc392-146">Настройка надстройки в организации может занять до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="dc392-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="dc392-147">В Центре администрирования Microsoft 365 перейдите на страницу **"Службы& надстройки"** <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> и нажмите **кнопку "Развернуть надстройку".**</span><span class="sxs-lookup"><span data-stu-id="dc392-147">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>, and then click **Deploy Add-In**.</span></span>

   ![Страница "Службы и надстройки" в Центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="dc392-149">В **появившемся всплывающем** окне "Развертывание новой надстройки" просмотрите сведения и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="dc392-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="dc392-150">На следующей странице выберите элемент **"Выбрать из Магазина".**</span><span class="sxs-lookup"><span data-stu-id="dc392-150">On the next page, click **Choose from the Store**.</span></span>

   ![Развертывание новой страницы надстройки](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="dc392-152">На **появившейся** странице "Выбор надстройки" в поле **поиска** введите **"Сообщение Report Message"** и щелкните **значок "Поиск".** ![ ](../../media/search-icon.png)</span><span class="sxs-lookup"><span data-stu-id="dc392-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="dc392-153">В списке результатов найдите отчет **Report Message** и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="dc392-153">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Выбор результатов поиска по надстройкам](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="dc392-155">В появившемся диалоговом окне просмотрите **Continue**сведения о лицензировании и конфиденциальности, а затем нажмите кнопку "Продолжить".</span><span class="sxs-lookup"><span data-stu-id="dc392-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="dc392-156">На **появившейся** странице "Настройка надстройки" настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="dc392-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="dc392-157">**Назначенные**пользователи: выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="dc392-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="dc392-158">**Все (по умолчанию)**</span><span class="sxs-lookup"><span data-stu-id="dc392-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="dc392-159">**Определенные пользователи и группы**</span><span class="sxs-lookup"><span data-stu-id="dc392-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="dc392-160">**Только я**</span><span class="sxs-lookup"><span data-stu-id="dc392-160">**Just me**</span></span>

   - <span data-ttu-id="dc392-161">**Метод развертывания:** выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="dc392-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="dc392-162">**Исправлена (по умолчанию).** Надстройка автоматически развертывается для указанных пользователей и не может удалить ее.</span><span class="sxs-lookup"><span data-stu-id="dc392-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="dc392-163">**Доступно:** пользователи могут устанавливать надстройку **при** просмотре \> **дома надстроек,** \> **управляемых администратором.**</span><span class="sxs-lookup"><span data-stu-id="dc392-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="dc392-164">**Необязательно:** надстройка автоматически развертывается для указанных пользователей, но может удалить ее.</span><span class="sxs-lookup"><span data-stu-id="dc392-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Страница настройки надстройки](../../media/configure-add-in.png)

   <span data-ttu-id="dc392-166">По завершении нажмите кнопку **"Развернуть".**</span><span class="sxs-lookup"><span data-stu-id="dc392-166">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="dc392-167">На **появившейся** странице "Отчет о развертывании сообщения" вы увидите отчет о ходе выполнения, а затем подтверждение развертывания надстройки.</span><span class="sxs-lookup"><span data-stu-id="dc392-167">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="dc392-168">После прочтения сведений нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="dc392-168">After you read the information, click **Next**.</span></span>

   ![Страница развертывания отчетного сообщения](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="dc392-170">На **появившейся странице надстройки** "Новый" просмотрите сведения и нажмите кнопку **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="dc392-170">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Представляем страницу надстройки](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="dc392-172">Узнайте, как использовать надстройку Report Message</span><span class="sxs-lookup"><span data-stu-id="dc392-172">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="dc392-173">Значки могут видеть следующие значки для пользователей, которым назначена надстройка:</span><span class="sxs-lookup"><span data-stu-id="dc392-173">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="dc392-174">В Outlook значок выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dc392-174">In Outlook, the icon looks like this:</span></span>

  ![Значок надстройки "Отчет о сообщении" для Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="dc392-176">В Outlook в Интернете значок выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dc392-176">In Outlook on the web, the icon looks like this:</span></span>

  ![Значок надстройки "Сообщение" Outlook в Интернете](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="dc392-178">Когда вы уведомите пользователей о надстройке Report Message, добавьте ссылку на [надстройку Report Message.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="dc392-178">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="dc392-179">Просмотр и изменение параметров надстройки Report Message</span><span class="sxs-lookup"><span data-stu-id="dc392-179">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="dc392-180">В Центре администрирования Microsoft 365 перейдите на страницу **& надстройки в этой** папке. <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns></span><span class="sxs-lookup"><span data-stu-id="dc392-180">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![Страница "Службы и надстройки" в новом Центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="dc392-182">Найдите и **выберите надстройку Report Message.**</span><span class="sxs-lookup"><span data-stu-id="dc392-182">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="dc392-183">В **появившемся** окне "Изменение сообщения отчета" измените и измените параметры в подходящем для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dc392-183">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="dc392-184">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="dc392-184">When you're finished, click **Save**.</span></span>

   ![Параметры надстройки Report Message](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="dc392-186">Просмотр и просмотр сообщений, отправленных в этот отчет</span><span class="sxs-lookup"><span data-stu-id="dc392-186">View and review reported messages</span></span>

<span data-ttu-id="dc392-187">Чтобы просмотреть сообщения, подключаемые пользователями в Майкрософт, вы можете:</span><span class="sxs-lookup"><span data-stu-id="dc392-187">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="dc392-188">На портале отправки администраторов.</span><span class="sxs-lookup"><span data-stu-id="dc392-188">Use the Admin Submissions portal.</span></span> <span data-ttu-id="dc392-189">Дополнительные сведения см. в статье ["Просмотр пользовательских отправок в Майкрософт.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="dc392-189">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="dc392-190">Создание правила потока обработки почты (также называемого правилом транспорта) для отправки копий отчетных сообщений.</span><span class="sxs-lookup"><span data-stu-id="dc392-190">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="dc392-191">Инструкции см. в статье ["Использование правил для потока обработки почты", чтобы узнать, что пользователи подчиникают в Майкрософт.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="dc392-191">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
