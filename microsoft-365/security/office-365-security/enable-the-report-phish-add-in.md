---
title: Включить надстройки Report Phish
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
description: Узнайте, как включить надстройку Report Phishing для Outlook и Outlook в Интернете, для отдельных пользователей или всей организации.
ms.openlocfilehash: 44fa55a82462de336982d3af2e3996c14699fd7c
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625393"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="92e81-103">Включение надстройки "Пожаловаться на фишинг"</span><span class="sxs-lookup"><span data-stu-id="92e81-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="92e81-104">Если вы администратор в Microsoft 365 с Exchange Online почтовыми ящиками, рекомендуем использовать портал Отправки в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="92e81-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="92e81-105">Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="92e81-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="92e81-106">Надстройки для сообщений и сообщений о фишинге для Outlook и Outlook в Интернете (ранее известные как Outlook Web App) позволяют пользователям легко сообщать о ложных срабатываниях (хорошая электронная почта, помеченная как плохие) или ложных отрицательных (разрешена плохая электронная почта) в Корпорацию Майкрософт и ее филиалы для анализа.</span><span class="sxs-lookup"><span data-stu-id="92e81-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="92e81-107">Корпорация Майкрософт использует эти материалы для повышения эффективности технологий защиты электронной почты.</span><span class="sxs-lookup"><span data-stu-id="92e81-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="92e81-108">Например, предположим, что люди сообщают много сообщений с помощью надстройки Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="92e81-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="92e81-109">Эти сведения будут использоваться в панели мониторинга [безопасности](security-dashboard.md) и других отчетах.</span><span class="sxs-lookup"><span data-stu-id="92e81-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="92e81-110">Группа безопасности организации может использовать эти сведения в качестве указания на необходимость обновления политик защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="92e81-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="92e81-111">Можно установить надстройку Report Message или Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="92e81-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="92e81-112">Если вы хотите, чтобы пользователи сообщали о спаме и фишинговых сообщениях, разместите надстройку Report Message в организации.</span><span class="sxs-lookup"><span data-stu-id="92e81-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="92e81-113">Дополнительные сведения см. в [добавлении "Включить сообщение отчета".](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="92e81-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="92e81-114">Надстройка Report Phishing предоставляет возможность сообщать только о фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="92e81-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="92e81-115">Администраторы могут включить надстройку Report Phishing для организации, а отдельные пользователи могут установить ее для себя.</span><span class="sxs-lookup"><span data-stu-id="92e81-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="92e81-116">Если вы индивидуальный пользователь, вы можете включить надстройку [Report Phishing для себя.](#get-the-report-phishing-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="92e81-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="92e81-117">Если вы глобальный администратор или администратор Exchange Online и Exchange настроены на использование проверки подлинности OAuth, вы можете включить надстройку Report Phishing для [вашей организации.](#get-and-enable-the-report-phishing-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="92e81-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="92e81-118">Фишинговый отчет Add-In теперь доступен с помощью [централизированного развертывания.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="92e81-118">The Report Phishing Add-In is now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="92e81-119">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="92e81-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="92e81-120">Надстройка Report Phishing работает с большинством Microsoft 365 и следующими продуктами:</span><span class="sxs-lookup"><span data-stu-id="92e81-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="92e81-121">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="92e81-121">Outlook on the web</span></span>
  - <span data-ttu-id="92e81-122">Outlook 2013 sp1 или более поздней</span><span class="sxs-lookup"><span data-stu-id="92e81-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="92e81-123">Outlook 2016 для Mac или более поздней</span><span class="sxs-lookup"><span data-stu-id="92e81-123">Outlook 2016 for Mac or later</span></span>
  - <span data-ttu-id="92e81-124">Outlook в Microsoft 365 приложения для Enterprise</span><span class="sxs-lookup"><span data-stu-id="92e81-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="92e81-125">Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="92e81-125">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="92e81-126">Надстройка Report Phishing недоступна для общих почтовых ящиков или почтовых ящиков в Exchange организациях.</span><span class="sxs-lookup"><span data-stu-id="92e81-126">The Report Phishing add-in is not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="92e81-127">Вы можете настроить сообщения, которые будут скопированы или перенаправлены в почтовый ящик, который указан.</span><span class="sxs-lookup"><span data-stu-id="92e81-127">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="92e81-128">Дополнительные сведения см. [в материале Политики отправки пользователей.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="92e81-128">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="92e81-129">Существующий веб-браузер должен работать с надстройки Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="92e81-129">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="92e81-130">Но если вы заметили, что надстройка недоступна или работает не так, как ожидалось, попробуйте другой браузер.</span><span class="sxs-lookup"><span data-stu-id="92e81-130">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="92e81-131">Для организационных установок необходимо настроить организацию для использования проверки подлинности OAuth.</span><span class="sxs-lookup"><span data-stu-id="92e81-131">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="92e81-132">Дополнительные сведения см. в [рубриках Определение,](../../admin/manage/centralized-deployment-of-add-ins.md)работает ли централизованное развертывание надстройок для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="92e81-132">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="92e81-133">Администраторы должны быть членами группы ролей глобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="92e81-133">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="92e81-134">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="92e81-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="92e81-135">Получите надстройку Report Phishing для себя</span><span class="sxs-lookup"><span data-stu-id="92e81-135">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="92e81-136">Перейдите в Microsoft AppSource и <https://appsource.microsoft.com/marketplace/apps> найдите надстройку Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="92e81-136">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="92e81-137">Нажмите **КНОПКУ GET IT NOW**.</span><span class="sxs-lookup"><span data-stu-id="92e81-137">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="92e81-138">В диалоговом окантове, который появляется, просмотрите условия использования и политику конфиденциальности, а затем нажмите **кнопку Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="92e81-138">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="92e81-139">Впишитесь с помощью учетной записи работы или учебного заведения (для бизнеса) или учетной записи Майкрософт (для личного использования).</span><span class="sxs-lookup"><span data-stu-id="92e81-139">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="92e81-140">После установки и включения надстройки вы увидите следующие значки:</span><span class="sxs-lookup"><span data-stu-id="92e81-140">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="92e81-141">В Outlook значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="92e81-141">In Outlook, the icon looks like this:</span></span>

  ![Отчет о значке надстройки фишинга для Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="92e81-143">В Outlook веб-страницы значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="92e81-143">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook на значке надстройки фишинга веб-отчета](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="92e81-145">Получить и включить надстройку Report Phishing для организации</span><span class="sxs-lookup"><span data-stu-id="92e81-145">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="92e81-146">Для появления надстройки в организации может занять до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="92e81-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="92e81-147">В центре администрирования Microsoft 365 перейдите на страницу надстройки **Параметры** на странице , если вы не видите страницу надстройки, перейдите на ссылку Параметры Интегрированные надстройки приложений на верхней части страницы Интегрированные \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  приложения. </span><span class="sxs-lookup"><span data-stu-id="92e81-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="92e81-148">Выберите **развертывание надстройки** в верхней части страницы, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="92e81-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Страница Службы и надстройки в центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="92e81-150">В **развертывании новой** надстройки, которая появится, просмотрите сведения, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="92e81-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="92e81-151">На следующей странице нажмите **кнопку Выберите из магазина**.</span><span class="sxs-lookup"><span data-stu-id="92e81-151">On the next page, click **Choose from the Store**.</span></span>

   ![Развертывание новой страницы надстройки](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="92e81-153">На странице **Выбор надстройки,** которая появится, нажмите кнопку в поле **Поиск,** введите **сообщение** фишинг, а затем нажмите **значок Поиска** ![ поиска ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="92e81-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="92e81-154">В списке результатов найдите **сообщение Фишинг** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="92e81-154">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="92e81-155">В диалоговом окте, который появится, просмотрите сведения о лицензировании и конфиденциальности, а затем нажмите **кнопку Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="92e81-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="92e81-156">На **странице Настройка надстройки,** которая появится, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="92e81-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="92e81-157">**Назначены пользователи:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="92e81-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="92e81-158">**Все** (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="92e81-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="92e81-159">**Конкретные пользователи / группы**</span><span class="sxs-lookup"><span data-stu-id="92e81-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="92e81-160">**Только я**</span><span class="sxs-lookup"><span data-stu-id="92e81-160">**Just me**</span></span>

   - <span data-ttu-id="92e81-161">**Метод развертывания:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="92e81-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="92e81-162">**Исправлено (по умолчанию).** Надстройка автоматически развертывается для указанных пользователей, и они не могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="92e81-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="92e81-163">**Доступно.** Пользователи могут установить надстройки в **Home** \> **Get надстройки,** \> **управляемые администратором.**</span><span class="sxs-lookup"><span data-stu-id="92e81-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="92e81-164">**Необязательный** вариант: надстройка автоматически развертывается для указанных пользователей, но они могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="92e81-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="92e81-165">По завершению щелкните **Развертывание**.</span><span class="sxs-lookup"><span data-stu-id="92e81-165">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="92e81-166">На странице **Развертывание фишинга** отчетов, которая отображается, вы увидите отчет о ходе выполнения, после чего будет подтверждено, что надстройка была развернута.</span><span class="sxs-lookup"><span data-stu-id="92e81-166">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="92e81-167">После прочтя сведений нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="92e81-167">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="92e81-168">На странице **Надстройка** "Объявить", которая появится, просмотрите сведения и нажмите **кнопку Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="92e81-168">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="92e81-169">Узнайте, как использовать надстройку Report Phishing</span><span class="sxs-lookup"><span data-stu-id="92e81-169">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="92e81-170">Люди, которым назначена надстройка, увидят следующие значки:</span><span class="sxs-lookup"><span data-stu-id="92e81-170">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="92e81-171">В Outlook значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="92e81-171">In Outlook, the icon looks like this:</span></span>

  ![Отчет о значке надстройки фишинга для Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="92e81-173">В Outlook веб-страницы значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="92e81-173">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook на значке надстройки фишинга веб-отчета](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="92e81-175">Просмотр или изменение параметров надстройки Report Phishing</span><span class="sxs-lookup"><span data-stu-id="92e81-175">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="92e81-176">В центре администрирования Microsoft 365 перейдите на страницу надстройки **Параметры** на странице , если вы не видите страницу надстройки, перейдите на ссылку Параметры Интегрированные надстройки приложений на верхней части страницы Интегрированные \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  приложения. </span><span class="sxs-lookup"><span data-stu-id="92e81-176">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="92e81-177">Найдите и выберите **надстройку Report Phishing.**</span><span class="sxs-lookup"><span data-stu-id="92e81-177">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="92e81-178">В **вылете Редактирование фишинговых** отчетов, которое отображается, просмотрите и отредактировать параметры, соответствующие вашей организации.</span><span class="sxs-lookup"><span data-stu-id="92e81-178">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="92e81-179">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="92e81-179">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="92e81-180">Просмотр и просмотр сообщений, о чем сообщалось</span><span class="sxs-lookup"><span data-stu-id="92e81-180">View and review reported messages</span></span>

<span data-ttu-id="92e81-181">Чтобы просмотреть сообщения, которые пользователи сообщают в Корпорацию Майкрософт, у вас есть такие параметры:</span><span class="sxs-lookup"><span data-stu-id="92e81-181">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="92e81-182">Используйте портал Отправки администратора.</span><span class="sxs-lookup"><span data-stu-id="92e81-182">Use the Admin Submissions portal.</span></span> <span data-ttu-id="92e81-183">Дополнительные сведения см. в [материале Просмотр пользовательских представлений в Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="92e81-183">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="92e81-184">Создайте правило потока почты (также известное как правило транспорта) для отправки копий сообщений.</span><span class="sxs-lookup"><span data-stu-id="92e81-184">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="92e81-185">Инструкции см. в инструкции Использование правил потока [почты, чтобы узнать, какие пользователи сообщают в Корпорацию Майкрософт.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="92e81-185">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
