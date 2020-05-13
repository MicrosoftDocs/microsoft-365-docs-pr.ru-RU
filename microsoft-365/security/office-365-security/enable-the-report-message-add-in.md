---
title: Включение надстройки "Пожаловаться на сообщение"
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Сведения о том, как включить надстройку сообщения отчета для Outlook и Outlook в Интернете для отдельных пользователей или всей Организации.
ms.openlocfilehash: 67fe2112e5d507ac1f0dc78ffa3534ebc9874916
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209491"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="07301-103">Включение надстройки "Пожаловаться на сообщение"</span><span class="sxs-lookup"><span data-stu-id="07301-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="07301-104">Если вы являетесь администратором в организации Microsoft 365 с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="07301-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="07301-105">Дополнительные сведения см. в [статье Использование отправки администратором для отправки подозреваемой спама, фишинга, URL-адресов и файлов в корпорацию Майкрософт](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="07301-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="07301-106">Надстройка сообщения отчета для Outlook и Outlook в Интернете (прежнее название — Outlook Web App) позволяет людям легко сообщать о ложных срабатываниях (хорошее письмо отмечено как плохое) или ложные отрицательные (недопустимые сообщения электронной почты) корпорации Майкрософт и ее аффилированным лицам для анализа.</span><span class="sxs-lookup"><span data-stu-id="07301-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="07301-107">Корпорация Майкрософт использует эти отправки для повышения эффективности технологий защиты электронной почты.</span><span class="sxs-lookup"><span data-stu-id="07301-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="07301-108">Например, предположим, что люди сообщают о большом числе фишинговых сообщений.</span><span class="sxs-lookup"><span data-stu-id="07301-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="07301-109">Эта информация послужит в качестве поверхности в [панели мониторинга безопасности](security-dashboard.md) и других отчетов.</span><span class="sxs-lookup"><span data-stu-id="07301-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="07301-110">Группа безопасности вашей организации может использовать эти сведения для указания того, что политики защиты от фишинга может потребоваться обновить.</span><span class="sxs-lookup"><span data-stu-id="07301-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="07301-111">Или, если пользователи сообщают о большом количестве сообщений, помеченных как нежелательные, с помощью надстройки Report Message, группе безопасности Организации может потребоваться настроить [политики защиты от нежелательной почты](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="07301-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="07301-112">Кроме того, если в организации используется [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) или [Plan 2](office-365-ti.md), надстройка сообщения отчета предоставляет группе безопасности Организации полезную информацию, которую можно использовать для просмотра и обновления политик безопасности.</span><span class="sxs-lookup"><span data-stu-id="07301-112">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="07301-113">Администраторы могут включить надстройку сообщений отчета для Организации, а отдельные пользователи могут установить их самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="07301-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="07301-114">Если вы являетесь отдельным пользователем, вы можете [включить для себя надстройку сообщения отчета](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="07301-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="07301-115">Если вы являетесь глобальным администратором или администратором Exchange Online, а Exchange настроен на использование проверки подлинности OAuth, вы можете [включить надстройку сообщения отчета для Организации](#get-and-enable-the-report-message-add-in-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="07301-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="07301-116">Теперь надстройка сообщений отчета доступна с помощью [централизованного развертывания](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="07301-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="07301-117">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="07301-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="07301-118">Надстройка сообщения отчета работает с большинством подписок Microsoft 365 и следующих продуктов:</span><span class="sxs-lookup"><span data-stu-id="07301-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="07301-119">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="07301-119">Outlook on the web</span></span>
  - <span data-ttu-id="07301-120">Outlook 2013 SP1 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="07301-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="07301-121">Outlook 2016 для Mac;</span><span class="sxs-lookup"><span data-stu-id="07301-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="07301-122">Outlook, входящий в состав приложений Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="07301-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="07301-123">В настоящее время надстройка сообщений отчета недоступна для:</span><span class="sxs-lookup"><span data-stu-id="07301-123">The Report Message add-in is currently not available for:</span></span>

  - <span data-ttu-id="07301-124">Почтовые ящики в локальных организациях Exchange</span><span class="sxs-lookup"><span data-stu-id="07301-124">Mailboxes in on-premises Exchange organizations</span></span>
  - <span data-ttu-id="07301-125">Подписки на GCC, GCC HIGH или DoD</span><span class="sxs-lookup"><span data-stu-id="07301-125">GCC, GCC HIGH, or DoD subscriptions</span></span>

- <span data-ttu-id="07301-126">Можно настроить копирование или перенаправление сообщений, отправленных в указанный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="07301-126">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="07301-127">Дополнительные сведения см. [в статье определение почтового ящика для отправленных пользователем сообщений о нежелательной почте и фишинговых сообщениях в Exchange Online](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="07301-127">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="07301-128">Существующий веб-браузер должен работать с надстройкой сообщения отчета.</span><span class="sxs-lookup"><span data-stu-id="07301-128">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="07301-129">Но если вы заметили, что надстройка недоступна или не работает должным образом, попробуйте другой браузер.</span><span class="sxs-lookup"><span data-stu-id="07301-129">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="07301-130">Для организационных установок Организация должна быть настроена на использование проверки подлинности OAuth.</span><span class="sxs-lookup"><span data-stu-id="07301-130">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="07301-131">Дополнительную информацию можно узнать [в статье определение того, работает ли централизованное развертывание надстроек для вашей организации](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="07301-131">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="07301-132">Администраторы должны быть членами группы ролей глобальные администраторы.</span><span class="sxs-lookup"><span data-stu-id="07301-132">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="07301-133">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="07301-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="07301-134">Получение надстройки "сообщение отчета" для себя</span><span class="sxs-lookup"><span data-stu-id="07301-134">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="07301-135">Перейдите на страницу Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> и найдите надстройку сообщения отчета.</span><span class="sxs-lookup"><span data-stu-id="07301-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="07301-136">Чтобы перейти непосредственно к надстройке сообщения отчета, перейдите на страницу <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="07301-136">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="07301-137">Нажмите кнопку **получить**.</span><span class="sxs-lookup"><span data-stu-id="07301-137">Click **GET IT NOW**.</span></span>

   ![Сообщение отчета: получить его сейчас](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="07301-139">В появившемся диалоговом окне просмотрите условия использования и политика конфиденциальности, а затем нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="07301-139">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="07301-140">Войдите с помощью рабочей или учебной учетной записи (для бизнес-использования) или учетной записи Майкрософт (для личного использования).</span><span class="sxs-lookup"><span data-stu-id="07301-140">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="07301-141">После установки и включения надстройки вы увидите следующие значки:</span><span class="sxs-lookup"><span data-stu-id="07301-141">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="07301-142">В Outlook значок выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07301-142">In Outlook, the icon looks like this:</span></span>

  ![Значок надстройки сообщения отчета для Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="07301-144">В Outlook в Интернете значок выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07301-144">In Outlook on the web, the icon looks like this:</span></span>

  ![Значок надстройки сообщения в веб-отчете Outlook](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="07301-146">Сведения о том, как использовать надстройку, можно найти [в разделе Использование надстройки Report Message](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="07301-146">To learn how to use the add-in, see [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="07301-147">Получение и включение надстройки сообщений отчета для Организации</span><span class="sxs-lookup"><span data-stu-id="07301-147">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="07301-148">Для отображения надстройки в Организации может потребоваться до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="07301-148">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="07301-149">В центре администрирования Microsoft 365 перейдите на страницу " **службы & надстроек** " по адресу <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> , а затем нажмите кнопку **развернуть надстройку**.</span><span class="sxs-lookup"><span data-stu-id="07301-149">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>, and then click **Deploy Add-In**.</span></span>

   ![Страница "службы и надстройки" в центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="07301-151">В появившемся всплывающем окне **развертывание новой надстройки** просмотрите сведения, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="07301-151">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="07301-152">На следующей странице щелкните **выбрать в магазине**.</span><span class="sxs-lookup"><span data-stu-id="07301-152">On the next page, click **Choose from the Store**.</span></span>

   ![Развертывание новой страницы надстройки](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="07301-154">На появившейся странице **Выбор надстройки** щелкните в поле **поиска** , введите **сообщение отчета**и нажмите кнопку **Поиск** поиска ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="07301-154">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="07301-155">В списке результатов найдите **сообщение отчета** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="07301-155">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Выбор результатов поиска для надстройки](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="07301-157">В появившемся диалоговом окне ознакомьтесь со сведениями о лицензировании и конфиденциальности, а затем нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="07301-157">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="07301-158">На открывшейся странице **Настройка надстройки** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="07301-158">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="07301-159">**Назначенные пользователи**: выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="07301-159">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="07301-160">**Все** (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="07301-160">**Everyone** (default)</span></span>
     - <span data-ttu-id="07301-161">**Конкретные пользователи и группы**</span><span class="sxs-lookup"><span data-stu-id="07301-161">**Specific users / groups**</span></span>
     - <span data-ttu-id="07301-162">**Только я**</span><span class="sxs-lookup"><span data-stu-id="07301-162">**Just me**</span></span>

   - <span data-ttu-id="07301-163">**Метод развертывания**: выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="07301-163">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="07301-164">**Fixed (по умолчанию)**: надстройка автоматически развертывается для указанных пользователей и не может удалить ее.</span><span class="sxs-lookup"><span data-stu-id="07301-164">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="07301-165">**Доступно**: пользователи могут устанавливать надстройки на **домашней странице** \> **получить** надстройки \> , **управляемые администратором**.</span><span class="sxs-lookup"><span data-stu-id="07301-165">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="07301-166">**Необязательно**: надстройка автоматически развертывается для указанных пользователей, но ее можно удалить.</span><span class="sxs-lookup"><span data-stu-id="07301-166">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Настройка страницы надстройки](../../media/configure-add-in.png)

   <span data-ttu-id="07301-168">Когда все будет готово, нажмите кнопку **развернуть**.</span><span class="sxs-lookup"><span data-stu-id="07301-168">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="07301-169">На появившейся странице **развертывание сообщения отчета** отображается отчет о ходе выполнения, а затем подтверждение, в котором была развернута надстройка.</span><span class="sxs-lookup"><span data-stu-id="07301-169">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="07301-170">Прочтите сведения и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="07301-170">After you read the information, click **Next**.</span></span>

   ![Страница "развертывание сообщения отчета"](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="07301-172">На появившейся странице **объявить надстройку** просмотрите сведения, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="07301-172">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Страница надстройки объявления](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="07301-174">Узнайте, как использовать надстройку "сообщение отчета"</span><span class="sxs-lookup"><span data-stu-id="07301-174">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="07301-175">Пользователи, которым назначена надстройка, увидят следующие значки:</span><span class="sxs-lookup"><span data-stu-id="07301-175">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="07301-176">В Outlook значок выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07301-176">In Outlook, the icon looks like this:</span></span>

  ![Значок надстройки сообщения отчета для Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="07301-178">В Outlook в Интернете значок выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07301-178">In Outlook on the web, the icon looks like this:</span></span>

  ![Значок надстройки сообщения в веб-отчете Outlook](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="07301-180">При уведомлении пользователей о надстройке сообщения отчета добавьте ссылку для [использования надстройки Report Message](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="07301-180">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="07301-181">Просмотр или изменение параметров для надстройки "сообщение отчета"</span><span class="sxs-lookup"><span data-stu-id="07301-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="07301-182">В центре администрирования Microsoft 365 перейдите на страницу " **службы &** надстроек" по адресу <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> .</span><span class="sxs-lookup"><span data-stu-id="07301-182">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![Страница "службы и надстройки" в новом центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="07301-184">Найдите и выберите надстройку **сообщения отчета** .</span><span class="sxs-lookup"><span data-stu-id="07301-184">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="07301-185">В появившемся всплывающем окне **изменение сообщения отчета** просмотрите и измените параметры в соответствии с требованиями Организации.</span><span class="sxs-lookup"><span data-stu-id="07301-185">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="07301-186">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="07301-186">When you're finished, click **Save**.</span></span>

   ![Параметры для надстройки сообщений отчета](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="07301-188">Просмотр и просмотр сообщений, о которых получено сообщение</span><span class="sxs-lookup"><span data-stu-id="07301-188">View and review reported messages</span></span>

<span data-ttu-id="07301-189">Чтобы просмотреть сообщения, отправляемые пользователями в корпорацию Майкрософт, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="07301-189">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="07301-190">Используйте портал отправки администратором.</span><span class="sxs-lookup"><span data-stu-id="07301-190">Use the Admin Submissions portal.</span></span> <span data-ttu-id="07301-191">Дополнительную информацию можно узнать [в статье Просмотр отправок пользователей в корпорацию Майкрософт](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="07301-191">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="07301-192">Создайте правило для почтового процесса (также называемое правилом транспорта), чтобы отправлять копии сообщений, отправленных в отчет.</span><span class="sxs-lookup"><span data-stu-id="07301-192">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="07301-193">Инструкции можно найти в статье [Использование правил для обработки почтового ящика для просмотра отчетов о пользователях в Майкрософт](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="07301-193">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
