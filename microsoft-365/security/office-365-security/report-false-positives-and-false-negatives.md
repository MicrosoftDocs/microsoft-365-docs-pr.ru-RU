---
title: Сообщение о ложных срабатывавах и ложных отрицательных результатах в Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Узнайте, как сообщать о ложных срабатываниях и ложных отрицательных результатах в Outlook и включить надстройки Report Message and Report Phishing.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38f940a98581c5678eef0c57c95f6349cdb41de8
ms.sourcegitcommit: ddb1bf56bcba4f03c803f79492e8cd0dc41a3d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2021
ms.locfileid: "52065208"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="17b66-103">Сообщение о ложных срабатывавах и ложных отрицательных результатах в Outlook</span><span class="sxs-lookup"><span data-stu-id="17b66-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="17b66-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="17b66-104">**Applies to**</span></span>
- [<span data-ttu-id="17b66-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="17b66-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="17b66-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="17b66-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="17b66-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="17b66-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="17b66-108">Если вы администратор в организации Microsoft 365 с почтовыми ящиками Exchange Online, рекомендуем использовать портал Отправки в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="17b66-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="17b66-109">Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="17b66-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="17b66-110">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в локальном почтовом ящике с использованием гибридной современной проверки подлинности можно отправлять ложные срабатывания (хорошая электронная почта, помеченная как спам) и ложные негативы (ненадежная электронная почта и фишинг разрешено) в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="17b66-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email marked as spam) and false negatives (bad email and phish allowed) to Exchange Online Protection (EOP).</span></span>

## <a name="things-to-remember-before-you-use-the-report-message-feature"></a><span data-ttu-id="17b66-111">Что следует помнить перед использованием функции "Сообщение отчета"</span><span class="sxs-lookup"><span data-stu-id="17b66-111">Things to remember before you use the Report Message feature</span></span>

- <span data-ttu-id="17b66-112">Для наилучшего использования пользовательской отправки используйте надстройку Report Message или надстройку Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="17b66-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="17b66-113">Обратите внимание, что эта надстройка работает для Outlook на всех платформах: в Интернете, iOS, Android и Desktop.</span><span class="sxs-lookup"><span data-stu-id="17b66-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="17b66-114">Если вы администратор в организации с почтовыми ящиками Exchange Online, используйте портал Отправки в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="17b66-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="17b66-115">Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="17b66-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="17b66-116">Вы можете настроить отправку сообщений непосредственно в Корпорацию Майкрософт, в почтовый ящик, который вы указываете, или оба.</span><span class="sxs-lookup"><span data-stu-id="17b66-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="17b66-117">Дополнительные сведения см. [в материале Политики отправки пользователей.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="17b66-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="17b66-118">Дополнительные сведения об отчетах о сообщениях в Корпорации Майкрософт см. в материалах [Report messages and files to Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="17b66-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="17b66-119">Использование функции сообщения отчета</span><span class="sxs-lookup"><span data-stu-id="17b66-119">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="17b66-120">Сообщение о нежелательных и фишинговых сообщениях</span><span class="sxs-lookup"><span data-stu-id="17b66-120">Report junk and phishing messages</span></span>

<span data-ttu-id="17b66-121">Для сообщений в папке "Входящие" или любой другой папки электронной почты, кроме нежелательной почты, используйте следующий метод для сообщения о нежелательной почте и фишинговых сообщениях:</span><span class="sxs-lookup"><span data-stu-id="17b66-121">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="17b66-122">Щелкните **эллипсы** Больше действий в правом верхнем углу выбранного сообщения, щелкните сообщение **Отчет** из выпадаемого меню, а затем выберите **нежелательное** или **фишинговое** сообщение.</span><span class="sxs-lookup"><span data-stu-id="17b66-122">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>
  
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="17b66-123">![Сообщение отчетов — дополнительные действия](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="17b66-123">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="17b66-124">![Сообщение отчета — нежелательное и фишинговое сообщение](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="17b66-124">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="17b66-125">Выбранные сообщения будут отправлены в Корпорацию Майкрософт для анализа и:</span><span class="sxs-lookup"><span data-stu-id="17b66-125">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="17b66-126">Перемещается в папку нежелательной почты, если сообщение о ней сообщается как спам.</span><span class="sxs-lookup"><span data-stu-id="17b66-126">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="17b66-127">Удаляется, если оно было отчитано как фишинг.</span><span class="sxs-lookup"><span data-stu-id="17b66-127">Deleted if it was reported as phishing.</span></span>
   
### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="17b66-128">Сообщения, которые не являются нежелательными</span><span class="sxs-lookup"><span data-stu-id="17b66-128">Report messages that are not junk</span></span>

1. <span data-ttu-id="17b66-129">Щелкните **эллипсы** Больше действий в правом верхнем углу выбранного сообщения, щелкните сообщение **Отчет** из выпадаемого меню, а затем нажмите **кнопку Не нежелательной**.</span><span class="sxs-lookup"><span data-stu-id="17b66-129">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="17b66-130">![Сообщение отчетов — дополнительные действия](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="17b66-130">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="17b66-131">![Сообщение отчетов — не нежелательное](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="17b66-131">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="17b66-132">Выбранное сообщение будет отправлено в Корпорацию Майкрософт для анализа и перемещено в папку "Входящие" или любую другую указанную папку.</span><span class="sxs-lookup"><span data-stu-id="17b66-132">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="enable-the-report-message-and-report-phishing-add-ins"></a><span data-ttu-id="17b66-133">Включить надстройки "Сообщение отчетов" и "Сообщение о фишинге"</span><span class="sxs-lookup"><span data-stu-id="17b66-133">Enable the Report Message and Report Phishing add-ins</span></span>

<span data-ttu-id="17b66-134">Надстройки Для Outlook и Outlook в Интернете (ранее известные как Outlook Web App) позволяют пользователям легко сообщать о ложных срабатываниях (хорошая электронная почта, помеченная как плохие) или ложных отрицательных (разрешенная плохая электронная почта) в Корпорацию Майкрософт и ее филиалы для анализа.</span><span class="sxs-lookup"><span data-stu-id="17b66-134">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="17b66-135">Корпорация Майкрософт использует эти материалы для повышения эффективности технологий защиты электронной почты.</span><span class="sxs-lookup"><span data-stu-id="17b66-135">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="17b66-136">Например, предположим, что люди сообщают много сообщений с помощью надстройки Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="17b66-136">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="17b66-137">Эти сведения будут использоваться в панели мониторинга безопасности и других отчетах.</span><span class="sxs-lookup"><span data-stu-id="17b66-137">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="17b66-138">Группа безопасности организации может использовать эти сведения в качестве указания на необходимость обновления политик защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="17b66-138">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="17b66-139">Можно установить надстройку Report Message или Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="17b66-139">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="17b66-140">Если вы хотите, чтобы пользователи сообщали о спаме и фишинговых сообщениях, разместите надстройку Report Message в организации.</span><span class="sxs-lookup"><span data-stu-id="17b66-140">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="17b66-141">Дополнительные сведения см. в добавлении Enable the Report Message.</span><span class="sxs-lookup"><span data-stu-id="17b66-141">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="17b66-142">Надстройка Report Message предоставляет возможность сообщать о спаме и фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="17b66-142">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="17b66-143">Администраторы могут включить надстройка Report Message для организации, а отдельные пользователи могут установить ее для себя.</span><span class="sxs-lookup"><span data-stu-id="17b66-143">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="17b66-144">Надстройка Report Phishing предоставляет возможность сообщать только о фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="17b66-144">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="17b66-145">Администраторы могут включить надстройку Report Phishing для организации, а отдельные пользователи могут установить ее для себя.</span><span class="sxs-lookup"><span data-stu-id="17b66-145">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="17b66-146">Если вы индивидуальный пользователь, вы можете включить оба надстройки для себя.</span><span class="sxs-lookup"><span data-stu-id="17b66-146">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="17b66-147">f Вы глобальный администратор или администратор Exchange Online, и Exchange настроена на использование проверки подлинности OAuth, вы можете включить надстройку Report Message и надстройку Report Phishing для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="17b66-147">f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="17b66-148">Обе надстройки теперь доступны через [централизованное развертывание.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="17b66-148">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="17b66-149">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="17b66-149">What do you need to know before you begin?</span></span>

- <span data-ttu-id="17b66-150">Надстройка Сообщения отчетов и надстройка Report Phishing работают с большинством подписок Microsoft 365 и следующими продуктами:</span><span class="sxs-lookup"><span data-stu-id="17b66-150">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="17b66-151">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="17b66-151">Outlook on the web</span></span>
  - <span data-ttu-id="17b66-152">Outlook 2013 SP1 или более поздний</span><span class="sxs-lookup"><span data-stu-id="17b66-152">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="17b66-153">Outlook 2016 для Mac;</span><span class="sxs-lookup"><span data-stu-id="17b66-153">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="17b66-154">Outlook, включенный в приложения Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="17b66-154">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="17b66-155">Приложение Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="17b66-155">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="17b66-156">Обе надстройки недоступны для общих почтовых ящиков или почтовых ящиков в локальной организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="17b66-156">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="17b66-157">Существующий веб-браузер должен работать как с надстройки Report Message, так и с надстройки Report Phishing. Но если вы заметили, что надстройка недоступна или работает не так, как ожидалось, попробуйте другой браузер.</span><span class="sxs-lookup"><span data-stu-id="17b66-157">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="17b66-158">Для организационных установок необходимо настроить организацию для использования проверки подлинности OAuth.</span><span class="sxs-lookup"><span data-stu-id="17b66-158">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="17b66-159">Дополнительные сведения см. в [рубриках Определение,](../../admin/manage/centralized-deployment-of-add-ins.md)работает ли централизованное развертывание надстройок для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="17b66-159">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="17b66-160">Администраторы должны быть членами группы ролей глобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="17b66-160">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="17b66-161">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="17b66-161">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="17b66-162">Получить надстройки сообщения отчета</span><span class="sxs-lookup"><span data-stu-id="17b66-162">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="17b66-163">Получите надстройка для себя</span><span class="sxs-lookup"><span data-stu-id="17b66-163">Get the add-in for yourself</span></span>

1. <span data-ttu-id="17b66-164">Перейдите в Microsoft AppSource и <https://appsource.microsoft.com/marketplace/apps> найдите надстройки "Сообщение отчетов".</span><span class="sxs-lookup"><span data-stu-id="17b66-164">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="17b66-165">Чтобы перейти непосредственно к надстройки Сообщение отчета, перейдите к <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="17b66-165">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="17b66-166">Нажмите **КНОПКУ GET IT NOW**.</span><span class="sxs-lookup"><span data-stu-id="17b66-166">Click **GET IT NOW**.</span></span>

   ![Сообщение отчета — получите его сейчас](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="17b66-168">В диалоговом окантове, который появляется, просмотрите условия использования и политику конфиденциальности, а затем нажмите **кнопку Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="17b66-168">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="17b66-169">Впишитесь с помощью учетной записи работы или учебного заведения (для бизнеса) или учетной записи Майкрософт (для личного использования).</span><span class="sxs-lookup"><span data-stu-id="17b66-169">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="17b66-170">После установки и включения надстройки вы увидите следующие значки:</span><span class="sxs-lookup"><span data-stu-id="17b66-170">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="17b66-171">В Outlook значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="17b66-171">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="17b66-172">![Значок надстройки Report Message для Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="17b66-172">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="17b66-173">В Outlook в Интернете значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="17b66-173">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="17b66-174">![Outlook на значке надстройки "Сообщение о веб-отчете"](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="17b66-174">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="17b66-175">Получить надстройка для организации</span><span class="sxs-lookup"><span data-stu-id="17b66-175">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="17b66-176">Для появления надстройки в организации может занять до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="17b66-176">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="17b66-177">В центре администрирования Microsoft 365 перейдите на страницу **Параметры** надстройки \>  по <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> крайней .</span><span class="sxs-lookup"><span data-stu-id="17b66-177">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="17b66-178">Если вы не видите  страницу надстройки, перейдите к ссылке Надстройки "Параметры интегрированных приложений" в верхней части страницы  \>  \>  **Интегрированные** приложения.</span><span class="sxs-lookup"><span data-stu-id="17b66-178">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="17b66-179">Выберите **развертывание надстройки** в верхней части страницы, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="17b66-179">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Страница Службы и надстройки в центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="17b66-181">В **развертывании новой** надстройки, которая появится, просмотрите сведения, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="17b66-181">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="17b66-182">На следующей странице нажмите **кнопку Выберите из магазина**.</span><span class="sxs-lookup"><span data-stu-id="17b66-182">On the next page, click **Choose from the Store**.</span></span>

   ![Развертывание новой страницы надстройки](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="17b66-184">На странице **Выберите надстройку,** которая  появится, щелкните в поле Поиск, **введите** сообщение отчета, а затем нажмите **значок Поиск** поиска ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="17b66-184">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="17b66-185">В списке результатов найдите **сообщение отчета** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="17b66-185">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Выбор результатов поиска надстройки](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="17b66-187">В диалоговом окте, который появится, просмотрите сведения о лицензировании и конфиденциальности, а затем нажмите **кнопку Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="17b66-187">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="17b66-188">На **странице Настройка надстройки,** которая появится, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="17b66-188">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="17b66-189">**Назначены пользователи:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="17b66-189">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="17b66-190">**Все** (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="17b66-190">**Everyone** (default)</span></span>
     - <span data-ttu-id="17b66-191">**Конкретные пользователи / группы**</span><span class="sxs-lookup"><span data-stu-id="17b66-191">**Specific users / groups**</span></span>
     - <span data-ttu-id="17b66-192">**Только я**</span><span class="sxs-lookup"><span data-stu-id="17b66-192">**Just me**</span></span>

   - <span data-ttu-id="17b66-193">**Метод развертывания:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="17b66-193">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="17b66-194">**Исправлено (по умолчанию).** Надстройка автоматически развертывается для указанных пользователей, и они не могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="17b66-194">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="17b66-195">**Доступно.** Пользователи могут установить надстройки в **Home** \> **Get надстройки,** \> **управляемые администратором.**</span><span class="sxs-lookup"><span data-stu-id="17b66-195">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="17b66-196">**Необязательный** вариант: надстройка автоматически развертывается для указанных пользователей, но они могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="17b66-196">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Настройка страницы надстройки](../../media/configure-add-in.png)

   <span data-ttu-id="17b66-198">По завершению щелкните **Развертывание**.</span><span class="sxs-lookup"><span data-stu-id="17b66-198">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="17b66-199">На странице **Развертывание сообщения отчетов,** которая отображается, вы увидите отчет о ходе выполнения, за которым следует подтверждение развертывания надстройки.</span><span class="sxs-lookup"><span data-stu-id="17b66-199">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="17b66-200">После прочтя сведений нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="17b66-200">After you read the information, click **Next**.</span></span>

   ![Развертывание страницы сообщения отчета](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="17b66-202">На странице **Надстройка** "Объявить", которая появится, просмотрите сведения и нажмите **кнопку Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="17b66-202">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Объявить страницу надстройки](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="17b66-204">Просмотр или изменение параметров надстройки "Сообщение отчетов"</span><span class="sxs-lookup"><span data-stu-id="17b66-204">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="17b66-205">В центре администрирования Microsoft 365 перейдите на страницу **Параметры** надстройки \>  по <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> крайней .</span><span class="sxs-lookup"><span data-stu-id="17b66-205">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="17b66-206">Если вы не видите  страницу надстройки, перейдите к ссылке Надстройки "Параметры интегрированных приложений" в верхней части страницы  \>  \>  **Интегрированные** приложения.</span><span class="sxs-lookup"><span data-stu-id="17b66-206">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Службы и Add-Ins в новом центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="17b66-208">Найдите и выберите **надстройка "Сообщение** отчетов".</span><span class="sxs-lookup"><span data-stu-id="17b66-208">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="17b66-209">В **вылете Сообщение** об редактировании отчетов, которое отображается, просмотрите и отредактируете параметры, соответствующие вашей организации.</span><span class="sxs-lookup"><span data-stu-id="17b66-209">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="17b66-210">По завершении нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="17b66-210">When you're finished, click **Save**.</span></span>

   ![Параметры надстройки "Сообщение отчетов"](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="17b66-212">Получить надстройку Для фишинга отчетов</span><span class="sxs-lookup"><span data-stu-id="17b66-212">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="17b66-213">Получите надстройка для себя</span><span class="sxs-lookup"><span data-stu-id="17b66-213">Get the add-in for yourself</span></span>

1. <span data-ttu-id="17b66-214">Перейдите в Microsoft AppSource и <https://appsource.microsoft.com/marketplace/apps> найдите надстройку Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="17b66-214">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="17b66-215">Нажмите **КНОПКУ GET IT NOW**.</span><span class="sxs-lookup"><span data-stu-id="17b66-215">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="17b66-216">В диалоговом окантове, который появляется, просмотрите условия использования и политику конфиденциальности, а затем нажмите **кнопку Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="17b66-216">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="17b66-217">Впишитесь с помощью учетной записи работы или учебного заведения (для бизнеса) или учетной записи Майкрософт (для личного использования).</span><span class="sxs-lookup"><span data-stu-id="17b66-217">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="17b66-218">После установки и включения надстройки вы увидите следующие значки:</span><span class="sxs-lookup"><span data-stu-id="17b66-218">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="17b66-219">В Outlook значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="17b66-219">In Outlook, the icon looks like this:</span></span>

  ![Отчет о значке надстройки фишинга для Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="17b66-221">В Outlook в Интернете значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="17b66-221">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="17b66-222">![Outlook на значке надстройки фишинга веб-отчета](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="17b66-222">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="17b66-223">Получить надстройка для организации</span><span class="sxs-lookup"><span data-stu-id="17b66-223">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="17b66-224">Для появления надстройки в организации может занять до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="17b66-224">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="17b66-225">В центре администрирования Microsoft 365 перейдите на страницу **Параметры** надстройки \>  по <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> крайней .</span><span class="sxs-lookup"><span data-stu-id="17b66-225">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="17b66-226">Если вы не видите  страницу надстройки, перейдите к ссылке Надстройки "Параметры интегрированных приложений" в верхней части страницы  \>  \>  **Интегрированные** приложения.</span><span class="sxs-lookup"><span data-stu-id="17b66-226">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="17b66-227">Выберите **развертывание надстройки** в верхней части страницы, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="17b66-227">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Страница Службы и надстройки в центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="17b66-229">В **развертывании новой** надстройки, которая появится, просмотрите сведения, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="17b66-229">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="17b66-230">На следующей странице нажмите **кнопку Выберите из магазина**.</span><span class="sxs-lookup"><span data-stu-id="17b66-230">On the next page, click **Choose from the Store**.</span></span>

   ![Развертывание новой страницы надстройки](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="17b66-232">На странице **Выбор надстройки,** которая появится, нажмите кнопку в поле **Поиск,** введите **сообщение** фишинг, а затем нажмите **значок Поиска** ![ поиска ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="17b66-232">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="17b66-233">В списке результатов найдите **сообщение Фишинг** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="17b66-233">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="17b66-234">В диалоговом окте, который появится, просмотрите сведения о лицензировании и конфиденциальности, а затем нажмите **кнопку Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="17b66-234">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="17b66-235">На **странице Настройка надстройки,** которая появится, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="17b66-235">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="17b66-236">**Назначены пользователи:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="17b66-236">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="17b66-237">**Все** (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="17b66-237">**Everyone** (default)</span></span>
     - <span data-ttu-id="17b66-238">**Конкретные пользователи / группы**</span><span class="sxs-lookup"><span data-stu-id="17b66-238">**Specific users / groups**</span></span>
     - <span data-ttu-id="17b66-239">**Только я**</span><span class="sxs-lookup"><span data-stu-id="17b66-239">**Just me**</span></span>

   - <span data-ttu-id="17b66-240">**Метод развертывания:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="17b66-240">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="17b66-241">**Исправлено (по умолчанию).** Надстройка автоматически развертывается для указанных пользователей, и они не могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="17b66-241">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="17b66-242">**Доступно.** Пользователи могут установить надстройки в **Home** \> **Get надстройки,** \> **управляемые администратором.**</span><span class="sxs-lookup"><span data-stu-id="17b66-242">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="17b66-243">**Необязательный** вариант: надстройка автоматически развертывается для указанных пользователей, но они могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="17b66-243">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="17b66-244">По завершению щелкните **Развертывание**.</span><span class="sxs-lookup"><span data-stu-id="17b66-244">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="17b66-245">На странице **Развертывание фишинга** отчетов, которая отображается, вы увидите отчет о ходе выполнения, после чего будет подтверждено, что надстройка была развернута.</span><span class="sxs-lookup"><span data-stu-id="17b66-245">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="17b66-246">После прочтя сведений нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="17b66-246">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="17b66-247">На странице **Надстройка** "Объявить", которая появится, просмотрите сведения и нажмите **кнопку Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="17b66-247">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="17b66-248">Просмотр или изменение параметров надстройки Report Phishing</span><span class="sxs-lookup"><span data-stu-id="17b66-248">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="17b66-249">В центре администрирования Microsoft 365 перейдите на страницу **Параметры** надстройки \>  по <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> крайней .</span><span class="sxs-lookup"><span data-stu-id="17b66-249">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="17b66-250">Если вы не видите  страницу надстройки, перейдите к ссылке Надстройки "Параметры интегрированных приложений" в верхней части страницы  \>  \>  **Интегрированные** приложения.</span><span class="sxs-lookup"><span data-stu-id="17b66-250">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="17b66-251">Найдите и выберите **надстройку Report Phishing.**</span><span class="sxs-lookup"><span data-stu-id="17b66-251">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="17b66-252">В **вылете Редактирование фишинговых** отчетов, которое отображается, просмотрите и отредактировать параметры, соответствующие вашей организации.</span><span class="sxs-lookup"><span data-stu-id="17b66-252">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="17b66-253">По завершении нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="17b66-253">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="17b66-254">Просмотр и просмотр сообщений, о чем сообщалось</span><span class="sxs-lookup"><span data-stu-id="17b66-254">View and review reported messages</span></span>

<span data-ttu-id="17b66-255">Чтобы просмотреть сообщения, которые пользователи сообщают в Корпорацию Майкрософт, у вас есть такие параметры:</span><span class="sxs-lookup"><span data-stu-id="17b66-255">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="17b66-256">Используйте портал Отправки администратора.</span><span class="sxs-lookup"><span data-stu-id="17b66-256">Use the Admin Submissions portal.</span></span> <span data-ttu-id="17b66-257">Дополнительные сведения см. в [материале Просмотр пользовательских представлений в Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="17b66-257">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="17b66-258">Создайте правило потока почты (также известное как правило транспорта) для отправки копий сообщений.</span><span class="sxs-lookup"><span data-stu-id="17b66-258">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="17b66-259">Инструкции см. в инструкции Использование правил потока почты, чтобы узнать, что пользователи [сообщают в Корпорацию Майкрософт.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="17b66-259">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>