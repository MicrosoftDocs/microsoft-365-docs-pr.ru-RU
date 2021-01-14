---
title: Включить надстройка Report Phish
f1.keywords:
- NOCSH
ms.author: siosulli
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
description: Узнайте, как включить надстройку Report Phishing для Outlook и Outlook в Интернете, для отдельных пользователей или всей организации.
ms.openlocfilehash: 2ea6a9bf9b00fc844aede6daeb9fc11f23c81e4a
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865286"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="bd370-103">Включить фишинговую надстройку report</span><span class="sxs-lookup"><span data-stu-id="bd370-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="bd370-104">Если вы администратор в организации Microsoft 365 с почтовыми ящиками Exchange Online, рекомендуем использовать портал "Отправки" в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="bd370-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="bd370-105">Дополнительные сведения см. в документе "Отправка администратора" для отправки подозрительной нежелательной [почты, фишинга, URL-адресов и файлов в корпорацию Майкрософт.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="bd370-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="bd370-106">Надстройки Report Message и Report Phishing для Outlook и Outlook в Интернете (прежнее название — Outlook Web App) позволяют пользователям легко сообщать о ложных срабатываниях (хорошая электронная почта, помеченная как пустая) или ложных отрицательных результатах (разрешена неверная почта) корпорации Майкрософт и ее аффилированным лицам для анализа.</span><span class="sxs-lookup"><span data-stu-id="bd370-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="bd370-107">Корпорация Майкрософт использует эти отправки для повышения эффективности технологий защиты электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bd370-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="bd370-108">Например, предположим, что люди сообщают о многих сообщениях с помощью надстройки Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="bd370-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="bd370-109">Эти сведения можно получить на панели мониторинга [безопасности](security-dashboard.md) и в других отчетах.</span><span class="sxs-lookup"><span data-stu-id="bd370-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="bd370-110">Группа безопасности вашей организации может использовать эти сведения в качестве указания на необходимость обновления политик защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="bd370-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="bd370-111">Вы можете установить надстройку Report Message или Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="bd370-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="bd370-112">Если вы хотите, чтобы пользователи сообщали о спаме и фишинговых сообщениях, разверните надстройку Report Message в своей организации.</span><span class="sxs-lookup"><span data-stu-id="bd370-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="bd370-113">Дополнительные сведения см. в [подстройки "Включить сообщение отчета".](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="bd370-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="bd370-114">Надстройка Report Phishing предоставляет возможность сообщать только о фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="bd370-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="bd370-115">Администраторы могут включить для организации надстройку Report Phishing, а отдельные пользователи могут установить ее самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="bd370-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="bd370-116">Если вы отдельный пользователь, вы можете включить для себя надстройку [Report Phishing.](#get-the-report-phishing-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="bd370-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="bd370-117">Если вы глобальный администратор или администратор Exchange Online, а Exchange настроен на использование проверки подлинности OAuth, вы можете включить для своей организации надстройку [Report Phishing.](#get-and-enable-the-report-phishing-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="bd370-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="bd370-118">Фишинговый отчет Add-In теперь доступен через [централизованное развертывание.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="bd370-118">The Report Phishing Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bd370-119">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="bd370-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bd370-120">Надстройка Report Phishing работает с большинством подписок Microsoft 365 и следующими продуктами:</span><span class="sxs-lookup"><span data-stu-id="bd370-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="bd370-121">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="bd370-121">Outlook on the web</span></span>
  - <span data-ttu-id="bd370-122">Outlook 2013 с sp1 или более поздней</span><span class="sxs-lookup"><span data-stu-id="bd370-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="bd370-123">Outlook 2016 для Mac</span><span class="sxs-lookup"><span data-stu-id="bd370-123">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="bd370-124">Outlook, включенный в приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="bd370-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="bd370-125">Надстройка Report Phishing недоступна для почтовых ящиков в локальной организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd370-125">The Report Phishing add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="bd370-126">Вы можете настроить копирование или перенаправление сообщений в задаемый почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="bd370-126">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="bd370-127">Дополнительные сведения [см. в политиках отправки пользователей.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="bd370-127">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="bd370-128">Существующий веб-браузер должен работать с надстройой Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="bd370-128">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="bd370-129">Но если вы заметите, что надстройка недоступна или не работает ожидаемым образом, попробуйте другой браузер.</span><span class="sxs-lookup"><span data-stu-id="bd370-129">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="bd370-130">Для организационных установок необходимо настроить организацию на использование проверки подлинности OAuth.</span><span class="sxs-lookup"><span data-stu-id="bd370-130">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="bd370-131">Дополнительные сведения см. в подстройки "Определение работы централизованного развертывания надстройки" [в организации.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="bd370-131">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="bd370-132">Администраторы должны быть членами группы ролей "Глобальные администраторы".</span><span class="sxs-lookup"><span data-stu-id="bd370-132">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="bd370-133">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="bd370-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="bd370-134">Получите для себя надстройку Report Phishing</span><span class="sxs-lookup"><span data-stu-id="bd370-134">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="bd370-135">Перейдите в Microsoft AppSource и найдите надстройку <https://appsource.microsoft.com/marketplace/apps> Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="bd370-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="bd370-136">Нажмите **КНОПКУ GET IT NOW**.</span><span class="sxs-lookup"><span data-stu-id="bd370-136">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="bd370-137">В от внешнем диалоговом окте просмотрите условия использования и политику конфиденциальности и нажмите кнопку **"Продолжить".**</span><span class="sxs-lookup"><span data-stu-id="bd370-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="bd370-138">Во sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span><span class="sxs-lookup"><span data-stu-id="bd370-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="bd370-139">После установки и включения надстройки вы увидите следующие значки:</span><span class="sxs-lookup"><span data-stu-id="bd370-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="bd370-140">В Outlook значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="bd370-140">In Outlook, the icon looks like this:</span></span>

  ![Значок фишинговой надстройки для Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="bd370-142">В Outlook в Интернете значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="bd370-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Значок фишинговой надстройки Outlook в Интернете](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="bd370-144">Получить и включить надстройку Report Phishing для вашей организации</span><span class="sxs-lookup"><span data-stu-id="bd370-144">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="bd370-145">Для появления надстройки в организации может занять до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="bd370-145">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="bd370-146">В Центре администрирования Microsoft 365 перейдите на страницу **"Параметры",** "Интегрированные приложения & надстройки" и нажмите кнопку "Развернуть <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> **надстройки".**</span><span class="sxs-lookup"><span data-stu-id="bd370-146">In the Microsoft 365 admin center, go to the **Settings, integrated Apps & Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, and then click **Deploy Add-In**.</span></span>

   ![Страница "Службы и надстройки" в Центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="bd370-148">В **окле "Развертывание новой** надстройки" просмотрите сведения и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="bd370-148">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="bd370-149">На следующей странице нажмите **кнопку "Выбрать из Магазина".**</span><span class="sxs-lookup"><span data-stu-id="bd370-149">On the next page, click **Choose from the Store**.</span></span>

   ![Развертывание новой страницы надстройки](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="bd370-151">На **отображаемой** странице "Выбор  надстройки" щелкните поле  "Поиск", введите "Сообщить о фишинге" **и** щелкните значок ![ ](../../media/search-icon.png) поиска.</span><span class="sxs-lookup"><span data-stu-id="bd370-151">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="bd370-152">В списке результатов найдите **фишинг** отчета и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="bd370-152">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

5. <span data-ttu-id="bd370-153">В от появляются диалоговое окно, просмотрите сведения о лицензировании и конфиденциальности, а затем нажмите кнопку **"Продолжить"**.</span><span class="sxs-lookup"><span data-stu-id="bd370-153">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="bd370-154">На **странице "Настройка надстройки"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="bd370-154">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="bd370-155">**Пользователи с назначенной** подписью: выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="bd370-155">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="bd370-156">**Все** (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="bd370-156">**Everyone** (default)</span></span>
     - <span data-ttu-id="bd370-157">**Конкретные пользователи и группы**</span><span class="sxs-lookup"><span data-stu-id="bd370-157">**Specific users / groups**</span></span>
     - <span data-ttu-id="bd370-158">**Только я**</span><span class="sxs-lookup"><span data-stu-id="bd370-158">**Just me**</span></span>

   - <span data-ttu-id="bd370-159">**Метод развертывания:** выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="bd370-159">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="bd370-160">**Исправлено (по умолчанию):** надстройка автоматически развертывается для указанных пользователей, и они не могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="bd370-160">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="bd370-161">**Доступно:** пользователи могут установить надстройки на **сайте Home** Get, управляемые \>  \> **администратором.**</span><span class="sxs-lookup"><span data-stu-id="bd370-161">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="bd370-162">**Необязательно:** надстройка автоматически развертывается для указанных пользователей, но они могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="bd370-162">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="bd370-163">По завершению нажмите кнопку **"Развернуть".**</span><span class="sxs-lookup"><span data-stu-id="bd370-163">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="bd370-164">На странице **"Развертывание** фишинга отчета" появится отчет о ходе выполнения, а затем подтверждение развертывания надстройки.</span><span class="sxs-lookup"><span data-stu-id="bd370-164">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="bd370-165">После прочтия сведений нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="bd370-165">After you read the information, click **Next**.</span></span>

8. <span data-ttu-id="bd370-166">На **откроемой странице** "Объявить надстройки" просмотрите сведения и нажмите кнопку **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="bd370-166">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="bd370-167">Узнайте, как использовать надстройку Report Phishing</span><span class="sxs-lookup"><span data-stu-id="bd370-167">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="bd370-168">Люди, которым назначена надстройка, увидят следующие значки:</span><span class="sxs-lookup"><span data-stu-id="bd370-168">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="bd370-169">В Outlook значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="bd370-169">In Outlook, the icon looks like this:</span></span>

  ![Значок фишинговой надстройки для Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="bd370-171">В Outlook в Интернете значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="bd370-171">In Outlook on the web, the icon looks like this:</span></span>

  ![Значок фишинговой надстройки Outlook в Интернете](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="bd370-173">Просмотр или изменение параметров для надстройки Report Phishing</span><span class="sxs-lookup"><span data-stu-id="bd370-173">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="bd370-174">В Центре администрирования Microsoft 365  перейдите на страницу "& надстройки" по этой <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> странице.</span><span class="sxs-lookup"><span data-stu-id="bd370-174">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

2. <span data-ttu-id="bd370-175">Найдите и выберите **надстройку Report Phishing.**</span><span class="sxs-lookup"><span data-stu-id="bd370-175">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="bd370-176">В **отредактируемом окте** "Отчет о фишинге", который отображается, просмотрите и отредактируете параметры, соответствующие вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bd370-176">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="bd370-177">Когда закончите, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="bd370-177">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="bd370-178">Просмотр и просмотр сообщений, о чем сообщается</span><span class="sxs-lookup"><span data-stu-id="bd370-178">View and review reported messages</span></span>

<span data-ttu-id="bd370-179">Чтобы просмотреть сообщения, которые пользователи сообщают в корпорацию Майкрософт, у вас есть указанные здесь варианты.</span><span class="sxs-lookup"><span data-stu-id="bd370-179">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="bd370-180">Используйте портал отправки администраторов.</span><span class="sxs-lookup"><span data-stu-id="bd370-180">Use the Admin Submissions portal.</span></span> <span data-ttu-id="bd370-181">Дополнительные сведения [см. в документе "Просмотр от отправленных пользователями данных в Корпорацию Майкрософт".](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="bd370-181">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="bd370-182">Создайте правило потока почты (также известное как правило транспорта) для отправки копий сообщений.</span><span class="sxs-lookup"><span data-stu-id="bd370-182">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="bd370-183">Инструкции см. в инструкциях по использованию правил потока почты, чтобы узнать, что ваши [пользователи сообщают корпорации Майкрософт.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="bd370-183">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>