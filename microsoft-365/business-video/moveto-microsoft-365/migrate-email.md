---
title: Перенос бизнес-электронной почты и календаря из Google Workspace
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
description: Узнайте, как перенести электронную почту, контакты и календарь из Google Workspace в Microsoft 365 для бизнеса.
ms.openlocfilehash: ab70a43fb7c26c23ebc9024b1cd2803c164a0aa4
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794711"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="87f00-103">Перенос бизнес-электронной почты и календаря из Google Workspace</span><span class="sxs-lookup"><span data-stu-id="87f00-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="87f00-104">Вы можете использовать миграцию под управлением администратора в Exchange Online из Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="87f00-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="87f00-105">Вы можете перенести почту одновременно или поэтапно.</span><span class="sxs-lookup"><span data-stu-id="87f00-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="87f00-106">Ниже покажем, как перенести данные электронной почты одновременно.</span><span class="sxs-lookup"><span data-stu-id="87f00-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="87f00-107">Дополнительные сведения см. в [переносе G Suite.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)</span><span class="sxs-lookup"><span data-stu-id="87f00-107">For more information, see [Perform a G Suite migration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="87f00-108">Процесс миграции состоит из нескольких этапов и может занять от нескольких часов до пары дней в зависимости от объема переносимого объема данных.</span><span class="sxs-lookup"><span data-stu-id="87f00-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="87f00-109">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="87f00-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="87f00-110">Создание учетной записи службы Google</span><span class="sxs-lookup"><span data-stu-id="87f00-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="87f00-111">Используя браузер Chrome, во sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="87f00-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="87f00-112">На новой вкладке или в окне перейдите на страницу ["Учетные записи служб".](https://console.developers.google.com/iam-admin/serviceaccounts)</span><span class="sxs-lookup"><span data-stu-id="87f00-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="87f00-113">Выберите **"Создать проект",** назовем его и выберите **"Создать".**</span><span class="sxs-lookup"><span data-stu-id="87f00-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="87f00-114">Выберите **"Создать учетную запись службы",** введите имя, выберите **"Создать"** и **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="87f00-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="87f00-115">Откройте меню **"Действия",** **выберите "Изменить"** и заметьте уникальный ИД.</span><span class="sxs-lookup"><span data-stu-id="87f00-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="87f00-116">Этот ИД потребуется позже.</span><span class="sxs-lookup"><span data-stu-id="87f00-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="87f00-117">Откройте раздел **"Показать делегирования для всего** домена".</span><span class="sxs-lookup"><span data-stu-id="87f00-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="87f00-118">Select **Enable G Suite Domain-wide Delegation,** enter a product name for the consent screen, and choose **Save**.</span><span class="sxs-lookup"><span data-stu-id="87f00-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="87f00-119">Название продукта не используется процессом миграции, но необходимо для сохранения в диалоговом оке.</span><span class="sxs-lookup"><span data-stu-id="87f00-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="87f00-120">Снова откройте **меню "Действия"** и выберите **"Создать ключ".**</span><span class="sxs-lookup"><span data-stu-id="87f00-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="87f00-121">Выберите **JSON,** а затем **создайте**.</span><span class="sxs-lookup"><span data-stu-id="87f00-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="87f00-122">Закрытый ключ сохранен в папке загрузки на устройстве.</span><span class="sxs-lookup"><span data-stu-id="87f00-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="87f00-123">Нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="87f00-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="87f00-124">Включить использование API для проекта</span><span class="sxs-lookup"><span data-stu-id="87f00-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="87f00-125">Перейдите на [страницу API.](https://console.developers.google.com/apis/library)</span><span class="sxs-lookup"><span data-stu-id="87f00-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="87f00-126">В области поиска введите **API Gmail.**</span><span class="sxs-lookup"><span data-stu-id="87f00-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="87f00-127">Выберите его и выберите **"Включить".**</span><span class="sxs-lookup"><span data-stu-id="87f00-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="87f00-128">Повторите этот процесс для API Календаря Google и API контактов.</span><span class="sxs-lookup"><span data-stu-id="87f00-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="87f00-129">Предоставление доступа к учетной записи службы</span><span class="sxs-lookup"><span data-stu-id="87f00-129">Grant access to the service account</span></span>

1. <span data-ttu-id="87f00-130">Вернись к консоли администрирования Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="87f00-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="87f00-131">Выберите **"Безопасность",** прокрутите вниз и откройте **элементы управления API.**</span><span class="sxs-lookup"><span data-stu-id="87f00-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="87f00-132">Прокрутите вниз и **выберите "Управление делегированиями на весь домен".**</span><span class="sxs-lookup"><span data-stu-id="87f00-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="87f00-133">Выберите **"Добавить"** и введите ранее заметимый вами ИД клиента.</span><span class="sxs-lookup"><span data-stu-id="87f00-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="87f00-134">Затем введите области OAuth для API Google.</span><span class="sxs-lookup"><span data-stu-id="87f00-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="87f00-135">Они доступны [на](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) aka.ms/GoogleWorkspaceMigration на шаге 5 и:</span><span class="sxs-lookup"><span data-stu-id="87f00-135">These are available at [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="87f00-136">Choose **Authorize**.</span><span class="sxs-lookup"><span data-stu-id="87f00-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="87f00-137">Создание под домена для почты, которая будет отправлена в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="87f00-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="87f00-138">Вернись к **консоли администрирования Google Workspace.**</span><span class="sxs-lookup"><span data-stu-id="87f00-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="87f00-139">Выберите **"Домены",** **"Управление доменами",** а затем добавьте **псевдоним домена.**</span><span class="sxs-lookup"><span data-stu-id="87f00-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="87f00-140">Введите псевдоним домена, например `m365.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="87f00-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="87f00-141">Затем выберите **"Продолжить" и проверьте владение доменом.**</span><span class="sxs-lookup"><span data-stu-id="87f00-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="87f00-142">Проверка домена обычно занимает всего несколько минут, но может занять до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="87f00-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="87f00-143">Перейдите в [Центр администрирования Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="87f00-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="87f00-144">В Центре **администрирования Microsoft 365** в левой области nav выберите **"Показать все",**"Параметры", "Домены" и **"Добавить домен".**</span><span class="sxs-lookup"><span data-stu-id="87f00-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="87f00-145">Введите ранее созданный поддомен, а затем выберите **"Использовать этот домен".**</span><span class="sxs-lookup"><span data-stu-id="87f00-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="87f00-146">Чтобы подключить домен, выберите **"Продолжить".**</span><span class="sxs-lookup"><span data-stu-id="87f00-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="87f00-147">Прокрутите вниз и запишите записи MX, CNAME и TXT.</span><span class="sxs-lookup"><span data-stu-id="87f00-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="87f00-148">Вернись в **консоль администратора Google.**</span><span class="sxs-lookup"><span data-stu-id="87f00-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="87f00-149">Выберите **"Домены",** **"Управление доменами",** **"Проверка сведений"** и **"Управление доменом".**</span><span class="sxs-lookup"><span data-stu-id="87f00-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="87f00-150">В левой области nav выберите **DNS** и прокрутите вниз до **пользовательских записей ресурсов.**</span><span class="sxs-lookup"><span data-stu-id="87f00-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="87f00-151">Откройте dropdown типа записи и выберите **MX,** введите или скопируйте и введите сведения о записи MX, которые вы ранее указали, а затем выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="87f00-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="87f00-152">Повторите процесс для записи CNAME и TXT.</span><span class="sxs-lookup"><span data-stu-id="87f00-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="87f00-153">Чтобы эти изменения вступили в силу, может потребоваться некоторое время.</span><span class="sxs-lookup"><span data-stu-id="87f00-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="87f00-154">Вернись к месту, где вы слева в Центре администрирования **Microsoft 365,** и выберите **"Продолжить".**</span><span class="sxs-lookup"><span data-stu-id="87f00-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="87f00-155">Ваш домен настроен.</span><span class="sxs-lookup"><span data-stu-id="87f00-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="87f00-156">Создание псевдонимов электронной почты в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="87f00-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="87f00-157">Перед началом миграции необходимо создать псевдонимы электронной почты для пользователей с новым поддоменом.</span><span class="sxs-lookup"><span data-stu-id="87f00-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="87f00-158">Чтобы начать следующий шаг,  в мастере добавления доменов в Центре администрирования Microsoft 365 выберите "Перейти **к активным пользователям".**</span><span class="sxs-lookup"><span data-stu-id="87f00-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="87f00-159">Выберите пользователя, а затем **управляйте именами пользователей и электронной почтой.**</span><span class="sxs-lookup"><span data-stu-id="87f00-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="87f00-160">В **dropdown domains** (Домены) выберите ранее созданный поддомен.</span><span class="sxs-lookup"><span data-stu-id="87f00-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="87f00-161">Введите имя пользователя, выберите **"Добавить",** **"Сохранить изменения"** и закройте окно.</span><span class="sxs-lookup"><span data-stu-id="87f00-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="87f00-162">Повторите этот процесс для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="87f00-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="87f00-163">Запуск процесса миграции</span><span class="sxs-lookup"><span data-stu-id="87f00-163">Start the migration process</span></span>

<span data-ttu-id="87f00-164">Завершив миграцию, вы будете готовы к миграции.</span><span class="sxs-lookup"><span data-stu-id="87f00-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="87f00-165">В левой области в Центре администрирования **Microsoft 365** прокрутите вниз до центров администрирования и выберите **Exchange.** </span><span class="sxs-lookup"><span data-stu-id="87f00-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="87f00-166">В **области получателей** выберите **миграцию,** выберите **"Новый",**"Миграция в Exchange **Online",**"Миграция G **Suite"** и **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="87f00-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="87f00-167">Создайте CSV-файл со списком почтовых ящиков, которые нужно перенести.</span><span class="sxs-lookup"><span data-stu-id="87f00-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="87f00-168">Убедитесь, что файл имеет такой формат:</span><span class="sxs-lookup"><span data-stu-id="87f00-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="87f00-169">Подробные сведения [см. в aka.ms/GoogleWorkspaceMigration.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac)</span><span class="sxs-lookup"><span data-stu-id="87f00-169">For details see [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="87f00-170">Выберите **"Выбрать файл",** перейдите к CSV-файлу, выберите его, выберите **"Открыть"** и **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="87f00-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="87f00-171">Проверьте адрес электронной почты администратора, который вы хотите использовать для тестирования.</span><span class="sxs-lookup"><span data-stu-id="87f00-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="87f00-172">Выберите **"Выбрать файл",** перейдите к ранее созданному JSON-файлу (обычно в папке "Загрузки" на компьютере), выберите его, выберите "Открыть" **и** **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="87f00-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="87f00-173">Введите имя в поле **"Имя нового пакета миграции".**</span><span class="sxs-lookup"><span data-stu-id="87f00-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="87f00-174">Введите поддомен, созданный в поле **"Целевой** домен доставки", выберите **"Далее"** и **"Создать"**.</span><span class="sxs-lookup"><span data-stu-id="87f00-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="87f00-175">После с сохраненных сведений выберите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="87f00-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="87f00-176">Теперь можно просмотреть состояние миграции.</span><span class="sxs-lookup"><span data-stu-id="87f00-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="87f00-177">Через некоторое время в зависимости от того, сколько пользователей вы хотите перенести, выберите **"Обновить".**</span><span class="sxs-lookup"><span data-stu-id="87f00-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="87f00-178">После того как состояние изменится на **"Синхронизировано",** выберите **"Завершить этот** пакет миграции", а затем **"Да".**</span><span class="sxs-lookup"><span data-stu-id="87f00-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="87f00-179">После завершения процесса состояние изменится на **"Завершено".**</span><span class="sxs-lookup"><span data-stu-id="87f00-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="87f00-180">При этом можно выбрать **"Просмотреть сведения" для** получения дополнительных сведений о миграции.</span><span class="sxs-lookup"><span data-stu-id="87f00-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="87f00-181">Нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="87f00-181">Select **Close**.</span></span> 
1. <span data-ttu-id="87f00-182">Откройте Outlook, чтобы убедиться, что все сообщения электронной почты из Google Workspace успешно перенесены.</span><span class="sxs-lookup"><span data-stu-id="87f00-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="87f00-183">Это также можно повторить для элементов календаря и контактов.</span><span class="sxs-lookup"><span data-stu-id="87f00-183">You can repeat this for calendar items and contacts as well.</span></span>