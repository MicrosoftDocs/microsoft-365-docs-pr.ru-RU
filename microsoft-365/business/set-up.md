---
title: Настройка Microsoft 365 бизнес премиум
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Откройте для себя шаги установки Microsoft 365 бизнес премиум, включая добавление домена и пользователей, настройку политик безопасности и другие.
ms.openlocfilehash: 3e15f16db2a233d2e11d444600398102b075932d
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624396"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="5054e-103">Настройка Microsoft 365 бизнес премиум в мастере установки</span><span class="sxs-lookup"><span data-stu-id="5054e-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

## <a name="watch-overview-of-microsoft-365-setup"></a><span data-ttu-id="5054e-104">Часы. Обзор Microsoft 365 настройки</span><span class="sxs-lookup"><span data-stu-id="5054e-104">Watch: Overview of Microsoft 365 setup</span></span>

<span data-ttu-id="5054e-105">Просмотрите это видео, чтобы просмотреть Microsoft 365 бизнес премиум настройки.</span><span class="sxs-lookup"><span data-stu-id="5054e-105">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="5054e-106">Добавление домена, пользователей и настройка политик</span><span class="sxs-lookup"><span data-stu-id="5054e-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="5054e-107">При покупке Microsoft 365 бизнес премиум вы можете использовать собственный домен или покупать его во время [регистрации.](sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="5054e-107">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="5054e-108">Если вы приобрели новый домен во время регистрации, он уже полностью настроен и можно перейти к пункту [Добавление пользователей и назначение лицензий](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="5054e-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="5054e-109">Добавление домена для персонализации входа</span><span class="sxs-lookup"><span data-stu-id="5054e-109">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="5054e-110">Войдите в [Центр администрирования Microsoft 365](https://admin.microsoft.com) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="5054e-110">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="5054e-111">Выберите **Перейти к установке**, чтобы запустить мастер установки.</span><span class="sxs-lookup"><span data-stu-id="5054e-111">Choose **Go to setup** to start the wizard.</span></span>

    ![Выберите Перейти к настройке.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="5054e-113">Со страницы **Установка приложений Office** можно также, если необходимо, установить приложения на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="5054e-113">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="5054e-114">На шаге **Добавить домен** введите имя домена, который вы хотите использовать (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="5054e-114">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5054e-p101">Если вы приобрели домен во время регистрации, шаг **Добавить домен** не будет отображаться. Вместо этого перейдите в раздел [Добавить пользователей](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="5054e-p101">If you purchased a domain during the sign-up, you will not see **Add a domain** step here. Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Снимок экрана страницы Personalize your sign-in.](../media/adddomain.png)

    
4. <span data-ttu-id="5054e-118">Выполните действия мастера по созданию записей DNS в любом поставщике [DNS-хостинга](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) для Microsoft 365, которые проверяют ваш домен.</span><span class="sxs-lookup"><span data-stu-id="5054e-118">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="5054e-119">Если вы знаете свой узел домена, см. также [инструкции для узла](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="5054e-119">If you know your domain host, see also the [host specific instructions](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="5054e-120">Если ваш поставщик услуг размещения — GoDaddy или другой узел, поддерживающий [подключение доменов](/office365/admin/get-help-with-domains/domain-connect), все просто: вам будет автоматически предложено войти в систему и разрешить Майкрософт проверить подлинность от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="5054e-120">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![На странице GoDaddy "Подтверждение доступа" выберите "Авторизовать".](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="5054e-122">Добавление пользователей и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="5054e-122">Add users and assign licenses</span></span>

<span data-ttu-id="5054e-123">Вы можете добавить пользователей в мастере или [позднее](../admin/add-users/add-users.md) в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="5054e-123">You can add users in the wizard, but you can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="5054e-124">Кроме того, если у вас есть локальный контроллер домена, вы можете добавить пользователей с помощью [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="5054e-124">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="5054e-125">Добавление пользователей в мастере</span><span class="sxs-lookup"><span data-stu-id="5054e-125">Add users in the wizard</span></span>

<span data-ttu-id="5054e-126">Все пользователи, добавленные в мастер, автоматически получают Microsoft 365 бизнес премиум лицензию.</span><span class="sxs-lookup"><span data-stu-id="5054e-126">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Снимок экрана страницы Добавление новых пользователей в мастере](../media/addnewuserspage.png)

1. <span data-ttu-id="5054e-128">Если в Microsoft 365 бизнес премиум подписки есть существующие пользователи (например, если вы использовали Azure AD Подключение), вы получите возможность назначить им лицензии сейчас.</span><span class="sxs-lookup"><span data-stu-id="5054e-128">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="5054e-129">Добавьте лицензии и для них.</span><span class="sxs-lookup"><span data-stu-id="5054e-129">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="5054e-p105">После добавления новых пользователей у вас также будет возможность предоставить им учетные данные. Вы можете распечатать их, отправить по электронной почте или скачать.</span><span class="sxs-lookup"><span data-stu-id="5054e-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="5054e-132">Подключение домена</span><span class="sxs-lookup"><span data-stu-id="5054e-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="5054e-133">Если вы решили воспользоваться доменом .onmicrosoft или использовали Azure AD Connect для настройки пользователей, этот шаг отображаться не будет.</span><span class="sxs-lookup"><span data-stu-id="5054e-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="5054e-134">Для настройки служб вам необходимо обновить некоторые записи узла DNS или регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="5054e-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="5054e-135">Мастер настройки обычно обнаруживает регистратор и предоставляет ссылку на пошаговые инструкции по обновлению записей NS на его сайте.</span><span class="sxs-lookup"><span data-stu-id="5054e-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="5054e-136">Если этого не сделать, измените именоимены для Microsoft 365 с любым [регистратором домена.](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md)</span><span class="sxs-lookup"><span data-stu-id="5054e-136">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="5054e-137">Если у вас уже есть записи DNS, например для существующего веб-сайта, но узел DNS поддерживает [подключение доменов](/office365/admin/get-help-with-domains/domain-connect), выберите пункт **Автоматическое добавление записей**.</span><span class="sxs-lookup"><span data-stu-id="5054e-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="5054e-138">На странице **Выберите веб-службы** примите все условия по умолчанию, нажмите **Далее**, а затем на странице узла DNS выберите **Авторизовать**.</span><span class="sxs-lookup"><span data-stu-id="5054e-138">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="5054e-p108">Если у вас уже есть записи DNS для других узлов DNS (не поддерживающих подключение доменов), вам потребуется управлять своими записями DNS, чтобы убедиться в наличии подключения существующих служб. Дополнительные сведения см. в статье [Основные сведения о доменах](/office365/admin/get-help-with-domains/dns-basics).</span><span class="sxs-lookup"><span data-stu-id="5054e-p108">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Активируйте страницу записей.](../media/activaterecords.png)

2. <span data-ttu-id="5054e-142">Выполните шаги, описанные в мастере, чтобы настроить электронную почту и другие службы.</span><span class="sxs-lookup"><span data-stu-id="5054e-142">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="5054e-143">Защита организации</span><span class="sxs-lookup"><span data-stu-id="5054e-143">Protect your organization</span></span> 

<span data-ttu-id="5054e-144">Политики, которые вы создали в мастере, автоматически применяются к группе [безопасности](/office365/admin/create-groups/compare-groups#security-groups) под названием *All Users*.</span><span class="sxs-lookup"><span data-stu-id="5054e-144">The policies you set up in the wizard are applied automatically to a [Security group](/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="5054e-145">Можно также создать дополнительные группы для назначения политик в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="5054e-145">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="5054e-146">При **повышении** защиты от расширенных киберугроз рекомендуется принимать по умолчанию, чтобы позволить Office 365 advance [Threat Protection](../security/office-365-security/defender-for-office-365.md) сканировать файлы и ссылки в Office приложениях.</span><span class="sxs-lookup"><span data-stu-id="5054e-146">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](../security/office-365-security/defender-for-office-365.md) scan files and links in Office apps.</span></span>

    ![Снимок экрана страницы "Увеличение защиты".](../media/increasetreatprotection.png)


2. <span data-ttu-id="5054e-148">На  странице Предотвращение утечек конфиденциальных данных примите по умолчанию, чтобы включить Office 365 защиты от потери данных (DLP), чтобы отслеживать конфиденциальные данные в Office приложениях и предотвращать случайный обмен этими данными за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="5054e-148">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="5054e-149">На странице Protect data **in Office** для мобильной страницы оставьте управление мобильными приложениями, расширите параметры и просмотрите их, а затем выберите политику управления мобильными **приложениями.**</span><span class="sxs-lookup"><span data-stu-id="5054e-149">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Снимок экрана protect data in Office для мобильной страницы.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="5054e-151">Защита компьютеров с Windows 10</span><span class="sxs-lookup"><span data-stu-id="5054e-151">Secure Windows 10 PCs</span></span>

<span data-ttu-id="5054e-152">В левом nav выберите **установку,** а затем в соответствии с входом и безопасностью **выберите** Secure **Windows 10 компьютеров.**</span><span class="sxs-lookup"><span data-stu-id="5054e-152">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="5054e-153">Выберите **View** для начала работы.</span><span class="sxs-lookup"><span data-stu-id="5054e-153">Choose **View** to get started.</span></span> <span data-ttu-id="5054e-154">См. [в Windows 10 компьютеры](secure-win-10-pcs.md) для выполнения инструкций.</span><span class="sxs-lookup"><span data-stu-id="5054e-154">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="5054e-155">Развертывание Office 365 клиентских приложений</span><span class="sxs-lookup"><span data-stu-id="5054e-155">Deploy Office 365 client apps</span></span>

<span data-ttu-id="5054e-156">Если вы решили автоматически установить Office приложения во время установки, приложения будут устанавливаться на устройствах Windows 10 после входа пользователей в Azure AD с Windows устройств с помощью учетных данных.</span><span class="sxs-lookup"><span data-stu-id="5054e-156">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="5054e-157">Чтобы установить Office на мобильные устройства iOS или Android, см. в приложении Настройка мобильных устройств [для Microsoft 365 бизнес премиум пользователей.](set-up-mobile-devices.md)</span><span class="sxs-lookup"><span data-stu-id="5054e-157">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="5054e-158">Вы также можете установить Office отдельно.</span><span class="sxs-lookup"><span data-stu-id="5054e-158">You can also install Office individually.</span></span> <span data-ttu-id="5054e-159">Инструкции [по установке Office на компьютере или Mac.](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)</span><span class="sxs-lookup"><span data-stu-id="5054e-159">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="related-content"></a><span data-ttu-id="5054e-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="5054e-160">Related content</span></span>

<span data-ttu-id="5054e-161">[Microsoft 365 для видео обучения бизнесу](../business-video/index.yml) (страница ссылки)</span><span class="sxs-lookup"><span data-stu-id="5054e-161">[Microsoft 365 for business training videos](../business-video/index.yml) (link page)</span></span>
