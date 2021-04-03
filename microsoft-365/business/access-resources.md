---
title: Доступ к локальному ресурсу с устройства Azure AD в Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Узнайте, как получить доступ к локальному ресурсу, например к линейке бизнес-приложений, файлам и принтерам с устройства Azure Active Directory, присоединенного к Устройству Windows 10.
ms.openlocfilehash: 27549d6c3b03413f2f05c69845caad155333ca97
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580321"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="a66a5-103">Доступ к локальному ресурсу с устройства Azure AD в Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="a66a5-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="a66a5-104">Эта статья применима к Microsoft 365 Бизнес Премиум.</span><span class="sxs-lookup"><span data-stu-id="a66a5-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="a66a5-105">Любое устройство с Windows 10, к которое присоединилось Azure Active Directory, имеет доступ ко всем облачным ресурсам, таким как приложения Microsoft 365, и может быть защищено Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="a66a5-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="a66a5-106">Вы также можете разрешить доступ к локальному ресурсу, например к приложениям бизнес-сети, файлам и принтерам.</span><span class="sxs-lookup"><span data-stu-id="a66a5-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="a66a5-107">Чтобы разрешить доступ, используйте [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) для синхронизации локального Active Directory с Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a66a5-107">To allow access, use [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="a66a5-108">Дополнительные дополнительные информации см. [в обзоре Введение в управление устройствами в Azure Active Directory.](/azure/active-directory/device-management-introduction)</span><span class="sxs-lookup"><span data-stu-id="a66a5-108">To learn more, see [Introduction to device management in Azure Active Directory](/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="a66a5-109">Действия также суммируются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="a66a5-109">The steps are also summarized in the following sections.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="a66a5-110">Запуск Подключения Azure AD</span><span class="sxs-lookup"><span data-stu-id="a66a5-110">Run Azure AD Connect</span></span>

<span data-ttu-id="a66a5-111">Выполните следующие действия, чтобы включить присоединенные к вашей организации устройства Azure AD для доступа к локальному ресурсу.</span><span class="sxs-lookup"><span data-stu-id="a66a5-111">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="a66a5-112">Чтобы синхронизировать пользователей, группы и контакты из локального Active Directory в Azure Active Directory, запустите мастер синхронизации каталогов и Azure AD Connect, как описано в настройках синхронизации каталогов [для Office 365.](../enterprise/set-up-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="a66a5-112">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](../enterprise/set-up-directory-synchronization.md).</span></span>
    
2. <span data-ttu-id="a66a5-113">После завершения синхронизации каталогов убедитесь, что устройства Windows 10 вашей организации присоединились к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a66a5-113">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="a66a5-114">Этот шаг делается индивидуально на каждом устройстве Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a66a5-114">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="a66a5-115">Дополнительные сведения см. в материале Настройка устройств Windows для [пользователей Microsoft 365 Business Premium.](set-up-windows-devices.md)</span><span class="sxs-lookup"><span data-stu-id="a66a5-115">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="a66a5-116">После того как устройства Windows 10 присоединились к Azure AD, каждый пользователь должен перезагрудить свои устройства и войти с учетными данными Microsoft 365 Бизнес Премиум.</span><span class="sxs-lookup"><span data-stu-id="a66a5-116">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="a66a5-117">Теперь все устройства также имеют доступ к локальному ресурсу.</span><span class="sxs-lookup"><span data-stu-id="a66a5-117">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="a66a5-118">Для получения доступа к локальному ресурсу для присоединенных устройств Azure AD не требуется дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="a66a5-118">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="a66a5-119">Эта функция встроена в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a66a5-119">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="a66a5-120">Если у вас есть планы входа на устройство AADJ, кроме метода пароля, например PIN-код/bio-metric с помощью входа учетных данных WHFB, а затем получить доступ к локальному ресурсу (акции, принтеры.). и т.д.), следуйте https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="a66a5-120">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="a66a5-121">Если организация не готова к развертыванию в описанной выше конфигурации устройств Azure AD, рассмотрите возможность настройки конфигурации устройств [Hybrid Azure AD Joined.](manage-windows-devices.md)</span><span class="sxs-lookup"><span data-stu-id="a66a5-121">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="a66a5-122">Соображения при вступив устройствах Windows в Azure AD</span><span class="sxs-lookup"><span data-stu-id="a66a5-122">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="a66a5-123">Если устройство Windows, к которое вы присоединились Azure-AD, ранее было соединено с доменом или в группе, рассмотрите следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="a66a5-123">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="a66a5-124">Когда устройство Azure AD присоединяется, оно создает нового пользователя, не ссылаясь на существующий профиль.</span><span class="sxs-lookup"><span data-stu-id="a66a5-124">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="a66a5-125">Профили необходимо перенести вручную.</span><span class="sxs-lookup"><span data-stu-id="a66a5-125">Profiles must be manually migrated.</span></span> <span data-ttu-id="a66a5-126">Профиль пользователя содержит такие сведения, как избранное, локальные файлы, параметры браузера и параметры меню Пуск.</span><span class="sxs-lookup"><span data-stu-id="a66a5-126">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="a66a5-127">Оптимальный подход — найти сторонний инструмент для совмещая существующие файлы и параметры с новым профилем.</span><span class="sxs-lookup"><span data-stu-id="a66a5-127">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="a66a5-128">Если устройство использует объекты групповой политики (GPO), некоторые [](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) GPOs могут не иметь сопоставимого поставщика служб конфигурации (CSP) в Intune.</span><span class="sxs-lookup"><span data-stu-id="a66a5-128">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="a66a5-129">Запустите [средство MMAT,](https://www.microsoft.com/download/details.aspx?id=45520) чтобы найти сопоставимые CSP для существующих GPOs.</span><span class="sxs-lookup"><span data-stu-id="a66a5-129">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="a66a5-130">Возможно, пользователи не смогут проверить подлинность приложений, которые зависят от проверки подлинности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a66a5-130">Users might not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="a66a5-131">Оцените устаревшее приложение и по возможности обновим приложение, использующее современный auth.</span><span class="sxs-lookup"><span data-stu-id="a66a5-131">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="a66a5-132">Обнаружение принтера Active Directory не будет работать.</span><span class="sxs-lookup"><span data-stu-id="a66a5-132">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="a66a5-133">Вы можете предоставить прямой путь принтера для всех пользователей или использовать [универсальный шрифт](/universal-print/).</span><span class="sxs-lookup"><span data-stu-id="a66a5-133">You can provide direct printer paths for all users or use [Universal Print](/universal-print/).</span></span>

### <a name="related-articles"></a><span data-ttu-id="a66a5-134">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="a66a5-134">Related Articles</span></span>

[<span data-ttu-id="a66a5-135">Необходимые условия для подключения Azure AD</span><span class="sxs-lookup"><span data-stu-id="a66a5-135">Prerequisites for Azure AD Connect</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)
