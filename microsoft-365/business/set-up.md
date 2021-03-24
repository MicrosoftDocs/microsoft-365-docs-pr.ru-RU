---
title: Настройка Microsoft 365 бизнес премиум
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
description: Откройте для себя этапы настройки для Microsoft 365 Business Premium, включая добавление домена и пользователей, настройку политик безопасности и т. д.
ms.openlocfilehash: 4d49ba7ccdb65691756aaa505d0856deb115595b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052241"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="0d5c3-103">Настройка Microsoft 365 Бизнес Премиум в мастере установки</span><span class="sxs-lookup"><span data-stu-id="0d5c3-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="0d5c3-104">Просмотрите это видео для обзора установки Microsoft 365 Бизнес Премиум.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="0d5c3-105">Добавление домена, пользователей и настройка политик</span><span class="sxs-lookup"><span data-stu-id="0d5c3-105">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="0d5c3-106">При покупке Microsoft 365 Бизнес Премиум у вас есть возможность использовать домен, который вы владеете, или покупать его во время [регистрации.](sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="0d5c3-106">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="0d5c3-107">Если вы приобрели новый домен во время регистрации, он уже полностью настроен и можно перейти к пункту [Добавление пользователей и назначение лицензий](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="0d5c3-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="0d5c3-108">Добавление домена для персонализации входа</span><span class="sxs-lookup"><span data-stu-id="0d5c3-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="0d5c3-109">Войдите в [Центр администрирования Microsoft 365](https://admin.microsoft.com) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="0d5c3-110">Выберите **Перейти к установке**, чтобы запустить мастер установки.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-110">Choose **Go to setup** to start the wizard.</span></span>

    ![Выберите Перейти к настройке.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="0d5c3-112">Со страницы **Установка приложений Office** можно также, если необходимо, установить приложения на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-112">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="0d5c3-113">На шаге **Добавить домен** введите имя домена, который вы хотите использовать (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0d5c3-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0d5c3-114">Если вы приобрели домен во время регистрации, шаг **Добавить домен** не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-114">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="0d5c3-115">Вместо этого перейдите в раздел [Добавить пользователей](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="0d5c3-115">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Снимок экрана страницы Personalize your sign-in.](../media/adddomain.png)

    
4. <span data-ttu-id="0d5c3-117">Выполните действия мастера по созданию записей DNS в любом [поставщике DNS-хостинга для Microsoft 365,](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) который проверяет ваш домен.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-117">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="0d5c3-118">Если вы знаете свой узел домена, см. также [инструкции для узла](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="0d5c3-118">If you know your domain host, see also the [host specific instructions](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="0d5c3-119">Если ваш поставщик услуг размещения — GoDaddy или другой узел, поддерживающий [подключение доменов](/office365/admin/get-help-with-domains/domain-connect), все просто: вам будет автоматически предложено войти в систему и разрешить Майкрософт проверить подлинность от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-119">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![На странице GoDaddy "Подтверждение доступа" выберите "Авторизовать".](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="0d5c3-121">Добавление пользователей и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="0d5c3-121">Add users and assign licenses</span></span>

<span data-ttu-id="0d5c3-122">Вы можете добавить пользователей в мастере или [позднее](../admin/add-users/add-users.md) в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-122">You can add users in the wizard, but you can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="0d5c3-123">Кроме того, если у вас есть локальный контроллер домена, вы можете добавить пользователей с помощью [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="0d5c3-123">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="0d5c3-124">Добавление пользователей в мастере</span><span class="sxs-lookup"><span data-stu-id="0d5c3-124">Add users in the wizard</span></span>

<span data-ttu-id="0d5c3-125">Все пользователи, добавленные в мастер, автоматически получают лицензию Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-125">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Снимок экрана страницы Добавление новых пользователей в мастере](../media/addnewuserspage.png)

1. <span data-ttu-id="0d5c3-127">Если в вашей подписке Microsoft 365 Business Premium есть существующие пользователи (например, если вы использовали Azure AD Connect), вы получите возможность назначить им лицензии сейчас.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-127">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="0d5c3-128">Добавьте лицензии и для них.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-128">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="0d5c3-129">После добавления пользователей у вас также будет возможность предоставить им учетные данные.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-129">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="0d5c3-130">Вы можете распечатать их, отправить по электронной почте или скачать.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-130">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="0d5c3-131">Подключение домена</span><span class="sxs-lookup"><span data-stu-id="0d5c3-131">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="0d5c3-132">Если вы решили воспользоваться доменом .onmicrosoft или использовали Azure AD Connect для настройки пользователей, этот шаг отображаться не будет.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-132">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="0d5c3-133">Для настройки служб вам необходимо обновить некоторые записи узла DNS или регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-133">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="0d5c3-134">Мастер настройки обычно обнаруживает регистратор и предоставляет ссылку на пошаговые инструкции по обновлению записей NS на его сайте.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-134">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="0d5c3-135">Если этого не сделать, измените именоимены, чтобы настроить [Microsoft 365 с любым регистратором домена.](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md)</span><span class="sxs-lookup"><span data-stu-id="0d5c3-135">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="0d5c3-136">Если у вас уже есть записи DNS, например для существующего веб-сайта, но узел DNS поддерживает [подключение доменов](/office365/admin/get-help-with-domains/domain-connect), выберите пункт **Автоматическое добавление записей**.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-136">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="0d5c3-137">На странице **Выберите веб-службы** примите все условия по умолчанию, нажмите **Далее**, а затем на странице узла DNS выберите **Авторизовать**.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-137">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="0d5c3-138">Если у вас уже есть записи DNS для других узлов DNS (не поддерживающих подключение доменов), вам потребуется управлять своими записями DNS, чтобы убедиться в наличии подключения существующих служб.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-138">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="0d5c3-139">Дополнительные сведения см. в статье [Основные сведения о доменах](/office365/admin/get-help-with-domains/dns-basics).</span><span class="sxs-lookup"><span data-stu-id="0d5c3-139">See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Активируйте страницу записей.](../media/activaterecords.png)

2. <span data-ttu-id="0d5c3-141">Выполните шаги, описанные в мастере, чтобы настроить электронную почту и другие службы.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-141">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="0d5c3-142">Защита организации</span><span class="sxs-lookup"><span data-stu-id="0d5c3-142">Protect your organization</span></span> 

<span data-ttu-id="0d5c3-143">Политики, которые вы создали в мастере, автоматически применяются к группе [безопасности](/office365/admin/create-groups/compare-groups#security-groups) под названием *All Users*.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-143">The policies you set up in the wizard are applied automatically to a [Security group](/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="0d5c3-144">Можно также создать дополнительные группы для назначения политик в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-144">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="0d5c3-145">При **повышении** защиты от расширенных киберугроз рекомендуется принимать по умолчанию файлы и ссылки [office 365 Advance Threat Protection](../security/defender-365-security/defender-for-office-365.md) для сканирования и ссылок в приложениях Office.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-145">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](../security/defender-365-security/defender-for-office-365.md) scan files and links in Office apps.</span></span>

    ![Снимок экрана страницы "Увеличение защиты".](../media/increasetreatprotection.png)


2. <span data-ttu-id="0d5c3-147">На  странице Предотвращение утечек конфиденциальных данных примите по умолчанию, чтобы включить Службу предотвращения потери данных Office 365 для отслеживания конфиденциальных данных в приложениях Office и предотвращения случайного обмена этими данными за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-147">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="0d5c3-148">На странице Защита данных **в Office для** мобильных устройств оставьте управление мобильными приложениями, расширите параметры и просмотрите их, а затем выберите политику управления **мобильными приложениями.**</span><span class="sxs-lookup"><span data-stu-id="0d5c3-148">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Снимок экрана "Защита данных в Office для мобильной страницы".](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="0d5c3-150">Защита компьютеров с Windows 10</span><span class="sxs-lookup"><span data-stu-id="0d5c3-150">Secure Windows 10 PCs</span></span>

<span data-ttu-id="0d5c3-151">В левом окантове выберите **установку,** а затем в соответствии с входом и безопасностью **выберите** **Безопасные компьютеры Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-151">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="0d5c3-152">Выберите **View** для начала работы.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-152">Choose **View** to get started.</span></span> <span data-ttu-id="0d5c3-153">Узнайте, [как обеспечить безопасность компьютеров Windows 10](secure-win-10-pcs.md) для выполнения инструкций.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-153">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="0d5c3-154">Развертывание клиентских приложений Office 365</span><span class="sxs-lookup"><span data-stu-id="0d5c3-154">Deploy Office 365 client apps</span></span>

<span data-ttu-id="0d5c3-155">Если вы решили автоматически установить приложения Office во время установки, приложения будут устанавливаться на устройствах Windows 10 после того, как пользователи во время входа в Azure AD со своих устройств Windows будут использовать свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-155">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="0d5c3-156">Чтобы установить Office на мобильных устройствах с iOS или Android, см. в рублях Настройка мобильных [устройств для пользователей Microsoft 365 Business Premium.](set-up-mobile-devices.md)</span><span class="sxs-lookup"><span data-stu-id="0d5c3-156">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="0d5c3-157">Вы также можете установить Office по отдельности.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-157">You can also install Office individually.</span></span> <span data-ttu-id="0d5c3-158">Инструкции [по установке Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) на КОМПЬЮТЕРе или Mac.</span><span class="sxs-lookup"><span data-stu-id="0d5c3-158">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d5c3-159">См. также</span><span class="sxs-lookup"><span data-stu-id="0d5c3-159">See also</span></span>

[<span data-ttu-id="0d5c3-160">Обучающие видеоролики по Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0d5c3-160">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
