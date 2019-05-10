---
title: Настройка Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660886"
---
# <a name="set-up-microsoft-365-business"></a><span data-ttu-id="bcb1b-103">Настройка Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="bcb1b-103">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="bcb1b-104">Прежде чем приступить к работе, ознакомьтесь со статьей получение сведений о регистрации в [Microsoft 365 Business](get-microsoft-365-business.md) .</span><span class="sxs-lookup"><span data-stu-id="bcb1b-104">Before you get started, see [Get Microsoft 365 Business](get-microsoft-365-business.md) for sign-up details.</span></span>

<span data-ttu-id="bcb1b-105">Посмотрите [короткий видеоролик о настройке Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) с помощью мастера настройки, а если у вас нет локальной службы Active Directory</span><span class="sxs-lookup"><span data-stu-id="bcb1b-105">Watch a [short video on how to set up Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) by using the set up wizard, and when you don't have an on-premises Active Directory</span></span>
  

## <a name="overview"></a><span data-ttu-id="bcb1b-106">Обзор</span><span class="sxs-lookup"><span data-stu-id="bcb1b-106">Overview</span></span>

<span data-ttu-id="bcb1b-107">Большинство этапов настройки можно выполнить в мастере установки, но Кроме того, указаны другие параметры.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-107">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>

1. <span data-ttu-id="bcb1b-108">[Добавление домена](#add-your-domain-to-personalize-sign-in) (если вы приобрели свой домен во время [регистрации](sign-up.md), этот шаг уже выполнен.)</span><span class="sxs-lookup"><span data-stu-id="bcb1b-108">[Add your domain](#add-your-domain-to-personalize-sign-in) (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>
2. <span data-ttu-id="bcb1b-109">Добавление пользователей.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-109">Add users.</span></span> <span data-ttu-id="bcb1b-110">Это можно сделать одним из трех способов:</span><span class="sxs-lookup"><span data-stu-id="bcb1b-110">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="bcb1b-111">В [мастере установки](#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-111">In the [setup wizard](#add-users-in-the-wizard).</span></span>
    - <span data-ttu-id="bcb1b-112">Используйте синхронизацию службы каталогов для [добавления пользователей с помощью Azure AD Connect,](#add-users-by-using-azure-ad-connect) если у вас есть локальная служба Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-112">Use directory synchronization to [add users by using Azure AD Connect](#add-users-by-using-azure-ad-connect) if you have an on-premises Active directory.</span></span>
    - <span data-ttu-id="bcb1b-113">Вы также можете [Добавить пользователей позже](add-users-m365b.md) в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
3. <span data-ttu-id="bcb1b-114">Настройка политик безопасности и настройка устройств.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-114">Set up security policies and configure devices.</span></span> <span data-ttu-id="bcb1b-115">Это можно сделать одним из трех способов:</span><span class="sxs-lookup"><span data-stu-id="bcb1b-115">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="bcb1b-116">В [мастере установки](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-116">In the [setup wizard](#set-up-policies-in-the-wizard).</span></span>  
    - <span data-ttu-id="bcb1b-117">В [центре администрирования](#modify-or-add-policies-in-the-admin-center).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-117">In the [admin center](#modify-or-add-policies-in-the-admin-center).</span></span>
    - <span data-ttu-id="bcb1b-118">В [центре администрирования Intune](https://docs.microsoft.com/intune/what-is-device-management).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-118">In the [Intune admin center](https://docs.microsoft.com/intune/what-is-device-management).</span></span>
4. <span data-ttu-id="bcb1b-119">Настройка устройств с Windows 10 и управление ими.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-119">Set up and manage Windows 10 devices.</span></span>

    <span data-ttu-id="bcb1b-120">Когда вы присоединяете устройство WIndows 10 к Azure AD, к нему применяются все политики.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-120">When you join a WIndows 10 device to Azure AD, all the policies get applied to it.</span></span>
    - <span data-ttu-id="bcb1b-121">Настройка конфигурации устройств с Windows 10 в [мастере установки](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-121">Set up Windows 10 device configurations in the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="bcb1b-122">Присоедините [новое устройство с Windows 10](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-122">Join a [new Windows 10 device](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) to Azure AD.</span></span>
    - <span data-ttu-id="bcb1b-123">Присоедините [существующее устройство Windows 10](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-123">Join an [existing Windows 10 device](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) to Azure AD.</span></span>
1. <span data-ttu-id="bcb1b-124">Установите Office 365 Business.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-124">Install Office 365 Business.</span></span>
    - <span data-ttu-id="bcb1b-125">Вы можете автоматически установить Office на устройствах с Windows с помощью [мастера установки](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-125">You can automatically install Office in the Windows devices by using the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="bcb1b-126">Автоматическая [Установка Office](auto-install-or-uninstall-office.md) из центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-126">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
    - <span data-ttu-id="bcb1b-127">Разрешите пользователям [устанавливать приложения Office](https://docs.microsoft.com/office365/admin/setup/install-applications) для Windows и устройств.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-127">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
1. <span data-ttu-id="bcb1b-128">Настройка дополнительной защиты.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-128">Set up additional security.</span></span>
    - <span data-ttu-id="bcb1b-129">Мастер установки добавляет политики для защиты устройств, но вы также можете воспользоваться дополнительными возможностями [обеспечения безопасности](#additional-security-settings) , чтобы обеспечить безопасность данных, учетных записей и сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-129">The setup wizard adds policies to secure your devices, but you can also take advantage of [additional security](#additional-security-settings) capabilities to helps secure your data, accounts, and emails.</span></span> 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="bcb1b-130">Добавление домена, пользователей и Настройка политик</span><span class="sxs-lookup"><span data-stu-id="bcb1b-130">Add your domain, users and set up policies</span></span>

![Баннер, который указывает https://aka.ms/aboutM365previewна.](media/m365admincenterchanging.png)

<span data-ttu-id="bcb1b-132">При покупке Microsoft 365 Business вы можете использовать домен, который вы владеете, или приобрести его во время [регистрации](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-132">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="bcb1b-133">Если вы приобрели новый домен при регистрации, все настроенные домены и вы можете перейти к [добавлению пользователей и назначению лицензий](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-133">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="bcb1b-134">Добавление домена для персонализации при входе</span><span class="sxs-lookup"><span data-stu-id="bcb1b-134">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="bcb1b-135">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с помощью учетных данных глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-135">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="bcb1b-136">Чтобы запустить мастер, нажмите кнопку **Добавить домен** .</span><span class="sxs-lookup"><span data-stu-id="bcb1b-136">Choose **Add a domain** to start the wizard.</span></span>

    ![Выберите Добавить домен.](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="bcb1b-138">В мастере введите имя домена, который вы хотите использовать (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-138">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![Снимок страницы "Персонализация" страницы входа.](media/personalizesignin.png)

    
4. <span data-ttu-id="bcb1b-140">Следуйте указаниям мастера, чтобы [создать записи DNS на любом поставщике услуг хостинга DNS для Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) , который подтверждает, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-140">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="bcb1b-141">Если вы знаете узел домена, ознакомьтесь с инструкциями, характерными для [узла](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-141">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="bcb1b-142">Если поставщик услуг хостинга — GoDaddy, процесс будет выполняться легко, и вам будет автоматически предложено войти и проверить подлинность Майкрософт от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-142">If your hosting provider is GoDaddy, the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![На странице "Подтверждение доступа GoDaddy" выберите авторизовать.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="bcb1b-144">Добавление пользователей и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="bcb1b-144">Add users and assign licenses</span></span>

<span data-ttu-id="bcb1b-145">Вы можете добавлять пользователей в мастер, но позднее вы можете [Добавить пользователей](add-users-m365b.md) в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-145">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="bcb1b-146">Кроме того, если у вас есть локальный контроллер домена, вы можете добавить пользователей с помощью [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-146">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="bcb1b-147">Добавление пользователей в мастер</span><span class="sxs-lookup"><span data-stu-id="bcb1b-147">Add users in the wizard</span></span>

<span data-ttu-id="bcb1b-148">Все пользователи, добавленные в мастере, автоматически получают лицензию Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-148">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>
<span data-ttu-id="bcb1b-149">Если у вас есть локальный контроллер домена и используете Active Directory, Узнайте, [как DDD Users с помощью Azure AD Connect](#add-users-by-using-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-149">If you have a local domain controller, and are using Active Directory, see [how to ddd users by using Azure AD Connect](#add-users-by-using-azure-ad-connect).</span></span>

![Снимок экрана со страницей "Добавление новых пользователей" в мастере](media/addnewuserspage.png)

1. <span data-ttu-id="bcb1b-p106">Если в вашей подписке на Office 365 бизнес уже есть пользователи (например, если вы использовали Azure AD Connect), вы сможете сейчас назначить им лицензии. Добавьте лицензии и для них.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-p106">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="bcb1b-153">После добавления пользователей вы также получите возможность совместного использования учетных данных с новыми добавленными пользователями.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-153">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="bcb1b-154">Вы можете распечатать их, отправить по электронной почте или скачать.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-154">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="bcb1b-155">Пропустите перенос сообщений электронной почты и нажмите кнопку **Далее** на странице **Перенос сообщений электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-155">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="bcb1b-156">Если вы переходите от другого поставщика услуг электронной почты и хотите скопировать данные позже, вы можете [перенести электронную почту и контакты в Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-156">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>

#### <a name="add-users-by-using-azure-ad-connect"></a><span data-ttu-id="bcb1b-157">Добавление пользователей с помощью Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="bcb1b-157">Add users by using Azure AD Connect</span></span>

 <span data-ttu-id="bcb1b-158">Если у вас есть локальный контроллер домена с Active Directory, вы синхронизируете пользователей с Microsoft 365 Business с помощью [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-158">If you have a local domain controller with Active Directory, you synchronize your users with Microsoft 365 Business by using [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span> <span data-ttu-id="bcb1b-159">Выполните это перед запуском мастера установки.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-159">Complete this before you start the setup wizard.</span></span> <span data-ttu-id="bcb1b-160">Его можно загрузить в центре администрирования:</span><span class="sxs-lookup"><span data-stu-id="bcb1b-160">You can download it in the admin center:</span></span>

- <span data-ttu-id="bcb1b-161">Перейдите к разделу **Активные пользователи** **пользователей** \> , выберите многоточие в верхней части страницы, а затем выберите **Синхронизация службы каталогов** , чтобы скачать Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-161">Go to **Users** \> **Active users**, select the ellipses on the top of the page and then select **Directory synchronization** to download Azure AD Connect.</span></span>

    ![На странице активные пользователи выберите многоточия _Гт_ Directory снчронизатион.](media/setupdirsync.png)

    > [!IMPORTANT]
    > <span data-ttu-id="bcb1b-163">Если вы создаете пользователей таким способом, вам по-прежнему потребуется назначить им лицензии в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-163">If you create users this way, you will still have to assign licenses to them in the admin center.</span></span>

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a><span data-ttu-id="bcb1b-164">Продолжите доступ к приложениям и устройствам, присоединенным к домену</span><span class="sxs-lookup"><span data-stu-id="bcb1b-164">Continue to access domain-joined apps and devices</span></span>

<span data-ttu-id="bcb1b-165">Если вы хотите продолжить доступ к приложениям и устройствам, присоединенных к домену, ознакомьтесь со следующими статьями, посвященными двум разным способам реализации:</span><span class="sxs-lookup"><span data-stu-id="bcb1b-165">If you want to continue to access domain-joined apps and devices, read the following articles for two different way of enabling that:</span></span>
  
- [<span data-ttu-id="bcb1b-166">Включение управления подключенными к домену устройств с Windows 10 в Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="bcb1b-166">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    - <span data-ttu-id="bcb1b-167">Это рекомендуемый способ.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-167">This is the recommended way.</span></span>

- [<span data-ttu-id="bcb1b-168">Доступ к локальным ресурсам из устройства, подключенного к Azure AD, в Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="bcb1b-168">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)

### <a name="connect-your-domain"></a><span data-ttu-id="bcb1b-169">Подключение домена</span><span class="sxs-lookup"><span data-stu-id="bcb1b-169">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="bcb1b-170">Если вы решили использовать домен onmicrosoft или использовать Azure AD Connect для настройки пользователей, этот шаг не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-170">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="bcb1b-171">Для настройки служб вам необходимо обновить некоторые записи узла DNS или регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-171">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="bcb1b-172">Мастер настройки обычно определяет регистратора и предоставляет ссылку на пошаговые инструкции по обновлению записей NS на его сайте.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-172">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="bcb1b-173">Если это не так, [измените серверов доменных имен, чтобы настроить Office 365 для любого регистратора доменных](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)имен.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-173">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="bcb1b-174">Если у вас есть существующие записи DNS, например существующий веб-сайт, вам будет необходимо управлять собственными записями DNS, чтобы убедиться, что существующие службы остаются подключенными.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-174">If you have existing DNS records, for example an existing web site, you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="bcb1b-175">Более подробную информацию можно узнать в разделе [domain основы доменов](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .</span><span class="sxs-lookup"><span data-stu-id="bcb1b-175">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Подсоедините страницу домена, чтобы управлять собственными записями DNS.](media/connectyourdomainpage.png)

2. <span data-ttu-id="bcb1b-177">Следуйте указаниям мастера, электронной почты и других служб.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-177">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="bcb1b-178">Настройка политик безопасности и конфигураций устройств</span><span class="sxs-lookup"><span data-stu-id="bcb1b-178">Set up security policies and device configurations</span></span> 

<span data-ttu-id="bcb1b-179">Эти политики применяются ко всем пользователям, которым назначена лицензия, или к группе пользователей, если вы решили назначить различные политики для набора пользователей.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-179">These policies apply to every user you give a license to, or to a group of users if you decide to assign different policies to a set of users.</span></span>

#### <a name="set-up-policies-in-the-wizard"></a><span data-ttu-id="bcb1b-180">Настройка политик в мастере</span><span class="sxs-lookup"><span data-stu-id="bcb1b-180">Set up policies in the wizard</span></span>

<span data-ttu-id="bcb1b-181">Политики, настроенные в мастере, автоматически применяются к [группе безопасности](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) с именем " *все пользователи*".</span><span class="sxs-lookup"><span data-stu-id="bcb1b-181">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span>

1. <span data-ttu-id="bcb1b-182">В разделе **Защита рабочих файлов на мобильных устройствах** — возможность защиты рабочих файлов по умолчанию выбрано **при потере или краже устройств** .</span><span class="sxs-lookup"><span data-stu-id="bcb1b-182">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="bcb1b-183">В этом случае рекомендуется включить **Управление доступом пользователей к файлам Office на мобильных устройствах**.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-183">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![Снимок экрана: страница "Защита рабочих файлов на мобильных устройствах".](media/protectworkfilesondevices.png)

     - <span data-ttu-id="bcb1b-185">Если вы развернете **рабочие файлы в случае потери или кражи устройств**, будут предварительно выбраны [значения по умолчанию](protect-work-files-on-lost-or-stolen-device.md) :</span><span class="sxs-lookup"><span data-stu-id="bcb1b-185">If you expand **Protect work files when devices are lost or stolen**, the [default values](protect-work-files-on-lost-or-stolen-device.md) are pre-selected:</span></span>

        ![Снимок экрана со значениями по умолчанию для защиты файлов на потерянных устройствах.](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="bcb1b-187">При выборе параметра **Управление доступом пользователей к файлам Office на мобильных устройствах** и их разворачивание отображаются [значения по умолчанию](manage-user-access-on-mobile-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="bcb1b-187">If you select **Manage how users access Office files on mobile devices** and expand it, the [default values](manage-user-access-on-mobile-devices.md) are shown.</span></span> <span data-ttu-id="bcb1b-188">Советуем во время настройки принять значения по умолчанию, чтобы создать политики приложений для устройств с Windows 10, iOS и Android, которые будут применяться ко всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-188">We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="bcb1b-189">По завершении настройки вы сможете создать дополнительные политики.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-189">You can create more policies after setup completes.</span></span>

        ![Снимок экрана параметров защиты для файлов Office на мобильных устройствах.](media/useraccessonmobile.png)

2. <span data-ttu-id="bcb1b-191">Последний шаг по защите данных и устройств позволяет настроить политики для защиты устройств с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-191">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="bcb1b-192">Эти параметры применяются автоматически, когда пользователь Windows 10 подключается к Организации.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-192">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="bcb1b-193">Вы можете развернуть **безопасные устройства Windows 10** , чтобы просмотреть и изменить [значения по умолчанию](secure-windows-10-devices.md).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-193">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="bcb1b-194">Вы также можете [автоматически устанавливать Office](install-office-on-windows-10-during-setup.md) на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-194">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Снимок экрана: Настройка страницы настройки устройства Windows 10.](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a><span data-ttu-id="bcb1b-196">Изменение или Добавление политик в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="bcb1b-196">Modify or add policies in the admin center</span></span>

<span data-ttu-id="bcb1b-197">В [статье Manage Microsoft 365 Business](manage.md) содержатся ссылки на разделы, посвященные просмотру и изменению политик защиты устройств и приложений, а также удалению и сбросу данных устройств пользователя.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-197">See [manage Microsoft 365 Business](manage.md) for links to topics on how to view and modify device and app protection polices, and how to remove data from, or reset user devices.</span></span>

## <a name="deploy-and-manage-windows-10"></a><span data-ttu-id="bcb1b-198">Развертывание Windows 10 и управление ими</span><span class="sxs-lookup"><span data-stu-id="bcb1b-198">Deploy and manage Windows 10</span></span>
<span data-ttu-id="bcb1b-199">Ознакомьтесь со статьей [Настройка устройств Windows для Microsoft 365 бизнес-пользователей](set-up-windows-devices.md) , чтобы вручную подключиться к Azure AD, во время установки для новых компьютеров или путем изменения профиля входа для существующих компьютеров.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-199">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) to manually connect to Azure AD, either during setup for new computers, or by changing sign-in profile for existing computers.</span></span> 

### <a name="use-autopilot-to-set-up-new-devices"></a><span data-ttu-id="bcb1b-200">Использование автопилота для настройки новых устройств</span><span class="sxs-lookup"><span data-stu-id="bcb1b-200">Use Autopilot to set up new devices</span></span>

<span data-ttu-id="bcb1b-201">Вы можете использовать [автопилот Windows](add-autopilot-devices-and-profile.md) для автоматической предварительной настройки **новых** устройств с Windows 10 для пользователя, но вам может быть проще получить [партнера](https://www.microsoft.com/solution-providers/search) , который может сделать это.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-201">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="bcb1b-202">Вы также можете перейти в [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) и попросить специалиста по облачным технологиям настроить новые устройства, которые вы приобрели.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-202">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

### <a name="access-on-premises-resources"></a><span data-ttu-id="bcb1b-203">Доступ к локальным ресурсам</span><span class="sxs-lookup"><span data-stu-id="bcb1b-203">Access on-premises resources</span></span>

<span data-ttu-id="bcb1b-204">Если ваша организация использует локальную службу Windows Server Active Directory, вы можете настроить Microsoft 365 бизнес для защиты устройств с Windows 10, сохраняя доступ к локальным ресурсам, требующим локальной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-204">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="bcb1b-205">Выполните действия, описанные в разделе " [Включение устройств, присоединенных к домену" с Windows 10 для управления в Microsoft 365 Business](manage-windows-devices.md) , чтобы настроить.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-205">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="bcb1b-206">Это предпочитаемый метод и устройства в этом состоянии называются гибридными подключенными устройствами Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-206">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

<span data-ttu-id="bcb1b-207">Если в вашей организации есть локальная служба Active Directory, содержащая некоторые локальные ресурсы (например, файловые ресурсы и принтеры), вы можете предоставить подключенным устройствам Azure AD доступ к этим ресурсам, выполнив действия, описанные здесь: [доступ к локальным ресурсам из Подключенное к Azure AD устройство в Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-207">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="bcb1b-208">Развертывание клиентских приложений Office 365</span><span class="sxs-lookup"><span data-stu-id="bcb1b-208">Deploy Office 365 client apps</span></span>

<span data-ttu-id="bcb1b-209">Если вы выбрали автоматическую установку приложений Office во время настройки, приложения будут устанавливаться на устройства с Windows 10, когда пользователи войдет в Azure AD с своих рабочих учетных данных.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-209">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="bcb1b-210">Чтобы установить Office на мобильные устройства с iOS или Android, ознакомьтесь со статьей [Настройка мобильных устройств для Microsoft 365 Business Users](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-210">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="bcb1b-211">Вы также можете установить Office по отдельности.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-211">You can also install Office individually.</span></span> <span data-ttu-id="bcb1b-212">Инструкции: [Install Office на ПК или Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) .</span><span class="sxs-lookup"><span data-stu-id="bcb1b-212">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) for instructions.</span></span>

## <a name="additional-security-settings"></a><span data-ttu-id="bcb1b-213">Дополнительные параметры безопасности</span><span class="sxs-lookup"><span data-stu-id="bcb1b-213">Additional security settings</span></span>

<span data-ttu-id="bcb1b-214">В дополнение к параметрам "безопасность и соответствие требованиям" в мастере установки можно также настроить следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="bcb1b-214">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="bcb1b-215">**Защита от вредоносных программ электронной почты**</span><span class="sxs-lookup"><span data-stu-id="bcb1b-215">**Email malware protection**</span></span>
- <span data-ttu-id="bcb1b-216">**Безопасные вложения Advanced Threat protection (ATP)**</span><span class="sxs-lookup"><span data-stu-id="bcb1b-216">**Advanced Threat Protection (ATP) Safe Attachments**</span></span>
- <span data-ttu-id="bcb1b-217">**Безопасные ссылки ATP**</span><span class="sxs-lookup"><span data-stu-id="bcb1b-217">**ATP Safe Links**</span></span>
- <span data-ttu-id="bcb1b-218">**Защита от фишинга Апт**</span><span class="sxs-lookup"><span data-stu-id="bcb1b-218">**APT anti-phishing**</span></span>
- <span data-ttu-id="bcb1b-219">**Архивация на базе Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="bcb1b-219">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="bcb1b-220">**Предотвращение потери данных (DLP)**</span><span class="sxs-lookup"><span data-stu-id="bcb1b-220">**Data loss prevention (DLP)**</span></span>
- <span data-ttu-id="bcb1b-221">**Azure Information Protection** (План 1)</span><span class="sxs-lookup"><span data-stu-id="bcb1b-221">**Azure Information Protection** (Plan 1)</span></span>
- <span data-ttu-id="bcb1b-222">**Доступность портала Intune**</span><span class="sxs-lookup"><span data-stu-id="bcb1b-222">**Intune portal availability**</span></span>

<span data-ttu-id="bcb1b-223">Чтобы приступить к работе, [Настройте дополнительные политики безопасности](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-223">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

<span data-ttu-id="bcb1b-224">Кроме того, вы можете ознакомиться с десятью рекомендациями по обеспечению безопасности [Microsoft 365 для бизнеса](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) в плане рекомендаций по обеспечению безопасности.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-224">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>