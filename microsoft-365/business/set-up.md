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
ms.openlocfilehash: efa7934ece0dfeac3c4b20daa37da6f1160901e7
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079813"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="ac885-103">Настройка Microsoft 365 бизнес премиум в мастере установки</span><span class="sxs-lookup"><span data-stu-id="ac885-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="ac885-104">В этом видеоролике приводится обзор программы установки Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="ac885-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

<span data-ttu-id="ac885-105">Если этот видеоролик помог вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="ac885-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="ac885-106">Добавление домена, пользователей и Настройка политик</span><span class="sxs-lookup"><span data-stu-id="ac885-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="ac885-107">При покупке Microsoft 365 Бизнес Премиум вы можете использовать домен, который вы являетесь участником, или приобрести его во время [регистрации](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="ac885-107">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="ac885-108">Если вы приобрели новый домен во время регистрации, он уже полностью настроен и можно перейти к пункту [Добавление пользователей и назначение лицензий](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="ac885-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="ac885-109">Добавление домена для персонализации входа</span><span class="sxs-lookup"><span data-stu-id="ac885-109">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="ac885-110">Войдите в [Центр администрирования Microsoft 365](https://admin.microsoft.com) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="ac885-110">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="ac885-111">Выберите **Перейти к установке**, чтобы запустить мастер установки.</span><span class="sxs-lookup"><span data-stu-id="ac885-111">Choose **Go to setup** to start the wizard.</span></span>

    ![Нажмите кнопку Перейти к программе установки.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="ac885-113">Со страницы **Установка приложений Office** можно также, если необходимо, установить приложения на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="ac885-113">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="ac885-114">На шаге **Добавить домен** введите имя домена, который вы хотите использовать (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ac885-114">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ac885-115">Если вы приобрели домен во время регистрации, шаг **Добавить домен** не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="ac885-115">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="ac885-116">Вместо этого перейдите в раздел [Добавить пользователей](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="ac885-116">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Снимок страницы "Персонализация" страницы входа.](../media/adddomain.png)

    
4. <span data-ttu-id="ac885-118">Следуйте указаниям мастера, чтобы [создать записи DNS на любом поставщике услуг хостинга DNS для Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) , который подтверждает, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="ac885-118">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="ac885-119">Если вы знаете свой узел домена, см. также [инструкции для узла](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="ac885-119">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="ac885-120">Если ваш поставщик услуг размещения — GoDaddy или другой узел, поддерживающий [подключение доменов](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), все просто: вам будет автоматически предложено войти в систему и разрешить Майкрософт проверить подлинность от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="ac885-120">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![На странице GoDaddy "Подтверждение доступа" выберите "Авторизовать".](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="ac885-122">Добавление пользователей и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="ac885-122">Add users and assign licenses</span></span>

<span data-ttu-id="ac885-123">Вы можете добавить пользователей в мастере или [позднее](add-users-m365b.md) в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="ac885-123">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="ac885-124">Кроме того, если у вас есть локальный контроллер домена, вы можете добавить пользователей с помощью [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="ac885-124">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="ac885-125">Добавление пользователей в мастере</span><span class="sxs-lookup"><span data-stu-id="ac885-125">Add users in the wizard</span></span>

<span data-ttu-id="ac885-126">Для всех пользователей, добавляемых в мастере, автоматически назначается лицензия Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="ac885-126">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Снимок экрана со страницей "Добавление новых пользователей" в мастере](../media/addnewuserspage.png)

1. <span data-ttu-id="ac885-128">Если у вашей подписки Microsoft 365 Business Premium есть существующие пользователи (например, если вы использовали Azure AD Connect), вы получите возможность назначить лицензии для них сейчас.</span><span class="sxs-lookup"><span data-stu-id="ac885-128">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="ac885-129">Добавьте лицензии и для них.</span><span class="sxs-lookup"><span data-stu-id="ac885-129">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="ac885-130">После добавления пользователей у вас также будет возможность предоставить им учетные данные.</span><span class="sxs-lookup"><span data-stu-id="ac885-130">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="ac885-131">Вы можете распечатать их, отправить по электронной почте или скачать.</span><span class="sxs-lookup"><span data-stu-id="ac885-131">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="ac885-132">Подключение домена</span><span class="sxs-lookup"><span data-stu-id="ac885-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="ac885-133">Если вы решили воспользоваться доменом .onmicrosoft или использовали Azure AD Connect для настройки пользователей, этот шаг отображаться не будет.</span><span class="sxs-lookup"><span data-stu-id="ac885-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="ac885-134">Для настройки служб вам необходимо обновить некоторые записи узла DNS или регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="ac885-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="ac885-135">Мастер настройки обычно обнаруживает регистратор и предоставляет ссылку на пошаговые инструкции по обновлению записей NS на его сайте.</span><span class="sxs-lookup"><span data-stu-id="ac885-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="ac885-136">Если это не так, [измените серверов доменных имен, чтобы настроить Microsoft 365 с помощью любого регистратора доменных](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar)имен.</span><span class="sxs-lookup"><span data-stu-id="ac885-136">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="ac885-137">Если у вас уже есть записи DNS, например для существующего веб-сайта, но узел DNS поддерживает [подключение доменов](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), выберите пункт **Автоматическое добавление записей**.</span><span class="sxs-lookup"><span data-stu-id="ac885-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="ac885-138">На странице **Выберите веб-службы** примите все условия по умолчанию, нажмите **Далее**, а затем на странице узла DNS выберите **Авторизовать**.</span><span class="sxs-lookup"><span data-stu-id="ac885-138">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="ac885-139">Если у вас уже есть записи DNS для других узлов DNS (не поддерживающих подключение доменов), вам потребуется управлять своими записями DNS, чтобы убедиться в наличии подключения существующих служб.</span><span class="sxs-lookup"><span data-stu-id="ac885-139">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="ac885-140">Дополнительные сведения см. в статье [Основные сведения о доменах](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics).</span><span class="sxs-lookup"><span data-stu-id="ac885-140">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Страница "Активация записей".](../media/activaterecords.png)

2. <span data-ttu-id="ac885-142">Выполните шаги, описанные в мастере, чтобы настроить электронную почту и другие службы.</span><span class="sxs-lookup"><span data-stu-id="ac885-142">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="ac885-143">Защита Организации</span><span class="sxs-lookup"><span data-stu-id="ac885-143">Protect your organization</span></span> 

<span data-ttu-id="ac885-144">Политики, настроенные в мастере, автоматически применяются к [группе безопасности](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) с именем " *все пользователи*".</span><span class="sxs-lookup"><span data-stu-id="ac885-144">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="ac885-145">Кроме того, можно создать дополнительные группы, чтобы назначить политики в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="ac885-145">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="ac885-146">При **увеличении защиты от расширенных угроз кибератак**рекомендуется принять значения по умолчанию, чтобы разрешить [Office 365 Advance Threat protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) сканировать файлы и ссылки в приложениях Office.</span><span class="sxs-lookup"><span data-stu-id="ac885-146">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![Снимок экрана: страница "увеличение защиты".](../media/increasetreatprotection.png)


2. <span data-ttu-id="ac885-148">На странице **предотвратить утечки конфиденциальных данных** примите значения по умолчанию, чтобы включить защиту от потери данных (DLP) Office 365 для отслеживания конфиденциальных данных в приложениях Office и предотвращения случайного доступа к ним за преворотами в Организации.</span><span class="sxs-lookup"><span data-stu-id="ac885-148">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="ac885-149">На странице **Защита данных в Office для мобильных устройств** оставьте управление мобильными приложениями включено, разверните параметры и просмотрите их, а затем выберите **создать политику управления мобильными приложениями**.</span><span class="sxs-lookup"><span data-stu-id="ac885-149">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Снимок экрана: защита данных на странице Office для мобильных устройств.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="ac885-151">Защита компьютеров с Windows 10</span><span class="sxs-lookup"><span data-stu-id="ac885-151">Secure Windows 10 PCs</span></span>

<span data-ttu-id="ac885-152">В левой панели навигации выберите пункт **Настройка** , а затем в разделе **Вход и безопасность**выберите **безопасность компьютеров с Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="ac885-152">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="ac885-153">Чтобы приступить к работе, нажмите кнопку **Просмотр** .</span><span class="sxs-lookup"><span data-stu-id="ac885-153">Choose **View** to get started.</span></span> <span data-ttu-id="ac885-154">Выполните инструкции [в статье Защита компьютеров с Windows 10](secure-win-10-pcs.md) .</span><span class="sxs-lookup"><span data-stu-id="ac885-154">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="ac885-155">Развертывание клиентских приложений Office 365</span><span class="sxs-lookup"><span data-stu-id="ac885-155">Deploy Office 365 client apps</span></span>

<span data-ttu-id="ac885-156">Если вы решили автоматически устанавливать приложения Office во время установки, они будут установлены на устройствах с Windows 10 после входа пользователей в Azure AD с помощью своих рабочих учетных данных.</span><span class="sxs-lookup"><span data-stu-id="ac885-156">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="ac885-157">Чтобы установить Office на мобильные устройства с iOS или Android, ознакомьтесь со статьей [Настройка мобильных устройств для пользователей Microsoft 365 Business Premium](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="ac885-157">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="ac885-158">Вы также можете установить Office по отдельности.</span><span class="sxs-lookup"><span data-stu-id="ac885-158">You can also install Office individually.</span></span> <span data-ttu-id="ac885-159">Инструкции: [Install Office на ПК или Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) .</span><span class="sxs-lookup"><span data-stu-id="ac885-159">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac885-160">См. также</span><span class="sxs-lookup"><span data-stu-id="ac885-160">See also</span></span>

[<span data-ttu-id="ac885-161">Обучающие видеоролики по Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ac885-161">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
