---
title: Настройка Microsoft 365 бизнес премиум
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: В этой статье приведены инструкции по настройке Microsoft 365 Business Premium, в том числе добавление домена и пользователей, Настройка политик безопасности и многое другое.
ms.openlocfilehash: 6606e9fd66aacab317e4b0bfd5ce2a090208018e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402946"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="85de9-103">Настройка Microsoft 365 бизнес премиум в мастере установки</span><span class="sxs-lookup"><span data-stu-id="85de9-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="85de9-104">В этом видеоролике приводится обзор программы установки Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="85de9-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

<span data-ttu-id="85de9-105">Если этот видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="85de9-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="85de9-106">Добавление домена, пользователей и Настройка политик</span><span class="sxs-lookup"><span data-stu-id="85de9-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="85de9-107">[![Надпись, оповещающая об изменении Центра администрирования. Дополнительные сведения см. на сайте aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="85de9-107">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="85de9-108">При покупке Microsoft 365 Бизнес Премиум вы можете использовать домен, который вы являетесь участником, или приобрести его во время [регистрации](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="85de9-108">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="85de9-109">Если вы приобрели новый домен при регистрации, все настроенные домены и вы можете перейти к [добавлению пользователей и назначению лицензий](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="85de9-109">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="85de9-110">Добавление домена для персонализации при входе</span><span class="sxs-lookup"><span data-stu-id="85de9-110">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="85de9-111">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с помощью учетных данных глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="85de9-111">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="85de9-112">Чтобы запустить мастер, нажмите кнопку **Перейти в программу установки** .</span><span class="sxs-lookup"><span data-stu-id="85de9-112">Choose **Go to setup** to start the wizard.</span></span>

    ![Нажмите кнопку Перейти к программе установки.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="85de9-114">На странице **Установка приложений Office** можно дополнительно установить приложения на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="85de9-114">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="85de9-115">На шаге **Добавление домена** введите имя домена, который вы хотите использовать (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="85de9-115">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="85de9-116">Если вы приобрели домен во время регистрации, вы не увидите шаг **Добавить домен** .</span><span class="sxs-lookup"><span data-stu-id="85de9-116">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="85de9-117">Перейдите к разделу [Добавление пользователей](#add-users-and-assign-licenses) .</span><span class="sxs-lookup"><span data-stu-id="85de9-117">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Снимок страницы "Персонализация" страницы входа.](../media/adddomain.png)

    
4. <span data-ttu-id="85de9-119">Следуйте указаниям мастера, чтобы [создать записи DNS на любом поставщике услуг хостинга DNS для Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) , который подтверждает, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="85de9-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="85de9-120">Если вы знаете узел домена, ознакомьтесь с [инструкциями, характерными для узла](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="85de9-120">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="85de9-121">Если поставщик услуг размещения — GoDaddy или другой узел, включенный с [подключением к домену](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), процесс будет прост, и вам будет автоматически предложено войти и проверить подлинность Майкрософт от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="85de9-121">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![На странице "Подтверждение доступа GoDaddy" выберите авторизовать.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="85de9-123">Добавление пользователей и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="85de9-123">Add users and assign licenses</span></span>

<span data-ttu-id="85de9-124">Вы можете добавлять пользователей в мастер, но позднее вы можете [Добавить пользователей](add-users-m365b.md) в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="85de9-124">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="85de9-125">Кроме того, если у вас есть локальный контроллер домена, вы можете добавить пользователей с помощью [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="85de9-125">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="85de9-126">Добавление пользователей в мастер</span><span class="sxs-lookup"><span data-stu-id="85de9-126">Add users in the wizard</span></span>

<span data-ttu-id="85de9-127">Для всех пользователей, добавляемых в мастере, автоматически назначается лицензия Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="85de9-127">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Снимок экрана со страницей "Добавление новых пользователей" в мастере](../media/addnewuserspage.png)

1. <span data-ttu-id="85de9-129">Если у вашей подписки Microsoft 365 Business Premium есть существующие пользователи (например, если вы использовали Azure AD Connect), вы получите возможность назначить лицензии для них сейчас.</span><span class="sxs-lookup"><span data-stu-id="85de9-129">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="85de9-130">Добавьте лицензии и для них.</span><span class="sxs-lookup"><span data-stu-id="85de9-130">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="85de9-131">После добавления пользователей вы также получите возможность предоставлять учетные данные новым добавленным пользователям.</span><span class="sxs-lookup"><span data-stu-id="85de9-131">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="85de9-132">Вы можете распечатать их, отправить по электронной почте или скачать.</span><span class="sxs-lookup"><span data-stu-id="85de9-132">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="85de9-133">Подключение домена</span><span class="sxs-lookup"><span data-stu-id="85de9-133">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="85de9-134">Если вы решили использовать домен onmicrosoft или использовать Azure AD Connect для настройки пользователей, этот шаг не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="85de9-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="85de9-135">Для настройки служб вам необходимо обновить некоторые записи узла DNS или регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="85de9-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="85de9-136">Мастер настройки обычно определяет регистратора и предоставляет ссылку на пошаговые инструкции по обновлению записей NS на его сайте.</span><span class="sxs-lookup"><span data-stu-id="85de9-136">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="85de9-137">Если это не так, [измените серверов доменных имен, чтобы настроить Office 365 для любого регистратора доменных](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar)имен.</span><span class="sxs-lookup"><span data-stu-id="85de9-137">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="85de9-138">Если у вас есть существующие записи DNS, например существующий веб-сайт, но ваш узел DNS включен для [подключения к домену](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), нажмите кнопку **добавить записи**.</span><span class="sxs-lookup"><span data-stu-id="85de9-138">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="85de9-139">На странице " **Выбор веб-служб** " примите все параметры по умолчанию и нажмите кнопку **Далее**, а затем — кнопку **авторизовать** на странице узла DNS.</span><span class="sxs-lookup"><span data-stu-id="85de9-139">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="85de9-140">Если у вас есть существующие записи DNS с другими узлами DNS (не включены для подключения к домену), вам потребуется управлять собственными записями DNS, чтобы убедиться, что существующие службы остаются подключенными.</span><span class="sxs-lookup"><span data-stu-id="85de9-140">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="85de9-141">Более подробную информацию можно узнать в разделе [domain основы доменов](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .</span><span class="sxs-lookup"><span data-stu-id="85de9-141">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Страница "Активация записей".](../media/activaterecords.png)

2. <span data-ttu-id="85de9-143">Следуйте указаниям мастера, электронной почты и других служб.</span><span class="sxs-lookup"><span data-stu-id="85de9-143">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="85de9-144">Защита Организации</span><span class="sxs-lookup"><span data-stu-id="85de9-144">Protect your organization</span></span> 

<span data-ttu-id="85de9-145">Политики, настроенные в мастере, автоматически применяются к [группе безопасности](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) с именем " *все пользователи*".</span><span class="sxs-lookup"><span data-stu-id="85de9-145">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="85de9-146">Кроме того, можно создать дополнительные группы, чтобы назначить политики в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="85de9-146">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="85de9-147">При **увеличении защиты от расширенных угроз кибератак**рекомендуется принять значения по умолчанию, чтобы разрешить [Office 365 Advance Threat protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) сканировать файлы и ссылки в приложениях Office.</span><span class="sxs-lookup"><span data-stu-id="85de9-147">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![Снимок экрана: страница "увеличение защиты".](../media/increasetreatprotection.png)


2. <span data-ttu-id="85de9-149">На странице **предотвратить утечки конфиденциальных данных** примите значения по умолчанию, чтобы включить защиту от потери данных (DLP) Office 365 для отслеживания конфиденциальных данных в приложениях Office и предотвращения случайного доступа к ним за преворотами в Организации.</span><span class="sxs-lookup"><span data-stu-id="85de9-149">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="85de9-150">На странице **Защита данных в Office для мобильных устройств** оставьте управление мобильными приложениями включено, разверните параметры и просмотрите их, а затем выберите **создать политику управления мобильными приложениями**.</span><span class="sxs-lookup"><span data-stu-id="85de9-150">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Снимок экрана: защита данных на странице Office для мобильных устройств.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="85de9-152">Защита компьютеров с Windows 10</span><span class="sxs-lookup"><span data-stu-id="85de9-152">Secure Windows 10 PCs</span></span>

<span data-ttu-id="85de9-153">В левой панели навигации выберите пункт **Настройка** , а затем в разделе **Вход и безопасность**выберите **безопасность компьютеров с Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="85de9-153">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="85de9-154">Чтобы приступить к работе, нажмите кнопку **Просмотр** .</span><span class="sxs-lookup"><span data-stu-id="85de9-154">Choose **View** to get started.</span></span> <span data-ttu-id="85de9-155">Выполните инструкции [в статье Защита компьютеров с Windows 10](secure-win-10-pcs.md) .</span><span class="sxs-lookup"><span data-stu-id="85de9-155">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="85de9-156">Развертывание клиентских приложений Office 365</span><span class="sxs-lookup"><span data-stu-id="85de9-156">Deploy Office 365 client apps</span></span>

<span data-ttu-id="85de9-157">Если вы решили автоматически устанавливать приложения Office во время установки, они будут установлены на устройствах с Windows 10 после входа пользователей в Azure AD с помощью своих рабочих учетных данных.</span><span class="sxs-lookup"><span data-stu-id="85de9-157">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="85de9-158">Чтобы установить Office на мобильные устройства с iOS или Android, ознакомьтесь со статьей [Настройка мобильных устройств для пользователей Microsoft 365 Business Premium](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="85de9-158">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="85de9-159">Вы также можете установить Office по отдельности.</span><span class="sxs-lookup"><span data-stu-id="85de9-159">You can also install Office individually.</span></span> <span data-ttu-id="85de9-160">Инструкции: [Install Office на ПК или Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) .</span><span class="sxs-lookup"><span data-stu-id="85de9-160">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="85de9-161">См. также</span><span class="sxs-lookup"><span data-stu-id="85de9-161">See also</span></span>

[<span data-ttu-id="85de9-162">Обучающие видеоролики по Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="85de9-162">Microsoft 365 for business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
