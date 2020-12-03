---
title: Переход на Microsoft 365 Business из Office 365 E3
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Узнайте, как перенести бизнес в Microsoft 365 бизнес премиум из Office 365 E3.
ms.openlocfilehash: eebf78c24ed4bfd1a4fc2d843f37aebbe3d35e31
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558265"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="4e299-103">Переход с Office 365 E3 на Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="4e299-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span> 

<span data-ttu-id="4e299-104">Microsoft 365 Business Premium содержит все необходимое для малого бизнеса, объединяя высококачественные облачные приложения для повышения производительности с простым управлением устройствами и безопасностью.</span><span class="sxs-lookup"><span data-stu-id="4e299-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="4e299-105">Если у вас уже есть подписка на Office 365 E3, но не более 300 сотрудников, попробуйте перейти на Microsoft 365 Business Premium для получения дополнительных функций безопасности.</span><span class="sxs-lookup"><span data-stu-id="4e299-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="4e299-106">Миграция проста: сначала можно сменить лицензии и все данные, а также сведения о пользователях в текущей подписке.</span><span class="sxs-lookup"><span data-stu-id="4e299-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="4e299-107">После миграции вам потребуется настроить компоненты, добавленные в Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="4e299-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="4e299-108">Различия между Office 365 E3 и Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="4e299-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="4e299-109">В этой таблице показаны различия между Microsoft 365 Business Premium и Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="4e299-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="4e299-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="4e299-110">Feature</span></span>    | <span data-ttu-id="4e299-111">Поддержка в Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="4e299-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="4e299-112">Поддержка в Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="4e299-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="4e299-113">**Локальная среда**</span><span class="sxs-lookup"><span data-stu-id="4e299-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="4e299-114">Приложения Office<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4e299-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="4e299-115">Приложения Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4e299-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="4e299-116">Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="4e299-116">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="4e299-117">**Облачные приложения для работы**</span><span class="sxs-lookup"><span data-stu-id="4e299-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="4e299-118">Exchange Online и Outlook</span><span class="sxs-lookup"><span data-stu-id="4e299-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="4e299-119">50 ГБ дискового пространства для почтового ящика и неограниченная Архивация на базе Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4e299-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="4e299-120">100 ГБ дискового пространства для почтового ящика и неограниченная Архивация на базе Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4e299-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="4e299-121">Teams</span><span class="sxs-lookup"><span data-stu-id="4e299-121">Teams</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Входит в состав Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4e299-124">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4e299-124">OneDrive for Business</span></span>    | <span data-ttu-id="4e299-125">ограничения на размер хранилища на одного пользователя (1 ТБ)</span><span class="sxs-lookup"><span data-stu-id="4e299-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="4e299-126">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="4e299-126">Unlimited</span></span> | 
| <span data-ttu-id="4e299-127">Yammer, SharePoint Online, планировщик, поток</span><span class="sxs-lookup"><span data-stu-id="4e299-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Входит в состав Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4e299-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="4e299-130">StaffHub</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Входит в состав Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4e299-133">Диспетчер клиентов Outlook, Милеик</span><span class="sxs-lookup"><span data-stu-id="4e299-133">Outlook Customer Manager, MileIQ</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | | 
| <span data-ttu-id="4e299-135">**Защита от угроз**</span><span class="sxs-lookup"><span data-stu-id="4e299-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="4e299-136">Защитник для Office 365, план 1</span><span class="sxs-lookup"><span data-stu-id="4e299-136">Defender for Office 365 Plan 1</span></span> | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | <span data-ttu-id="4e299-138">Не включено, но его можно добавить на</span><span class="sxs-lookup"><span data-stu-id="4e299-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="4e299-139">**управление удостоверениями;**</span><span class="sxs-lookup"><span data-stu-id="4e299-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="4e299-140">Самостоятельный сброс паролей для гибридных учетных записей Azure Active Directory (Azure AD), Multi-Factor Authentication (MFA) Azure AD (MFA), условный доступ, обратная запись пароля для локальных удостоверений</span><span class="sxs-lookup"><span data-stu-id="4e299-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    |  | 
| <span data-ttu-id="4e299-142">**Управление устройствами и приложениями**</span><span class="sxs-lookup"><span data-stu-id="4e299-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="4e299-143">Microsoft Intune, Windows для автопилота</span><span class="sxs-lookup"><span data-stu-id="4e299-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    |  |
| <span data-ttu-id="4e299-145">Активация совместно используемого компьютера</span><span class="sxs-lookup"><span data-stu-id="4e299-145">Shared computer activation</span></span>|     ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Входит в состав Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="4e299-148">Права на обновление до Windows 10 Pro из лицензий Win 7/8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="4e299-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    || 
| <span data-ttu-id="4e299-150">**Защита информации**</span><span class="sxs-lookup"><span data-stu-id="4e299-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="4e299-151">Защита от потери данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="4e299-151">Office 365 Data Loss Prevention</span></span>|    ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)|![Входит в состав Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="4e299-154">Azure Information Protection (план 1), принудительное применение BitLocker</span><span class="sxs-lookup"><span data-stu-id="4e299-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)||
|<span data-ttu-id="4e299-156">Azure Information Protection (план 1), метки чувствительности</span><span class="sxs-lookup"><span data-stu-id="4e299-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)||
|<span data-ttu-id="4e299-158">**Лицензия клиентского доступа (права CAL)**</span><span class="sxs-lookup"><span data-stu-id="4e299-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="4e299-159">Набор корпоративных лицензий CAL (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="4e299-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Входит в состав Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="4e299-161"><sup>1</sup> в версии приложения Office для Microsoft 365 Business Premium не предусмотрена Активация корпоративных политик, телеметрии приложений, элементов управления обновления, сравнения и выполнения запросов, а также бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="4e299-161"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="4e299-162">Миграция</span><span class="sxs-lookup"><span data-stu-id="4e299-162">Migration</span></span>

<span data-ttu-id="4e299-163">Чтобы перенести свою подписку, ознакомьтесь с инструкциями в статье [Change Plans вручную](../commerce/subscriptions/change-plans-manually.md) , чтобы переместить всего нескольких пользователей в Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="4e299-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="4e299-164">Вы также можете [обновлять пользователей автоматически](../commerce/subscriptions/upgrade-to-different-plan.md)или работать с партнером, чтобы переместить подписку на E3 и лицензии на подписку Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="4e299-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="4e299-165">В следующих разделах описываются изменения, которые необходимо выполнить, если они есть, и действия, которые можно выполнить после миграции.</span><span class="sxs-lookup"><span data-stu-id="4e299-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="4e299-166">Конфигурация и данные подписки на Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="4e299-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="4e299-167">Вам не нужно вносить никаких изменений в текущую подписку или данные перед миграцией, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="4e299-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="4e299-168">Конфигурация подписки, например записи DNS и доменные имена.</span><span class="sxs-lookup"><span data-stu-id="4e299-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="4e299-169">Учетные записи пользователей и групп и параметры проверки подлинности, такие как многофакторная проверка подлинности или политики условного доступа.</span><span class="sxs-lookup"><span data-stu-id="4e299-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="4e299-170">Конфигурации служб производительности и их данные, такие как Teams, почтовые ящики Exchange Online, сайты SharePoint Online, папки OneDrive для бизнеса и записные книжки OneNote.</span><span class="sxs-lookup"><span data-stu-id="4e299-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="4e299-171">Приложения Office будут масштабироваться автоматически.</span><span class="sxs-lookup"><span data-stu-id="4e299-171">Office applications will scale automatically.</span></span> <span data-ttu-id="4e299-172">Современное лицензирование Office 365 будет проверять назначение лицензии пользователя каждые 72 часов и преобразовывать приложения Office в версию, которая соответствует подписке пользователя.</span><span class="sxs-lookup"><span data-stu-id="4e299-172">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="4e299-173">Windows 10</span><span class="sxs-lookup"><span data-stu-id="4e299-173">Windows 10</span></span>

<span data-ttu-id="4e299-174">Если Windows не находится в обновлении Windows Pro Creator, [обновите их до версии Windows Pro](upgrade-to-windows-pro-creators-update.md)Creators.</span><span class="sxs-lookup"><span data-stu-id="4e299-174">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="4e299-175">Настройка политик для защиты устройств и файлов пользователей</span><span class="sxs-lookup"><span data-stu-id="4e299-175">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="4e299-176">Если вы настроили политики и устройства для Office 365 MDM, эти устройства будут перечислены на странице " **устройства** " центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e299-176">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4e299-177">Все настроенные политики будут отображаться в списке классических политик на [портале Intune](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span><span class="sxs-lookup"><span data-stu-id="4e299-177">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="4e299-178">После назначения лицензий Microsoft 365 Business Premium можно приступить к защите устройств и файлов пользователей.</span><span class="sxs-lookup"><span data-stu-id="4e299-178">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="4e299-179">Если вы обновили всех пользователей в Организации до Microsoft 365 Business Premium, вы увидите мастер установки на домашней странице и можете выполнить настройку [Microsoft 365 бизнес премиум в мастере установки](set-up.md) , чтобы защитить файлы и мобильные устройства.</span><span class="sxs-lookup"><span data-stu-id="4e299-179">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="4e299-180">Вы также можете выполнить следующие действия на странице "устройства":</span><span class="sxs-lookup"><span data-stu-id="4e299-180">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="4e299-181">В левой панели навигации центра администрирования перейдите к разделу **Devices** \> **политики** устройств.</span><span class="sxs-lookup"><span data-stu-id="4e299-181">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="4e299-182">На странице " **политики устройств** " нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="4e299-182">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="4e299-183">В области **Добавить политику** укажите имя политики, а затем выберите **тип политики** из раскрывающегося меню.</span><span class="sxs-lookup"><span data-stu-id="4e299-183">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="4e299-184">Вы можете настроить политики приложений для защиты файлов на устройствах с Android и iPhone, а также в Windows 10, а также настроить политики конфигурации устройств для устройств с Windows 10, принадлежащих компании.</span><span class="sxs-lookup"><span data-stu-id="4e299-184">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="4e299-185">Для получения подробных сведений ознакомьтесь со следующими ссылками:</span><span class="sxs-lookup"><span data-stu-id="4e299-185">See the following links for details:</span></span>
    
  - [<span data-ttu-id="4e299-186">Настройка параметров защиты приложений для устройств с Android и iOS</span><span class="sxs-lookup"><span data-stu-id="4e299-186">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="4e299-187">Настройка параметров защиты приложений для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="4e299-187">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="4e299-188">Настройка параметров защиты устройств для компьютеров с Windows 10</span><span class="sxs-lookup"><span data-stu-id="4e299-188">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="4e299-189">После настройки политик вы и ваши сотрудники смогут настраивать устройства:</span><span class="sxs-lookup"><span data-stu-id="4e299-189">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="4e299-190">Пошаговые инструкции по [настройке устройств Windows для пользователей Microsoft 365 Business Premium](set-up-windows-devices.md) для устройств с Windows.</span><span class="sxs-lookup"><span data-stu-id="4e299-190">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="4e299-191">Выполните действия, описанные в статье [Настройка мобильных устройств для пользователей Microsoft 365 Business Premium](set-up-mobile-devices.md) для телефонов с Android и iPhone.</span><span class="sxs-lookup"><span data-stu-id="4e299-191">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="4e299-192">Размер почтового ящика</span><span class="sxs-lookup"><span data-stu-id="4e299-192">Mailbox Size</span></span>

<span data-ttu-id="4e299-193">Microsoft 365 Business Premium имеет ограничения на размер хранилища 50 ГБ по мере использования Exchange Online (план 1).</span><span class="sxs-lookup"><span data-stu-id="4e299-193">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="4e299-194">При переходе на Microsoft 365 бизнес премиум, если пользователь превышает 50 ГБ хранилища почтовых ящиков, рекомендуется назначить его пользователю Exchange Online (план 2) и удалить Exchange Online (план 1), так как его невозможно назначить обоим пользователям.</span><span class="sxs-lookup"><span data-stu-id="4e299-194">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>


### <a name="threat-protection"></a><span data-ttu-id="4e299-195">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="4e299-195">Threat protection</span></span>

<span data-ttu-id="4e299-196">После перехода на Microsoft 365 Business Premium вы защитник для Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e299-196">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="4e299-197">Общие сведения: [защитник Майкрософт для Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) .</span><span class="sxs-lookup"><span data-stu-id="4e299-197">See [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview.</span></span> <span data-ttu-id="4e299-198">Чтобы настроить, ознакомьтесь со статьей [Настройка безопасных ссылок](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [Настройка безопасных вложений](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)и [Настройка защиты от фишинга в защитнике для Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="4e299-198">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="4e299-199">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="4e299-199">Sensitivity labels</span></span>

<span data-ttu-id="4e299-200">Чтобы приступить к использованию меток конфиденциальности, ознакомьтесь со статьей [Обзор меток конфиденциальности](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) , а затем [Создайте видео метки конфиденциальности и управляйте ими](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) .</span><span class="sxs-lookup"><span data-stu-id="4e299-200">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
