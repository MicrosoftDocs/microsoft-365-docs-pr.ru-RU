---
title: Миграция с Microsoft 365 бизнес на Microsoft 365 E3
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Сведения о том, как перенести бизнес-деятельность из Microsoft 365 Business в Microsoft 365 E3.
ms.openlocfilehash: 0d636c0572850a53612bf756508c4b57f1b3e4eb
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153524"
---
# <a name="migrate-from-microsoft-365-business-to-microsoft-365-e3"></a><span data-ttu-id="0fabe-103">Миграция с Microsoft 365 бизнес на Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="0fabe-103">Migrate from Microsoft 365 Business to Microsoft 365 E3</span></span>

<span data-ttu-id="0fabe-104">Microsoft 365 Business имеет все необходимое для малого бизнеса, объединяя лучшие облачные приложения для продуктивной работы с помощью простого управления устройствами и обеспечения безопасности, которые позволяют сотрудникам выполнять свои действия.</span><span class="sxs-lookup"><span data-stu-id="0fabe-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="0fabe-105">Однако в некоторых случаях вам может потребоваться перенести свою подписку на Microsoft 365 Business в Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="0fabe-105">In some cases, however, you may need to migrate your Microsoft 365 Business subscription to Microsoft 365 E3.</span></span> 

<span data-ttu-id="0fabe-106">Например, ваша организация увеличилась и нуждается в более чем 300 лицензиях (Поздравляем, кстати).</span><span class="sxs-lookup"><span data-stu-id="0fabe-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="0fabe-107">Кроме того, для вашего бизнеса требуются корпоративные функции, такие как Office 365 профессиональный плюс, Windows 10 Корпоративная или корпоративные клиентские лицензии (CAL).</span><span class="sxs-lookup"><span data-stu-id="0fabe-107">Or, your business needs enterprise features, such as Office 365 ProPlus, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="0fabe-108">Обновление упрощается: вы можете запустить обновление [из центра администрирования](../commerce/subscriptions/upgrade-to-different-plan.md).</span><span class="sxs-lookup"><span data-stu-id="0fabe-108">Upgrading is easy: you can start the upgrade [from the Admin center](../commerce/subscriptions/upgrade-to-different-plan.md).</span></span> <span data-ttu-id="0fabe-109">Все ваши данные и конфигурация в текущей подписке поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="0fabe-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="0fabe-110">Вы не можете подготовиться к миграции и не предпринимать никаких дополнительных действий, кроме использования новых функций.</span><span class="sxs-lookup"><span data-stu-id="0fabe-110">There's nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span>

>[!Note]
><span data-ttu-id="0fabe-111">Вы также можете использовать подписку на Microsoft 365 Business для получения до 300 рабочих мест и получения подписки на Microsoft 365 E3 для более чем 300 рабочих мест.</span><span class="sxs-lookup"><span data-stu-id="0fabe-111">You can also use a Microsoft 365 Business subscription for up to 300 seats and get a Microsoft 365 E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="0fabe-112">Однако Office 365 ATP не входит в состав Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="0fabe-112">However, Office 365 ATP is not included with Microsoft 365 E3.</span></span> <span data-ttu-id="0fabe-113">Для продолжения защиты от угроз необходимо добавить дополнительные лицензии Office 365 ATP, чтобы обеспечить лицензирование всех пользователей в области политик Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="0fabe-113">For continued threat protection, you should add additional Office 365 ATP licenses so that all of the users in scope of your Office 365 ATP polices are licensed.</span></span>
>

## <a name="differences-between-microsoft-365-business-and-microsoft-365-enterprise"></a><span data-ttu-id="0fabe-114">Различия между Microsoft 365 Business и Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="0fabe-114">Differences between Microsoft 365 Business and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="0fabe-115">В этой таблице показаны различия между Microsoft 365 Business и Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="0fabe-115">This table shows the differences between Microsoft 365 Business and Microsoft 365 E3.</span></span>

| <span data-ttu-id="0fabe-116">Компонент</span><span class="sxs-lookup"><span data-stu-id="0fabe-116">Feature</span></span>    | <span data-ttu-id="0fabe-117">Поддержка в Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="0fabe-117">Support in Microsoft 365 Business</span></span>    | <span data-ttu-id="0fabe-118">Поддержка в Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="0fabe-118">Support in Microsoft 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="0fabe-119">**Локальная среда**</span><span class="sxs-lookup"><span data-stu-id="0fabe-119">**On-premises**</span></span>        | | | 
| <span data-ttu-id="0fabe-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="0fabe-120">Windows 10</span></span>    | <span data-ttu-id="0fabe-121">Windows 10 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0fabe-121">Windows 10 Business</span></span>  |     <span data-ttu-id="0fabe-122">Windows 10 Корпоративная E3</span><span class="sxs-lookup"><span data-stu-id="0fabe-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="0fabe-123">Приложения Office \*</span><span class="sxs-lookup"><span data-stu-id="0fabe-123">Office apps\*</span></span>    | [<span data-ttu-id="0fabe-124">Office 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="0fabe-124">Office 365 Business</span></span>](#office-365-business)    | <span data-ttu-id="0fabe-125">Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="0fabe-125">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="0fabe-126">**Облачные приложения для работы**</span><span class="sxs-lookup"><span data-stu-id="0fabe-126">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="0fabe-127">Exchange Online и Outlook</span><span class="sxs-lookup"><span data-stu-id="0fabe-127">Exchange Online and Outlook</span></span>    | <span data-ttu-id="0fabe-128">50 ГБ дискового пространства для почтового ящика и неограниченная Архивация на базе Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0fabe-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>    | <span data-ttu-id="0fabe-129">100 ГБ дискового пространства для почтового ящика и неограниченная Архивация на базе Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0fabe-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="0fabe-130">Teams</span><span class="sxs-lookup"><span data-stu-id="0fabe-130">Teams</span></span>    | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0fabe-133">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0fabe-133">OneDrive for Business</span></span>    | <span data-ttu-id="0fabe-134">ограничения на размер хранилища на одного пользователя (1 ТБ)</span><span class="sxs-lookup"><span data-stu-id="0fabe-134">1 TB storage limit per user</span></span>    | <span data-ttu-id="0fabe-135">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="0fabe-135">Unlimited</span></span> | 
| <span data-ttu-id="0fabe-136">Yammer, SharePoint Online, планировщик, поток</span><span class="sxs-lookup"><span data-stu-id="0fabe-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0fabe-139">Диспетчер клиентов Outlook, Милеик</span><span class="sxs-lookup"><span data-stu-id="0fabe-139">Outlook Customer Manager, MileIQ</span></span>    | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | | 
| <span data-ttu-id="0fabe-141">**Защита от угроз**</span><span class="sxs-lookup"><span data-stu-id="0fabe-141">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="0fabe-142">Возможности сокращения уязвимой зоны</span><span class="sxs-lookup"><span data-stu-id="0fabe-142">Attack surface reduction capabilities</span></span>    | [<span data-ttu-id="0fabe-143">Просмотреть этот список</span><span class="sxs-lookup"><span data-stu-id="0fabe-143">See this list</span></span>](#threat-protection) | <span data-ttu-id="0fabe-144">Корпоративное управление изоляцией на основе оборудования для Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0fabe-144">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="0fabe-145">Office 365 Advanced Threat protection (ATP), план 1</span><span class="sxs-lookup"><span data-stu-id="0fabe-145">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | <span data-ttu-id="0fabe-147">Не включено, но его можно добавить на</span><span class="sxs-lookup"><span data-stu-id="0fabe-147">Not included, but can be added on</span></span> | 
| <span data-ttu-id="0fabe-148">**управление удостоверениями;**</span><span class="sxs-lookup"><span data-stu-id="0fabe-148">**Identity management**</span></span>        | | | 
| <span data-ttu-id="0fabe-149">Самостоятельный сброс паролей для гибридных учетных записей Azure Active Directory (Azure AD), многофакторная проверка подлинности Azure, условный доступ, обратная запись пароля для локальных удостоверений</span><span class="sxs-lookup"><span data-stu-id="0fabe-149">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure Multi-Factor Authentication, Conditional Access, password writeback for on-premises identities</span></span>|     ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0fabe-152">Обнаружение облачных приложений, работоспособность подключения Azure AD</span><span class="sxs-lookup"><span data-stu-id="0fabe-152">Cloud App Discovery, Azure AD Connect Health</span></span>    |     | ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0fabe-154">Единый вход для приложений Azure AD Office 365 (SSO): 10 приложений на пользователя (приложения коллекции, такие как Salesforce) \*</span><span class="sxs-lookup"><span data-stu-id="0fabe-154">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0fabe-157">Единый вход Azure AD Premium P1: без ограничений (локальных приложений через прокси приложения Azure AD и приложения без галереи с помощью шаблонов интеграции приложений самостоятельно)</span><span class="sxs-lookup"><span data-stu-id="0fabe-157">Azure AD Premium P1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>    |     | ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0fabe-159">**Управление устройствами и приложениями**</span><span class="sxs-lookup"><span data-stu-id="0fabe-159">**Device and app management**</span></span>        | | | 
| <span data-ttu-id="0fabe-160">Microsoft Intune, Windows для автопилота</span><span class="sxs-lookup"><span data-stu-id="0fabe-160">Microsoft Intune, Windows Autopilot</span></span>|     ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="0fabe-163">Доступ к виртуальному рабочему столу (вда)</span><span class="sxs-lookup"><span data-stu-id="0fabe-163">Virtual Desktop Access (VDA)</span></span>    |  |     ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="0fabe-165">Виртуальный рабочий стол Windows (ВВД)</span><span class="sxs-lookup"><span data-stu-id="0fabe-165">Windows Virtual Desktop (WVD)</span></span>    | ![Входит в состав Microsoft 365 Business](../media/check-mark.png) |     ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="0fabe-168">Активация на общем компьютере (SCA)</span><span class="sxs-lookup"><span data-stu-id="0fabe-168">Shared Computer Activation (SCA)</span></span>    | ![Входит в состав Microsoft 365 Business](../media/check-mark.png) |     ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0fabe-171">Пакет оптимизации рабочего стола Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0fabe-171">Microsoft Desktop Optimization Package</span></span>    | |     ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0fabe-173">**Защита информации**</span><span class="sxs-lookup"><span data-stu-id="0fabe-173">**Information protection**</span></span>        | | | 
| <span data-ttu-id="0fabe-174">Защита от потери данных в Office 365, план Azure Information Protection (план 1)</span><span class="sxs-lookup"><span data-stu-id="0fabe-174">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>    | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0fabe-177">Защита информации о Windows для конечной точки DLP</span><span class="sxs-lookup"><span data-stu-id="0fabe-177">Window Information Protection for endpoint DLP</span></span>    | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0fabe-180">**Лицензия клиентского доступа (права CAL)**</span><span class="sxs-lookup"><span data-stu-id="0fabe-180">**Client Access License (CAL rights)**</span></span>    | | |     
| <span data-ttu-id="0fabe-181">Набор корпоративных лицензий CAL (Exchange, SharePoint, Skype, Windows, диспетчер конфигурации конечных точек Майкрософт, управление правами Windows)</span><span class="sxs-lookup"><span data-stu-id="0fabe-181">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span></span>| |         ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0fabe-183">**Соответствие требованиям**</span><span class="sxs-lookup"><span data-stu-id="0fabe-183">**Compliance**</span></span>        | | | 
| <span data-ttu-id="0fabe-184">Неограниченная Архивация электронной почты</span><span class="sxs-lookup"><span data-stu-id="0fabe-184">Unlimited email archiving</span></span>    | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0fabe-187">Оценка соответствия требованиям/диспетчер соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="0fabe-187">Compliance Score/Compliance Manager</span></span>    | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0fabe-190">Обнаружение электронных данных</span><span class="sxs-lookup"><span data-stu-id="0fabe-190">eDiscovery</span></span>    | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0fabe-193">Удержание на месте и удержание для судебного разбирательства</span><span class="sxs-lookup"><span data-stu-id="0fabe-193">In-place hold and litigation hold</span></span>    | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0fabe-196">Теги и политики хранения для управления записями сообщений</span><span class="sxs-lookup"><span data-stu-id="0fabe-196">Messaging Records Management (MRM) retention tags and retention policies</span></span>    | ![Входит в состав Microsoft 365 Business](../media/check-mark.png)    | ![Входит в состав Microsoft 365 E3](../media/check-mark.png) | 
||||

<span data-ttu-id="0fabe-199">\*Пользователи, которым назначен доступ к приложениям SaaS, могут получать единый единый доступ к 10 приложениям.</span><span class="sxs-lookup"><span data-stu-id="0fabe-199">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="0fabe-200">Администраторы могут настраивать единый вход и изменять доступ пользователей к различным приложениям SaaS, но доступ SSO разрешен только для 10 приложений на пользователя за раз.</span><span class="sxs-lookup"><span data-stu-id="0fabe-200">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="0fabe-201">Все приложения Office 365 считаются одним приложением.</span><span class="sxs-lookup"><span data-stu-id="0fabe-201">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="0fabe-202">Миграция</span><span class="sxs-lookup"><span data-stu-id="0fabe-202">Migration</span></span>

<span data-ttu-id="0fabe-203">Для миграции свяжитесь с вашим партнером, чтобы перенести Microsoft 365 бизнес-подписку и лицензии на подходящую подписку Microsoft 365 E3 с лицензиями.</span><span class="sxs-lookup"><span data-stu-id="0fabe-203">To migrate, work with your partner to move your Microsoft 365 Business subscription and licenses to a suitable Microsoft 365 E3 subscription with its licenses.</span></span>

<span data-ttu-id="0fabe-204">В следующих разделах описываются изменения, которые необходимо выполнить, если они есть, и действия, которые можно выполнить после миграции.</span><span class="sxs-lookup"><span data-stu-id="0fabe-204">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="0fabe-205">Конфигурация и данные подписки Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0fabe-205">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="0fabe-206">Вам не нужно вносить никаких изменений в текущую подписку или данные перед миграцией, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="0fabe-206">You don't need to make any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="0fabe-207">Конфигурация подписки, например доменные имена DNS.</span><span class="sxs-lookup"><span data-stu-id="0fabe-207">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="0fabe-208">Учетные записи пользователей и групп и параметры проверки подлинности, такие как многофакторная проверка подлинности или политики условного доступа.</span><span class="sxs-lookup"><span data-stu-id="0fabe-208">User and group accounts and authentication settings, such as multi factor authentication or Conditional Access policies.</span></span>
- <span data-ttu-id="0fabe-209">Конфигурации служб производительности и их данные, такие как Teams, почтовые ящики Exchange Online, сайты SharePoint Online, папки OneDrive для бизнеса и записные книжки OneNote.</span><span class="sxs-lookup"><span data-stu-id="0fabe-209">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="0fabe-210">Теперь пользователи могут работать с неограниченным хранилищем в папках почтовых ящиков Exchange Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0fabe-210">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="0fabe-211">Вы можете начать использовать обнаружение облачных приложений, работоспособность Azure AD Connect и единый вход для более чем 10 приложений.</span><span class="sxs-lookup"><span data-stu-id="0fabe-211">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

>[!Note]
><span data-ttu-id="0fabe-212">Пользователи, перенесенные в Microsoft 365 E3, больше не могут использовать Outlook Customer Manager и Милеик.</span><span class="sxs-lookup"><span data-stu-id="0fabe-212">Users migrated to Microsoft 365 E3 can no longer use Outlook Customer Manager and MileIQ.</span></span>
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="0fabe-213">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="0fabe-213">Threat protection</span></span>

<span data-ttu-id="0fabe-214">Windows 10 бизнес включает следующие средства защиты:</span><span class="sxs-lookup"><span data-stu-id="0fabe-214">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="0fabe-215">Обеспечение целостности процесса загрузки операционной системы</span><span class="sxs-lookup"><span data-stu-id="0fabe-215">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="0fabe-216">Обеспечение целостности важных рабочих компонентов</span><span class="sxs-lookup"><span data-stu-id="0fabe-216">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="0fabe-217">Повышенная уязвимость и устранение уязвимостей с использованием нулевого дня</span><span class="sxs-lookup"><span data-stu-id="0fabe-217">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="0fabe-218">Защита сети на основе репутации для Microsoft EDGE, Internet Explorer и Chrome</span><span class="sxs-lookup"><span data-stu-id="0fabe-218">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="0fabe-219">Брандмауэр на основе узла</span><span class="sxs-lookup"><span data-stu-id="0fabe-219">Host-based firewall</span></span>
- <span data-ttu-id="0fabe-220">Снижение опасности для атаки программой «шантажистом»</span><span class="sxs-lookup"><span data-stu-id="0fabe-220">Ransomware mitigations</span></span>
- <span data-ttu-id="0fabe-221">Изоляция на основе оборудования для Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0fabe-221">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="0fabe-222">Управление приложениями на базе интеллектуального графа безопасности</span><span class="sxs-lookup"><span data-stu-id="0fabe-222">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="0fabe-223">Управление устройством (USB)</span><span class="sxs-lookup"><span data-stu-id="0fabe-223">Device control (USB)</span></span>
- <span data-ttu-id="0fabe-224">Защита сети от угроз для веб-угроз</span><span class="sxs-lookup"><span data-stu-id="0fabe-224">Network protection for web-based threats</span></span>
- <span data-ttu-id="0fabe-225">Правила предотвращения вторжения для узла</span><span class="sxs-lookup"><span data-stu-id="0fabe-225">Host intrusion prevention rules</span></span>

<span data-ttu-id="0fabe-226">Windows 10 Корпоративная E3 также включает управление изоляцией на основе аппаратного обеспечения для Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="0fabe-226">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="0fabe-227">Для всех пользователей, перенесенных в Microsoft 365 E3, требуется лицензия на Office 365 ATP для продолжения защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="0fabe-227">Users migrated to Microsoft 365 E3 will each require an Office 365 ATP license for continued threat protection.</span></span> <span data-ttu-id="0fabe-228">Обязательно приобретайте дополнительные лицензии Office 365 ATP, чтобы обеспечить лицензирование всех пользователей в области политик Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="0fabe-228">Be sure to purchase additional Office 365 ATP licenses so that all of the users in scope of your Office 365 ATP polices are licensed.</span></span> 
>

### <a name="device-management-with-intune"></a><span data-ttu-id="0fabe-229">Управление устройствами с помощью Intune</span><span class="sxs-lookup"><span data-stu-id="0fabe-229">Device management with Intune</span></span>

<span data-ttu-id="0fabe-230">Нет необходимости вносить какие – либо изменения в текущую конфигурацию Intune перед миграцией, которая включает зарегистрированные устройства и параметры устройств и приложений.</span><span class="sxs-lookup"><span data-stu-id="0fabe-230">You don't need to make any changes to your current Intune configuration before migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="0fabe-231">Windows 10</span><span class="sxs-lookup"><span data-stu-id="0fabe-231">Windows 10</span></span>

<span data-ttu-id="0fabe-232">Microsoft 365 Business включает Windows 10 бизнес, которую можно установить с помощью Windows автопилота.</span><span class="sxs-lookup"><span data-stu-id="0fabe-232">Microsoft 365 Business includes Windows 10 Business, which you can install with Windows AutoPilot.</span></span> <span data-ttu-id="0fabe-233">При переходе на Microsoft 365 E3 каждая пользовательская лицензия включает Windows 10 Корпоративная версия E3, которую можно также установить с помощью Windows автопилота.</span><span class="sxs-lookup"><span data-stu-id="0fabe-233">When you migrate to Microsoft 365 E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
### <a name="office-365-business"></a><span data-ttu-id="0fabe-234">Office 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="0fabe-234">Office 365 Business</span></span>

<span data-ttu-id="0fabe-235">Office 365 Business Client, установленный на устройствах, автоматически начнет использовать функции Office 365 профессиональный плюс.</span><span class="sxs-lookup"><span data-stu-id="0fabe-235">Your Office 365 Business client installed on your devices will automatically begin to use the features of Office 365 ProPlus.</span></span> <span data-ttu-id="0fabe-236">После миграции теперь можно использовать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="0fabe-236">After migration, you can now use:</span></span>

 - <span data-ttu-id="0fabe-237">Активация корпоративных лицензий с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="0fabe-237">Volume activation through Group Policy</span></span>
 - <span data-ttu-id="0fabe-238">Телеметрии приложений</span><span class="sxs-lookup"><span data-stu-id="0fabe-238">App telemetry</span></span>
 - <span data-ttu-id="0fabe-239">Обновление элементов управления</span><span class="sxs-lookup"><span data-stu-id="0fabe-239">Update controls</span></span>
 - <span data-ttu-id="0fabe-240">Сравнение и запрос электронной таблицы</span><span class="sxs-lookup"><span data-stu-id="0fabe-240">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="0fabe-241">Бизнес-аналитика</span><span class="sxs-lookup"><span data-stu-id="0fabe-241">Business intelligence</span></span>

