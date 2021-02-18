---
title: Включить надстройка Report Phish
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
ms.openlocfilehash: 8242f3fcac27f8c76f7bef5a84c70960a204e3bd
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286661"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="c7867-103">Включение надстройки "Пожаловаться на фишинг"</span><span class="sxs-lookup"><span data-stu-id="c7867-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="c7867-104">Если вы администратор в организации Microsoft 365 с почтовыми ящиками Exchange Online, рекомендуем использовать портал "Отправки" в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c7867-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="c7867-105">Дополнительные сведения см. в документе "Отправка администратора" для отправки подозрительной нежелательной [почты, фишинга, URL-адресов и файлов в корпорацию Майкрософт.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c7867-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="c7867-106">Надстройки Report Message и Report Phishing для Outlook и Outlook в Интернете (прежнее название — Outlook Web App) позволяют пользователям легко сообщать о ложных срабатываниях (хорошая электронная почта помечена как пустая) или ложных отрицательных результатах (разрешены неверные сообщения) корпорации Майкрософт и ее аффилированным лицам для анализа.</span><span class="sxs-lookup"><span data-stu-id="c7867-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="c7867-107">Корпорация Майкрософт использует эти отправки для повышения эффективности технологий защиты электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c7867-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="c7867-108">Например, предположим, что люди сообщают о многих сообщениях с помощью надстройки Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="c7867-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="c7867-109">Эти сведения можно получить на панели мониторинга [безопасности](security-dashboard.md) и в других отчетах.</span><span class="sxs-lookup"><span data-stu-id="c7867-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="c7867-110">Группа безопасности вашей организации может использовать эти сведения в качестве указания на необходимость обновления политик защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="c7867-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="c7867-111">Вы можете установить надстройку Report Message или Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="c7867-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="c7867-112">Если вы хотите, чтобы пользователи сообщали о спаме и фишинговых сообщениях, разверните надстройку Report Message в своей организации.</span><span class="sxs-lookup"><span data-stu-id="c7867-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="c7867-113">Дополнительные сведения см. в [подстройки "Включить сообщение отчета".](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="c7867-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="c7867-114">Надстройка Report Phishing предоставляет возможность сообщать только о фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="c7867-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="c7867-115">Администраторы могут включить для организации надстройку Report Phishing, а отдельные пользователи могут установить ее самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="c7867-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="c7867-116">Если вы отдельный пользователь, вы можете включить для себя надстройку [Report Phishing.](#get-the-report-phishing-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="c7867-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="c7867-117">Если вы глобальный администратор или администратор Exchange Online, а в Exchange настроена проверка подлинности OAuth, вы можете включить для своей организации надстройку [Report Phishing.](#get-and-enable-the-report-phishing-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="c7867-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="c7867-118">Фишинговый отчет Add-In теперь доступен через [централизованное развертывание.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="c7867-118">The Report Phishing Add-In is now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c7867-119">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="c7867-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c7867-120">Надстройка Report Phishing работает с большинством подписок Microsoft 365 и следующими продуктами:</span><span class="sxs-lookup"><span data-stu-id="c7867-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="c7867-121">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="c7867-121">Outlook on the web</span></span>
  - <span data-ttu-id="c7867-122">Outlook 2013 с sp1 или более поздней</span><span class="sxs-lookup"><span data-stu-id="c7867-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="c7867-123">Outlook 2016 для Mac</span><span class="sxs-lookup"><span data-stu-id="c7867-123">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="c7867-124">Outlook, включенный в приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="c7867-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="c7867-125">Приложение Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="c7867-125">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="c7867-126">Надстройка Report Phishing недоступна для почтовых ящиков в локальной организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="c7867-126">The Report Phishing add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="c7867-127">Вы можете настроить копирование или перенаправление сообщений в задаемый почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="c7867-127">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="c7867-128">Дополнительные сведения [см. в политиках отправки пользователей.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c7867-128">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="c7867-129">Существующий веб-браузер должен работать с надстройой Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="c7867-129">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="c7867-130">Но если вы заметите, что надстройка недоступна или не работает ожидаемым образом, попробуйте другой браузер.</span><span class="sxs-lookup"><span data-stu-id="c7867-130">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="c7867-131">Для организационных установок необходимо настроить организацию на использование проверки подлинности OAuth.</span><span class="sxs-lookup"><span data-stu-id="c7867-131">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="c7867-132">Дополнительные сведения см. в подстройки "Определение работы централизованного развертывания надстройки [для организации".](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="c7867-132">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="c7867-133">Администраторы должны быть членами группы ролей "Глобальные администраторы".</span><span class="sxs-lookup"><span data-stu-id="c7867-133">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="c7867-134">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c7867-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="c7867-135">Получите для себя надстройку Report Phishing</span><span class="sxs-lookup"><span data-stu-id="c7867-135">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="c7867-136">Перейдите в Microsoft AppSource и найдите надстройку <https://appsource.microsoft.com/marketplace/apps> Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="c7867-136">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="c7867-137">Нажмите **КНОПКУ GET IT NOW**.</span><span class="sxs-lookup"><span data-stu-id="c7867-137">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="c7867-138">В от появляются диалоговое окно, просмотрите условия использования и политику конфиденциальности, а затем нажмите кнопку **"Продолжить.**</span><span class="sxs-lookup"><span data-stu-id="c7867-138">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="c7867-139">Во sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span><span class="sxs-lookup"><span data-stu-id="c7867-139">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="c7867-140">После установки и включения надстройки вы увидите следующие значки:</span><span class="sxs-lookup"><span data-stu-id="c7867-140">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="c7867-141">В Outlook значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="c7867-141">In Outlook, the icon looks like this:</span></span>

  ![Значок фишинговой надстройки для Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="c7867-143">В Outlook в Интернете значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="c7867-143">In Outlook on the web, the icon looks like this:</span></span>

  ![Значок фишинговой надстройки Outlook в Интернете](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="c7867-145">Получить и включить надстройку Report Phishing для вашей организации</span><span class="sxs-lookup"><span data-stu-id="c7867-145">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="c7867-146">Для появления надстройки в организации может занять до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="c7867-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="c7867-147">В Центре администрирования Microsoft 365 перейдите  на страницу "Надстройки параметров" в верхней части страницы "Интегрированные \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> приложения".   \>  \>  </span><span class="sxs-lookup"><span data-stu-id="c7867-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="c7867-148">Выберите **"Развернуть надстройки"** в верхней части страницы, а затем — **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="c7867-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Страница "Службы и надстройки" в Центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="c7867-150">В **окле "Развертывание новой** надстройки" просмотрите сведения и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="c7867-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="c7867-151">На следующей странице нажмите **кнопку "Выбрать из Магазина".**</span><span class="sxs-lookup"><span data-stu-id="c7867-151">On the next page, click **Choose from the Store**.</span></span>

   ![Развертывание новой страницы надстройки](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="c7867-153">На **отображаемой** странице "Выбор  надстройки" щелкните поле  "Поиск", введите "Сообщить о фишинге" **и** щелкните значок ![ ](../../media/search-icon.png) поиска.</span><span class="sxs-lookup"><span data-stu-id="c7867-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="c7867-154">В списке результатов найдите **фишинг** отчета и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="c7867-154">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="c7867-155">В от появляются диалоговое окно, просмотрите сведения о лицензировании и конфиденциальности, а затем нажмите кнопку **"Продолжить"**.</span><span class="sxs-lookup"><span data-stu-id="c7867-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="c7867-156">На **странице "Настройка надстройки"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c7867-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c7867-157">**Пользователи с назначенной** подписью: выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="c7867-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="c7867-158">**Все** (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c7867-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="c7867-159">**Конкретные пользователи и группы**</span><span class="sxs-lookup"><span data-stu-id="c7867-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="c7867-160">**Только я**</span><span class="sxs-lookup"><span data-stu-id="c7867-160">**Just me**</span></span>

   - <span data-ttu-id="c7867-161">**Метод развертывания:** выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="c7867-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="c7867-162">**Исправлено (по умолчанию):** надстройка автоматически развертывается для указанных пользователей, и они не могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="c7867-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="c7867-163">**Доступно:** пользователи могут установить надстройки на домашней сайте **Get** \> надстройки, **управляемые** \> **администратором.**</span><span class="sxs-lookup"><span data-stu-id="c7867-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="c7867-164">**Необязательно:** надстройка автоматически развертывается для указанных пользователей, но они могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="c7867-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="c7867-165">По завершению нажмите кнопку **"Развернуть".**</span><span class="sxs-lookup"><span data-stu-id="c7867-165">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="c7867-166">На странице **"Развертывание** фишинга отчета" появится отчет о ходе выполнения, а затем подтверждение развертывания надстройки.</span><span class="sxs-lookup"><span data-stu-id="c7867-166">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="c7867-167">После прочтия сведений нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="c7867-167">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="c7867-168">На **откроемой странице** "Объявить надстройки" просмотрите сведения и нажмите кнопку **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="c7867-168">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="c7867-169">Узнайте, как использовать надстройку Report Phishing</span><span class="sxs-lookup"><span data-stu-id="c7867-169">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="c7867-170">Люди, которым назначена надстройка, увидят следующие значки:</span><span class="sxs-lookup"><span data-stu-id="c7867-170">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="c7867-171">В Outlook значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="c7867-171">In Outlook, the icon looks like this:</span></span>

  ![Значок фишинговой надстройки для Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="c7867-173">В Outlook в Интернете значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="c7867-173">In Outlook on the web, the icon looks like this:</span></span>

  ![Значок фишинговой надстройки Outlook в Интернете](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="c7867-175">Просмотр или изменение параметров для надстройки Report Phishing</span><span class="sxs-lookup"><span data-stu-id="c7867-175">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="c7867-176">В Центре администрирования Microsoft 365 перейдите  на страницу "Надстройки параметров" в верхней части страницы "Интегрированные \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> приложения".   \>  \>  </span><span class="sxs-lookup"><span data-stu-id="c7867-176">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="c7867-177">Найдите и выберите **надстройку Report Phishing.**</span><span class="sxs-lookup"><span data-stu-id="c7867-177">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="c7867-178">В **отредактируемом окте** "Отчет о фишинге", который отображается, просмотрите и отредактируете параметры, соответствующие вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c7867-178">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="c7867-179">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c7867-179">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="c7867-180">Просмотр и просмотр сообщений, о чем сообщается</span><span class="sxs-lookup"><span data-stu-id="c7867-180">View and review reported messages</span></span>

<span data-ttu-id="c7867-181">Чтобы просмотреть сообщения, которые пользователи сообщают корпорации Майкрософт, можно получить указанные здесь варианты.</span><span class="sxs-lookup"><span data-stu-id="c7867-181">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="c7867-182">Используйте портал отправки администраторов.</span><span class="sxs-lookup"><span data-stu-id="c7867-182">Use the Admin Submissions portal.</span></span> <span data-ttu-id="c7867-183">Дополнительные сведения [см. в документе "Просмотр от отправленных пользователями данных в Корпорацию Майкрософт".](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="c7867-183">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="c7867-184">Создайте правило потока почты (также известное как правило транспорта) для отправки копий сообщений.</span><span class="sxs-lookup"><span data-stu-id="c7867-184">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="c7867-185">Инструкции см. в инструкциях по использованию правил потока почты, чтобы узнать, что ваши [пользователи сообщают корпорации Майкрософт.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="c7867-185">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
