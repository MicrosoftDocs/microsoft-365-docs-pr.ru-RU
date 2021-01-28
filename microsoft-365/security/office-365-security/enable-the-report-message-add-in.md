---
title: Включение надстройки "Пожаловаться на сообщение"
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Узнайте, как включить надстройки Report Message для Outlook и Outlook в Интернете, для отдельных пользователей или всей организации.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1f8cffaa6346ec7f426da3c862014ed85a9a367
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029236"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="00b13-103">Включение надстройки "Пожаловаться на сообщение"</span><span class="sxs-lookup"><span data-stu-id="00b13-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="00b13-104">Если вы администратор в организации Microsoft 365 с почтовыми ящиками Exchange Online, рекомендуем использовать портал "Отправки" в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="00b13-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="00b13-105">Дополнительные сведения см. в документе "Отправка администратора" для отправки подозрительной нежелательной [почты, фишинга, URL-адресов и файлов в корпорацию Майкрософт.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="00b13-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="00b13-106">Надстройки Report Message и Report Phishing для Outlook и Outlook в Интернете (прежнее название — Outlook Web App) позволяют пользователям легко сообщать о ложных срабатываниях (хорошая электронная почта помечена как пустая) или ложных отрицательных результатах (разрешена неверная почта) корпорации Майкрософт и ее аффилированным лицам для анализа.</span><span class="sxs-lookup"><span data-stu-id="00b13-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="00b13-107">Корпорация Майкрософт использует эти отправки для повышения эффективности технологий защиты электронной почты.</span><span class="sxs-lookup"><span data-stu-id="00b13-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="00b13-108">Например, если люди сообщают о многих сообщениях, которые были помечены как нежелательные с помощью надстройки Report Message, [](configure-your-spam-filter-policies.md)группе безопасности вашей организации может потребоваться настроить политики защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="00b13-108">For example, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="00b13-109">Вы можете установить надстройку Report Message или Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="00b13-109">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="00b13-110">Если вы хотите, чтобы пользователи сообщали только о фишинговых сообщениях, разверните надстройку Report Phishing в своей организации.</span><span class="sxs-lookup"><span data-stu-id="00b13-110">If you want your users to report only phishing messages, deploy the Report Phishing add-in in your organization.</span></span> <span data-ttu-id="00b13-111">Дополнительные сведения см. в [подстройки "Включить отчет о фишинге".](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="00b13-111">For more information, see [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="00b13-112">Надстройка Report Message предоставляет возможность сообщать о спаме и фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="00b13-112">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="00b13-113">Администраторы могут включить надстройка Report Message для организации, а отдельные пользователи могут установить ее самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="00b13-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="00b13-114">Если вы отдельный пользователь, вы можете включить надстройки [Report Message для себя.](#get-the-report-message-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="00b13-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="00b13-115">Если вы глобальный администратор или администратор Exchange Online, а в Exchange настроена проверка подлинности OAuth, вы можете включить надстройку Report Message для [своей организации.](#get-and-enable-the-report-message-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="00b13-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="00b13-116">Отчетный отчет Add-In теперь доступен через [централизованное развертывание.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="00b13-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="00b13-117">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="00b13-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="00b13-118">Надстройка Report Message работает с большинством подписок Microsoft 365 и следующими продуктами:</span><span class="sxs-lookup"><span data-stu-id="00b13-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="00b13-119">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="00b13-119">Outlook on the web</span></span>
  - <span data-ttu-id="00b13-120">Outlook 2013 с sp1 или более поздней</span><span class="sxs-lookup"><span data-stu-id="00b13-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="00b13-121">Outlook 2016 для Mac</span><span class="sxs-lookup"><span data-stu-id="00b13-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="00b13-122">Outlook, включенный в приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="00b13-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="00b13-123">Надстройка Report Message недоступна для почтовых ящиков в локальной организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="00b13-123">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="00b13-124">Вы можете настроить копирование или перенаправление сообщений в задаемый почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="00b13-124">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="00b13-125">Дополнительные сведения [см. в политиках отправки пользователей.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="00b13-125">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="00b13-126">Существующий веб-браузер должен работать с надстройой Report Message.</span><span class="sxs-lookup"><span data-stu-id="00b13-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="00b13-127">Но если вы заметите, что надстройка недоступна или не работает ожидаемым образом, попробуйте другой браузер.</span><span class="sxs-lookup"><span data-stu-id="00b13-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="00b13-128">Для организационных установок необходимо настроить организацию на использование проверки подлинности OAuth.</span><span class="sxs-lookup"><span data-stu-id="00b13-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="00b13-129">Дополнительные сведения см. в подстройки "Определение работы централизованного развертывания надстройки" [в организации.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="00b13-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="00b13-130">Администраторы должны быть членами группы ролей "Глобальные администраторы".</span><span class="sxs-lookup"><span data-stu-id="00b13-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="00b13-131">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="00b13-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="00b13-132">Получите для себя надстройка Report Message</span><span class="sxs-lookup"><span data-stu-id="00b13-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="00b13-133">Перейдите в Microsoft AppSource и найдите надстройки <https://appsource.microsoft.com/marketplace/apps> Report Message.</span><span class="sxs-lookup"><span data-stu-id="00b13-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="00b13-134">Чтобы перейти непосредственно к надстройки Report Message, перейдите к <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="00b13-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="00b13-135">Нажмите **КНОПКУ GET IT NOW**.</span><span class="sxs-lookup"><span data-stu-id="00b13-135">Click **GET IT NOW**.</span></span>

   ![Report Message - Get It Now](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="00b13-137">В от внешнем диалоговом окте просмотрите условия использования и политику конфиденциальности и нажмите кнопку **"Продолжить".**</span><span class="sxs-lookup"><span data-stu-id="00b13-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="00b13-138">Во sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span><span class="sxs-lookup"><span data-stu-id="00b13-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="00b13-139">После установки и включения надстройки вы увидите следующие значки:</span><span class="sxs-lookup"><span data-stu-id="00b13-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="00b13-140">В Outlook значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="00b13-140">In Outlook, the icon looks like this:</span></span>

  ![Значок надстройки Report Message для Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="00b13-142">В Outlook в Интернете значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="00b13-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Значок надстройки Outlook в Интернете Report Message](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="00b13-144">Чтобы узнать, как использовать надстройки, см. использование надстройки [Report Message.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="00b13-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="00b13-145">Get and enable the Report Message add-in for your organization</span><span class="sxs-lookup"><span data-stu-id="00b13-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="00b13-146">Для появления надстройки в организации может занять до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="00b13-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="00b13-147">В Центре администрирования Microsoft 365 перейдите  на страницу "Надстройки параметров" по ссылке "Если страница надстройки не видите", перейдите по ссылке "Надстройки, интегрированные в параметры" в верхней части страницы "Интегрированные \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  приложения". </span><span class="sxs-lookup"><span data-stu-id="00b13-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="00b13-148">Выберите **"Развернуть надстройки"** в верхней части страницы, а затем — **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="00b13-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Страница "Службы и надстройки" в Центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="00b13-150">В **окле "Развертывание новой** надстройки" просмотрите сведения и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="00b13-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="00b13-151">На следующей странице нажмите **кнопку "Выбрать из Магазина".**</span><span class="sxs-lookup"><span data-stu-id="00b13-151">On the next page, click **Choose from the Store**.</span></span>

   ![Развертывание новой страницы надстройки](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="00b13-153">На **отображаемой** странице "Выбор  надстройки" щелкните поле  "Поиск", введите сообщение **отчета,** а затем щелкните значок ![ ](../../media/search-icon.png) поиска.</span><span class="sxs-lookup"><span data-stu-id="00b13-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="00b13-154">В списке результатов найдите сообщение **отчета** и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="00b13-154">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Выбор результатов поиска надстройки](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="00b13-156">В от появляются диалоговое окно, просмотрите сведения о лицензировании и конфиденциальности, а затем нажмите кнопку **"Продолжить"**.</span><span class="sxs-lookup"><span data-stu-id="00b13-156">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="00b13-157">На **странице "Настройка надстройки"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="00b13-157">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="00b13-158">**Пользователи с назначенной** подписью: выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="00b13-158">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="00b13-159">**Все** (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="00b13-159">**Everyone** (default)</span></span>
     - <span data-ttu-id="00b13-160">**Конкретные пользователи и группы**</span><span class="sxs-lookup"><span data-stu-id="00b13-160">**Specific users / groups**</span></span>
     - <span data-ttu-id="00b13-161">**Только я**</span><span class="sxs-lookup"><span data-stu-id="00b13-161">**Just me**</span></span>

   - <span data-ttu-id="00b13-162">**Метод развертывания:** выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="00b13-162">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="00b13-163">**Исправлено (по умолчанию):** надстройка автоматически развертывается для указанных пользователей, и они не могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="00b13-163">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="00b13-164">**Доступно:** пользователи могут установить надстройки на **сайте Home** Get, управляемые \>  \> **администратором.**</span><span class="sxs-lookup"><span data-stu-id="00b13-164">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="00b13-165">**Необязательно:** надстройка автоматически развертывается для указанных пользователей, но они могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="00b13-165">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Страница настройки надстройки](../../media/configure-add-in.png)

   <span data-ttu-id="00b13-167">По завершению нажмите кнопку **"Развернуть".**</span><span class="sxs-lookup"><span data-stu-id="00b13-167">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="00b13-168">На странице **"Развертывание** сообщения отчета" появится отчет о ходе выполнения, а затем подтверждение развертывания надстройки.</span><span class="sxs-lookup"><span data-stu-id="00b13-168">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="00b13-169">После прочтия сведений нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="00b13-169">After you read the information, click **Next**.</span></span>

   ![Страница "Развертывание сообщения отчета"](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="00b13-171">На **откроемой странице** "Объявить надстройки" просмотрите сведения и нажмите кнопку **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="00b13-171">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Страница "Объявить надстройки"](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="00b13-173">Использование надстройки Report Message</span><span class="sxs-lookup"><span data-stu-id="00b13-173">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="00b13-174">Люди, которым назначена надстройка, увидят следующие значки:</span><span class="sxs-lookup"><span data-stu-id="00b13-174">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="00b13-175">В Outlook значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="00b13-175">In Outlook, the icon looks like this:</span></span>

  ![Значок надстройки Report Message для Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="00b13-177">В Outlook в Интернете значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="00b13-177">In Outlook on the web, the icon looks like this:</span></span>

  ![Значок надстройки "Сообщение в Outlook в Интернете"](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="00b13-179">Когда вы уведомляете пользователей о надстройки Report Message, включайте ссылку на использование надстройки [Report Message.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="00b13-179">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="00b13-180">Просмотр или изменение параметров надстройки Report Message</span><span class="sxs-lookup"><span data-stu-id="00b13-180">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="00b13-181">В Центре администрирования Microsoft 365 перейдите  на страницу "Надстройки параметров" по ссылке "Если страница надстройки не видите", перейдите по ссылке "Надстройки, интегрированные в параметры" в верхней части страницы "Интегрированные \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  приложения". </span><span class="sxs-lookup"><span data-stu-id="00b13-181">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Страница "Службы и Add-Ins" в новом Центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="00b13-183">Найдите и выберите **надстройки Report Message.**</span><span class="sxs-lookup"><span data-stu-id="00b13-183">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="00b13-184">В **отобра просмотреть** и изменить параметры в соответствующем для вашей организации октете "Изменение сообщения отчета".</span><span class="sxs-lookup"><span data-stu-id="00b13-184">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="00b13-185">Когда закончите, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="00b13-185">When you're finished, click **Save**.</span></span>

   ![Параметры надстройки Report Message](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="00b13-187">Просмотр и просмотр сообщений, о чем сообщается</span><span class="sxs-lookup"><span data-stu-id="00b13-187">View and review reported messages</span></span>

<span data-ttu-id="00b13-188">Чтобы просмотреть сообщения, которые пользователи сообщают в корпорацию Майкрософт, у вас есть указанные здесь варианты.</span><span class="sxs-lookup"><span data-stu-id="00b13-188">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="00b13-189">Используйте портал отправки администраторов.</span><span class="sxs-lookup"><span data-stu-id="00b13-189">Use the Admin Submissions portal.</span></span> <span data-ttu-id="00b13-190">Дополнительные сведения [см. в документе "Просмотр от отправленных пользователями данных в Корпорацию Майкрософт".](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="00b13-190">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="00b13-191">Создайте правило потока почты (также известное как правило транспорта) для отправки копий сообщений.</span><span class="sxs-lookup"><span data-stu-id="00b13-191">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="00b13-192">Инструкции см. в инструкциях по использованию правил потока почты, чтобы узнать, что ваши [пользователи сообщают корпорации Майкрософт.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="00b13-192">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
