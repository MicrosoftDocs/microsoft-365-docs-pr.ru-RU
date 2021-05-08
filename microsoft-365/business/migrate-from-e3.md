---
title: Миграция в Microsoft 365 бизнес из Office 365 E3
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Узнайте, как переместить бизнес в Microsoft 365 бизнес премиум из Office 365 E3.
ms.openlocfilehash: f08b054473fdd63ec2372e81c776a1b64f89fe9d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244843"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="e1cea-103">Перенос из Office 365 E3 в Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="e1cea-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span>

<span data-ttu-id="e1cea-104">Microsoft 365 бизнес премиум имеет все необходимое для вашего малого бизнеса, сочетая лучшие в своем классе приложения с облачной производительностью с простым управлением устройствами и безопасностью.</span><span class="sxs-lookup"><span data-stu-id="e1cea-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="e1cea-105">Если у вас в настоящее время Office 365 подписка на E3, но не более 300 сотрудников, рассмотрите возможность Microsoft 365 бизнес премиум дополнительных функций безопасности.</span><span class="sxs-lookup"><span data-stu-id="e1cea-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="e1cea-106">Миграция проста: сначала переключаются лицензии, и все данные и сведения о пользователях в текущей подписке сохраняются.</span><span class="sxs-lookup"><span data-stu-id="e1cea-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="e1cea-107">После переноса необходимо настроить функции, добавленные в Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="e1cea-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="e1cea-108">Различия между Office 365 E3 и Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="e1cea-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="e1cea-109">В этой таблице показаны различия между Microsoft 365 бизнес премиум и Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="e1cea-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="e1cea-110">Функция</span><span class="sxs-lookup"><span data-stu-id="e1cea-110">Feature</span></span>    | <span data-ttu-id="e1cea-111">Поддержка в Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="e1cea-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="e1cea-112">Поддержка Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="e1cea-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="e1cea-113">**Локальная среда**</span><span class="sxs-lookup"><span data-stu-id="e1cea-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="e1cea-114">Office приложения<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e1cea-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="e1cea-115">Приложения Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e1cea-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="e1cea-116">Microsoft 365 корпоративные приложения</span><span class="sxs-lookup"><span data-stu-id="e1cea-116">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="e1cea-117">**Приложения облачной производительности**</span><span class="sxs-lookup"><span data-stu-id="e1cea-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="e1cea-118">Exchange Online и Outlook</span><span class="sxs-lookup"><span data-stu-id="e1cea-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="e1cea-119">Ограничение хранения 50 ГБ на почтовый ящик и неограниченное Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="e1cea-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="e1cea-120">Ограничение хранения 100 ГБ на почтовый ящик и неограниченное Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="e1cea-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="e1cea-121">Teams</span><span class="sxs-lookup"><span data-stu-id="e1cea-121">Teams</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e1cea-124">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e1cea-124">OneDrive for Business</span></span>    | <span data-ttu-id="e1cea-125">Ограничение хранения 1 ТБ на пользователя</span><span class="sxs-lookup"><span data-stu-id="e1cea-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="e1cea-126">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="e1cea-126">Unlimited</span></span> | 
| <span data-ttu-id="e1cea-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="e1cea-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e1cea-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="e1cea-130">StaffHub</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e1cea-133">MileIQ</span><span class="sxs-lookup"><span data-stu-id="e1cea-133">MileIQ</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | | 
| <span data-ttu-id="e1cea-135">**Защита от угроз**</span><span class="sxs-lookup"><span data-stu-id="e1cea-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="e1cea-136">Defender для Office 365 (план 1)</span><span class="sxs-lookup"><span data-stu-id="e1cea-136">Defender for Office 365 Plan 1</span></span> | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | <span data-ttu-id="e1cea-138">Не включено, но может быть добавлено в</span><span class="sxs-lookup"><span data-stu-id="e1cea-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="e1cea-139">**управление удостоверениями;**</span><span class="sxs-lookup"><span data-stu-id="e1cea-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="e1cea-140">Сброс пароля самообслуживления для гибридных учетных записей Azure Active Directory (Azure AD), многофакторной проверки подлинности Azure AD (MFA), условного доступа, списания паролей для идентификаторов локального доступа</span><span class="sxs-lookup"><span data-stu-id="e1cea-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    |  | 
| <span data-ttu-id="e1cea-142">**Управление устройствами и приложениями**</span><span class="sxs-lookup"><span data-stu-id="e1cea-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="e1cea-143">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="e1cea-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    |  |
| <span data-ttu-id="e1cea-145">Активация совместно используемого компьютера</span><span class="sxs-lookup"><span data-stu-id="e1cea-145">Shared computer activation</span></span>|     ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="e1cea-148">Обновление прав на Windows 10 Pro из лицензий Win 7/8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="e1cea-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    || 
| <span data-ttu-id="e1cea-150">**Защита информации**</span><span class="sxs-lookup"><span data-stu-id="e1cea-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="e1cea-151">Защита от потери данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="e1cea-151">Office 365 Data Loss Prevention</span></span>|    ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)|![Включено в Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="e1cea-154">План 1, BitLocker Azure</span><span class="sxs-lookup"><span data-stu-id="e1cea-154">Azure Information Protection Plan 1, BitLocker enforcement</span></span>|![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)||
|<span data-ttu-id="e1cea-156">План защиты информации Azure 1, метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="e1cea-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)||
|<span data-ttu-id="e1cea-158">**Лицензия клиентского доступа (права CAL)**</span><span class="sxs-lookup"><span data-stu-id="e1cea-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="e1cea-159">Enterprise Cal Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="e1cea-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Включено в Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="e1cea-161"><sup>1</sup> Microsoft 365 бизнес премиум версии Office не включает активацию тома с помощью групповой политики, телеметрии приложений, элементов управления обновлениями, сравнения электронных таблиц и запросов или бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="e1cea-161"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="e1cea-162">Миграция</span><span class="sxs-lookup"><span data-stu-id="e1cea-162">Migration</span></span>

<span data-ttu-id="e1cea-163">Чтобы перенести подписку, см. в инструкциях [Поменяйте](../commerce/subscriptions/change-plans-manually.md) планы вручную, если вы хотите переместить несколько Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="e1cea-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="e1cea-164">Вы также можете [обновить](../commerce/subscriptions/upgrade-to-different-plan.md)всех автоматически или работать с партнером, чтобы переместить подписку на E3 и лицензии на Microsoft 365 бизнес премиум подписку.</span><span class="sxs-lookup"><span data-stu-id="e1cea-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="e1cea-165">В следующих разделах описываются изменения, которые необходимо внести, если таковые есть, и то, что можно сделать после миграции.</span><span class="sxs-lookup"><span data-stu-id="e1cea-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="e1cea-166">Office 365 Конфигурация и данные подписки на E3</span><span class="sxs-lookup"><span data-stu-id="e1cea-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="e1cea-167">Вам не нужно вносить изменения в текущую подписку или данные перед миграцией, включающие:</span><span class="sxs-lookup"><span data-stu-id="e1cea-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="e1cea-168">Конфигурация подписки, например записи DNS и доменные имена.</span><span class="sxs-lookup"><span data-stu-id="e1cea-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="e1cea-169">Учетные записи пользователей и групп и параметры проверки подлинности, такие как многофакторная проверка подлинности или политики условного доступа.</span><span class="sxs-lookup"><span data-stu-id="e1cea-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="e1cea-170">Конфигурации служб производительности и их данные, такие как Teams, Exchange Online почтовые ящики, сайты SharePoint Online, OneDrive для бизнеса папок и OneNote блокноты.</span><span class="sxs-lookup"><span data-stu-id="e1cea-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="e1cea-171">Office приложения будут масштабироваться автоматически.</span><span class="sxs-lookup"><span data-stu-id="e1cea-171">Office applications will scale automatically.</span></span> <span data-ttu-id="e1cea-172">Office 365 лицензирование проверяет назначение лицензии пользователя каждые 72 часа и преобразует Office приложения в версию, которая соответствует подписке пользователя.</span><span class="sxs-lookup"><span data-stu-id="e1cea-172">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="e1cea-173">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e1cea-173">Windows 10</span></span>

<span data-ttu-id="e1cea-174">Если ваши Windows еще не Windows Pro обновления Создателя, обновите их до [Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="e1cea-174">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="e1cea-175">Настройка политик для защиты пользовательских устройств и файлов</span><span class="sxs-lookup"><span data-stu-id="e1cea-175">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="e1cea-176">Если вы Office 365 политики и устройства MDM, эти устройства будут перечислены на странице **Устройства** в центре администрирования Microsoft 365 администратора.</span><span class="sxs-lookup"><span data-stu-id="e1cea-176">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e1cea-177">Все политики, которые вы создали, будут показываться в списке классических политик на портале [Intune.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)</span><span class="sxs-lookup"><span data-stu-id="e1cea-177">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="e1cea-178">После присвоения лицензий Microsoft 365 бизнес премиум вы можете начать защищать устройства и файлы пользователей.</span><span class="sxs-lookup"><span data-stu-id="e1cea-178">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="e1cea-179">Если вы обновили все Microsoft 365 бизнес премиум организации, вы увидите мастера настройки на домашней странице [](set-up.md) и сможете следовать за настройками Microsoft 365 бизнес премиум в действиях мастера установки для защиты файлов и мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="e1cea-179">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="e1cea-180">Вы также можете выполнить эти действия на странице Устройства:</span><span class="sxs-lookup"><span data-stu-id="e1cea-180">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="e1cea-181">В центре администрирования в левом nav перейдите к **политикам устройств.** \> </span><span class="sxs-lookup"><span data-stu-id="e1cea-181">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="e1cea-182">На странице **Политики устройства** выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e1cea-182">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="e1cea-183">В области **Добавить политику** удайте политику имя, а затем выберите тип **политики** из отсея.</span><span class="sxs-lookup"><span data-stu-id="e1cea-183">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="e1cea-184">Можно настроить политики приложений для защиты файлов на устройствах Android и iPhone, а также Windows 10, а также настроить политики конфигурации устройств для устройств, Windows 10 устройств.</span><span class="sxs-lookup"><span data-stu-id="e1cea-184">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="e1cea-185">Подробные сведения см. в следующих ссылках:</span><span class="sxs-lookup"><span data-stu-id="e1cea-185">See the following links for details:</span></span>
    
  - [<span data-ttu-id="e1cea-186">Настройка параметров защиты приложений для устройств с Android и iOS</span><span class="sxs-lookup"><span data-stu-id="e1cea-186">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="e1cea-187">Настройка параметров защиты приложений для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="e1cea-187">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="e1cea-188">Установите параметры защиты устройств для Windows 10 ПК</span><span class="sxs-lookup"><span data-stu-id="e1cea-188">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="e1cea-189">После того как вы настроите политики, вы и ваши сотрудники сможете настроить устройства:</span><span class="sxs-lookup"><span data-stu-id="e1cea-189">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="e1cea-190">См. [в Windows устройств для Microsoft 365 бизнес премиум для](set-up-windows-devices.md) действий для Windows устройств.</span><span class="sxs-lookup"><span data-stu-id="e1cea-190">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="e1cea-191">Настройка [мобильных устройств для Microsoft 365 бизнес премиум для](set-up-mobile-devices.md) действий для android-телефонов и iPhone.</span><span class="sxs-lookup"><span data-stu-id="e1cea-191">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="e1cea-192">Размер почтового ящика</span><span class="sxs-lookup"><span data-stu-id="e1cea-192">Mailbox Size</span></span>

<span data-ttu-id="e1cea-193">Microsoft 365 бизнес премиум имеет ограничение хранилища в 50 ГБ, так как Exchange Online 1.</span><span class="sxs-lookup"><span data-stu-id="e1cea-193">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="e1cea-194">При переносе в Microsoft 365 бизнес премиум, если объем хранилища почтовых ящиков превышает 50 ГБ, рекомендуется назначить этому пользователю Exchange Online Plan 2 и удалить Exchange Online Plan 1, так как назначение обоих нецелесообразны.</span><span class="sxs-lookup"><span data-stu-id="e1cea-194">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>


### <a name="threat-protection"></a><span data-ttu-id="e1cea-195">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="e1cea-195">Threat protection</span></span>

<span data-ttu-id="e1cea-196">После переноса в Microsoft 365 бизнес премиум у вас есть Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="e1cea-196">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="e1cea-197">Обзор [см. в Office 365](../security/office-365-security/defender-for-office-365.md) Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e1cea-197">See [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for an overview.</span></span> <span data-ttu-id="e1cea-198">Чтобы настроить, см. в Сейф [ссылки,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa) [Сейф](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)вложения и настройка защиты от фишинга в [Defender для Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="e1cea-198">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="e1cea-199">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="e1cea-199">Sensitivity labels</span></span>

<span data-ttu-id="e1cea-200">Чтобы начать использовать метки чувствительности, [см.](../compliance/sensitivity-labels.md) обзор меток чувствительности и создание и управление видео [меток чувствительности.](../business-video/create-sensitivity-labels.md)</span><span class="sxs-lookup"><span data-stu-id="e1cea-200">To start using sensitivity labels, see [Overview of sensitivity labels](../compliance/sensitivity-labels.md) and [create and manage sensitivity labels](../business-video/create-sensitivity-labels.md) video.</span></span>
