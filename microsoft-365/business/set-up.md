---
title: Настройка Microsoft 365 Business
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Узнайте, как настроить Microsoft 365 Business.
ms.openlocfilehash: 1efb7379930f639cf10875cf5aa6731001bb41c8
ms.sourcegitcommit: 2e5ae52bb641ee1f72c077260b5d0f35622935fe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "37005205"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a><span data-ttu-id="6c5b8-103">Настройка Microsoft 365 Business в мастере установки</span><span class="sxs-lookup"><span data-stu-id="6c5b8-103">Set up Microsoft 365 Business in the setup wizard</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="6c5b8-104">Добавление домена, пользователей и Настройка политик</span><span class="sxs-lookup"><span data-stu-id="6c5b8-104">Add your domain, users, and set up policies</span></span>

![Баннер, который указывает https://aka.ms/aboutM365previewна.](media/m365admincenterchanging.png)

<span data-ttu-id="6c5b8-106">При покупке Microsoft 365 Business вы можете использовать домен, который вы владеете, или приобрести его во время [регистрации](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="6c5b8-106">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="6c5b8-107">Если вы приобрели новый домен при регистрации, все настроенные домены и вы можете перейти к [добавлению пользователей и назначению лицензий](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="6c5b8-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="6c5b8-108">Добавление домена для персонализации при входе</span><span class="sxs-lookup"><span data-stu-id="6c5b8-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="6c5b8-109">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с помощью учетных данных глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="6c5b8-110">Выберите **Добавить домен** или **Добавить пользователей** для запуска мастера.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-110">Choose **Add a domain** or **Add users** to start the wizard.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="6c5b8-111">Если вы приобрели домен во время регистрации, вы не увидите шаг **Добавить домен** .</span><span class="sxs-lookup"><span data-stu-id="6c5b8-111">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="6c5b8-112">Перейдите к разделу [Добавление пользователей](#add-users-and-assign-licenses) .</span><span class="sxs-lookup"><span data-stu-id="6c5b8-112">Go to [Add users ](#add-users-and-assign-licenses) instead.</span></span>

    ![Выберите Добавить домен.](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="6c5b8-114">В мастере введите имя домена, который вы хотите использовать (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6c5b8-114">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![Снимок страницы "Персонализация" страницы входа.](media/personalizesignin.png)

    
4. <span data-ttu-id="6c5b8-116">Следуйте указаниям мастера, чтобы [создать записи DNS на любом поставщике услуг хостинга DNS для Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) , который подтверждает, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="6c5b8-117">Если вы знаете узел домена, ознакомьтесь с [инструкциями, характерными для узла](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="6c5b8-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="6c5b8-118">Если поставщик услуг размещения — GoDaddy, или другой узел, включенный с [подключением к домену](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), процесс будет прост, и вам будет автоматически предложено войти и проверить подлинность Майкрософт от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-118">If your hosting provider is GoDaddy, or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect),the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![На странице "Подтверждение доступа GoDaddy" выберите авторизовать.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="6c5b8-120">Добавление пользователей и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="6c5b8-120">Add users and assign licenses</span></span>

<span data-ttu-id="6c5b8-121">Вы можете добавлять пользователей в мастер, но позднее вы можете [Добавить пользователей](add-users-m365b.md) в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-121">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="6c5b8-122">Кроме того, если у вас есть локальный контроллер домена, вы можете добавить пользователей с помощью [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="6c5b8-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="6c5b8-123">Добавление пользователей в мастер</span><span class="sxs-lookup"><span data-stu-id="6c5b8-123">Add users in the wizard</span></span>

<span data-ttu-id="6c5b8-124">Все пользователи, добавленные в мастере, автоматически получают лицензию Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>

![Снимок экрана со страницей "Добавление новых пользователей" в мастере](media/addnewuserspage.png)

1. <span data-ttu-id="6c5b8-126">Если ваша подписка на Microsoft 365 Business имеет существующих пользователей (например, если вы использовали Azure AD Connect), вы получите возможность назначить лицензии для них сейчас.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-126">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you get an option to assign licenses to them now.</span></span> <span data-ttu-id="6c5b8-127">Добавьте лицензии и для них.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-127">Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="6c5b8-128">После добавления пользователей вы также получите возможность совместного использования учетных данных с новыми добавленными пользователями.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-128">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="6c5b8-129">Вы можете распечатать их, отправить по электронной почте или скачать.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-129">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="6c5b8-130">Пропустите перенос сообщений электронной почты и нажмите кнопку **Далее** на странице **Перенос сообщений электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="6c5b8-131">Если вы переходите от другого поставщика услуг электронной почты и хотите скопировать данные позже, вы можете [перенести электронную почту и контакты в Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="6c5b8-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>


### <a name="connect-your-domain"></a><span data-ttu-id="6c5b8-132">Подключение домена</span><span class="sxs-lookup"><span data-stu-id="6c5b8-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="6c5b8-133">Если вы решили использовать домен onmicrosoft или использовать Azure AD Connect для настройки пользователей, этот шаг не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="6c5b8-134">Для настройки служб вам необходимо обновить некоторые записи узла DNS или регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="6c5b8-135">Мастер настройки обычно определяет регистратора и предоставляет ссылку на пошаговые инструкции по обновлению записей NS на его сайте.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="6c5b8-136">Если это не так, [измените серверов доменных имен, чтобы настроить Office 365 для любого регистратора доменных](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)имен.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-136">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="6c5b8-137">Если у вас есть существующие записи DNS, например существующий веб-сайт, но ваш узел DNS включен для [подключения к домену](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), нажмите кнопку **добавить записи**.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> 
    - <span data-ttu-id="6c5b8-138">Если у вас есть существующие записи DNS с другими узлами DNS (не включены для подключения к домену), вам потребуется управлять собственными записями DNS, чтобы убедиться, что существующие службы остаются подключенными.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-138">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="6c5b8-139">Более подробную информацию можно узнать в разделе [domain основы доменов](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .</span><span class="sxs-lookup"><span data-stu-id="6c5b8-139">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Подсоедините страницу домена, чтобы управлять собственными записями DNS.](media/connectyourdomainpage.png)

2. <span data-ttu-id="6c5b8-141">Следуйте указаниям мастера, электронной почты и других служб.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-141">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="6c5b8-142">Настройка политик безопасности и конфигураций устройств</span><span class="sxs-lookup"><span data-stu-id="6c5b8-142">Set up security policies and device configurations</span></span> 

<span data-ttu-id="6c5b8-143">Политики, настроенные в мастере, автоматически применяются к [группе безопасности](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) с именем " *все пользователи*".</span><span class="sxs-lookup"><span data-stu-id="6c5b8-143">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="6c5b8-144">Кроме того, можно создать дополнительные группы, чтобы назначить политики в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-144">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="6c5b8-145">В разделе **Защита рабочих файлов на мобильных устройствах** — возможность защиты рабочих файлов по умолчанию выбрано **при потере или краже устройств** .</span><span class="sxs-lookup"><span data-stu-id="6c5b8-145">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="6c5b8-146">В этом случае рекомендуется включить **Управление доступом пользователей к файлам Office на мобильных устройствах**.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-146">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![Снимок экрана: страница "Защита рабочих файлов на мобильных устройствах".](media/protectworkfilesondevices.png)

     - <span data-ttu-id="6c5b8-148">Expand **Защитите рабочие файлы при потере или краже устройств** для отображения [значений по умолчанию](protect-work-files-on-lost-or-stolen-device.md):</span><span class="sxs-lookup"><span data-stu-id="6c5b8-148">Expand **Protect work files when devices are lost or stolen** to display the [default values](protect-work-files-on-lost-or-stolen-device.md):</span></span>

        ![Снимок экрана со значениями по умолчанию для защиты файлов на потерянных устройствах.](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="6c5b8-150">Выберите **Управление доступом пользователей к файлам Office на мобильных устройствах** и разверните его, чтобы отобразить [значения по умолчанию](manage-user-access-on-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="6c5b8-150">Select **Manage how users access Office files on mobile devices** and expand it to display the [default values](manage-user-access-on-mobile-devices.md).</span></span> <span data-ttu-id="6c5b8-151">Рекомендуется принять значения по умолчанию во время установки, чтобы создать политики приложений для Android, iOS и Windows 10, которые применяются ко всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-151">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="6c5b8-152">По завершении настройки вы сможете создать дополнительные политики.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-152">You can create more policies after setup completes.</span></span>

        ![Снимок экрана параметров защиты для файлов Office на мобильных устройствах.](media/useraccessonmobile.png)

2. <span data-ttu-id="6c5b8-154">Последний шаг по защите данных и устройств позволяет настроить политики для защиты устройств с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-154">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="6c5b8-155">Эти параметры применяются автоматически, когда пользователь Windows 10 подключается к Организации.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-155">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="6c5b8-156">Вы можете развернуть **безопасные устройства Windows 10** , чтобы просмотреть и изменить [значения по умолчанию](secure-windows-10-devices.md).</span><span class="sxs-lookup"><span data-stu-id="6c5b8-156">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="6c5b8-157">Вы также можете [автоматически устанавливать Office](install-office-on-windows-10-during-setup.md) на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-157">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Снимок экрана: Настройка страницы настройки устройства Windows 10.](media/setwin10config.png)



## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="6c5b8-159">Развертывание клиентских приложений Office 365</span><span class="sxs-lookup"><span data-stu-id="6c5b8-159">Deploy Office 365 client apps</span></span>

<span data-ttu-id="6c5b8-160">Если вы выбрали автоматическую установку приложений Office во время настройки, приложения будут устанавливаться на устройства с Windows 10, когда пользователи войдет в Azure AD с своих рабочих учетных данных.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-160">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="6c5b8-161">Чтобы установить Office на мобильные устройства с iOS или Android, ознакомьтесь со статьей [Настройка мобильных устройств для Microsoft 365 Business Users](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="6c5b8-161">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="6c5b8-162">Вы также можете установить Office по отдельности.</span><span class="sxs-lookup"><span data-stu-id="6c5b8-162">You can also install Office individually.</span></span> <span data-ttu-id="6c5b8-163">Инструкции: [Install Office на ПК или Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) .</span><span class="sxs-lookup"><span data-stu-id="6c5b8-163">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>
