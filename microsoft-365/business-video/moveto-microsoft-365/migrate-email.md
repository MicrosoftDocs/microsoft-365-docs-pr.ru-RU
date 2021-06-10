---
title: Перенос бизнес-электронной почты и календаря из Рабочей области Google
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как перенести электронную почту, контакты и календарь из Рабочей области Google в Microsoft 365 для бизнеса.
ms.openlocfilehash: d6639032b379a2cd632b6ab6ee7e4082b1e7be0b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913626"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="644cd-103">Перенос бизнес-электронной почты и календаря из Рабочей области Google</span><span class="sxs-lookup"><span data-stu-id="644cd-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="644cd-104">Миграцию с управлением администратором можно использовать для Exchange Online из Рабочей области Google.</span><span class="sxs-lookup"><span data-stu-id="644cd-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="644cd-105">Вы можете перенести почту одновременно или поэтапно.</span><span class="sxs-lookup"><span data-stu-id="644cd-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="644cd-106">В следующих действиях покажите, как перенести данные электронной почты одновременно.</span><span class="sxs-lookup"><span data-stu-id="644cd-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="644cd-107">Дополнительные сведения см. в [дополнительных сведениях о переносе пакета G.](/exchange/mailbox-migration/perform-g-suite-migration)</span><span class="sxs-lookup"><span data-stu-id="644cd-107">For more information, see [Perform a G Suite migration](/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="644cd-108">Процесс миграции занимает несколько этапов и может занять от нескольких часов до нескольких дней в зависимости от объема переноса данных.</span><span class="sxs-lookup"><span data-stu-id="644cd-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="644cd-109">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="644cd-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="644cd-110">Создание учетной записи службы Google</span><span class="sxs-lookup"><span data-stu-id="644cd-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="644cd-111">С помощью браузера Chrome вопишитесь в консоль администрирования Google Workspace [по admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="644cd-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="644cd-112">В новой вкладке или окне перейдите на страницу [Учетные записи](https://console.developers.google.com/iam-admin/serviceaccounts) службы.</span><span class="sxs-lookup"><span data-stu-id="644cd-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="644cd-113">Выберите **Создать проект,** назови проект и выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="644cd-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="644cd-114">Выберите **Создать учетную запись службы,** введите имя, выберите **Создать** и затем **сделать**.</span><span class="sxs-lookup"><span data-stu-id="644cd-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="644cd-115">Откройте меню **Действия,** **выберите Изменить** и принять к сведению уникальный ID.</span><span class="sxs-lookup"><span data-stu-id="644cd-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="644cd-116">Этот ID потребуется позднее в процессе.</span><span class="sxs-lookup"><span data-stu-id="644cd-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="644cd-117">Откройте раздел **Делегирования в масштабе домена Show.**</span><span class="sxs-lookup"><span data-stu-id="644cd-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="644cd-118">Выберите **Включить делегирования домена G Suite,** введите имя продукта для экрана согласия и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="644cd-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="644cd-119">Имя продукта не используется в процессе миграции, но необходимо для сохранения в диалоговом окте.</span><span class="sxs-lookup"><span data-stu-id="644cd-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="644cd-120">Откройте меню **Действия** снова и выберите **Создать ключ**.</span><span class="sxs-lookup"><span data-stu-id="644cd-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="644cd-121">Выберите **JSON,** а затем **создайте**.</span><span class="sxs-lookup"><span data-stu-id="644cd-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="644cd-122">Закрытый ключ сохранен в папке загрузки на устройстве.</span><span class="sxs-lookup"><span data-stu-id="644cd-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="644cd-123">Нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="644cd-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="644cd-124">Включить использование API для проекта</span><span class="sxs-lookup"><span data-stu-id="644cd-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="644cd-125">Перейдите на [страницу API.](https://console.developers.google.com/apis/library)</span><span class="sxs-lookup"><span data-stu-id="644cd-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="644cd-126">В панели поиска введите **API Gmail.**</span><span class="sxs-lookup"><span data-stu-id="644cd-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="644cd-127">Выберите его, а затем выберите **Включить**.</span><span class="sxs-lookup"><span data-stu-id="644cd-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="644cd-128">Повторите этот процесс для API календаря Google и API контактов.</span><span class="sxs-lookup"><span data-stu-id="644cd-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="644cd-129">Предоставление доступа к учетной записи службы</span><span class="sxs-lookup"><span data-stu-id="644cd-129">Grant access to the service account</span></span>

1. <span data-ttu-id="644cd-130">Возвращайся на консоль администрирования Рабочей области Google.</span><span class="sxs-lookup"><span data-stu-id="644cd-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="644cd-131">Выберите **элементы безопасности,** прокрутите вниз и откройте **элементы управления API.**</span><span class="sxs-lookup"><span data-stu-id="644cd-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="644cd-132">Прокрутите вниз и **выберите Управление делегирования на весь домен.**</span><span class="sxs-lookup"><span data-stu-id="644cd-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="644cd-133">Выберите **Добавить новое** и введите клиентский ID, о чем вы ранее сообщали.</span><span class="sxs-lookup"><span data-stu-id="644cd-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="644cd-134">Затем введите области OAuth для API Google.</span><span class="sxs-lookup"><span data-stu-id="644cd-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="644cd-135">Они доступны по [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) на шаге 5 и являются:</span><span class="sxs-lookup"><span data-stu-id="644cd-135">These are available at [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="644cd-136">Выберите **Авториз.**</span><span class="sxs-lookup"><span data-stu-id="644cd-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="644cd-137">Создание под домена для почты, которая будет Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="644cd-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="644cd-138">Возвращайся на **консоль администрирования Рабочей области Google.**</span><span class="sxs-lookup"><span data-stu-id="644cd-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="644cd-139">Выберите **домены,** **управление доменами,** затем **добавьте псевдоним домена.**</span><span class="sxs-lookup"><span data-stu-id="644cd-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="644cd-140">Введите псевдоним домена, например `m365.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="644cd-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="644cd-141">Затем выберите **Продолжить и проверить владение доменом**.</span><span class="sxs-lookup"><span data-stu-id="644cd-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="644cd-142">Проверка домена обычно занимает всего несколько минут, но может занять до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="644cd-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="644cd-143">Перейдите в [центр Microsoft 365 администрирования.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="644cd-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="644cd-144">В центре **администрирования Microsoft 365** в левом nav выберите Показать все **,** **Параметры,** домены, а затем добавить **домен**.</span><span class="sxs-lookup"><span data-stu-id="644cd-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="644cd-145">Введите ранее созданный поддомен, а затем **выберите Используйте этот домен.**</span><span class="sxs-lookup"><span data-stu-id="644cd-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="644cd-146">Чтобы подключить домен, выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="644cd-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="644cd-147">Прокрутите вниз и обратите внимание на записи MX, CNAME и записи TXT.</span><span class="sxs-lookup"><span data-stu-id="644cd-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="644cd-148">Возвращение на консоль **администратора Google**.</span><span class="sxs-lookup"><span data-stu-id="644cd-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="644cd-149">Выберите **домены,** выберите **Управление доменами,** **проверка сведений,** а затем **управление доменом**.</span><span class="sxs-lookup"><span data-stu-id="644cd-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="644cd-150">В левом nav выберите **DNS** и прокрутите вниз до **пользовательских записей ресурсов.**</span><span class="sxs-lookup"><span data-stu-id="644cd-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="644cd-151">Откройте падение типа записи и выберите **MX,** введите или скопируйте и введите ранее отмеченные сведения о записи MX, а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="644cd-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="644cd-152">Повторите процесс для записи CNAME и записи TXT.</span><span class="sxs-lookup"><span data-stu-id="644cd-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="644cd-153">Чтобы эти изменения вступили в силу, может потребоваться некоторое время.</span><span class="sxs-lookup"><span data-stu-id="644cd-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="644cd-154">Возвращайся к месту, где вы Microsoft 365 **центре администрирования,** и выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="644cd-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="644cd-155">Теперь домен настроен.</span><span class="sxs-lookup"><span data-stu-id="644cd-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="644cd-156">Создание псевдонимов электронной почты в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="644cd-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="644cd-157">Перед началом миграции необходимо создать псевдонимы электронной почты для пользователей с помощью нового поддомена.</span><span class="sxs-lookup"><span data-stu-id="644cd-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="644cd-158">Чтобы начать следующий шаг, в мастере **добавить** домены в центре администрирования Microsoft 365 выберите **Перейти к активным пользователям.**</span><span class="sxs-lookup"><span data-stu-id="644cd-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="644cd-159">Выберите пользователя, а затем **управляйте иным и электронным письмом.**</span><span class="sxs-lookup"><span data-stu-id="644cd-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="644cd-160">Из **выпадаемой** области доменов выберите поддомен, созданный ранее.</span><span class="sxs-lookup"><span data-stu-id="644cd-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="644cd-161">Введите имя пользователя, выберите **Добавить,** **Сохранить изменения** и закрыть окно.</span><span class="sxs-lookup"><span data-stu-id="644cd-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="644cd-162">Повторите этот процесс для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="644cd-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="644cd-163">Запуск процесса миграции</span><span class="sxs-lookup"><span data-stu-id="644cd-163">Start the migration process</span></span>

<span data-ttu-id="644cd-164">Когда вы закончите, вы будете готовы к миграции.</span><span class="sxs-lookup"><span data-stu-id="644cd-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="644cd-165">В левом nav центра **администрирования Microsoft 365** прокрутите вниз до **центров** администрирования и выберите **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="644cd-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="644cd-166">В **соответствии с получателями** выберите **миграцию,** выберите **New**, **Миграция** в Exchange Online, выберите **миграцию G Suite,** а затем **далее**.</span><span class="sxs-lookup"><span data-stu-id="644cd-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="644cd-167">Создайте CSV-файл со списком почтовых ящиков, которые необходимо перенести.</span><span class="sxs-lookup"><span data-stu-id="644cd-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="644cd-168">Убедитесь, что файл следует такому формату:</span><span class="sxs-lookup"><span data-stu-id="644cd-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="644cd-169">Подробные сведения [см. в aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span><span class="sxs-lookup"><span data-stu-id="644cd-169">For details see [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="644cd-170">Выберите **выберите файл,** перейдите к CSV-файлу, выберите его, выберите **Открыть,** а затем **далее**.</span><span class="sxs-lookup"><span data-stu-id="644cd-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="644cd-171">Проверьте адрес электронной почты администратора, который необходимо использовать для тестирования.</span><span class="sxs-lookup"><span data-stu-id="644cd-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="644cd-172">Выберите **Выберите файл,** перейдите к ранее созданному файлу JSON (обычно в папке Downloads на компьютере), выберите его, выберите **Open**, а затем **далее**.</span><span class="sxs-lookup"><span data-stu-id="644cd-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="644cd-173">Введите имя в поле **Имя пакета новых миграций.**</span><span class="sxs-lookup"><span data-stu-id="644cd-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="644cd-174">Введите поддомен, созданный в поле **Домен целевой** доставки, выберите **Далее** и **затем New**.</span><span class="sxs-lookup"><span data-stu-id="644cd-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="644cd-175">После сэкономленных сведений выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="644cd-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="644cd-176">Теперь можно просмотреть состояние миграции.</span><span class="sxs-lookup"><span data-stu-id="644cd-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="644cd-177">После некоторого времени, в зависимости от того, сколько пользователей вы мигрируете, выберите **Обновление**.</span><span class="sxs-lookup"><span data-stu-id="644cd-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="644cd-178">После изменения состояния на **Synced** выберите **Завершить эту партию** миграции ,затем **да.**</span><span class="sxs-lookup"><span data-stu-id="644cd-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="644cd-179">После завершения процесса состояние изменится на **завершенное.**</span><span class="sxs-lookup"><span data-stu-id="644cd-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="644cd-180">Если вы хотите, вы можете выбрать **сведения Просмотра для** получения дополнительных сведений о миграции.</span><span class="sxs-lookup"><span data-stu-id="644cd-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="644cd-181">Нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="644cd-181">Select **Close**.</span></span> 
1. <span data-ttu-id="644cd-182">Откройте Outlook, чтобы убедиться, что все электронные письма из Рабочей области Google успешно перенесены.</span><span class="sxs-lookup"><span data-stu-id="644cd-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="644cd-183">Это можно повторить и для элементов календаря и контактов.</span><span class="sxs-lookup"><span data-stu-id="644cd-183">You can repeat this for calendar items and contacts as well.</span></span>