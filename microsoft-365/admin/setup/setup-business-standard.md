---
title: Настройка Microsoft 365 бизнес стандарт
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Узнайте, как настроить подписку на Microsoft 365 бизнес стандарт.
ms.openlocfilehash: b42dd0779c708410614ea2ab0d134aa3dcf0c7e9
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44778929"
---
# <a name="set-up-microsoft-business-standard"></a><span data-ttu-id="17482-103">Настройка Microsoft 365 бизнес стандарт</span><span class="sxs-lookup"><span data-stu-id="17482-103">Set up Microsoft Business Standard</span></span>
  
 <span data-ttu-id="17482-104">*Эти инструкции предназначены для коммерческих и [некоммерческих](https://go.microsoft.com/fwlink/p/?LinkId=627221) организаций, использующих **[план подписки Microsoft 365 бизнес стандарт.](https://go.microsoft.com/fwlink/p/?LinkId=627220)***</span><span class="sxs-lookup"><span data-stu-id="17482-104">*These steps are for businesses and [nonprofits](https://go.microsoft.com/fwlink/p/?LinkId=627221) that have the **[Microsoft 365 Business Standard plan.](https://go.microsoft.com/fwlink/p/?LinkId=627220)***</span></span>

<span data-ttu-id="17482-105">Посмотрите короткое видео о настройке Microsoft 365 бизнес стандарт (прежнее название — Office 365 бизнес премиум).</span><span class="sxs-lookup"><span data-stu-id="17482-105">Watch a short video about setting up Microsoft 365 Business Standard (formerly known as Office 365 Business Premium).</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/913be1ad-bae1-40c0-9ded-15bb477b828b]

<span data-ttu-id="17482-106">Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="17482-106">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="17482-107">Добавление домена для персонализации входа</span><span class="sxs-lookup"><span data-stu-id="17482-107">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="17482-108">При покупке Microsoft 365 бизнес стандарт вы можете воспользоваться принадлежащим вам доменом или купить домен во время регистрации.</span><span class="sxs-lookup"><span data-stu-id="17482-108">When you purchase Microsoft 365 Business Standard, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="17482-109">Если вы приобрели новый домен во время регистрации, он уже полностью настроен и можно перейти к пункту [Добавление пользователей и назначение лицензий](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="17482-109">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

1. <span data-ttu-id="17482-110">Войдите в [Центр администрирования Microsoft 365](https://admin.microsoft.com) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="17482-110">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="17482-111">Выберите **Перейти к установке**, чтобы запустить мастер установки.</span><span class="sxs-lookup"><span data-stu-id="17482-111">Choose **Go to setup** to start the wizard.</span></span>

3. <span data-ttu-id="17482-112">Со страницы **Установка приложений Office** можно также, если необходимо, установить приложения на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="17482-112">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="17482-113">На шаге **Добавить домен** введите имя домена, который вы хотите использовать (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="17482-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="17482-114">Если вы приобрели домен во время регистрации, шаг **Добавить домен** не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="17482-114">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="17482-115">Вместо этого перейдите в раздел [Добавить пользователей](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="17482-115">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="17482-116">Выполните шаги, описанные в мастере, по [созданию записей DNS для Office 365 у любого поставщика услуг размещения DNS](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider), который проверяет, являетесь ли вы владельцем домена.</span><span class="sxs-lookup"><span data-stu-id="17482-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="17482-117">Если вы знаете свой узел домена, см. также [инструкции, связанные с узлом](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="17482-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="17482-118">Если ваш поставщик услуг размещения — GoDaddy или другой узел, поддерживающий [подключение доменов](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), все просто: вам будет автоматически предложено войти в систему и разрешить Майкрософт проверить подлинность от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="17482-118">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![На странице GoDaddy "Подтверждение доступа" выберите "Авторизовать".](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="17482-120">Добавление пользователей и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="17482-120">Add users and assign licenses</span></span>

<span data-ttu-id="17482-121">Вы можете добавить пользователей в мастере или [позднее](../add-users/add-users.md) в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="17482-121">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="17482-122">Кроме того, если у вас есть локальный контроллер домена, вы можете добавить пользователей с помощью [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="17482-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="17482-123">Добавление пользователей в мастере</span><span class="sxs-lookup"><span data-stu-id="17482-123">Add users in the wizard</span></span>

<span data-ttu-id="17482-124">Всем пользователям, которых вы добавляете в мастере, автоматически назначается лицензия Microsoft 365 бизнес стандарт.</span><span class="sxs-lookup"><span data-stu-id="17482-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Standard license.</span></span>

1. <span data-ttu-id="17482-125">Если в вашей подписке на Microsoft 365 бизнес стандарт уже есть пользователи (например, если вы использовали Azure AD Connect), вы можете назначить им лицензии прямо сейчас.</span><span class="sxs-lookup"><span data-stu-id="17482-125">If your Microsoft 365 Business Standard subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="17482-126">Добавьте лицензии и для них.</span><span class="sxs-lookup"><span data-stu-id="17482-126">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="17482-127">После добавления пользователей у вас также будет возможность предоставить им учетные данные.</span><span class="sxs-lookup"><span data-stu-id="17482-127">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="17482-128">Вы можете распечатать их, отправить по электронной почте или скачать.</span><span class="sxs-lookup"><span data-stu-id="17482-128">You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="17482-129">Подключение домена</span><span class="sxs-lookup"><span data-stu-id="17482-129">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="17482-130">Если вы решили воспользоваться доменом .onmicrosoft или использовали Azure AD Connect для настройки пользователей, этот шаг отображаться не будет.</span><span class="sxs-lookup"><span data-stu-id="17482-130">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="17482-131">Для настройки служб вам необходимо обновить некоторые записи узла DNS или регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="17482-131">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="17482-132">Мастер настройки обычно обнаруживает регистратор и предоставляет ссылку на пошаговые инструкции по обновлению записей NS на его сайте.</span><span class="sxs-lookup"><span data-stu-id="17482-132">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="17482-133">В противном случае [измените серверы доменных имен для настройки Office 365 у любого регистратора доменных имен](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span><span class="sxs-lookup"><span data-stu-id="17482-133">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="17482-134">Если у вас уже есть записи DNS, например для существующего веб-сайта, но узел DNS поддерживает [подключение доменов](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), выберите пункт **Автоматическое добавление записей**.</span><span class="sxs-lookup"><span data-stu-id="17482-134">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="17482-135">На странице **Выберите веб-службы** примите все условия по умолчанию, нажмите **Далее**, а затем на странице узла DNS выберите **Авторизовать**.</span><span class="sxs-lookup"><span data-stu-id="17482-135">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="17482-136">Если у вас уже есть записи DNS для других узлов DNS (не поддерживающих подключение доменов), вам потребуется управлять своими записями DNS, чтобы убедиться в наличии подключения существующих служб.</span><span class="sxs-lookup"><span data-stu-id="17482-136">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="17482-137">Дополнительные сведения см. в статье [Основные сведения о доменах](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics).</span><span class="sxs-lookup"><span data-stu-id="17482-137">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="17482-138">Выполните шаги, описанные в мастере, чтобы настроить электронную почту и другие службы.</span><span class="sxs-lookup"><span data-stu-id="17482-138">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="17482-139">По завершении процесса регистрации вы будете перенаправлены в Центр администрирования, где с помощью мастера установите приложения Office, добавите свой домен, пользователей и назначите лицензии.</span><span class="sxs-lookup"><span data-stu-id="17482-139">When the signup process is complete, you'll be directed to the admin center, where you'll follow a wizard to install Office apps, add your domain, add users, and assign licenses.</span></span> <span data-ttu-id="17482-140">Выполнив первоначальные настройки, вы сможете продолжить настраивать службы, входящие в состав подписок, на странице**Настройка** в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="17482-140">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="17482-141">Дополнительные сведения о мастере настройки и странице **Настройка** в Центре администрирования см. в статье [Различия между мастером настройки и страницей "Настройка"](o365-setup-wizard-and-setup-page.md).</span><span class="sxs-lookup"><span data-stu-id="17482-141">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>

## <a name="finish-setting-up"></a><span data-ttu-id="17482-142">Завершение настройки</span><span class="sxs-lookup"><span data-stu-id="17482-142">Finish setting up</span></span>

### <a name="set-up-outlook-for-email"></a><span data-ttu-id="17482-143">Настройка Outlook для работы с электронной почтой</span><span class="sxs-lookup"><span data-stu-id="17482-143">Set up Outlook for email</span></span>

1. <span data-ttu-id="17482-144">В меню "Пуск" в Windows найдите Outlookи выберите это приложение.</span><span class="sxs-lookup"><span data-stu-id="17482-144">On the Windows Start menu, search for Outlook, and select it.</span></span>

    <span data-ttu-id="17482-145">(Если вы используете компьютер Mac, откройте Outlook с панели инструментов или найдите с помощью диспетчера файлов Finder.)</span><span class="sxs-lookup"><span data-stu-id="17482-145">(If you're using a Mac, open Outlook from the toolbar or locate it using the Finder.)</span></span>

    <span data-ttu-id="17482-146">Если вы только что установили Outlook, на странице приветствия нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="17482-146">If you've just installed Outlook, on the Welcome page, select **Next**.</span></span>

2. <span data-ttu-id="17482-147">Выберите **Файл** \> **Сведения** \> **Добавить учетную запись**.</span><span class="sxs-lookup"><span data-stu-id="17482-147">Choose **File** \> **Info** \> **Add Account**.</span></span>

3. <span data-ttu-id="17482-148">Введите свой адрес электронной почты Microsoft и нажмите кнопку **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="17482-148">Enter your Microsoft email address and select **Connect**.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
<span data-ttu-id="17482-149">Дополнительные сведения см. в статье [Настройка Outlook для работы с электронной почтой](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span><span class="sxs-lookup"><span data-stu-id="17482-149">More at [Set up Outlook for email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span></span>
  
### <a name="import-email"></a><span data-ttu-id="17482-150">Импорт электронной почты</span><span class="sxs-lookup"><span data-stu-id="17482-150">Import email</span></span>

<span data-ttu-id="17482-151">При использовании Outlook с другой учетной записью электронной почты старые сообщения электронной почты, элементы календаря и контакты можно импортировать в новую учетную запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="17482-151">If you were using Outlook with another email account, you can import your previous email, calendar, and contacts into your new Microsoft account.</span></span>
  
1. <span data-ttu-id="17482-152">**Экспорт старых сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="17482-152">**Export your old email**</span></span>

    <span data-ttu-id="17482-153">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span><span class="sxs-lookup"><span data-stu-id="17482-153">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>

    <span data-ttu-id="17482-154">Выберите пункт **Экспорт в файл** и следуйте инструкциям для экспорта файла данных Outlook (PST) и всех вложенных папок.</span><span class="sxs-lookup"><span data-stu-id="17482-154">Select **Export to a File** and then follow the steps to export your Outlook Data File (.pst) and any subfolders.</span></span>

2. <span data-ttu-id="17482-155">**Импорт старых сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="17482-155">**Import your old email**</span></span>

    <span data-ttu-id="17482-156">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span><span class="sxs-lookup"><span data-stu-id="17482-156">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span></span>

    <span data-ttu-id="17482-157">В этот раз выберите пункт **Импорт из другой программы или файла** и следуйте инструкциям для импорта файла резервной копии, созданного при экспорте старых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="17482-157">This time, select **Import from another program or file** and follow the steps to import the backup file you created when you exported your old email.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
<span data-ttu-id="17482-158">Дополнительные сведения см. в статье [Импорт электронной почты с помощью Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span><span class="sxs-lookup"><span data-stu-id="17482-158">More at [Import email with Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span></span>

<span data-ttu-id="17482-159">Кроме того, вы можете импортировать сообщения всех пользователей с помощью Центра администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="17482-159">You can also use Exchange admin center to import everyone's email.</span></span> <span data-ttu-id="17482-160">Дополнительные сведения см. в статье [Перенос нескольких учетных записей электронной почты](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="17482-160">For more information, see [migrate multiple email accounts](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
### <a name="use-a-public-website"></a><span data-ttu-id="17482-161">Использование общедоступного веб-сайта</span><span class="sxs-lookup"><span data-stu-id="17482-161">Use a public website</span></span>

<span data-ttu-id="17482-162">Microsoft 365 doesn't include a public website for your business.</span><span class="sxs-lookup"><span data-stu-id="17482-162">Microsoft 365 doesn't include a public website for your business.</span></span> <span data-ttu-id="17482-163">If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.</span><span class="sxs-lookup"><span data-stu-id="17482-163">If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.</span></span>
  
1. <span data-ttu-id="17482-164">В Центре администрирования в разделе **Ресурсы** выберите пункт **Общедоступный веб-сайт**.</span><span class="sxs-lookup"><span data-stu-id="17482-164">From the admin center, go to **Resources**, and then select **Public website**.</span></span>

2. <span data-ttu-id="17482-165">Щелкните ссылку **Дополнительные сведения** под одним из вариантов, а затем зарегистрируйтесь у партнера и воспользуйтесь его инструментами для настройки и оформления сайта.</span><span class="sxs-lookup"><span data-stu-id="17482-165">Select **Learn more** under one of the options, and then sign up with a website partner and use their tools to set up and design your site.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

<span data-ttu-id="17482-166">Дополнительные сведения см. в статье [Использование общедоступного веб-сайта](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="17482-166">More at [Use a public website](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>