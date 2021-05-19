---
title: Настройка Microsoft 365 бизнес базовый
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
search.appverid:
- MET150
- MOE150
- BEA160
description: Узнайте, как настроить подписку на Microsoft 365 бизнес базовый.
ms.openlocfilehash: 51a83d4cc230fa4bdb78bba71c9c7193a36fd391
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535726"
---
# <a name="set-up-microsoft-365-business-basic"></a><span data-ttu-id="8b075-103">Настройка Microsoft 365 бизнес базовый</span><span class="sxs-lookup"><span data-stu-id="8b075-103">Set up Microsoft 365 Business Basic</span></span>

 <span data-ttu-id="8b075-104">Посмотрите короткое видео о настройке Microsoft 365 бизнес базовый.</span><span class="sxs-lookup"><span data-stu-id="8b075-104">Watch a short video about setting up Microsoft 365 Business Basic.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

<span data-ttu-id="8b075-105">Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="8b075-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="8b075-106">Добавление домена для персонализации входа</span><span class="sxs-lookup"><span data-stu-id="8b075-106">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="8b075-107">При покупке Microsoft 365 бизнес базовый вы можете воспользоваться принадлежащим вам доменом или купить домен во время регистрации.</span><span class="sxs-lookup"><span data-stu-id="8b075-107">When you purchase Microsoft 365 Business Basic, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="8b075-108">Если вы приобрели новый домен во время регистрации, он уже полностью настроен и можно перейти к пункту [Добавление пользователей и назначение лицензий](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="8b075-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

 ::: moniker range="o365-worldwide"

1. <span data-ttu-id="8b075-109">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="8b075-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8b075-110">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span><span class="sxs-lookup"><span data-stu-id="8b075-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8b075-111">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="8b075-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="8b075-112">Выберите **Перейти к установке**, чтобы запустить мастер установки.</span><span class="sxs-lookup"><span data-stu-id="8b075-112">Choose **Go to setup** to start the wizard.</span></span>
    
3. <span data-ttu-id="8b075-113">На шаге **Добавить домен** введите имя домена, который вы хотите использовать (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8b075-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8b075-p101">Если вы приобрели домен во время регистрации, шаг **Добавить домен** не будет отображаться. Вместо этого перейдите в раздел [Добавить пользователей](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="8b075-p101">If you purchased a domain during the sign-up, you will not see **Add a domain** step here. Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="8b075-116">Выполните шаги, описанные в мастере, по [созданию записей DNS для Office 365 у любого поставщика услуг размещения DNS](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider), который проверяет, являетесь ли вы владельцем домена.</span><span class="sxs-lookup"><span data-stu-id="8b075-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="8b075-117">Если вы знаете свой узел домена, см. также [инструкции для узла](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="8b075-117">If you know your domain host, see also the [host specific instructions](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="8b075-118">Если ваш поставщик услуг размещения — GoDaddy или другой узел, поддерживающий [подключение доменов](/office365/admin/get-help-with-domains/domain-connect), все просто: вам будет автоматически предложено войти в систему и разрешить Майкрософт проверить подлинность от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="8b075-118">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![На странице GoDaddy "Подтверждение доступа" выберите "Авторизовать".](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="8b075-120">Добавление пользователей и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="8b075-120">Add users and assign licenses</span></span>

<span data-ttu-id="8b075-121">Вы можете добавить пользователей в мастере или [позднее](../add-users/add-users.md) в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="8b075-121">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="8b075-122">Кроме того, если у вас есть локальный контроллер домена, вы можете добавить пользователей с помощью [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="8b075-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="8b075-123">Добавление пользователей в мастере</span><span class="sxs-lookup"><span data-stu-id="8b075-123">Add users in the wizard</span></span>

<span data-ttu-id="8b075-124">Всем пользователям, которых вы добавляете в мастере, автоматически назначается лицензия Microsoft 365 бизнес базовый.</span><span class="sxs-lookup"><span data-stu-id="8b075-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Basic license.</span></span>

1. <span data-ttu-id="8b075-p104">Если в вашей подписке на Microsoft 365 бизнес базовый уже есть пользователи (например, если вы использовали Azure AD Connect), вы можете назначить им лицензии прямо сейчас. Добавьте лицензии и для них.</span><span class="sxs-lookup"><span data-stu-id="8b075-p104">If your Microsoft 365 Business Basic subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="8b075-p105">После добавления новых пользователей у вас также будет возможность предоставить им учетные данные. Вы можете распечатать их, отправить по электронной почте или скачать.</span><span class="sxs-lookup"><span data-stu-id="8b075-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="8b075-129">Подключение домена</span><span class="sxs-lookup"><span data-stu-id="8b075-129">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="8b075-130">Если вы решили воспользоваться доменом .onmicrosoft или использовали Azure AD Connect для настройки пользователей, этот шаг отображаться не будет.</span><span class="sxs-lookup"><span data-stu-id="8b075-130">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="8b075-131">Для настройки служб вам необходимо обновить некоторые записи узла DNS или регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="8b075-131">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="8b075-132">Мастер настройки обычно обнаруживает регистратор и предоставляет ссылку на пошаговые инструкции по обновлению записей NS на его сайте.</span><span class="sxs-lookup"><span data-stu-id="8b075-132">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="8b075-133">В противном случае [измените серверы доменных имен для настройки Office 365 у любого регистратора доменных имен](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="8b075-133">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="8b075-134">Если у вас уже есть записи DNS, например для существующего веб-сайта, но узел DNS поддерживает [подключение доменов](/office365/admin/get-help-with-domains/domain-connect), выберите пункт **Автоматическое добавление записей**.</span><span class="sxs-lookup"><span data-stu-id="8b075-134">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="8b075-135">На странице **Выберите веб-службы** примите все условия по умолчанию, нажмите **Далее**, а затем на странице узла DNS выберите **Авторизовать**.</span><span class="sxs-lookup"><span data-stu-id="8b075-135">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="8b075-p108">Если у вас уже есть записи DNS для других узлов DNS (не поддерживающих подключение доменов), вам потребуется управлять своими записями DNS, чтобы убедиться в наличии подключения существующих служб. Дополнительные сведения см. в статье [Основные сведения о доменах](/office365/admin/get-help-with-domains/dns-basics).</span><span class="sxs-lookup"><span data-stu-id="8b075-p108">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="8b075-138">Выполните шаги, описанные в мастере, чтобы настроить электронную почту и другие службы.</span><span class="sxs-lookup"><span data-stu-id="8b075-138">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="8b075-139">По завершении процесса регистрации вы будете перенаправлены в Центр администрирования, где можно добавить пользователей и назначить лицензии.</span><span class="sxs-lookup"><span data-stu-id="8b075-139">When the signup process is complete, you'll be directed to the admin center, where you can add users, and assign licenses.</span></span> <span data-ttu-id="8b075-140">Выполнив первоначальные настройки, вы сможете продолжить настраивать службы, входящие в состав подписок, на странице **Настройка** в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="8b075-140">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="8b075-141">Дополнительные сведения о мастере настройки и странице **Настройка** в Центре администрирования см. в статье [Различия между мастером настройки и страницей "Настройка"](o365-setup-wizard-and-setup-page.md).</span><span class="sxs-lookup"><span data-stu-id="8b075-141">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>