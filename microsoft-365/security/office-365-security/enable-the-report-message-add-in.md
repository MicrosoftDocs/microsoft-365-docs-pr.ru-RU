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
ms.openlocfilehash: 8949322b0b691d59e59e5f7b80d2b9650e4115d5
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029913"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="019f2-103">Включить сообщение отчета или надстройки для фишинга отчетов</span><span class="sxs-lookup"><span data-stu-id="019f2-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="019f2-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="019f2-104">**Applies to**</span></span>
- [<span data-ttu-id="019f2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="019f2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="019f2-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="019f2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="019f2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="019f2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="019f2-108">Если вы администратор в организации Microsoft 365 с почтовыми ящиками Exchange Online, рекомендуем использовать портал Отправки на портале Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="019f2-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="019f2-109">Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="019f2-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="019f2-110">Надстройки Для Outlook и Outlook в Интернете (ранее известные как Outlook Web App) позволяют пользователям легко сообщать о ложных срабатываниях (хорошая электронная почта, помеченная как плохие) или ложных отрицательных (разрешенная плохая электронная почта) в Корпорацию Майкрософт и ее филиалы для анализа.</span><span class="sxs-lookup"><span data-stu-id="019f2-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="019f2-111">Корпорация Майкрософт использует эти материалы для повышения эффективности технологий защиты электронной почты.</span><span class="sxs-lookup"><span data-stu-id="019f2-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="019f2-112">Например, предположим, что люди сообщают много сообщений с помощью надстройки Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="019f2-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="019f2-113">Эти сведения будут использоваться в панели мониторинга безопасности и других отчетах.</span><span class="sxs-lookup"><span data-stu-id="019f2-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="019f2-114">Группа безопасности организации может использовать эти сведения в качестве указания на необходимость обновления политик защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="019f2-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="019f2-115">Можно установить надстройку Report Message или Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="019f2-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="019f2-116">Если вы хотите, чтобы пользователи сообщали о спаме и фишинговых сообщениях, разместите надстройку Report Message в организации.</span><span class="sxs-lookup"><span data-stu-id="019f2-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="019f2-117">Дополнительные сведения см. в добавлении Enable the Report Message.</span><span class="sxs-lookup"><span data-stu-id="019f2-117">For more information, see Enable the Report Message add-in.</span></span>

<span data-ttu-id="019f2-118">Надстройка Report Message предоставляет возможность сообщать о спаме и фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="019f2-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="019f2-119">Администраторы могут включить надстройка Report Message для организации, а отдельные пользователи могут установить ее для себя.</span><span class="sxs-lookup"><span data-stu-id="019f2-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="019f2-120">Надстройка Report Phishing предоставляет возможность сообщать только о фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="019f2-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="019f2-121">Администраторы могут включить надстройку Report Phishing для организации, а отдельные пользователи могут установить ее для себя.</span><span class="sxs-lookup"><span data-stu-id="019f2-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="019f2-122">Если вы индивидуальный пользователь, вы можете включить оба надстройки для себя.</span><span class="sxs-lookup"><span data-stu-id="019f2-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="019f2-123">Если вы глобальный администратор или администратор Exchange Online, а Exchange настроена на использование проверки подлинности OAuth, вы можете включить надстройку Report Message и надстройку Report Phishing для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="019f2-123">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="019f2-124">Обе надстройки теперь доступны через [централизованное развертывание.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="019f2-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="019f2-125">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="019f2-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="019f2-126">Надстройка Сообщения отчетов и надстройка Report Phishing работают с большинством подписок Microsoft 365 и следующими продуктами:</span><span class="sxs-lookup"><span data-stu-id="019f2-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>
  - <span data-ttu-id="019f2-127">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="019f2-127">Outlook on the web</span></span>
  - <span data-ttu-id="019f2-128">Outlook 2013 SP1 или более поздний</span><span class="sxs-lookup"><span data-stu-id="019f2-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="019f2-129">Outlook 2016 для Mac;</span><span class="sxs-lookup"><span data-stu-id="019f2-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="019f2-130">Outlook, включенный в приложения Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="019f2-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="019f2-131">Приложение Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="019f2-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="019f2-132">Обе надстройки недоступны для общих почтовых ящиков или почтовых ящиков в локальной организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="019f2-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="019f2-133">Существующий веб-браузер должен работать как с надстройки Report Message, так и с надстройки Report Phishing. Но если вы заметили, что надстройка недоступна или работает не так, как ожидалось, попробуйте другой браузер.</span><span class="sxs-lookup"><span data-stu-id="019f2-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="019f2-134">Для организационных установок необходимо настроить организацию для использования проверки подлинности OAuth.</span><span class="sxs-lookup"><span data-stu-id="019f2-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="019f2-135">Дополнительные сведения см. в [рубриках Определение,](../../admin/manage/centralized-deployment-of-add-ins.md)работает ли централизованное развертывание надстройок для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="019f2-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="019f2-136">Администраторы должны быть членами группы ролей глобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="019f2-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="019f2-137">Дополнительные сведения см. [в веб-сайте Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="019f2-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="019f2-138">Дополнительные сведения о том, как сообщать о сообщении с помощью функции Сообщение отчетов, см. в обзоре [Report false positives and false negatives in Outlook.](report-false-positives-and-false-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="019f2-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="019f2-139">Мы не рекомендуем встроенный интерфейс отчетности в Outlook, так как он не может использовать политику отправки [пользователей.](./user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="019f2-139">We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span> <span data-ttu-id="019f2-140">Рекомендуется использовать надстройку "Сообщение отчетов" или надстройку Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="019f2-140">We recommend using the Report Message add-in or the Report Phishing add-in instead.</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="019f2-141">Получить надстройки сообщения отчета</span><span class="sxs-lookup"><span data-stu-id="019f2-141">Get the Report Message add-in</span></span>

### <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="019f2-142">Получите надстройка "Сообщение отчетов" для себя</span><span class="sxs-lookup"><span data-stu-id="019f2-142">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="019f2-143">Перейдите в Microsoft AppSource и <https://appsource.microsoft.com/marketplace/apps> найдите надстройки "Сообщение отчетов".</span><span class="sxs-lookup"><span data-stu-id="019f2-143">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="019f2-144">Чтобы перейти непосредственно к надстройки Сообщение отчета, перейдите к <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="019f2-144">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="019f2-145">Нажмите **КНОПКУ GET IT NOW**.</span><span class="sxs-lookup"><span data-stu-id="019f2-145">Click **GET IT NOW**.</span></span>

   ![Сообщение отчета — получите его сейчас](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="019f2-147">В диалоговом окантове, который появляется, просмотрите условия использования и политику конфиденциальности, а затем нажмите **кнопку Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="019f2-147">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="019f2-148">Впишитесь с помощью учетной записи работы или учебного заведения (для бизнеса) или учетной записи Майкрософт (для личного использования).</span><span class="sxs-lookup"><span data-stu-id="019f2-148">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="019f2-149">После установки и включения надстройки вы увидите следующие значки:</span><span class="sxs-lookup"><span data-stu-id="019f2-149">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="019f2-150">В Outlook значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="019f2-150">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="019f2-151">![Значок надстройки Report Message для Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="019f2-151">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="019f2-152">В Outlook в Интернете значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="019f2-152">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="019f2-153">![Outlook на значке надстройки "Сообщение о веб-отчете"](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="019f2-153">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="019f2-154">Получите надстройка "Сообщение отчета" для организации</span><span class="sxs-lookup"><span data-stu-id="019f2-154">Get the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="019f2-155">Для появления надстройки в организации может занять до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="019f2-155">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="019f2-156">В центре администрирования Microsoft 365  перейдите на страницу \> **Надстройки** параметров по <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> крайней мере .</span><span class="sxs-lookup"><span data-stu-id="019f2-156">In the Microsoft 365 admin center, go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="019f2-157">Если вы не видите  страницу надстройки, перейдите к ссылке Надстройки "Параметры интегрированных приложений" в верхней части страницы  \>  \>  **Интегрированные** приложения.</span><span class="sxs-lookup"><span data-stu-id="019f2-157">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="019f2-158">Выберите **развертывание надстройки** в верхней части страницы, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="019f2-158">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Страница Службы и надстройки в центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="019f2-160">В **развертывании новой** надстройки, которая появится, просмотрите сведения, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="019f2-160">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="019f2-161">На следующей странице нажмите **кнопку Выберите из магазина**.</span><span class="sxs-lookup"><span data-stu-id="019f2-161">On the next page, click **Choose from the Store**.</span></span>

   ![Развертывание новой страницы надстройки](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="019f2-163">На странице **Выберите надстройку,** которая  появится, щелкните в поле Поиск, **введите** сообщение отчета, а затем нажмите **значок Поиск** поиска ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="019f2-163">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="019f2-164">В списке результатов найдите **сообщение отчета** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="019f2-164">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Выбор результатов поиска надстройки](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="019f2-166">В диалоговом окте, который появится, просмотрите сведения о лицензировании и конфиденциальности, а затем нажмите **кнопку Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="019f2-166">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="019f2-167">На **странице Настройка надстройки,** которая появится, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="019f2-167">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="019f2-168">**Назначены пользователи:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="019f2-168">**Assigned users**: Select one of the following values:</span></span>
     - <span data-ttu-id="019f2-169">**Все** (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="019f2-169">**Everyone** (default)</span></span>
     - <span data-ttu-id="019f2-170">**Конкретные пользователи / группы**</span><span class="sxs-lookup"><span data-stu-id="019f2-170">**Specific users / groups**</span></span>
     - <span data-ttu-id="019f2-171">**Только я**</span><span class="sxs-lookup"><span data-stu-id="019f2-171">**Just me**</span></span>

   - <span data-ttu-id="019f2-172">**Метод развертывания:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="019f2-172">**Deployment method**: Select one of the following values:</span></span>
     - <span data-ttu-id="019f2-173">**Исправлено (по умолчанию).** Надстройка автоматически развертывается для указанных пользователей, и они не могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="019f2-173">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="019f2-174">**Доступно.** Пользователи могут установить надстройки в **Home** \> **Get надстройки,** \> **управляемые администратором.**</span><span class="sxs-lookup"><span data-stu-id="019f2-174">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="019f2-175">**Необязательный** вариант: надстройка автоматически развертывается для указанных пользователей, но они могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="019f2-175">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Настройка страницы надстройки](../../media/configure-add-in.png)

   <span data-ttu-id="019f2-177">По завершению щелкните **Развертывание**.</span><span class="sxs-lookup"><span data-stu-id="019f2-177">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="019f2-178">На странице **Развертывание сообщения отчетов,** которая отображается, вы увидите отчет о ходе выполнения, за которым следует подтверждение развертывания надстройки.</span><span class="sxs-lookup"><span data-stu-id="019f2-178">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="019f2-179">После прочтя сведений нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="019f2-179">After you read the information, click **Next**.</span></span>

   ![Развертывание страницы сообщения отчета](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="019f2-181">На странице **Надстройка** "Объявить", которая появится, просмотрите сведения и нажмите **кнопку Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="019f2-181">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Объявить страницу надстройки](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="019f2-183">Просмотр или изменение параметров надстройки "Сообщение отчетов"</span><span class="sxs-lookup"><span data-stu-id="019f2-183">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="019f2-184">В центре администрирования Microsoft 365 перейдите на страницу **Параметры** надстройки \>  по <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> крайней .</span><span class="sxs-lookup"><span data-stu-id="019f2-184">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="019f2-185">Если вы не видите  страницу надстройки, перейдите к ссылке Надстройки "Параметры интегрированных приложений" в верхней части страницы  \>  \>  **Интегрированные** приложения.</span><span class="sxs-lookup"><span data-stu-id="019f2-185">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Службы и Add-Ins в новом центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="019f2-187">Найдите и выберите **надстройка "Сообщение** отчетов".</span><span class="sxs-lookup"><span data-stu-id="019f2-187">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="019f2-188">В **вылете Сообщение** об редактировании отчетов, которое отображается, просмотрите и отредактируете параметры, соответствующие вашей организации.</span><span class="sxs-lookup"><span data-stu-id="019f2-188">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="019f2-189">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="019f2-189">When you're finished, click **Save**.</span></span>

   ![Параметры надстройки "Сообщение отчетов"](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="019f2-191">Получить надстройку Для фишинга отчетов</span><span class="sxs-lookup"><span data-stu-id="019f2-191">Get the Report Phishing add-in</span></span>

### <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="019f2-192">Получите надстройку Report Phishing для себя</span><span class="sxs-lookup"><span data-stu-id="019f2-192">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="019f2-193">Перейдите в Microsoft AppSource и <https://appsource.microsoft.com/marketplace/apps> найдите надстройку Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="019f2-193">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="019f2-194">Нажмите **КНОПКУ GET IT NOW**.</span><span class="sxs-lookup"><span data-stu-id="019f2-194">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="019f2-195">В диалоговом окантове, который появляется, просмотрите условия использования и политику конфиденциальности, а затем нажмите **кнопку Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="019f2-195">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="019f2-196">Впишитесь с помощью учетной записи работы или учебного заведения (для бизнеса) или учетной записи Майкрософт (для личного использования).</span><span class="sxs-lookup"><span data-stu-id="019f2-196">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="019f2-197">После установки и включения надстройки вы увидите следующие значки:</span><span class="sxs-lookup"><span data-stu-id="019f2-197">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="019f2-198">В Outlook значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="019f2-198">In Outlook, the icon looks like this:</span></span>

  ![Отчет о значке надстройки фишинга для Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="019f2-200">В Outlook в Интернете значок выглядит так:</span><span class="sxs-lookup"><span data-stu-id="019f2-200">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="019f2-201">![Outlook на значке надстройки фишинга веб-отчета](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="019f2-201">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="019f2-202">Получите надстройку "Фишинг отчетов" для организации</span><span class="sxs-lookup"><span data-stu-id="019f2-202">Get the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="019f2-203">Для появления надстройки в организации может занять до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="019f2-203">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="019f2-204">В центре администрирования Microsoft 365 перейдите на страницу **Параметры** надстройки \>  по <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> крайней .</span><span class="sxs-lookup"><span data-stu-id="019f2-204">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="019f2-205">Если вы не видите  страницу надстройки, перейдите к ссылке Надстройки "Параметры интегрированных приложений" в верхней части страницы  \>  \>  **Интегрированные** приложения.</span><span class="sxs-lookup"><span data-stu-id="019f2-205">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="019f2-206">Выберите **развертывание надстройки** в верхней части страницы, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="019f2-206">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Страница Службы и надстройки в центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="019f2-208">В **развертывании новой** надстройки, которая появится, просмотрите сведения, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="019f2-208">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="019f2-209">На следующей странице нажмите **кнопку Выберите из магазина**.</span><span class="sxs-lookup"><span data-stu-id="019f2-209">On the next page, click **Choose from the Store**.</span></span>

   ![Развертывание новой страницы надстройки](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="019f2-211">На странице **Выбор надстройки,** которая появится, нажмите кнопку в поле **Поиск,** введите **сообщение** фишинг, а затем нажмите **значок Поиска** ![ поиска ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="019f2-211">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="019f2-212">В списке результатов найдите **сообщение Фишинг** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="019f2-212">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="019f2-213">В диалоговом окте, который появится, просмотрите сведения о лицензировании и конфиденциальности, а затем нажмите **кнопку Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="019f2-213">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="019f2-214">На **странице Настройка надстройки,** которая появится, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="019f2-214">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="019f2-215">**Назначены пользователи:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="019f2-215">**Assigned users**: Select one of the following values:</span></span>
     - <span data-ttu-id="019f2-216">**Все** (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="019f2-216">**Everyone** (default)</span></span>
     - <span data-ttu-id="019f2-217">**Конкретные пользователи / группы**</span><span class="sxs-lookup"><span data-stu-id="019f2-217">**Specific users / groups**</span></span>
     - <span data-ttu-id="019f2-218">**Только я**</span><span class="sxs-lookup"><span data-stu-id="019f2-218">**Just me**</span></span>

   - <span data-ttu-id="019f2-219">**Метод развертывания:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="019f2-219">**Deployment method**: Select one of the following values:</span></span>
     - <span data-ttu-id="019f2-220">**Исправлено (по умолчанию).** Надстройка автоматически развертывается для указанных пользователей, и они не могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="019f2-220">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="019f2-221">**Доступно.** Пользователи могут установить надстройки в **Home** \> **Get надстройки,** \> **управляемые администратором.**</span><span class="sxs-lookup"><span data-stu-id="019f2-221">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="019f2-222">**Необязательный** вариант: надстройка автоматически развертывается для указанных пользователей, но они могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="019f2-222">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="019f2-223">По завершению щелкните **Развертывание**.</span><span class="sxs-lookup"><span data-stu-id="019f2-223">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="019f2-224">На странице **Развертывание фишинга** отчетов, которая отображается, вы увидите отчет о ходе выполнения, после чего будет подтверждено, что надстройка была развернута.</span><span class="sxs-lookup"><span data-stu-id="019f2-224">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="019f2-225">После прочтя сведений нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="019f2-225">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="019f2-226">На странице **Надстройка** "Объявить", которая появится, просмотрите сведения и нажмите **кнопку Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="019f2-226">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="019f2-227">Просмотр или изменение параметров надстройки Report Phishing</span><span class="sxs-lookup"><span data-stu-id="019f2-227">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="019f2-228">В центре администрирования Microsoft 365 перейдите на страницу **Параметры** надстройки \>  по <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> крайней .</span><span class="sxs-lookup"><span data-stu-id="019f2-228">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="019f2-229">Если вы не видите  страницу надстройки, перейдите к ссылке Надстройки "Параметры интегрированных приложений" в верхней части страницы  \>  \>  **Интегрированные** приложения.</span><span class="sxs-lookup"><span data-stu-id="019f2-229">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="019f2-230">Найдите и выберите **надстройку Report Phishing.**</span><span class="sxs-lookup"><span data-stu-id="019f2-230">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="019f2-231">В **вылете Редактирование фишинговых** отчетов, которое отображается, просмотрите и отредактировать параметры, соответствующие вашей организации.</span><span class="sxs-lookup"><span data-stu-id="019f2-231">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="019f2-232">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="019f2-232">When you're finished, click **Save**.</span></span>
