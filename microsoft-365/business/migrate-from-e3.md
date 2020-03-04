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
search.appverid:
- BCS160
- MET150
description: Узнайте, как перенести бизнес в Microsoft 365 Business из Office 365 E3.
ms.openlocfilehash: b86a163792aa71f0bca115ab918e0800acc0427d
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "42409684"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a><span data-ttu-id="cc5c2-103">Переход с Office 365 E3 на Microsoft 365 Бизнес</span><span class="sxs-lookup"><span data-stu-id="cc5c2-103">Migrating from Office 365 E3 to Microsoft 365 Business</span></span> 

<span data-ttu-id="cc5c2-104">Microsoft 365 Business имеет все необходимое для малого бизнеса, объединяя лучшие облачные приложения для продуктивной работы с использованием простого управления устройствами и обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="cc5c2-105">Если у вас уже есть подписка на Office 365 E3, но не более 300 сотрудников, попробуйте перейти на Microsoft 365 Business для получения дополнительных функций безопасности.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business for added security features.</span></span>

<span data-ttu-id="cc5c2-106">Миграция проста: сначала можно сменить лицензии и все данные, а также сведения о пользователях в текущей подписке.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="cc5c2-107">После миграции вам потребуется настроить компоненты, добавленные в Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a><span data-ttu-id="cc5c2-108">Различия между Office 365 E3 и Microsoft 365 Бизнес</span><span class="sxs-lookup"><span data-stu-id="cc5c2-108">Differences between Office 365 E3 and Microsoft 365 Business</span></span>

<span data-ttu-id="cc5c2-109">В этой таблице показаны различия между Microsoft 365 Business и Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-109">This table shows the differences between Microsoft 365 Business and Office 365 E3.</span></span>

| <span data-ttu-id="cc5c2-110">Функция</span><span class="sxs-lookup"><span data-stu-id="cc5c2-110">Feature</span></span>    | <span data-ttu-id="cc5c2-111">Поддержка в Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="cc5c2-111">Support in Microsoft 365 Business</span></span>    | <span data-ttu-id="cc5c2-112">Поддержка в Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="cc5c2-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="cc5c2-113">**Локальная среда**</span><span class="sxs-lookup"><span data-stu-id="cc5c2-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="cc5c2-114">Приложения Office<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cc5c2-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="cc5c2-115">Office 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="cc5c2-115">Office 365 Business</span></span>    | <span data-ttu-id="cc5c2-116">Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="cc5c2-116">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="cc5c2-117">**Облачные приложения для работы**</span><span class="sxs-lookup"><span data-stu-id="cc5c2-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="cc5c2-118">Exchange Online и Outlook</span><span class="sxs-lookup"><span data-stu-id="cc5c2-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="cc5c2-119">50 ГБ дискового пространства для почтового ящика и неограниченная Архивация на базе Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cc5c2-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="cc5c2-120">100 ГБ дискового пространства для почтового ящика и неограниченная Архивация на базе Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cc5c2-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="cc5c2-121">Teams</span><span class="sxs-lookup"><span data-stu-id="cc5c2-121">Teams</span></span>    | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | ![Входит в состав Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="cc5c2-124">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cc5c2-124">OneDrive for Business</span></span>    | <span data-ttu-id="cc5c2-125">ограничения на размер хранилища на одного пользователя (1 ТБ)</span><span class="sxs-lookup"><span data-stu-id="cc5c2-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="cc5c2-126">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="cc5c2-126">Unlimited</span></span> | 
| <span data-ttu-id="cc5c2-127">Yammer, SharePoint Online, планировщик, поток</span><span class="sxs-lookup"><span data-stu-id="cc5c2-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | ![Входит в состав Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="cc5c2-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="cc5c2-130">StaffHub</span></span>    | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | ![Входит в состав Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="cc5c2-133">Диспетчер клиентов Outlook, Милеик</span><span class="sxs-lookup"><span data-stu-id="cc5c2-133">Outlook Customer Manager, MileIQ</span></span>    | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | | 
| <span data-ttu-id="cc5c2-135">**Защита от угроз**</span><span class="sxs-lookup"><span data-stu-id="cc5c2-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="cc5c2-136">Office 365 Advanced Threat protection (ATP), план 1</span><span class="sxs-lookup"><span data-stu-id="cc5c2-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | <span data-ttu-id="cc5c2-138">Не включено, но его можно добавить на</span><span class="sxs-lookup"><span data-stu-id="cc5c2-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="cc5c2-139">**управление удостоверениями;**</span><span class="sxs-lookup"><span data-stu-id="cc5c2-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="cc5c2-140">Самостоятельный сброс паролей для гибридных учетных записей Azure Active Directory (Azure AD), служба Azure Multi-Factor Authentication (MFA), условный доступ, обратная запись пароля для локальных удостоверений</span><span class="sxs-lookup"><span data-stu-id="cc5c2-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    |  | 
| <span data-ttu-id="cc5c2-142">**Управление устройствами и приложениями**</span><span class="sxs-lookup"><span data-stu-id="cc5c2-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="cc5c2-143">Microsoft Intune, Windows для автопилота</span><span class="sxs-lookup"><span data-stu-id="cc5c2-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    |  |
| <span data-ttu-id="cc5c2-145">Активация совместно используемого компьютера</span><span class="sxs-lookup"><span data-stu-id="cc5c2-145">Shared computer activation</span></span>|     ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | ![Входит в состав Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="cc5c2-148">Права на обновление до Windows 10 Pro из лицензий Win 7/8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="cc5c2-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    || 
| <span data-ttu-id="cc5c2-150">**Защита информации**</span><span class="sxs-lookup"><span data-stu-id="cc5c2-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="cc5c2-151">Защита от потери данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="cc5c2-151">Office 365 Data Loss Prevention</span></span>|    ![Входит в состав Microsoft 365 Business](../media/check-mark.png)|![Входит в состав Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="cc5c2-154">Azure Information Protection (план 1), принудительное применение BitLocker</span><span class="sxs-lookup"><span data-stu-id="cc5c2-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Входит в состав Microsoft 365 Business](../media/check-mark.png)||
|<span data-ttu-id="cc5c2-156">Azure Information Protection (план 1), метки чувствительности</span><span class="sxs-lookup"><span data-stu-id="cc5c2-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Входит в состав Microsoft 365 Business](../media/check-mark.png)||
|<span data-ttu-id="cc5c2-158">**Лицензия клиентского доступа (права CAL)**</span><span class="sxs-lookup"><span data-stu-id="cc5c2-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="cc5c2-159">Набор корпоративных лицензий CAL (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="cc5c2-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Входит в состав Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="cc5c2-161"><sup>1</sup> в microsoft Office 365 бизнес версия приложений Office не включает активацию корпоративных лицензий с помощью групповой политики, телеметрии приложений, элементов управления обновления, сравнения и выполнения запросов, а также бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-161"><sup>1</sup> The Microsoft 365 Business version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="cc5c2-162">Миграция</span><span class="sxs-lookup"><span data-stu-id="cc5c2-162">Migration</span></span>

<span data-ttu-id="cc5c2-163">Чтобы перенести свою подписку, ознакомьтесь с инструкциями в статье [Change Plans вручную](../commerce/subscriptions/change-plans-manually.md) , чтобы переместить всего нескольких пользователей в Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business.</span></span> <span data-ttu-id="cc5c2-164">Вы также можете [обновлять пользователей автоматически](../commerce/subscriptions/upgrade-to-different-plan.md)или работать с партнером, чтобы перенести подписку на E3 и лицензии на Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business subscription.</span></span>
<span data-ttu-id="cc5c2-165">В следующих разделах описываются изменения, которые необходимо выполнить, если они есть, и действия, которые можно выполнить после миграции.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="cc5c2-166">Конфигурация и данные подписки на Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="cc5c2-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="cc5c2-167">Вам не нужно вносить никаких изменений в текущую подписку или данные перед миграцией, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="cc5c2-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="cc5c2-168">Конфигурация подписки, например записи DNS и доменные имена.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="cc5c2-169">Учетные записи пользователей и групп и параметры проверки подлинности, такие как многофакторная проверка подлинности или политики условного доступа.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="cc5c2-170">Конфигурации служб производительности и их данные, такие как Teams, почтовые ящики Exchange Online, сайты SharePoint Online, папки OneDrive для бизнеса и записные книжки OneNote.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

### <a name="windows-10"></a><span data-ttu-id="cc5c2-171">Windows 10</span><span class="sxs-lookup"><span data-stu-id="cc5c2-171">Windows 10</span></span>

<span data-ttu-id="cc5c2-172">Если Windows не находится в обновлении Windows Pro Creator, [обновите их до версии Windows Pro](upgrade-to-windows-pro-creators-update.md)Creators.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-172">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="cc5c2-173">Настройка политик для защиты устройств и файлов пользователей</span><span class="sxs-lookup"><span data-stu-id="cc5c2-173">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="cc5c2-174">Если вы настроили политики и устройства для Office 365 MDM, эти устройства будут перечислены на странице " **устройства** " центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-174">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="cc5c2-175">Все настроенные политики будут отображаться в списке классических политик на [портале Intune](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span><span class="sxs-lookup"><span data-stu-id="cc5c2-175">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="cc5c2-176">После назначения лицензий Microsoft 365 Business можно приступить к защите устройств и файлов пользователей.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-176">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="cc5c2-177">Если вы обновили всех пользователей в Организации до Microsoft 365 Business, вы увидите мастер установки на домашней странице, а также можете воспользоваться инструкциями по [настройке Microsoft 365 для бизнеса в мастере установки](set-up.md) , чтобы защитить файлы и мобильные устройства.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-177">If you upgraded everyone in your organization to Microsoft 365 Business, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="cc5c2-178">Вы также можете выполнить следующие действия на странице "устройства":</span><span class="sxs-lookup"><span data-stu-id="cc5c2-178">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="cc5c2-179">В левой панели навигации центра администрирования перейдите к разделу **политики** **устройств** \> .</span><span class="sxs-lookup"><span data-stu-id="cc5c2-179">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="cc5c2-180">На странице " **политики устройств** " нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-180">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="cc5c2-181">В области **Добавить политику** укажите имя политики, а затем выберите **тип политики** из раскрывающегося меню.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-181">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="cc5c2-182">Вы можете настроить политики приложений для защиты файлов на устройствах с Android и iPhone, а также в Windows 10, а также настроить политики конфигурации устройств для устройств с Windows 10, принадлежащих компании.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-182">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="cc5c2-183">Для получения подробных сведений ознакомьтесь со следующими ссылками:</span><span class="sxs-lookup"><span data-stu-id="cc5c2-183">See the following links for details:</span></span>
    
  - [<span data-ttu-id="cc5c2-184">Настройка параметров защиты приложений для устройств с Android и iOS</span><span class="sxs-lookup"><span data-stu-id="cc5c2-184">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="cc5c2-185">Настройка параметров защиты приложений для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="cc5c2-185">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="cc5c2-186">Настройка параметров защиты устройств для компьютеров с Windows 10</span><span class="sxs-lookup"><span data-stu-id="cc5c2-186">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="cc5c2-187">После настройки политик вы и ваши сотрудники смогут настраивать устройства:</span><span class="sxs-lookup"><span data-stu-id="cc5c2-187">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="cc5c2-188">Пошаговые инструкции по [настройке устройств Windows для Microsoft 365 бизнес-пользователей](set-up-windows-devices.md) для устройств с Windows.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-188">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="cc5c2-189">Выполните действия, описанные в [статье Настройка мобильных устройств для пользователей Microsoft 365 Business](set-up-mobile-devices.md) для телефонов с Android и iPhone.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-189">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 

### <a name="threat-protection"></a><span data-ttu-id="cc5c2-190">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="cc5c2-190">Threat protection</span></span>

<span data-ttu-id="cc5c2-191">После перехода на Microsoft 365 Business вы получите Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-191">After migrating to Microsoft 365 Business, you have Office 365 ATP.</span></span> <span data-ttu-id="cc5c2-192">Обзор [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) для просмотра.</span><span class="sxs-lookup"><span data-stu-id="cc5c2-192">See [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview.</span></span> <span data-ttu-id="cc5c2-193">Чтобы настроить, ознакомьтесь со статьей [Настройка безопасных ссылок ATP](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [Настройка безопасных вложений ATP](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)и [Настройка антифишинга ATP](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="cc5c2-193">To set up, see [set up ATP safe links](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [set up ATP safe attachments](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up ATP anti-phishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="cc5c2-194">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="cc5c2-194">Sensitivity labels</span></span>

<span data-ttu-id="cc5c2-195">Чтобы приступить к использованию меток конфиденциальности, ознакомьтесь со статьей [Обзор меток конфиденциальности](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) , а затем [Создайте видео метки конфиденциальности и управляйте ими](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) .</span><span class="sxs-lookup"><span data-stu-id="cc5c2-195">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
