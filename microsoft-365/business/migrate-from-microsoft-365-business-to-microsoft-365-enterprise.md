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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Узнайте, как переместить бизнес из Microsoft 365 бизнес премиум в Microsoft 365 E3.
ms.openlocfilehash: 10630671f3deb7eff0ad0f601d301b90743ee35f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164520"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a><span data-ttu-id="93f97-103">Миграция с Microsoft 365 бизнес премиум на Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="93f97-103">Migrate from Microsoft 365 Business Premium to Microsoft 365 E3</span></span>

<span data-ttu-id="93f97-104">Microsoft 365 бизнес премиум имеет все необходимое для малого бизнеса, объединяя лучшие в своем классе облачные приложения для повышения производительности с простым управлением устройствами и безопасностью, которые позволяют сотрудникам работать наилучшим образом.</span><span class="sxs-lookup"><span data-stu-id="93f97-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="93f97-105">Однако в некоторых случаях может потребоваться перенести Microsoft 365 бизнес премиум подписку на Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="93f97-105">In some cases, however, you may need to migrate your Microsoft 365 Business Premium subscription to Microsoft 365 E3.</span></span> 

<span data-ttu-id="93f97-106">Например, ваш бизнес вырос и нуждается в более чем 300 лицензиях (кстати, поздравления).</span><span class="sxs-lookup"><span data-stu-id="93f97-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="93f97-107">Или вашему бизнесу необходимы корпоративные функции, такие как Приложения Microsoft 365 для предприятий, Windows 10 Корпоративная E3 или Enterprise клиентских лицензий доступа (CALs).</span><span class="sxs-lookup"><span data-stu-id="93f97-107">Or, your business needs enterprise features, such as Microsoft 365 Apps for enterprise, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="93f97-108">Обновление легко: вы можете начать обновление [из центра администрирования.](../commerce/subscriptions/upgrade-to-different-plan.md)</span><span class="sxs-lookup"><span data-stu-id="93f97-108">Upgrading is easy: you can start the upgrade [from the Admin center](../commerce/subscriptions/upgrade-to-different-plan.md).</span></span> <span data-ttu-id="93f97-109">Все данные и конфигурация текущей подписки поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="93f97-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="93f97-110">Ничего не нужно делать для подготовки к миграции и ничего не делать после этого, кроме использования новых функций.</span><span class="sxs-lookup"><span data-stu-id="93f97-110">There's nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span>

>[!Note]
><span data-ttu-id="93f97-111">Вы также можете использовать подписку Microsoft 365 бизнес премиум до 300 мест и получить Microsoft 365 E3 более 300 мест.</span><span class="sxs-lookup"><span data-stu-id="93f97-111">You can also use a Microsoft 365 Business Premium subscription for up to 300 seats and get a Microsoft 365 E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="93f97-112">Однако Microsoft Defender для Office 365 не входит в Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="93f97-112">However, Microsoft Defender for Office 365 is not included with Microsoft 365 E3.</span></span> <span data-ttu-id="93f97-113">Для дальнейшей защиты от угроз необходимо добавить дополнительные лицензии Defender для Office 365, чтобы все пользователи в области защитника для Office 365 лицензированы.</span><span class="sxs-lookup"><span data-stu-id="93f97-113">For continued threat protection, you should add additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span>
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a><span data-ttu-id="93f97-114">Различия между Microsoft 365 бизнес премиум и Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="93f97-114">Differences between Microsoft 365 Business Premium and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="93f97-115">В этой таблице показаны различия между Microsoft 365 бизнес премиум и Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="93f97-115">This table shows the differences between Microsoft 365 Business Premium and Microsoft 365 E3.</span></span>

| <span data-ttu-id="93f97-116">Возможность</span><span class="sxs-lookup"><span data-stu-id="93f97-116">Feature</span></span>    | <span data-ttu-id="93f97-117">Поддержка в Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="93f97-117">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="93f97-118">Поддержка в Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="93f97-118">Support in Microsoft 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="93f97-119">**Локальная среда**</span><span class="sxs-lookup"><span data-stu-id="93f97-119">**On-premises**</span></span>        | | | 
| <span data-ttu-id="93f97-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="93f97-120">Windows 10</span></span>    | <span data-ttu-id="93f97-121">Windows 10 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="93f97-121">Windows 10 Business</span></span>  |     <span data-ttu-id="93f97-122">Windows 10 Корпоративная E3</span><span class="sxs-lookup"><span data-stu-id="93f97-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="93f97-123">Office приложения\*</span><span class="sxs-lookup"><span data-stu-id="93f97-123">Office apps\*</span></span>    | [<span data-ttu-id="93f97-124">Приложения Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="93f97-124">Microsoft 365 Apps for business</span></span>](#office-365-business)    | <span data-ttu-id="93f97-125">Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="93f97-125">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="93f97-126">**Приложения облачной производительности**</span><span class="sxs-lookup"><span data-stu-id="93f97-126">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="93f97-127">Exchange Online и Outlook</span><span class="sxs-lookup"><span data-stu-id="93f97-127">Exchange Online and Outlook</span></span>    | <span data-ttu-id="93f97-128">Ограничение хранения 50 ГБ на почтовый ящик и Exchange Online архивирования</span><span class="sxs-lookup"><span data-stu-id="93f97-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>    | <span data-ttu-id="93f97-129">Ограничение хранения 100 ГБ на почтовый ящик и Exchange Online архивирования</span><span class="sxs-lookup"><span data-stu-id="93f97-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="93f97-130">Teams</span><span class="sxs-lookup"><span data-stu-id="93f97-130">Teams</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="93f97-133">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="93f97-133">OneDrive for Business</span></span>    | <span data-ttu-id="93f97-134">Ограничение хранения 1 ТБ на пользователя</span><span class="sxs-lookup"><span data-stu-id="93f97-134">1 TB storage limit per user</span></span>    | <span data-ttu-id="93f97-135">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="93f97-135">Unlimited</span></span> | 
| <span data-ttu-id="93f97-136">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="93f97-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="93f97-139">**Защита от угроз**</span><span class="sxs-lookup"><span data-stu-id="93f97-139">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="93f97-140">Возможности уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="93f97-140">Attack surface reduction capabilities</span></span>    | [<span data-ttu-id="93f97-141">См. этот список</span><span class="sxs-lookup"><span data-stu-id="93f97-141">See this list</span></span>](#threat-protection) | <span data-ttu-id="93f97-142">Enterprise управление аппаратной изоляцией для Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="93f97-142">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="93f97-143">Defender для Office 365 (план 1)</span><span class="sxs-lookup"><span data-stu-id="93f97-143">Defender for Office 365 Plan 1</span></span> | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | <span data-ttu-id="93f97-145">Не включено, но может быть добавлено в</span><span class="sxs-lookup"><span data-stu-id="93f97-145">Not included, but can be added on</span></span> | 
| <span data-ttu-id="93f97-146">**управление удостоверениями;**</span><span class="sxs-lookup"><span data-stu-id="93f97-146">**Identity management**</span></span>        | | | 
| <span data-ttu-id="93f97-147">Сброс пароля самообслуживления для гибридных учетных записей Azure Active Directory (Azure AD), многофакторной проверки подлинности Azure AD (MFA), условного доступа, списания паролей для идентификаторов локального доступа</span><span class="sxs-lookup"><span data-stu-id="93f97-147">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="93f97-150">Обнаружение облачных приложений, Azure AD Подключение health</span><span class="sxs-lookup"><span data-stu-id="93f97-150">Cloud App Discovery, Azure AD Connect Health</span></span>    |     | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="93f97-152">Azure AD Office 365 приложения Sign-On (SSO): 10 приложений на одного пользователя (приложения Gallery SaaS, такие как Salesforce)\*</span><span class="sxs-lookup"><span data-stu-id="93f97-152">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="93f97-155">Azure AD Premium 1 SSO: нет ограничений (локальное приложение через прокси-серверы приложений Azure AD и приложения без галереи с Self-Service шаблонами интеграции приложений)</span><span class="sxs-lookup"><span data-stu-id="93f97-155">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>    |     | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="93f97-157">**Управление устройствами и приложениями**</span><span class="sxs-lookup"><span data-stu-id="93f97-157">**Device and app management**</span></span>        | | | 
| <span data-ttu-id="93f97-158">Microsoft Intune, Windows автопилот</span><span class="sxs-lookup"><span data-stu-id="93f97-158">Microsoft Intune, Windows Autopilot</span></span>|     ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="93f97-161">Виртуальный настольный доступ (VDA)</span><span class="sxs-lookup"><span data-stu-id="93f97-161">Virtual Desktop Access (VDA)</span></span>    |  |     ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="93f97-163">Windows Виртуальный рабочий стол (WVD)</span><span class="sxs-lookup"><span data-stu-id="93f97-163">Windows Virtual Desktop (WVD)</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png) |     ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="93f97-166">Активация общего компьютера (SCA)</span><span class="sxs-lookup"><span data-stu-id="93f97-166">Shared Computer Activation (SCA)</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png) |     ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="93f97-169">Пакет оптимизации рабочего стола Майкрософт</span><span class="sxs-lookup"><span data-stu-id="93f97-169">Microsoft Desktop Optimization Package</span></span>    | |     ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="93f97-171">**Защита информации**</span><span class="sxs-lookup"><span data-stu-id="93f97-171">**Information protection**</span></span>        | | | 
| <span data-ttu-id="93f97-172">Office 365 Предотвращение потери данных, План защиты информации Azure 1</span><span class="sxs-lookup"><span data-stu-id="93f97-172">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="93f97-175">Защита информации окна для конечной точки DLP</span><span class="sxs-lookup"><span data-stu-id="93f97-175">Window Information Protection for endpoint DLP</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="93f97-178">**Лицензия клиентского доступа (права CAL)**</span><span class="sxs-lookup"><span data-stu-id="93f97-178">**Client Access License (CAL rights)**</span></span>    | | |     
| <span data-ttu-id="93f97-179">Enterprise Cal Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows управление правами)</span><span class="sxs-lookup"><span data-stu-id="93f97-179">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span></span>| |         ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="93f97-181">**Соответствие требованиям**</span><span class="sxs-lookup"><span data-stu-id="93f97-181">**Compliance**</span></span>        | | | 
| <span data-ttu-id="93f97-182">Неограниченное архивативка электронной почты</span><span class="sxs-lookup"><span data-stu-id="93f97-182">Unlimited email archiving</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="93f97-185">Диспетчер соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="93f97-185">Compliance Manager</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="93f97-188">Обнаружение электронных данных</span><span class="sxs-lookup"><span data-stu-id="93f97-188">eDiscovery</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="93f97-191">Удержание на месте и судебное удержание</span><span class="sxs-lookup"><span data-stu-id="93f97-191">In-place hold and litigation hold</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="93f97-194">Теги и политики хранения для управления записями сообщений</span><span class="sxs-lookup"><span data-stu-id="93f97-194">Messaging Records Management (MRM) retention tags and retention policies</span></span>    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
||||

<span data-ttu-id="93f97-197">\* Пользователи, которым был назначен доступ к приложениям SaaS, могут получить доступ к SSO до 10 приложений.</span><span class="sxs-lookup"><span data-stu-id="93f97-197">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="93f97-198">Администраторы могут настраивать SSO и изменять доступ пользователей к различным приложениям SaaS, но доступ к SSO разрешен только для 10 приложений на одного пользователя одновременно.</span><span class="sxs-lookup"><span data-stu-id="93f97-198">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="93f97-199">Все Office 365 считаются одним приложением.</span><span class="sxs-lookup"><span data-stu-id="93f97-199">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="93f97-200">Миграция</span><span class="sxs-lookup"><span data-stu-id="93f97-200">Migration</span></span>

<span data-ttu-id="93f97-201">Чтобы перейти, работайте с партнером, чтобы переместить Microsoft 365 бизнес премиум подписку и лицензии в подходящий Microsoft 365 E3 с его лицензиями.</span><span class="sxs-lookup"><span data-stu-id="93f97-201">To migrate, work with your partner to move your Microsoft 365 Business Premium subscription and licenses to a suitable Microsoft 365 E3 subscription with its licenses.</span></span>

<span data-ttu-id="93f97-202">В следующих разделах описываются изменения, которые необходимо внести, если таковые есть, и что можно сделать после миграции.</span><span class="sxs-lookup"><span data-stu-id="93f97-202">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="93f97-203">Microsoft 365 конфигурации подписки и данных</span><span class="sxs-lookup"><span data-stu-id="93f97-203">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="93f97-204">Перед переносом не нужно вносить изменения в текущую подписку или данные, которые включают:</span><span class="sxs-lookup"><span data-stu-id="93f97-204">You don't need to make any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="93f97-205">Конфигурация подписки, например доменные имена DNS.</span><span class="sxs-lookup"><span data-stu-id="93f97-205">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="93f97-206">Учетные записи пользователей и групп и параметры проверки подлинности, такие как многофакторная проверка подлинности или политики условного доступа.</span><span class="sxs-lookup"><span data-stu-id="93f97-206">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="93f97-207">Конфигурации служб производительности и их данные, такие как Teams, Exchange Online почтовые ящики, сайты SharePoint Online, OneDrive для бизнеса папок и OneNote блокноты.</span><span class="sxs-lookup"><span data-stu-id="93f97-207">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="93f97-208">Теперь пользователи могут пользоваться неограниченным хранилищем в Exchange Online почтовых ящиках и OneDrive для бизнеса папках.</span><span class="sxs-lookup"><span data-stu-id="93f97-208">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="93f97-209">Для более чем 10 приложений можно приступить к использованию облачных приложений discovery, Azure AD Подключение health и SSO.</span><span class="sxs-lookup"><span data-stu-id="93f97-209">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="93f97-210">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="93f97-210">Threat protection</span></span>

<span data-ttu-id="93f97-211">Windows 10 для бизнеса включает следующие средства защиты:</span><span class="sxs-lookup"><span data-stu-id="93f97-211">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="93f97-212">Правоприменители целостности процесса загрузки операционной системы</span><span class="sxs-lookup"><span data-stu-id="93f97-212">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="93f97-213">Правоприменители целостности конфиденциальных операционных компонентов</span><span class="sxs-lookup"><span data-stu-id="93f97-213">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="93f97-214">Расширенный уровень уязвимости и смягчение последствий использования нулевого дня</span><span class="sxs-lookup"><span data-stu-id="93f97-214">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="93f97-215">Защита сети на основе репутации для Microsoft Edge, Internet Explorer и Chrome</span><span class="sxs-lookup"><span data-stu-id="93f97-215">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="93f97-216">Брандмауэр на основе хостов</span><span class="sxs-lookup"><span data-stu-id="93f97-216">Host-based firewall</span></span>
- <span data-ttu-id="93f97-217">Смягчение последствий программ-вымогателей</span><span class="sxs-lookup"><span data-stu-id="93f97-217">Ransomware mitigations</span></span>
- <span data-ttu-id="93f97-218">Аппаратная изоляция для Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="93f97-218">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="93f97-219">Управление приложениями с помощью интеллектуальной системы Graph</span><span class="sxs-lookup"><span data-stu-id="93f97-219">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="93f97-220">Управление устройствами (USB)</span><span class="sxs-lookup"><span data-stu-id="93f97-220">Device control (USB)</span></span>
- <span data-ttu-id="93f97-221">Защита сети от веб-угроз</span><span class="sxs-lookup"><span data-stu-id="93f97-221">Network protection for web-based threats</span></span>
- <span data-ttu-id="93f97-222">Правила предотвращения вторжений на хост</span><span class="sxs-lookup"><span data-stu-id="93f97-222">Host intrusion prevention rules</span></span>

<span data-ttu-id="93f97-223">Windows 10 Корпоративная E3 также включает корпоративное управление аппаратной изоляцией для Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="93f97-223">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="93f97-224">Пользователи, перенесенные в Microsoft 365 E3, потребуют лицензию Microsoft Defender для Office 365 для дальнейшей защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="93f97-224">Users migrated to Microsoft 365 E3 will each require a Microsoft Defender for Office 365 license for continued threat protection.</span></span> <span data-ttu-id="93f97-225">Не забудьте приобрести дополнительные лицензии Defender для Office 365, чтобы все пользователи в области защитника для Office 365 были лицензированы.</span><span class="sxs-lookup"><span data-stu-id="93f97-225">Be sure to purchase additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span> 
>

### <a name="device-management-with-intune"></a><span data-ttu-id="93f97-226">Управление устройствами с помощью Intune</span><span class="sxs-lookup"><span data-stu-id="93f97-226">Device management with Intune</span></span>

<span data-ttu-id="93f97-227">Вам не нужно вносить изменения в текущую конфигурацию Intune перед миграцией, которая включает зарегистрированные устройства, устройства и параметры приложений.</span><span class="sxs-lookup"><span data-stu-id="93f97-227">You don't need to make any changes to your current Intune configuration before migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="93f97-228">Windows 10</span><span class="sxs-lookup"><span data-stu-id="93f97-228">Windows 10</span></span>

<span data-ttu-id="93f97-229">Microsoft 365 бизнес премиум включает Windows 10 для бизнеса, которые можно установить с помощью Windows AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="93f97-229">Microsoft 365 Business Premium includes Windows 10 Business, which you can install with Windows AutoPilot.</span></span> <span data-ttu-id="93f97-230">При миграции в Microsoft 365 E3 каждая лицензия пользователя включает Windows 10 Корпоративная E3, которую можно также установить Windows автопилотом.</span><span class="sxs-lookup"><span data-stu-id="93f97-230">When you migrate to Microsoft 365 E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a><span data-ttu-id="93f97-231">Приложения Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="93f97-231">Microsoft 365 Apps for business</span></span>

<span data-ttu-id="93f97-232">Ваш Приложения Microsoft 365 для бизнеса клиент, установленный на устройствах, автоматически начнет использовать функции Приложения Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="93f97-232">Your Microsoft 365 Apps for business client installed on your devices will automatically begin to use the features of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="93f97-233">После переноса теперь можно использовать:</span><span class="sxs-lookup"><span data-stu-id="93f97-233">After migration, you can now use:</span></span>

 - <span data-ttu-id="93f97-234">Поддержка групповой политики</span><span class="sxs-lookup"><span data-stu-id="93f97-234">Group Policy support</span></span>
 - <span data-ttu-id="93f97-235">Сравнение электронных таблиц и запрос</span><span class="sxs-lookup"><span data-stu-id="93f97-235">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="93f97-236">Бизнес-аналитика</span><span class="sxs-lookup"><span data-stu-id="93f97-236">Business intelligence</span></span>

