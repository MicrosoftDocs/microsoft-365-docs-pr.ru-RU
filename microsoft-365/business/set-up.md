---
title: Настройка Microsoft 365 Business с помощью мастера настройки
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
description: Узнайте, как настроить Microsoft 365 бизнес, выполнив четыре действия.
ms.openlocfilehash: a1c8a41c3e291983276280a063248bdd10a7f85a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283946"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="27d3d-103">Настройка Microsoft 365 Business с помощью мастера настройки</span><span class="sxs-lookup"><span data-stu-id="27d3d-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="27d3d-104">Выполните шаги 1-4 ниже.</span><span class="sxs-lookup"><span data-stu-id="27d3d-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="27d3d-105">Настройка Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="27d3d-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="27d3d-106">Посмотрите видеоролик о том, как настроить Microsoft 365 бизнес, если у вас нет локальной службы Active Directory:</span><span class="sxs-lookup"><span data-stu-id="27d3d-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="27d3d-107">Действия по настройке включают сведения для настроек, которые включают в себя локальный каталог Active Directory.</span><span class="sxs-lookup"><span data-stu-id="27d3d-107">The set-up steps include information for setups that include local Active Directory.</span></span> <span data-ttu-id="27d3d-108">Если вы хотите продолжить доступ к подключенным к домену устройствам, ознакомьтесь со следующими статьями, посвященными двум разным способам реализации, и выполните действия, описанные перед запуском мастера установки:</span><span class="sxs-lookup"><span data-stu-id="27d3d-108">If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="27d3d-109">Включение управления подключенными к домену устройств с Windows 10 в Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="27d3d-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="27d3d-110">— Это рекомендуемый способ.</span><span class="sxs-lookup"><span data-stu-id="27d3d-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="27d3d-111">Доступ к локальным ресурсам из устройства, подключенного к Azure AD, в Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="27d3d-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="27d3d-112">Шаг 1: Персонализация входа</span><span class="sxs-lookup"><span data-stu-id="27d3d-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="27d3d-p102">Войдите в [Microsoft 365 Business](https://portal.microsoft.com) с учетными данными глобального администратора. Щелкните плитку **Администратор**, чтобы перейти в Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="27d3d-p102">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="27d3d-115">В центре администрирования нажмите кнопку **начать установку** (в зависимости от состояния системы вместо нее может отображаться кнопка **Продолжить установку**), чтобы запустить мастер.</span><span class="sxs-lookup"><span data-stu-id="27d3d-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="27d3d-116">Введите имя домена, который вы хотите использовать (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="27d3d-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="27d3d-117">Смелее! Введите имя домена, даже если вы проверили его, например, с помощью Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="27d3d-117">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example.</span></span> <span data-ttu-id="27d3d-118">Следующие два действия не относятся к вам, если вы использовали Azure AD Connect для проверки домена.</span><span class="sxs-lookup"><span data-stu-id="27d3d-118">The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="27d3d-119">Следуйте указаниям мастера, чтобы [создать записи DNS на любом поставщике услуг хостинга DNS для Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) , который подтверждает, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="27d3d-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="27d3d-120">Вы можете просмотреть пример видео [: Setup Office 365 в новом центре администрирования](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8).</span><span class="sxs-lookup"><span data-stu-id="27d3d-120">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8).</span></span> <span data-ttu-id="27d3d-121">В него не включены этапы защиты данных, связанные с Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="27d3d-121">Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="27d3d-123">Шаг 2: Добавление пользователей и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="27d3d-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="27d3d-124">Вы можете добавить пользователей здесь или [позднее](add-users-m365b.md) в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="27d3d-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="27d3d-125">Всем добавляемым пользователям автоматически назначается лицензия Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="27d3d-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="27d3d-p105">Если в вашей подписке на Office 365 бизнес уже есть пользователи (например, если вы использовали Azure AD Connect), вы сможете сейчас назначить им лицензии. Добавьте лицензии и для них.</span><span class="sxs-lookup"><span data-stu-id="27d3d-p105">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="27d3d-p106">У вас также будет возможность передать учетные данные добавленным пользователям. Вы можете распечатать их, отправить по электронной почте или скачать.</span><span class="sxs-lookup"><span data-stu-id="27d3d-p106">You will also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="27d3d-130">Пропустите перенос сообщений электронной почты и нажмите кнопку **Далее** на странице **Перенос сообщений электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="27d3d-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="27d3d-131">Если вы переходите от другого поставщика услуг электронной почты и хотите скопировать данные позже, вы можете [перенести электронную почту и контакты в Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="27d3d-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="27d3d-133">Шаг 3: подключение домена</span><span class="sxs-lookup"><span data-stu-id="27d3d-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="27d3d-134">Если вы решили использовать домен. onmicrosoft или использовать Azure AD Connect, это действие не будет выводиться.</span><span class="sxs-lookup"><span data-stu-id="27d3d-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="27d3d-135">Для настройки служб вам необходимо обновить некоторые записи узла DNS или регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="27d3d-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="27d3d-136">Мастер настройки обычно определяет регистратора и предоставляет ссылку на пошаговые инструкции по обновлению записей NS на его сайте.</span><span class="sxs-lookup"><span data-stu-id="27d3d-136">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="27d3d-137">Если это не так, [измените серверов доменных имен, чтобы настроить Office 365 для любого регистратора доменных](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)имен.</span><span class="sxs-lookup"><span data-stu-id="27d3d-137">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="27d3d-138">Для вас будут настроены электронная почта и другие службы.</span><span class="sxs-lookup"><span data-stu-id="27d3d-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="27d3d-139">Шаг 4: Управление устройствами и рабочими файлами</span><span class="sxs-lookup"><span data-stu-id="27d3d-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="27d3d-140">На странице **Защита данных на мобильных устройствах** **включите** параметры **Защита рабочих файлов при краже или потере устройств** и **Контроль над доступом пользователей к файлам Office с мобильных устройств**.</span><span class="sxs-lookup"><span data-stu-id="27d3d-140">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**.</span></span> <span data-ttu-id="27d3d-141">Кроме того, можно получить доступ ко всем подпараметрам, щелкнув значок шеврона рядом с каждым параметром.</span><span class="sxs-lookup"><span data-stu-id="27d3d-141">You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="27d3d-142">Все рабочие файлы ваших лицензированных пользователей теперь защищены на устройствах iOS и Android, как только они [устанавливают приложения Office](set-up-mobile-devices.md) (и проходят проверку подлинности с помощью Microsoft 365 Business Credentials).</span><span class="sxs-lookup"><span data-stu-id="27d3d-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="27d3d-144">На странице " **Настройка устройств с Windows 10** " установите для параметра **Secure Windows 10 Devices** значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="27d3d-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="27d3d-145">Кроме того, можно получить доступ ко всем подпараметрам, щелкнув Шеврон рядом с ним.</span><span class="sxs-lookup"><span data-stu-id="27d3d-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="27d3d-146">Установите для параметра **установить устройства Office в Windows 10** значение **Да** , если у всех пользователей есть компьютеры с Windows 10, либо нет установленных установленных приложений Office, либо "нажми и работай" установки Office.</span><span class="sxs-lookup"><span data-stu-id="27d3d-146">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs.</span></span> <span data-ttu-id="27d3d-147">Если это не так, установите для этого параметра значение **нет**.</span><span class="sxs-lookup"><span data-stu-id="27d3d-147">If this is not the case, set this option to **No**.</span></span> <span data-ttu-id="27d3d-148">Вы можете [автоматически установить Office](auto-install-or-uninstall-office.md) позднее из центра администрирования после подготовки компьютеров пользователей.</span><span class="sxs-lookup"><span data-stu-id="27d3d-148">You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers.</span></span> <span data-ttu-id="27d3d-149">Инструкции можно найти в разделе [Подготовка к установке клиента Office](prepare-for-office-client-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="27d3d-149">For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="27d3d-150">Рабочие файлы лицензированных пользователей на устройствах с Windows 10 будут отображаться сразу после [присоединения устройства Windows 10](set-up-windows-devices.md) к домену Microsoft 365 Business Azure AD или [установки Windows 10 на новом компьютере](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) при одновременном подключении к Microsoft 365 Домен бизнес-службы Azure AD.</span><span class="sxs-lookup"><span data-stu-id="27d3d-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="27d3d-151">Нажмите кнопку **Далее** и завершите работу программы установки.</span><span class="sxs-lookup"><span data-stu-id="27d3d-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="27d3d-152">На этом этапе мы не будем рады получить отзыв о том, что поможет нам улучшить работу.</span><span class="sxs-lookup"><span data-stu-id="27d3d-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="27d3d-154">Дополнительные параметры безопасности</span><span class="sxs-lookup"><span data-stu-id="27d3d-154">Additional security settings</span></span>

<span data-ttu-id="27d3d-155">В дополнение к параметрам "безопасность и соответствие требованиям" в мастере установки можно также настроить следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="27d3d-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="27d3d-156">Настройка защиты от небезопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="27d3d-156">Set up protection against unsafe attachments.</span></span> <span data-ttu-id="27d3d-157">**РасширенНая защита от угроз** (ATP) определяет вредоносный контент, а затем блокирует доставку небезопасных вложений, помогая защититься от фишинговых схем и заражения программой-шантажистом.</span><span class="sxs-lookup"><span data-stu-id="27d3d-157">**Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections.</span></span> <span data-ttu-id="27d3d-158">Чтобы активировать защиту вложений, ознакомьтесь со статьей [Настройка политик безопасных вложенИй в Office 365 ATP](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span><span class="sxs-lookup"><span data-stu-id="27d3d-158">To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="27d3d-159">Защитите среду, когда пользователи щелкают вредоносные ссылки.</span><span class="sxs-lookup"><span data-stu-id="27d3d-159">Protect your environment when users click malicious links.</span></span> <span data-ttu-id="27d3d-160">ATP просматривает ссылки в сообщениях электронной почты на тот момент, когда пользователь щелкает их.</span><span class="sxs-lookup"><span data-stu-id="27d3d-160">ATP examines links in email at the time a user clicks them.</span></span> <span data-ttu-id="27d3d-161">Если ссылка небезопасна, пользователь не сможет посетить сайт или сообщить о том, что сайт заблокирован.</span><span class="sxs-lookup"><span data-stu-id="27d3d-161">If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked.</span></span> <span data-ttu-id="27d3d-162">Это помогает защититься от фишинговых схем.</span><span class="sxs-lookup"><span data-stu-id="27d3d-162">This helps protect against phishing schemes.</span></span> <span data-ttu-id="27d3d-163">[Настройка политик безопасных ссылок на office 365 ATP](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) или [Настройка политик безОпасных ссылок на Office 365 для ATP](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span><span class="sxs-lookup"><span data-stu-id="27d3d-163">[Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="27d3d-164">Вы можете сохранить все содержимое почтового ящика, включая удаленные элементы, поместив весь почтовый ящик пользователя на **удержание**для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="27d3d-164">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**.</span></span> <span data-ttu-id="27d3d-165">Инструкции см.</span><span class="sxs-lookup"><span data-stu-id="27d3d-165">For instructions, see</span></span> 
- <span data-ttu-id="27d3d-166">[Настройка хранения электронной почты с помощью архивации на базе Exchange Online](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span><span class="sxs-lookup"><span data-stu-id="27d3d-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="27d3d-167">Настройка настраиваемых **политик хранения**, например, для сохранения определенного периода времени или окончательного удаления контента в конце периода хранения.</span><span class="sxs-lookup"><span data-stu-id="27d3d-167">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="27d3d-168">Вы можете включить специальные политики хранения в центре ценных бумаг и соответствия требованиям, перейдите к разделу **Хранение** **данных управления данными** \> , а затем следуйте указаниям мастера.</span><span class="sxs-lookup"><span data-stu-id="27d3d-168">You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard.</span></span> <span data-ttu-id="27d3d-169">Чтобы узнать больше, ознакомьтесь [со статьЕй Обзор политик хранения](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="27d3d-169">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="27d3d-170">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="27d3d-170">Next steps</span></span>

<span data-ttu-id="27d3d-171">Для пользователей, у которых есть лицензии, следующий этап заключается в настройке устройств.</span><span class="sxs-lookup"><span data-stu-id="27d3d-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="27d3d-172">Ознакомьтесь со статьями [Настройка устройств с Windows для пользователей Microsoft 365 Business](set-up-windows-devices.md) и [Настройка мобильных устройств для пользователей Microsoft 365 Business](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="27d3d-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="27d3d-173">Ссылки на статьи, посвященные настройте устройств и политик защиты приложений, а также удалению данных с пользовательских устройств приведены в статье [Управление Microsoft 365 Business](manage.md).</span><span class="sxs-lookup"><span data-stu-id="27d3d-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


