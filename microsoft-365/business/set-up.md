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
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Узнайте, как настроить Microsoft 365 для бизнеса, выполнив четыре действия.
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870445"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="1147e-103">Настройка Microsoft 365 Business с помощью мастера настройки</span><span class="sxs-lookup"><span data-stu-id="1147e-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="1147e-104">Выполните шаги 1 – 4 ниже.</span><span class="sxs-lookup"><span data-stu-id="1147e-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="1147e-105">Настройка Microsoft 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="1147e-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="1147e-106">Посмотрите видеоролик о том, как настроить Microsoft 365 Business, когда у вас нет локальной Active Directory:</span><span class="sxs-lookup"><span data-stu-id="1147e-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="1147e-p101">Этапы настройки включают сведения для настройки параметров, включая локального Active Directory. Если вы хотите получить доступ к домену устройств, ознакомьтесь со следующими статьями для двух различных способом и выполните действия, прежде чем запускать мастер установки:</span><span class="sxs-lookup"><span data-stu-id="1147e-p101">The set-up steps include information for setups that include local Active Directory. If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="1147e-109">Включение присоединенный к домену устройств Windows 10 для управления Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1147e-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="1147e-110">— Это рекомендуемый способ.</span><span class="sxs-lookup"><span data-stu-id="1147e-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="1147e-111">Доступ к локальным ресурсам с Azure присоединился к AD устройства в Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="1147e-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="1147e-112">Этап 1: Настройка входа</span><span class="sxs-lookup"><span data-stu-id="1147e-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="1147e-p102">Войдите в [Microsoft 365 Business](https://portal.microsoft.com) с учетными данными глобального администратора. Щелкните плитку **Администратор**, чтобы перейти в Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="1147e-p102">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="1147e-115">В центре администрирования нажмите кнопку **начать установку** (в зависимости от состояния системы вместо нее может отображаться кнопка **Продолжить установку**), чтобы запустить мастер.</span><span class="sxs-lookup"><span data-stu-id="1147e-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="1147e-116">Введите имя домена, который вы хотите использовать (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="1147e-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="1147e-p103">Пойти дальше и введите ваш домен, даже в том случае, если проверки во время использования Azure AD "Подключение", например. Следующие два действия не применяются к вам при использовании подключить Azure AD и проверки домена.</span><span class="sxs-lookup"><span data-stu-id="1147e-p103">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example. The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="1147e-119">Следуйте инструкциям мастера в [статье Создание записей DNS на любой поставщика услуг размещения DNS для Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) , который подтверждает, что этот домен принадлежит вам.</span><span class="sxs-lookup"><span data-stu-id="1147e-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="1147e-p104">Можно просмотреть пример видеоролик о [видео: Настройка Office 365 в центре администрирования нового](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Обратите внимание, что в этом видео не включает действия защиты данных из Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1147e-p104">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="1147e-123">Шаг 2: Добавление пользователей и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="1147e-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="1147e-124">Вы можете добавить пользователей здесь или [позднее](add-users-m365b.md) в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="1147e-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="1147e-125">Всем добавляемым пользователям автоматически назначается лицензия Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="1147e-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="1147e-p105">Если в вашей подписке на Office 365 бизнес уже есть пользователи (например, если вы использовали Azure AD Connect), вы сможете сейчас назначить им лицензии. Добавьте лицензии и для них.</span><span class="sxs-lookup"><span data-stu-id="1147e-p105">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="1147e-p106">У вас также будет возможность передать учетные данные добавленным пользователям. Вы можете распечатать их, отправить по электронной почте или скачать.</span><span class="sxs-lookup"><span data-stu-id="1147e-p106">You will also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="1147e-130">Пропустите перенос сообщений электронной почты и нажмите кнопку **Далее** на странице **Перенос сообщений электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="1147e-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="1147e-131">Если осуществляется переход от другой поставщик электронной почты и для копирования данных более поздней версии, можно [миграции электронной почты и контактов в Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="1147e-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="1147e-133">Шаг 3: Подключения вашего домена</span><span class="sxs-lookup"><span data-stu-id="1147e-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="1147e-134">Если вы решили использовать .onmicrosoft домена или используется подключение Azure AD, этот шаг не появится.</span><span class="sxs-lookup"><span data-stu-id="1147e-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="1147e-135">Для настройки служб вам необходимо обновить некоторые записи узла DNS или регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="1147e-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="1147e-p107">Мастер установки обычно определяет регистратор и предоставляет ссылки на пошаговые инструкции для обновления своих записей NS на веб-сайте регистратора. Если это не так, [nameservers изменений для настройки Office 365 с помощью любого регистратора доменных имен](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="1147e-p107">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website. If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="1147e-138">Для вас будут настроены электронная почта и другие службы.</span><span class="sxs-lookup"><span data-stu-id="1147e-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="1147e-139">Шаг 4: Управление устройствами и рабочие файлы</span><span class="sxs-lookup"><span data-stu-id="1147e-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="1147e-p108">**Защита рабочих файлов на мобильных устройствах** страницы значение **защитить рабочих файлов при кражи или потери устройства** и параметры **управления доступа пользователей к файлов Office на мобильных устройствах** **на**. Вы также можете открыть вложенных задавая, нажав кнопку угловые скобки рядом с каждого из параметров.</span><span class="sxs-lookup"><span data-stu-id="1147e-p108">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**. You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="1147e-142">Все файлы рабочих лицензированных пользователей теперь защищены от операций ввода-вывода и устройствами Android, как только они [устанавливать приложения Office](set-up-mobile-devices.md) (и проверки подлинности с помощью их учетных данных в Microsoft 365 Business).</span><span class="sxs-lookup"><span data-stu-id="1147e-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="1147e-144">На странице **Конфигурация устройства задайте 10 Windows** задайте для параметра **Безопасного устройств Windows 10** значение **на**.</span><span class="sxs-lookup"><span data-stu-id="1147e-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="1147e-145">Можно также получить доступ всех вложенных параметру, щелкнув значок рядом с ним.</span><span class="sxs-lookup"><span data-stu-id="1147e-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="1147e-p109">Задайте для параметра **Установки Office на устройствах Windows 10** значение **Да,** Если все пользователи имеют компьютеров Windows 10 и устанавливает нет существующих Office или click-to-run установок Office. Если это не так, присвойте этому параметру значение **Нет**. Можно [автоматически установить Office](auto-install-or-uninstall-office.md) позднее в центре администрирования после завершения разработки компьютерах пользователей. Сведения содержатся в разделе [Подготовка к установке клиента Office](prepare-for-office-client-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="1147e-p109">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs. If this is not the case, set this option to **No**. You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers. For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="1147e-150">Файлы рабочих лицензированным пользователям на устройствах Windows 10 будет отображаться как только они [присоединиться к свои устройства Windows 10](set-up-windows-devices.md) для домена Microsoft 365 Business Azure AD или [установить 10 Windows на новом компьютере](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) одновременно присоединение Microsoft 365 Бизнес-среде Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1147e-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="1147e-151">Нажмите кнопку **Далее** и все готово к установке.</span><span class="sxs-lookup"><span data-stu-id="1147e-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="1147e-152">Оставьте нам свои отзывы и предложения на этом этапе нам для улучшения качества.</span><span class="sxs-lookup"><span data-stu-id="1147e-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="1147e-154">Дополнительные параметры безопасности</span><span class="sxs-lookup"><span data-stu-id="1147e-154">Additional security settings</span></span>

<span data-ttu-id="1147e-155">В дополнение к безопасности и соответствия требованиям установки в мастере установки можно настроить дополнительные параметры перечислены ниже:</span><span class="sxs-lookup"><span data-stu-id="1147e-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="1147e-p110">Настройка защиты от потенциально опасных вложений. **Дополнительные защиту от угроз** (ATP) идентифицирует вредоносного содержимого и затем блокирует доставки небезопасных вложений защита от фишинга и ransomware вирусов. Защита вложений, см [политиках Office 365 ATP безопасные вложения](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span><span class="sxs-lookup"><span data-stu-id="1147e-p110">Set up protection against unsafe attachments. **Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections. To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="1147e-p111">Когда пользователи щелкают вредоносных ссылки защиты среды. В то время, пользователь щелкает их ATP проверяет ссылки по электронной почте. Если ссылка небезопасные, пользователь предупреждение о том, чтобы не посетите веб-сайт или проинформированы о том, что сайт был заблокирован. Это обеспечивает защиту от фишинга. [Настройка политик Office 365 ATP безопасных ссылки](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) или [Настройка политики Office 365 ATP безопасных ссылки](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span><span class="sxs-lookup"><span data-stu-id="1147e-p111">Protect your environment when users click malicious links. ATP examines links in email at the time a user clicks them. If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked. This helps protect against phishing schemes. [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="1147e-p112">Позволяет сохранить все содержимое почтового ящика, включая удаленных элементов, поместив ко всему почтовому ящику пользователя на **хранение для судебного удержания**. Дополнительные сведения см.</span><span class="sxs-lookup"><span data-stu-id="1147e-p112">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**. For instructions, see</span></span> 
- <span data-ttu-id="1147e-166">[Настройка хранения электронной почты с помощью архивации Exchange Online](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span><span class="sxs-lookup"><span data-stu-id="1147e-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="1147e-p113">Например, Настройка настраиваемой **политики хранения**, сохранены на определенное время или окончательно удалить контент в конце периода хранения. Можно включить политики хранения настраиваемых в центре соответствия требованиям, последовательно выберите пункты **управления данными** и по ценным бумагам \> **хранения**, а затем следуйте инструкциям мастера. Для получения дополнительных сведений см [политики хранения](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="1147e-p113">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period. You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard. To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="1147e-170">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="1147e-170">Next steps</span></span>

<span data-ttu-id="1147e-171">Для пользователей, у которых есть лицензии, следующий этап заключается в настройке устройств.</span><span class="sxs-lookup"><span data-stu-id="1147e-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="1147e-172">Ознакомьтесь со статьями [Настройка устройств с Windows для пользователей Microsoft 365 Business](set-up-windows-devices.md) и [Настройка мобильных устройств для пользователей Microsoft 365 Business](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="1147e-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="1147e-173">Ссылки на статьи, посвященные настройте устройств и политик защиты приложений, а также удалению данных с пользовательских устройств приведены в статье [Управление Microsoft 365 Business](manage.md).</span><span class="sxs-lookup"><span data-stu-id="1147e-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


