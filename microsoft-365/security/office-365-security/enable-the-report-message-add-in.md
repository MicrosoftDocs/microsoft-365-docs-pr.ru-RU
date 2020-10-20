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
description: Сведения о том, как включить надстройку сообщения отчета для Outlook и Outlook в Интернете для отдельных пользователей или всей Организации.
ms.openlocfilehash: b061d9db44b08a65b59481035c055a1b75eb6e3c
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600373"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="e4cb2-103">Включение надстройки "Пожаловаться на сообщение"</span><span class="sxs-lookup"><span data-stu-id="e4cb2-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="e4cb2-104">Если вы являетесь администратором в организации Microsoft 365 с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="e4cb2-105">Дополнительные сведения см. в [статье Использование отправки администратором для отправки подозреваемой спама, фишинга, URL-адресов и файлов в корпорацию Майкрософт](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="e4cb2-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="e4cb2-106">Надстройка сообщения отчета для Outlook и Outlook в Интернете (прежнее название — Outlook Web App) позволяет людям легко сообщать о ложных срабатываниях (хорошее письмо отмечено как плохое) или ложные отрицательные (недопустимые сообщения электронной почты) корпорации Майкрософт и ее аффилированным лицам для анализа.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="e4cb2-107">Корпорация Майкрософт использует эти отправки для повышения эффективности технологий защиты электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="e4cb2-108">Например, предположим, что люди сообщают о большом числе фишинговых сообщений.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="e4cb2-109">Эта информация послужит в качестве поверхности в [панели мониторинга безопасности](security-dashboard.md) и других отчетов.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="e4cb2-110">Группа безопасности вашей организации может использовать эти сведения для указания того, что политики защиты от фишинга может потребоваться обновить.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="e4cb2-111">Или, если пользователи сообщают о большом количестве сообщений, помеченных как нежелательные, с помощью надстройки Report Message, группе безопасности Организации может потребоваться настроить [политики защиты от нежелательной почты](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e4cb2-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="e4cb2-112">Кроме того, если в организации используется [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) или [Plan 2](office-365-ti.md), надстройка сообщения отчета предоставляет группе безопасности Организации полезную информацию, которую можно использовать для просмотра и обновления политик безопасности.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-112">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="e4cb2-113">Администраторы могут включить надстройку сообщений отчета для Организации, а отдельные пользователи могут установить их самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="e4cb2-114">Если вы являетесь отдельным пользователем, вы можете [включить для себя надстройку сообщения отчета](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="e4cb2-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="e4cb2-115">Если вы являетесь глобальным администратором или администратором Exchange Online, а Exchange настроен на использование проверки подлинности OAuth, вы можете [включить надстройку сообщения отчета для Организации](#get-and-enable-the-report-message-add-in-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="e4cb2-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="e4cb2-116">Теперь Add-In сообщения отчетов можно использовать для [централизованного развертывания](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="e4cb2-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e4cb2-117">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="e4cb2-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e4cb2-118">Надстройка сообщения отчета работает с большинством подписок Microsoft 365 и следующих продуктов:</span><span class="sxs-lookup"><span data-stu-id="e4cb2-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="e4cb2-119">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="e4cb2-119">Outlook on the web</span></span>
  - <span data-ttu-id="e4cb2-120">Outlook 2013 SP1 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="e4cb2-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="e4cb2-121">Outlook 2016 для Mac;</span><span class="sxs-lookup"><span data-stu-id="e4cb2-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="e4cb2-122">Outlook, входящий в состав приложений Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e4cb2-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="e4cb2-123">Надстройка сообщений отчета недоступна для почтовых ящиков в локальных организациях Exchange.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-123">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="e4cb2-124">Можно настроить копирование или перенаправление сообщений, отправленных в указанный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-124">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="e4cb2-125">Для получения дополнительных сведений обратитесь к разделу [политики отправки пользователей](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="e4cb2-125">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="e4cb2-126">Существующий веб-браузер должен работать с надстройкой сообщения отчета.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="e4cb2-127">Но если вы заметили, что надстройка недоступна или не работает должным образом, попробуйте другой браузер.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="e4cb2-128">Для организационных установок Организация должна быть настроена на использование проверки подлинности OAuth.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="e4cb2-129">Дополнительную информацию можно узнать [в статье определение того, работает ли централизованное развертывание надстроек для вашей организации](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="e4cb2-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="e4cb2-130">Администраторы должны быть членами группы ролей глобальные администраторы.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="e4cb2-131">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e4cb2-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="e4cb2-132">Получение надстройки "сообщение отчета" для себя</span><span class="sxs-lookup"><span data-stu-id="e4cb2-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="e4cb2-133">Перейдите на страницу Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> и найдите надстройку сообщения отчета.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="e4cb2-134">Чтобы перейти непосредственно к надстройке сообщения отчета, перейдите на страницу <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="e4cb2-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="e4cb2-135">Нажмите кнопку **получить**.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-135">Click **GET IT NOW**.</span></span>

   ![Сообщение отчета: получить его сейчас](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="e4cb2-137">В появившемся диалоговом окне просмотрите условия использования и политика конфиденциальности, а затем нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="e4cb2-138">Войдите с помощью рабочей или учебной учетной записи (для бизнес-использования) или учетной записи Майкрософт (для личного использования).</span><span class="sxs-lookup"><span data-stu-id="e4cb2-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="e4cb2-139">После установки и включения надстройки вы увидите следующие значки:</span><span class="sxs-lookup"><span data-stu-id="e4cb2-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="e4cb2-140">В Outlook значок выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e4cb2-140">In Outlook, the icon looks like this:</span></span>

  ![Значок надстройки сообщения отчета для Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="e4cb2-142">В Outlook в Интернете значок выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e4cb2-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Значок надстройки сообщения в веб-отчете Outlook](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="e4cb2-144">Сведения о том, как использовать надстройку, можно найти [в разделе Использование надстройки Report Message](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="e4cb2-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="e4cb2-145">Получение и включение надстройки сообщений отчета для Организации</span><span class="sxs-lookup"><span data-stu-id="e4cb2-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="e4cb2-146">Для отображения надстройки в Организации может потребоваться до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="e4cb2-147">В центре администрирования Microsoft 365 перейдите на страницу **Параметры, интегрированные приложения & надстройки** по адресу <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> и нажмите кнопку **развернуть надстройку**.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-147">In the Microsoft 365 admin center, go to the **Settings, integrated Apps & Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, and then click **Deploy Add-In**.</span></span>

   ![Страница "службы и надстройки" в центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="e4cb2-149">В появившемся всплывающем окне **развертывание новой надстройки** просмотрите сведения, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="e4cb2-150">На следующей странице щелкните **выбрать в магазине**.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-150">On the next page, click **Choose from the Store**.</span></span>

   ![Развертывание новой страницы надстройки](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="e4cb2-152">На появившейся странице **Выбор надстройки** щелкните в поле **поиска** , введите **сообщение отчета**и нажмите кнопку **Поиск** поиска ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="e4cb2-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="e4cb2-153">В списке результатов найдите **сообщение отчета** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-153">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Выбор результатов поиска для надстройки](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="e4cb2-155">В появившемся диалоговом окне ознакомьтесь со сведениями о лицензировании и конфиденциальности, а затем нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="e4cb2-156">На открывшейся странице **Настройка надстройки** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e4cb2-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e4cb2-157">**Назначенные пользователи**: выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="e4cb2-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="e4cb2-158">**Все** (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e4cb2-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="e4cb2-159">**Конкретные пользователи и группы**</span><span class="sxs-lookup"><span data-stu-id="e4cb2-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="e4cb2-160">**Только я**</span><span class="sxs-lookup"><span data-stu-id="e4cb2-160">**Just me**</span></span>

   - <span data-ttu-id="e4cb2-161">**Метод развертывания**: выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="e4cb2-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="e4cb2-162">**Fixed (по умолчанию)**: надстройка автоматически развертывается для указанных пользователей и не может удалить ее.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="e4cb2-163">**Доступно**: пользователи могут устанавливать надстройки на **домашней странице** \> **получить** надстройки \> , **управляемые администратором**.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="e4cb2-164">**Необязательно**: надстройка автоматически развертывается для указанных пользователей, но ее можно удалить.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Настройка страницы надстройки](../../media/configure-add-in.png)

   <span data-ttu-id="e4cb2-166">Когда все будет готово, нажмите кнопку **развернуть**.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-166">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="e4cb2-167">На появившейся странице **развертывание сообщения отчета** отображается отчет о ходе выполнения, а затем подтверждение, в котором была развернута надстройка.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-167">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="e4cb2-168">Прочтите сведения и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-168">After you read the information, click **Next**.</span></span>

   ![Страница "развертывание сообщения отчета"](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="e4cb2-170">На появившейся странице **объявить надстройку** просмотрите сведения, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-170">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Страница надстройки объявления](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="e4cb2-172">Узнайте, как использовать надстройку "сообщение отчета"</span><span class="sxs-lookup"><span data-stu-id="e4cb2-172">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="e4cb2-173">Пользователи, которым назначена надстройка, увидят следующие значки:</span><span class="sxs-lookup"><span data-stu-id="e4cb2-173">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="e4cb2-174">В Outlook значок выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e4cb2-174">In Outlook, the icon looks like this:</span></span>

  ![Значок надстройки сообщения отчета для Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="e4cb2-176">В Outlook в Интернете значок выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e4cb2-176">In Outlook on the web, the icon looks like this:</span></span>

  ![Значок надстройки сообщения в веб-отчете Outlook](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="e4cb2-178">При уведомлении пользователей о надстройке сообщения отчета добавьте ссылку для [использования надстройки Report Message](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="e4cb2-178">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="e4cb2-179">Просмотр или изменение параметров для надстройки "сообщение отчета"</span><span class="sxs-lookup"><span data-stu-id="e4cb2-179">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="e4cb2-180">В центре администрирования Microsoft 365 перейдите на страницу " **службы &** надстроек" по адресу <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> .</span><span class="sxs-lookup"><span data-stu-id="e4cb2-180">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![Службы и Add-Ins страница в новом центре администрирования Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="e4cb2-182">Найдите и выберите надстройку **сообщения отчета** .</span><span class="sxs-lookup"><span data-stu-id="e4cb2-182">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="e4cb2-183">В появившемся всплывающем окне **изменение сообщения отчета** просмотрите и измените параметры в соответствии с требованиями Организации.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-183">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="e4cb2-184">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-184">When you're finished, click **Save**.</span></span>

   ![Параметры для надстройки сообщений отчета](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="e4cb2-186">Просмотр и просмотр сообщений, о которых получено сообщение</span><span class="sxs-lookup"><span data-stu-id="e4cb2-186">View and review reported messages</span></span>

<span data-ttu-id="e4cb2-187">Чтобы просмотреть сообщения, отправляемые пользователями в корпорацию Майкрософт, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-187">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="e4cb2-188">Используйте портал отправки администратором.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-188">Use the Admin Submissions portal.</span></span> <span data-ttu-id="e4cb2-189">Дополнительную информацию можно узнать [в статье Просмотр отправок пользователей в корпорацию Майкрософт](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="e4cb2-189">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="e4cb2-190">Создайте правило для почтового процесса (также называемое правилом транспорта), чтобы отправлять копии сообщений, отправленных в отчет.</span><span class="sxs-lookup"><span data-stu-id="e4cb2-190">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="e4cb2-191">Инструкции можно найти в статье [Использование правил для обработки почтового ящика для просмотра отчетов о пользователях в Майкрософт](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="e4cb2-191">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
