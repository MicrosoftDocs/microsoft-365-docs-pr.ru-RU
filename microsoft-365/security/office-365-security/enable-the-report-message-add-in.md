---
title: Включить сообщение отчета или надстройки для фишинга отчетов
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
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
description: Узнайте, как включить надстройки Report Message или Report Phishing для Outlook и Outlook в Интернете, для отдельных пользователей или для всей организации.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 25c4f7d67fd4fa876544a17df0f4bc1abfd7b3e7
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782937"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="7be87-103">Включить сообщение отчета или надстройки для фишинга отчетов</span><span class="sxs-lookup"><span data-stu-id="7be87-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7be87-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="7be87-104">**Applies to**</span></span>
- [<span data-ttu-id="7be87-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7be87-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7be87-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="7be87-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7be87-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7be87-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="7be87-108">Если вы администратор в Microsoft 365 с Exchange Online почтовыми ящиками, рекомендуем использовать портал Отправки в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="7be87-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="7be87-109">Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="7be87-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="7be87-110">Надстройки для сообщений и сообщений о фишинге для Outlook и Outlook в Интернете (ранее известные как Outlook Web App) позволяют пользователям легко сообщать о ложных срабатываниях (хорошая электронная почта, помеченная как плохие) или ложных отрицательных (разрешена плохая электронная почта) в Корпорацию Майкрософт и ее филиалы для анализа.</span><span class="sxs-lookup"><span data-stu-id="7be87-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="7be87-111">Корпорация Майкрософт использует эти материалы для повышения эффективности технологий защиты электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7be87-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="7be87-112">Например, предположим, что люди сообщают много сообщений с помощью надстройки Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="7be87-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="7be87-113">Эти сведения будут использоваться в панели мониторинга безопасности и других отчетах.</span><span class="sxs-lookup"><span data-stu-id="7be87-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="7be87-114">Группа безопасности организации может использовать эти сведения в качестве указания на необходимость обновления политик защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="7be87-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="7be87-115">Можно установить надстройку Report Message или Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="7be87-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="7be87-116">Если вы хотите, чтобы пользователи сообщали о спаме и фишинговых сообщениях, разместите надстройку Report Message в организации.</span><span class="sxs-lookup"><span data-stu-id="7be87-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="7be87-117">Дополнительные сведения см. в добавлении Enable the Report Message.</span><span class="sxs-lookup"><span data-stu-id="7be87-117">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="7be87-118">Надстройка Report Message предоставляет возможность сообщать о спаме и фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="7be87-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="7be87-119">Администраторы могут включить надстройка Report Message для организации, а отдельные пользователи могут установить ее для себя.</span><span class="sxs-lookup"><span data-stu-id="7be87-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="7be87-120">Надстройка Report Phishing предоставляет возможность сообщать только о фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="7be87-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="7be87-121">Администраторы могут включить надстройку Report Phishing для организации, а отдельные пользователи могут установить ее для себя.</span><span class="sxs-lookup"><span data-stu-id="7be87-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="7be87-122">Если вы индивидуальный пользователь, вы можете включить оба надстройки для себя.</span><span class="sxs-lookup"><span data-stu-id="7be87-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="7be87-123">Если вы глобальный администратор или администратор Exchange Online и Exchange настроены на использование проверки подлинности OAuth, вы можете включить надстройку Report Message и надстройку Report Phishing для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7be87-123">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="7be87-124">Обе надстройки теперь доступны через [централизованное развертывание.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="7be87-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7be87-125">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="7be87-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7be87-126">Надстройка Сообщения отчетов и надстройка Report Phishing работают с большинством Microsoft 365 и следующими продуктами:</span><span class="sxs-lookup"><span data-stu-id="7be87-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="7be87-127">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="7be87-127">Outlook on the web</span></span>
  - <span data-ttu-id="7be87-128">Outlook 2013 sp1 или более поздней</span><span class="sxs-lookup"><span data-stu-id="7be87-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="7be87-129">Outlook 2016 для Mac;</span><span class="sxs-lookup"><span data-stu-id="7be87-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="7be87-130">Outlook в Microsoft 365 приложения для Enterprise</span><span class="sxs-lookup"><span data-stu-id="7be87-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="7be87-131">Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="7be87-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="7be87-132">Обе надстройки недоступны для общих почтовых ящиков или почтовых ящиков в Exchange организациях.</span><span class="sxs-lookup"><span data-stu-id="7be87-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="7be87-133">Существующий веб-браузер должен работать как с надстройки Report Message, так и с надстройки Report Phishing. Но если вы заметили, что надстройка недоступна или работает не так, как ожидалось, попробуйте другой браузер.</span><span class="sxs-lookup"><span data-stu-id="7be87-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="7be87-134">Для организационных установок необходимо настроить организацию для использования проверки подлинности OAuth.</span><span class="sxs-lookup"><span data-stu-id="7be87-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="7be87-135">Дополнительные сведения см. в [рубриках Определение,](../../admin/manage/centralized-deployment-of-add-ins.md)работает ли централизованное развертывание надстройок для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7be87-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="7be87-136">Администраторы должны быть членами группы ролей глобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="7be87-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="7be87-137">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7be87-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="7be87-138">Дополнительные сведения о том, как сообщить о сообщении с помощью функции Сообщение отчетов, см. в сообщении [Report false positives and false negatives in Outlook.](report-false-positives-and-false-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="7be87-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="7be87-139">Получить надстройки сообщения отчета</span><span class="sxs-lookup"><span data-stu-id="7be87-139">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="7be87-140">Получите надстройка для себя</span><span class="sxs-lookup"><span data-stu-id="7be87-140">Get the add-in for yourself</span></span>

1. <span data-ttu-id="7be87-141">Перейдите в Microsoft AppSource и <https://appsource.microsoft.com/marketplace/apps> найдите надстройки "Сообщение отчетов".</span><span class="sxs-lookup"><span data-stu-id="7be87-141">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="7be87-142">Чтобы перейти непосредственно к надстройки Сообщение отчета, перейдите к <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="7be87-142">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="7be87-143">Нажмите **КНОПКУ GET IT NOW**.</span><span class="sxs-lookup"><span data-stu-id="7be87-143">Click **GET IT NOW**.</span></span>

   ![Сообщение отчета — получите его сейчас](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="7be87-145">В диалоговом окантове, который появляется, просмотрите условия использования и политику конфиденциальности, а затем нажмите **кнопку Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="7be87-145">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="7be87-146">Впишитесь с помощью учетной записи работы или учебного заведения (для бизнеса) или учетной записи Майкрософт (для личного использования).</span><span class="sxs-lookup"><span data-stu-id="7be87-146">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="7be87-147">После установки и включения надстройки вы увидите следующие значки:</span><span class="sxs-lookup"><span data-stu-id="7be87-147">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="7be87-148">В Outlook значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="7be87-148">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="7be87-149">![Значок надстройки Report Message для Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="7be87-149">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="7be87-150">В Outlook веб-страницы значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="7be87-150">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="7be87-151">![Outlook значок надстройки "Сообщение о веб-отчете"](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="7be87-151">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="7be87-152">Получить надстройка для организации</span><span class="sxs-lookup"><span data-stu-id="7be87-152">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="7be87-153">Для появления надстройки в организации может занять до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="7be87-153">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="7be87-154">В центре Microsoft 365 администрирования перейдите на страницу Параметры  \> **надстройки** по <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> крайней .</span><span class="sxs-lookup"><span data-stu-id="7be87-154">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="7be87-155">Если вы не видите  страницу надстройки, перейдите к **ссылке Параметры** интегрированных надстройок приложений в верхней части страницы \>  \>  **Интегрированные** приложения.</span><span class="sxs-lookup"><span data-stu-id="7be87-155">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="7be87-156">Выберите **развертывание надстройки** в верхней части страницы, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7be87-156">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Страница Службы и надстройки в центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="7be87-158">В **развертывании новой** надстройки, которая появится, просмотрите сведения, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="7be87-158">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="7be87-159">На следующей странице нажмите **кнопку Выберите из магазина**.</span><span class="sxs-lookup"><span data-stu-id="7be87-159">On the next page, click **Choose from the Store**.</span></span>

   ![Развертывание новой страницы надстройки](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="7be87-161">На странице **Выберите надстройку,** которая  появится, щелкните в поле Поиск, **введите** сообщение отчета, а затем нажмите **значок Поиск** поиска ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="7be87-161">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="7be87-162">В списке результатов найдите **сообщение отчета** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7be87-162">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Выбор результатов поиска надстройки](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="7be87-164">В диалоговом окте, который появится, просмотрите сведения о лицензировании и конфиденциальности, а затем нажмите **кнопку Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="7be87-164">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="7be87-165">На **странице Настройка надстройки,** которая появится, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="7be87-165">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="7be87-166">**Назначены пользователи:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="7be87-166">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="7be87-167">**Все** (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7be87-167">**Everyone** (default)</span></span>
     - <span data-ttu-id="7be87-168">**Конкретные пользователи / группы**</span><span class="sxs-lookup"><span data-stu-id="7be87-168">**Specific users / groups**</span></span>
     - <span data-ttu-id="7be87-169">**Только я**</span><span class="sxs-lookup"><span data-stu-id="7be87-169">**Just me**</span></span>

   - <span data-ttu-id="7be87-170">**Метод развертывания:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="7be87-170">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="7be87-171">**Исправлено (по умолчанию).** Надстройка автоматически развертывается для указанных пользователей, и они не могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="7be87-171">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="7be87-172">**Доступно.** Пользователи могут установить надстройки в **Home** \> **Get надстройки,** \> **управляемые администратором.**</span><span class="sxs-lookup"><span data-stu-id="7be87-172">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="7be87-173">**Необязательный** вариант: надстройка автоматически развертывается для указанных пользователей, но они могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="7be87-173">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Настройка страницы надстройки](../../media/configure-add-in.png)

   <span data-ttu-id="7be87-175">По завершению щелкните **Развертывание**.</span><span class="sxs-lookup"><span data-stu-id="7be87-175">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="7be87-176">На странице **Развертывание сообщения отчетов,** которая отображается, вы увидите отчет о ходе выполнения, за которым следует подтверждение развертывания надстройки.</span><span class="sxs-lookup"><span data-stu-id="7be87-176">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="7be87-177">После прочтя сведений нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7be87-177">After you read the information, click **Next**.</span></span>

   ![Развертывание страницы сообщения отчета](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="7be87-179">На странице **Надстройка** "Объявить", которая появится, просмотрите сведения и нажмите **кнопку Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7be87-179">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Объявить страницу надстройки](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="7be87-181">Просмотр или изменение параметров надстройки "Сообщение отчетов"</span><span class="sxs-lookup"><span data-stu-id="7be87-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="7be87-182">В центре Microsoft 365 администрирования перейдите на страницу Параметры  \> **надстройки** по <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> крайней .</span><span class="sxs-lookup"><span data-stu-id="7be87-182">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="7be87-183">Если вы не видите  страницу надстройки, перейдите к **ссылке Параметры** интегрированных надстройок приложений в верхней части страницы \>  \>  **Интегрированные** приложения.</span><span class="sxs-lookup"><span data-stu-id="7be87-183">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Службы и Add-Ins в новом центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="7be87-185">Найдите и выберите **надстройка "Сообщение** отчетов".</span><span class="sxs-lookup"><span data-stu-id="7be87-185">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="7be87-186">В **вылете Сообщение** об редактировании отчетов, которое отображается, просмотрите и отредактируете параметры, соответствующие вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7be87-186">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="7be87-187">По завершении нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7be87-187">When you're finished, click **Save**.</span></span>

   ![Параметры надстройки "Сообщение отчетов"](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="7be87-189">Получить надстройку Для фишинга отчетов</span><span class="sxs-lookup"><span data-stu-id="7be87-189">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="7be87-190">Получите надстройка для себя</span><span class="sxs-lookup"><span data-stu-id="7be87-190">Get the add-in for yourself</span></span>

1. <span data-ttu-id="7be87-191">Перейдите в Microsoft AppSource и <https://appsource.microsoft.com/marketplace/apps> найдите надстройку Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="7be87-191">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="7be87-192">Нажмите **КНОПКУ GET IT NOW**.</span><span class="sxs-lookup"><span data-stu-id="7be87-192">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="7be87-193">В диалоговом окантове, который появляется, просмотрите условия использования и политику конфиденциальности, а затем нажмите **кнопку Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="7be87-193">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="7be87-194">Впишитесь с помощью учетной записи работы или учебного заведения (для бизнеса) или учетной записи Майкрософт (для личного использования).</span><span class="sxs-lookup"><span data-stu-id="7be87-194">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="7be87-195">После установки и включения надстройки вы увидите следующие значки:</span><span class="sxs-lookup"><span data-stu-id="7be87-195">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="7be87-196">В Outlook значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="7be87-196">In Outlook, the icon looks like this:</span></span>

  ![Отчет о значке надстройки фишинга для Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="7be87-198">В Outlook веб-страницы значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="7be87-198">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="7be87-199">![Outlook на значке надстройки фишинга веб-отчета](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="7be87-199">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="7be87-200">Получить надстройка для организации</span><span class="sxs-lookup"><span data-stu-id="7be87-200">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="7be87-201">Для появления надстройки в организации может занять до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="7be87-201">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="7be87-202">В центре Microsoft 365 администрирования перейдите на страницу Параметры  \> **надстройки** по <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> крайней .</span><span class="sxs-lookup"><span data-stu-id="7be87-202">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="7be87-203">Если вы не видите  страницу надстройки, перейдите к **ссылке Параметры** интегрированных надстройок приложений в верхней части страницы \>  \>  **Интегрированные** приложения.</span><span class="sxs-lookup"><span data-stu-id="7be87-203">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="7be87-204">Выберите **развертывание надстройки** в верхней части страницы, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7be87-204">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Страница Службы и надстройки в центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="7be87-206">В **развертывании новой** надстройки, которая появится, просмотрите сведения, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="7be87-206">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="7be87-207">На следующей странице нажмите **кнопку Выберите из магазина**.</span><span class="sxs-lookup"><span data-stu-id="7be87-207">On the next page, click **Choose from the Store**.</span></span>

   ![Развертывание новой страницы надстройки](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="7be87-209">На странице **Выбор надстройки,** которая появится, нажмите кнопку в поле **Поиск,** введите **сообщение** фишинг, а затем нажмите **значок Поиска** ![ поиска ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="7be87-209">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="7be87-210">В списке результатов найдите **сообщение Фишинг** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7be87-210">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="7be87-211">В диалоговом окте, который появится, просмотрите сведения о лицензировании и конфиденциальности, а затем нажмите **кнопку Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="7be87-211">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="7be87-212">На **странице Настройка надстройки,** которая появится, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="7be87-212">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="7be87-213">**Назначены пользователи:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="7be87-213">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="7be87-214">**Все** (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7be87-214">**Everyone** (default)</span></span>
     - <span data-ttu-id="7be87-215">**Конкретные пользователи / группы**</span><span class="sxs-lookup"><span data-stu-id="7be87-215">**Specific users / groups**</span></span>
     - <span data-ttu-id="7be87-216">**Только я**</span><span class="sxs-lookup"><span data-stu-id="7be87-216">**Just me**</span></span>

   - <span data-ttu-id="7be87-217">**Метод развертывания:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="7be87-217">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="7be87-218">**Исправлено (по умолчанию).** Надстройка автоматически развертывается для указанных пользователей, и они не могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="7be87-218">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="7be87-219">**Доступно.** Пользователи могут установить надстройки в **Home** \> **Get надстройки,** \> **управляемые администратором.**</span><span class="sxs-lookup"><span data-stu-id="7be87-219">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="7be87-220">**Необязательный** вариант: надстройка автоматически развертывается для указанных пользователей, но они могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="7be87-220">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="7be87-221">По завершению щелкните **Развертывание**.</span><span class="sxs-lookup"><span data-stu-id="7be87-221">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="7be87-222">На странице **Развертывание фишинга** отчетов, которая отображается, вы увидите отчет о ходе выполнения, после чего будет подтверждено, что надстройка была развернута.</span><span class="sxs-lookup"><span data-stu-id="7be87-222">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="7be87-223">После прочтя сведений нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7be87-223">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="7be87-224">На странице **Надстройка** "Объявить", которая появится, просмотрите сведения и нажмите **кнопку Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7be87-224">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="7be87-225">Просмотр или изменение параметров надстройки Report Phishing</span><span class="sxs-lookup"><span data-stu-id="7be87-225">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="7be87-226">В центре Microsoft 365 администрирования перейдите на страницу Параметры  \> **надстройки** по <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> крайней .</span><span class="sxs-lookup"><span data-stu-id="7be87-226">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="7be87-227">Если вы не видите  страницу надстройки, перейдите к **ссылке Параметры** интегрированных надстройок приложений в верхней части страницы \>  \>  **Интегрированные** приложения.</span><span class="sxs-lookup"><span data-stu-id="7be87-227">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="7be87-228">Найдите и выберите **надстройку Report Phishing.**</span><span class="sxs-lookup"><span data-stu-id="7be87-228">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="7be87-229">В **вылете Редактирование фишинговых** отчетов, которое отображается, просмотрите и отредактировать параметры, соответствующие вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7be87-229">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="7be87-230">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7be87-230">When you're finished, click **Save**.</span></span>
