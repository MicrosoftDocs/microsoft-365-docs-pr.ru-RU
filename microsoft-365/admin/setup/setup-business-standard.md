---
title: Настройка Microsoft 365 бизнес стандарт
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
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
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
- BEA160
description: При покупке Microsoft 365 бизнес стандарт вы можете воспользоваться принадлежащим вам доменом или купить домен во время регистрации.
ms.openlocfilehash: 861a9e38f10f0cd654e2b10c1879811cd668bc1f
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393815"
---
# <a name="set-up-microsoft-business-standard"></a><span data-ttu-id="cb6cd-103">Настройка Microsoft бизнес стандарт</span><span class="sxs-lookup"><span data-stu-id="cb6cd-103">Set up Microsoft Business Standard</span></span>



## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="cb6cd-104">Добавление домена для персонализации входа</span><span class="sxs-lookup"><span data-stu-id="cb6cd-104">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="cb6cd-105">При покупке Microsoft 365 бизнес стандарт вы можете воспользоваться принадлежащим вам доменом или купить домен во время регистрации.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-105">When you purchase Microsoft 365 Business Standard, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="cb6cd-106">Если вы приобрели новый домен во время регистрации, он уже полностью настроен и можно перейти к пункту [Добавление пользователей и назначение лицензий](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="cb6cd-106">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

1. <span data-ttu-id="cb6cd-107">Войдите в [Центр администрирования Microsoft 365](https://admin.microsoft.com) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="cb6cd-108">Выберите **Перейти к установке**, чтобы запустить мастер установки.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-108">Choose **Go to setup** to start the wizard.</span></span>

3. <span data-ttu-id="cb6cd-109">Со страницы **Установка приложений Office** можно также, если необходимо, установить приложения на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-109">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="cb6cd-110">На шаге **Добавить домен** введите имя домена, который вы хотите использовать (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cb6cd-110">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cb6cd-p101">Если вы приобрели домен во время регистрации, шаг **Добавить домен** не будет отображаться. Вместо этого перейдите в раздел [Добавить пользователей](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="cb6cd-p101">If you purchased a domain during the sign-up, you will not see **Add a domain** step here. Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="cb6cd-113">Выполните шаги, описанные в мастере, по [созданию записей DNS для Office 365 у любого поставщика услуг размещения DNS](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider), который проверяет, являетесь ли вы владельцем домена.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-113">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="cb6cd-114">Если вы знаете узел домена, см. также статью [Добавление домена в Microsoft 365](/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="cb6cd-114">If you know your domain host, see also [Add a domain to Microsoft 365](/microsoft-365/admin/setup/add-domain).</span></span>

    <span data-ttu-id="cb6cd-115">Если ваш поставщик услуг размещения — GoDaddy или другой узел, поддерживающий [подключение доменов](/office365/admin/get-help-with-domains/domain-connect), все просто: вам будет автоматически предложено войти в систему и разрешить Майкрософт проверить подлинность от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-115">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![На странице GoDaddy "Подтверждение доступа" выберите "Авторизовать".](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="cb6cd-117">Добавление пользователей и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="cb6cd-117">Add users and assign licenses</span></span>

<span data-ttu-id="cb6cd-118">Вы можете добавить пользователей в мастере или [позднее](../add-users/add-users.md) в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-118">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="cb6cd-119">Кроме того, если у вас есть локальный контроллер домена, вы можете добавить пользователей с помощью [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="cb6cd-119">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="cb6cd-120">Добавление пользователей в мастере</span><span class="sxs-lookup"><span data-stu-id="cb6cd-120">Add users in the wizard</span></span>

<span data-ttu-id="cb6cd-121">Всем пользователям, которых вы добавляете в мастере, автоматически назначается лицензия Microsoft 365 бизнес стандарт.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-121">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Standard license.</span></span>

1. <span data-ttu-id="cb6cd-p104">Если в вашей подписке на Microsoft 365 бизнес стандарт уже есть пользователи (например, если вы использовали Azure AD Connect), вы можете назначить им лицензии прямо сейчас. Добавьте лицензии и для них.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-p104">If your Microsoft 365 Business Standard subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="cb6cd-p105">После добавления новых пользователей у вас также будет возможность предоставить им учетные данные. Вы можете распечатать их, отправить по электронной почте или скачать.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="cb6cd-126">Подключение домена</span><span class="sxs-lookup"><span data-stu-id="cb6cd-126">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="cb6cd-127">Если вы решили воспользоваться доменом .onmicrosoft или использовали Azure AD Connect для настройки пользователей, этот шаг отображаться не будет.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-127">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="cb6cd-128">Для настройки служб вам необходимо обновить некоторые записи узла DNS или регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-128">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="cb6cd-129">Мастер настройки обычно обнаруживает регистратор и предоставляет ссылку на пошаговые инструкции по обновлению записей NS на его сайте.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-129">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="cb6cd-130">В противном случае [измените серверы доменных имен для настройки Office 365 у любого регистратора доменных имен](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="cb6cd-130">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="cb6cd-131">Если у вас уже есть записи DNS, например для существующего веб-сайта, но узел DNS поддерживает [подключение доменов](/office365/admin/get-help-with-domains/domain-connect), выберите пункт **Автоматическое добавление записей**.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-131">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="cb6cd-132">На странице **Выберите веб-службы** примите все условия по умолчанию, нажмите **Далее**, а затем на странице узла DNS выберите **Авторизовать**.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-132">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="cb6cd-p108">Если у вас уже есть записи DNS для других узлов DNS (не поддерживающих подключение доменов), вам потребуется управлять своими записями DNS, чтобы убедиться в наличии подключения существующих служб. Дополнительные сведения см. в статье [Основные сведения о доменах](/office365/admin/get-help-with-domains/dns-basics).</span><span class="sxs-lookup"><span data-stu-id="cb6cd-p108">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="cb6cd-135">Выполните шаги, описанные в мастере, чтобы настроить электронную почту и другие службы.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-135">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="cb6cd-136">По завершении процесса регистрации вы будете перенаправлены в Центр администрирования, где с помощью мастера установите приложения Office, добавите свой домен, пользователей и назначите лицензии.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-136">When the signup process is complete, you'll be directed to the admin center, where you'll follow a wizard to install Office apps, add your domain, add users, and assign licenses.</span></span> <span data-ttu-id="cb6cd-137">Выполнив первоначальные настройки, вы сможете продолжить настраивать службы, входящие в состав подписок, на странице **Настройка** в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-137">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="cb6cd-138">Дополнительные сведения о мастере настройки и странице **Настройка** в Центре администрирования см. в статье [Различия между мастером настройки и страницей "Настройка"](o365-setup-wizard-and-setup-page.md).</span><span class="sxs-lookup"><span data-stu-id="cb6cd-138">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>

## <a name="finish-setting-up"></a><span data-ttu-id="cb6cd-139">Завершение настройки</span><span class="sxs-lookup"><span data-stu-id="cb6cd-139">Finish setting up</span></span>

### <a name="set-up-outlook-for-email"></a><span data-ttu-id="cb6cd-140">Настройка Outlook для работы с электронной почтой</span><span class="sxs-lookup"><span data-stu-id="cb6cd-140">Set up Outlook for email</span></span>

1. <span data-ttu-id="cb6cd-141">В меню "Пуск" в Windows найдите Outlookи выберите это приложение.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-141">On the Windows Start menu, search for Outlook, and select it.</span></span>

    <span data-ttu-id="cb6cd-142">(Если вы используете компьютер Mac, откройте Outlook с панели инструментов или найдите с помощью диспетчера файлов Finder.)</span><span class="sxs-lookup"><span data-stu-id="cb6cd-142">(If you're using a Mac, open Outlook from the toolbar or locate it using the Finder.)</span></span>

    <span data-ttu-id="cb6cd-143">Если вы только что установили Outlook, на странице приветствия нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-143">If you've just installed Outlook, on the Welcome page, select **Next**.</span></span>

2. <span data-ttu-id="cb6cd-144">Выберите **Файл** \> **Сведения** \> **Добавить учетную запись**.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-144">Choose **File** \> **Info** \> **Add Account**.</span></span>

3. <span data-ttu-id="cb6cd-145">Введите свой адрес электронной почты Microsoft и нажмите кнопку **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-145">Enter your Microsoft email address and select **Connect**.</span></span>

## <a name="watch-set-up-outlook-for-email"></a><span data-ttu-id="cb6cd-146">Просмотр: настройка Outlook для работы с электронной почтой</span><span class="sxs-lookup"><span data-stu-id="cb6cd-146">Watch: Set up Outlook for email</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
<span data-ttu-id="cb6cd-147">Дополнительные сведения см. в статье [Настройка Outlook для работы с электронной почтой](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span><span class="sxs-lookup"><span data-stu-id="cb6cd-147">More at [Set up Outlook for email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span></span>
  
### <a name="import-email"></a><span data-ttu-id="cb6cd-148">Импорт электронной почты</span><span class="sxs-lookup"><span data-stu-id="cb6cd-148">Import email</span></span>

<span data-ttu-id="cb6cd-149">При использовании Outlook с другой учетной записью электронной почты старые сообщения электронной почты, элементы календаря и контакты можно импортировать в новую учетную запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-149">If you were using Outlook with another email account, you can import your previous email, calendar, and contacts into your new Microsoft account.</span></span>
  
1. <span data-ttu-id="cb6cd-150">**Экспорт старых сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="cb6cd-150">**Export your old email**</span></span>

    <span data-ttu-id="cb6cd-151">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-151">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>

    <span data-ttu-id="cb6cd-152">Выберите пункт **Экспорт в файл** и следуйте инструкциям для экспорта файла данных Outlook (PST) и всех вложенных папок.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-152">Select **Export to a File** and then follow the steps to export your Outlook Data File (.pst) and any subfolders.</span></span>

2. <span data-ttu-id="cb6cd-153">**Импорт старых сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="cb6cd-153">**Import your old email**</span></span>

    <span data-ttu-id="cb6cd-154">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-154">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span></span>

    <span data-ttu-id="cb6cd-155">В этот раз выберите пункт **Импорт из другой программы или файла** и следуйте инструкциям для импорта файла резервной копии, созданного при экспорте старых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-155">This time, select **Import from another program or file** and follow the steps to import the backup file you created when you exported your old email.</span></span>

## <a name="watch-import-and-redirect-email"></a><span data-ttu-id="cb6cd-156">Просмотр: импорт и перенаправление электронной почты</span><span class="sxs-lookup"><span data-stu-id="cb6cd-156">Watch: Import and redirect email</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
<span data-ttu-id="cb6cd-157">Дополнительные сведения см. в статье [Импорт электронной почты с помощью Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span><span class="sxs-lookup"><span data-stu-id="cb6cd-157">More at [Import email with Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span></span>

<span data-ttu-id="cb6cd-158">Кроме того, вы можете импортировать сообщения всех пользователей с помощью Центра администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-158">You can also use Exchange admin center to import everyone's email.</span></span> <span data-ttu-id="cb6cd-159">Дополнительные сведения см. в статье [Перенос нескольких учетных записей электронной почты](/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="cb6cd-159">For more information, see [migrate multiple email accounts](/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
### <a name="use-a-public-website"></a><span data-ttu-id="cb6cd-160">Использование общедоступного веб-сайта</span><span class="sxs-lookup"><span data-stu-id="cb6cd-160">Use a public website</span></span>

<span data-ttu-id="cb6cd-p111">Microsoft 365 не включает общедоступный веб-сайт для организации. Чтобы его настроить, рекомендуется воспользоваться услугами партнера Майкрософт, например GoDaddy или WIX.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-p111">Microsoft 365 doesn't include a public website for your business. If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.</span></span>
  
1. <span data-ttu-id="cb6cd-163">В Центре администрирования в разделе **Ресурсы** выберите пункт **Общедоступный веб-сайт**.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-163">From the admin center, go to **Resources**, and then select **Public website**.</span></span>

2. <span data-ttu-id="cb6cd-164">Щелкните ссылку **Дополнительные сведения** под одним из вариантов, а затем зарегистрируйтесь у партнера и воспользуйтесь его инструментами для настройки и оформления сайта.</span><span class="sxs-lookup"><span data-stu-id="cb6cd-164">Select **Learn more** under one of the options, and then sign up with a website partner and use their tools to set up and design your site.</span></span>

## <a name="watch-create-your-business-website"></a><span data-ttu-id="cb6cd-165">Просмотр: создание веб-сайта для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cb6cd-165">Watch: Create your business website</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="related-content"></a><span data-ttu-id="cb6cd-166">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="cb6cd-166">Related content</span></span>

<span data-ttu-id="cb6cd-167">[Создание веб-сайта](../../business-video/create-web-site.md) (видео)</span><span class="sxs-lookup"><span data-stu-id="cb6cd-167">[Create a website](../../business-video/create-web-site.md) (video)</span></span>\
<span data-ttu-id="cb6cd-168">[Microsoft 365 для бизнеса](../../business-video/index.yml) (страница ссылки)</span><span class="sxs-lookup"><span data-stu-id="cb6cd-168">[Microsoft 365 for your business](../../business-video/index.yml) (link page)</span></span>
