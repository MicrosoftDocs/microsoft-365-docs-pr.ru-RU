---
title: Доступ к локальному ресурсу с устройства, присоединенного к Azure AD, в Microsoft 365 бизнес
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Узнайте, как получить доступ к локальному ресурсу, например к бизнес-приложениям, файловой папке и принтерам с устройства с Windows 10, присоединенного к Azure Active Directory.
ms.openlocfilehash: 22edf0c23d6318e1f70bcb21b2cd697ea0a75da4
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688240"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="8ace9-103">Доступ к локальному ресурсу с устройства, присоединенного к Azure AD, в Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="8ace9-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="8ace9-104">Эта статья относится к Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="8ace9-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="8ace9-105">Любое устройство с Windows 10, присоединенное к Azure Active Directory, имеет доступ ко всем облачным ресурсам, таким как приложения Microsoft 365, и может быть защищено с помощью Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="8ace9-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="8ace9-106">Вы также можете разрешить доступ к локальному ресурсу, например бизнес-приложениям, файловой папке и принтерам.</span><span class="sxs-lookup"><span data-stu-id="8ace9-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="8ace9-107">Чтобы разрешить доступ, используйте [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) для синхронизации локальной службы Active Directory с Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8ace9-107">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="8ace9-108">Дополнительные узнать см. [в введении в управление устройствами в Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/device-management-introduction)</span><span class="sxs-lookup"><span data-stu-id="8ace9-108">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="8ace9-109">Эти действия также подводятся в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="8ace9-109">The steps are also summarized in the following sections.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="8ace9-110">Запуск Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="8ace9-110">Run Azure AD Connect</span></span>

<span data-ttu-id="8ace9-111">Выполните следующие действия, чтобы позволить устройствам, присоединенным к Azure AD, получать доступ к локальному ресурсу.</span><span class="sxs-lookup"><span data-stu-id="8ace9-111">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="8ace9-112">Чтобы синхронизировать пользователей, группы и контакты из локальной службы Active Directory в Azure Active Directory, запустите мастер синхронизации службы каталогов и Azure AD Connect, как описано в описании в описании "Настройка синхронизации службы каталогов для [Office 365".](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</span><span class="sxs-lookup"><span data-stu-id="8ace9-112">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span></span>
    
2. <span data-ttu-id="8ace9-113">После завершения синхронизации службы каталогов убедитесь, что устройства с Windows 10 вашей организации присоединились к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8ace9-113">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="8ace9-114">Это делается отдельно на каждом устройстве с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8ace9-114">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="8ace9-115">Дополнительные сведения см. в подсети "Настройка устройств с Windows для [пользователей Microsoft 365 бизнес премиум".](set-up-windows-devices.md)</span><span class="sxs-lookup"><span data-stu-id="8ace9-115">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="8ace9-116">После присоединив устройства с Windows 10 к Azure AD, каждый пользователь должен перезагрудить свои устройства и войти в учетные данные Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="8ace9-116">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="8ace9-117">Все устройства теперь также имеют доступ к локальному ресурсу.</span><span class="sxs-lookup"><span data-stu-id="8ace9-117">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="8ace9-118">Для получения доступа к локальному ресурсу для устройств, присоединенных к Azure AD, не требуется никаких дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="8ace9-118">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="8ace9-119">Эта функция встроена в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8ace9-119">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="8ace9-120">Если у вас есть планы входа на устройство AADJ, которое не является паролем, например PIN-код или метрика bio-metric, через учетные данные WHFB, а затем доступ к локальному ресурсу (shares,printers.). и т. д.), следуйте https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="8ace9-120">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="8ace9-121">Если ваша организация не готова к развертыванию в описанной выше конфигурации устройства, которая присоединилась к Azure AD, рассмотрите возможность настройки гибридной конфигурации устройств, которые присоединились к [Azure AD.](manage-windows-devices.md)</span><span class="sxs-lookup"><span data-stu-id="8ace9-121">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="8ace9-122">Вопросы присоединить устройства с Windows к Azure AD</span><span class="sxs-lookup"><span data-stu-id="8ace9-122">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="8ace9-123">Если устройство с Windows, которое вы присоединили к Azure-AD, ранее было в домене или в группе, рассмотрите следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="8ace9-123">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="8ace9-124">Когда устройство Присоединяется к Azure AD, оно создает нового пользователя, не ссылаясь на существующий профиль.</span><span class="sxs-lookup"><span data-stu-id="8ace9-124">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="8ace9-125">Профили необходимо перенести вручную.</span><span class="sxs-lookup"><span data-stu-id="8ace9-125">Profiles must be manually migrated.</span></span> <span data-ttu-id="8ace9-126">Профиль пользователя содержит такие сведения, как избранное, локальные файлы, параметры браузера и параметры меню "Пуск".</span><span class="sxs-lookup"><span data-stu-id="8ace9-126">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="8ace9-127">Лучший подход — найти стороне средство для связи существующих файлов и параметров с новым профилем.</span><span class="sxs-lookup"><span data-stu-id="8ace9-127">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="8ace9-128">Если устройство использует объекты групповой политики (GPO), некоторые [](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) объекты групповой политики могут не иметь сравнимого поставщика служб конфигурации (CSP) в Intune.</span><span class="sxs-lookup"><span data-stu-id="8ace9-128">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="8ace9-129">Запустите [средство MMAT, чтобы](https://www.microsoft.com/download/details.aspx?id=45520) найти сравнимых CSP для существующих GGPOs.</span><span class="sxs-lookup"><span data-stu-id="8ace9-129">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="8ace9-130">Пользователи не смогут проверить подлинность в приложениях, которые зависят от проверки подлинности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8ace9-130">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="8ace9-131">Оцените устаревшее приложение и по возможности рассмотрите возможность обновления до приложения, которое использует современную auth.</span><span class="sxs-lookup"><span data-stu-id="8ace9-131">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="8ace9-132">Обнаружение принтера Active Directory не будет работать.</span><span class="sxs-lookup"><span data-stu-id="8ace9-132">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="8ace9-133">Вы можете предоставить прямой путь принтера для всех пользователей или использовать [универсальную печать.](https://aka.ms/UPDocs)</span><span class="sxs-lookup"><span data-stu-id="8ace9-133">You can provide direct printer paths for all users or use [Universal Print](https://aka.ms/UPDocs).</span></span>
