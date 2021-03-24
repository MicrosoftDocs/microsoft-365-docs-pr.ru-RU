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
description: Узнайте, как включить надстройки Сообщения отчетов для Outlook и Outlook в Интернете, для отдельных пользователей или всей организации.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4e85af902eaaa41eb82acf8d4b4baedc538e7888
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072566"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="f1b74-103">Включение надстройки "Пожаловаться на сообщение"</span><span class="sxs-lookup"><span data-stu-id="f1b74-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f1b74-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="f1b74-104">**Applies to**</span></span>
- [<span data-ttu-id="f1b74-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f1b74-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f1b74-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="f1b74-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f1b74-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1b74-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="f1b74-108">Если вы администратор в организации Microsoft 365 с почтовыми ящиками Exchange Online, рекомендуем использовать портал Отправки в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f1b74-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f1b74-109">Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f1b74-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="f1b74-110">Надстройки Для Outlook и Outlook в Интернете (ранее известные как Outlook Web App) позволяют пользователям легко сообщать о ложных срабатываниях (хорошая электронная почта, помеченная как плохая) или ложных отрицательных (разрешена плохая электронная почта) в Корпорацию Майкрософт и ее филиалы для анализа.</span><span class="sxs-lookup"><span data-stu-id="f1b74-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="f1b74-111">Корпорация Майкрософт использует эти материалы для повышения эффективности технологий защиты электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f1b74-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="f1b74-112">Например, если люди сообщают много сообщений, помеченных как нежелательной почты, как не нежелательной почты с помощью надстройки Report Message, группе безопасности организации может потребоваться изменить политики защиты от нежелательной [почты.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f1b74-112">For example, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="f1b74-113">Можно установить надстройку Report Message или Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="f1b74-113">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="f1b74-114">Если вы хотите, чтобы пользователи сообщали только о фишинговых сообщениях, разверните надстройку Report Phishing в организации.</span><span class="sxs-lookup"><span data-stu-id="f1b74-114">If you want your users to report only phishing messages, deploy the Report Phishing add-in in your organization.</span></span> <span data-ttu-id="f1b74-115">Дополнительные сведения см. в [добавлении Enable the Report Phishing.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="f1b74-115">For more information, see [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="f1b74-116">Надстройка Report Message предоставляет возможность сообщать о спаме и фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="f1b74-116">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="f1b74-117">Администраторы могут включить надстройка Report Message для организации, а отдельные пользователи могут установить ее для себя.</span><span class="sxs-lookup"><span data-stu-id="f1b74-117">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="f1b74-118">Если вы индивидуальный пользователь, вы можете включить надстройки [Report Message для себя.](#get-the-report-message-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="f1b74-118">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="f1b74-119">Если вы глобальный администратор или администратор Exchange Online, а Exchange настроена на использование проверки подлинности OAuth, вы можете включить надстройку [Report Message для вашей организации.](#get-and-enable-the-report-message-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="f1b74-119">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="f1b74-120">Сообщение отчета Add-In теперь доступно через [централизованное развертывание.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="f1b74-120">The Report Message Add-In is now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f1b74-121">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="f1b74-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f1b74-122">Надстройка Report Message работает с большинством подписок Microsoft 365 и следующими продуктами:</span><span class="sxs-lookup"><span data-stu-id="f1b74-122">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="f1b74-123">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="f1b74-123">Outlook on the web</span></span>
  - <span data-ttu-id="f1b74-124">Outlook 2013 SP1 или более поздний</span><span class="sxs-lookup"><span data-stu-id="f1b74-124">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="f1b74-125">Outlook 2016 для Mac;</span><span class="sxs-lookup"><span data-stu-id="f1b74-125">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="f1b74-126">Outlook, включенный в приложения Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="f1b74-126">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="f1b74-127">Приложение Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="f1b74-127">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="f1b74-128">Надстройка Сообщения отчетов недоступна для общих почтовых ящиков или почтовых ящиков в локальной организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="f1b74-128">The Report Message add-in is not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="f1b74-129">Вы можете настроить сообщения, которые будут скопированы или перенаправлены в почтовый ящик, который указан.</span><span class="sxs-lookup"><span data-stu-id="f1b74-129">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="f1b74-130">Дополнительные сведения см. [в материале Политики отправки пользователей.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f1b74-130">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="f1b74-131">Существующий веб-браузер должен работать с надстройка сообщением отчета.</span><span class="sxs-lookup"><span data-stu-id="f1b74-131">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="f1b74-132">Но если вы заметили, что надстройка недоступна или работает не так, как ожидалось, попробуйте другой браузер.</span><span class="sxs-lookup"><span data-stu-id="f1b74-132">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="f1b74-133">Для организационных установок необходимо настроить организацию для использования проверки подлинности OAuth.</span><span class="sxs-lookup"><span data-stu-id="f1b74-133">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="f1b74-134">Дополнительные сведения см. в [рубриках Определение,](../../admin/manage/centralized-deployment-of-add-ins.md)работает ли централизованное развертывание надстройок для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f1b74-134">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="f1b74-135">Администраторы должны быть членами группы ролей глобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="f1b74-135">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="f1b74-136">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f1b74-136">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="f1b74-137">Получите надстройка "Сообщение отчетов" для себя</span><span class="sxs-lookup"><span data-stu-id="f1b74-137">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="f1b74-138">Перейдите в Microsoft AppSource и <https://appsource.microsoft.com/marketplace/apps> найдите надстройки "Сообщение отчетов".</span><span class="sxs-lookup"><span data-stu-id="f1b74-138">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="f1b74-139">Чтобы перейти непосредственно к надстройки Сообщение отчета, перейдите к <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="f1b74-139">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="f1b74-140">Нажмите **КНОПКУ GET IT NOW**.</span><span class="sxs-lookup"><span data-stu-id="f1b74-140">Click **GET IT NOW**.</span></span>

   ![Сообщение отчета — получите его сейчас](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="f1b74-142">В диалоговом окантове, который появляется, просмотрите условия использования и политику конфиденциальности, а затем нажмите **кнопку Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="f1b74-142">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="f1b74-143">Впишитесь с помощью учетной записи работы или учебного заведения (для бизнеса) или учетной записи Майкрософт (для личного использования).</span><span class="sxs-lookup"><span data-stu-id="f1b74-143">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="f1b74-144">После установки и включения надстройки вы увидите следующие значки:</span><span class="sxs-lookup"><span data-stu-id="f1b74-144">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="f1b74-145">В Outlook значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="f1b74-145">In Outlook, the icon looks like this:</span></span>

  ![Значок надстройки Report Message для Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="f1b74-147">В Outlook в Интернете значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="f1b74-147">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook на значке надстройки "Сообщение о веб-отчете"](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="f1b74-149">Подробнее об использовании надстройки см. в добавлении ["Сообщение отчетов".](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="f1b74-149">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="f1b74-150">Получить и включить надстройка "Сообщение отчетов" для организации</span><span class="sxs-lookup"><span data-stu-id="f1b74-150">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="f1b74-151">Для появления надстройки в организации может занять до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="f1b74-151">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="f1b74-152">В центре администрирования Microsoft 365 перейдите  на страницу Параметры надстройки по ссылке . Если вы не видите страницу надстройки, перейдите к ссылке Надстройки "Параметры интегрированных приложений" в верхней части страницы Интегрированные \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  приложения. </span><span class="sxs-lookup"><span data-stu-id="f1b74-152">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="f1b74-153">Выберите **развертывание надстройки** в верхней части страницы, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1b74-153">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Страница Службы и надстройки в центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="f1b74-155">В **развертывании новой** надстройки, которая появится, просмотрите сведения, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1b74-155">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="f1b74-156">На следующей странице нажмите **кнопку Выберите из магазина**.</span><span class="sxs-lookup"><span data-stu-id="f1b74-156">On the next page, click **Choose from the Store**.</span></span>

   ![Развертывание новой страницы надстройки](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="f1b74-158">На странице **Выберите надстройку,** которая  появится, щелкните в поле Поиск, **введите** сообщение отчета, а затем нажмите **значок Поиск** поиска ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="f1b74-158">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="f1b74-159">В списке результатов найдите **сообщение отчета** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f1b74-159">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Выбор результатов поиска надстройки](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="f1b74-161">В диалоговом окте, который появится, просмотрите сведения о лицензировании и конфиденциальности, а затем нажмите **кнопку Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="f1b74-161">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="f1b74-162">На **странице Настройка надстройки,** которая появится, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f1b74-162">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f1b74-163">**Назначены пользователи:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="f1b74-163">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="f1b74-164">**Все** (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="f1b74-164">**Everyone** (default)</span></span>
     - <span data-ttu-id="f1b74-165">**Конкретные пользователи / группы**</span><span class="sxs-lookup"><span data-stu-id="f1b74-165">**Specific users / groups**</span></span>
     - <span data-ttu-id="f1b74-166">**Только я**</span><span class="sxs-lookup"><span data-stu-id="f1b74-166">**Just me**</span></span>

   - <span data-ttu-id="f1b74-167">**Метод развертывания:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="f1b74-167">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="f1b74-168">**Исправлено (по умолчанию).** Надстройка автоматически развертывается для указанных пользователей, и они не могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="f1b74-168">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="f1b74-169">**Доступно.** Пользователи могут установить надстройки в **Home** \> **Get надстройки,** \> **управляемые администратором.**</span><span class="sxs-lookup"><span data-stu-id="f1b74-169">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="f1b74-170">**Необязательный** вариант: надстройка автоматически развертывается для указанных пользователей, но они могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="f1b74-170">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Настройка страницы надстройки](../../media/configure-add-in.png)

   <span data-ttu-id="f1b74-172">По завершению щелкните **Развертывание**.</span><span class="sxs-lookup"><span data-stu-id="f1b74-172">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="f1b74-173">На странице **Развертывание сообщения отчетов,** которая отображается, вы увидите отчет о ходе выполнения, за которым следует подтверждение развертывания надстройки.</span><span class="sxs-lookup"><span data-stu-id="f1b74-173">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="f1b74-174">После прочтя сведений нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1b74-174">After you read the information, click **Next**.</span></span>

   ![Развертывание страницы сообщения отчета](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="f1b74-176">На странице **Надстройка** "Объявить", которая появится, просмотрите сведения и нажмите **кнопку Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f1b74-176">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Объявить страницу надстройки](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="f1b74-178">Узнайте, как использовать надстройки "Сообщение отчетов"</span><span class="sxs-lookup"><span data-stu-id="f1b74-178">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="f1b74-179">Люди, которым назначена надстройка, увидят следующие значки:</span><span class="sxs-lookup"><span data-stu-id="f1b74-179">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="f1b74-180">В Outlook значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="f1b74-180">In Outlook, the icon looks like this:</span></span>

  ![Значок надстройки сообщения отчетов для Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="f1b74-182">В Outlook в Интернете значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="f1b74-182">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook на значке надстройки сообщения веб-отчета](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="f1b74-184">При оповещение пользователей о надстройки "Сообщение отчетов" включайте ссылку на использование надстройки ["Сообщение отчетов".](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="f1b74-184">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="f1b74-185">Просмотр или изменение параметров надстройки "Сообщение отчетов"</span><span class="sxs-lookup"><span data-stu-id="f1b74-185">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="f1b74-186">В центре администрирования Microsoft 365 перейдите  на страницу Параметры надстройки по ссылке . Если вы не видите страницу надстройки, перейдите к ссылке Надстройки "Параметры интегрированных приложений" в верхней части страницы Интегрированные \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  приложения. </span><span class="sxs-lookup"><span data-stu-id="f1b74-186">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Службы и Add-Ins в новом центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="f1b74-188">Найдите и выберите **надстройка "Сообщение** отчетов".</span><span class="sxs-lookup"><span data-stu-id="f1b74-188">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="f1b74-189">В **вылете Сообщение** об редактировании отчетов, которое отображается, просмотрите и отредактируете параметры, соответствующие вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f1b74-189">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="f1b74-190">Когда закончите, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f1b74-190">When you're finished, click **Save**.</span></span>

   ![Параметры надстройки "Сообщение отчетов"](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="f1b74-192">Просмотр и просмотр сообщений, о чем сообщалось</span><span class="sxs-lookup"><span data-stu-id="f1b74-192">View and review reported messages</span></span>

<span data-ttu-id="f1b74-193">Чтобы просмотреть сообщения, которые пользователи сообщают в Корпорацию Майкрософт, у вас есть такие параметры:</span><span class="sxs-lookup"><span data-stu-id="f1b74-193">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="f1b74-194">Используйте портал Отправки администратора.</span><span class="sxs-lookup"><span data-stu-id="f1b74-194">Use the Admin Submissions portal.</span></span> <span data-ttu-id="f1b74-195">Дополнительные сведения см. в [материале Просмотр пользовательских представлений в Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="f1b74-195">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="f1b74-196">Создайте правило потока почты (также известное как правило транспорта) для отправки копий сообщений.</span><span class="sxs-lookup"><span data-stu-id="f1b74-196">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="f1b74-197">Инструкции см. в инструкции Использование правил потока почты, чтобы узнать, что пользователи [сообщают в Корпорацию Майкрософт.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="f1b74-197">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
