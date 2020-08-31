---
title: Доступ к локальным ресурсам из устройства, подключенного к Azure AD, в Microsoft 365 Business
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
description: Узнайте, как получить доступ к локальным ресурсам, таким как бизнес-приложения, общие файловые ресурсы и принтеры из Azure Active Directory, подключенной к устройству Windows 10.
ms.openlocfilehash: 9b83781afee746b06bbdf90962de0f55ffbcb118
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307500"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="60bcc-103">Доступ к локальным ресурсам из устройства, подключенного к Azure AD, в Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="60bcc-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="60bcc-104">Эта статья относится к Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="60bcc-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="60bcc-105">Любое устройство Windows 10, к которому присоединена служба Azure Active Directory, имеет доступ ко всем облачным ресурсам, таким как приложения Microsoft 365, и может быть защищено с помощью Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="60bcc-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="60bcc-106">Вы также можете разрешить доступ к локальным ресурсам, таким как бизнес-приложения, общие файловые ресурсы и принтеры.</span><span class="sxs-lookup"><span data-stu-id="60bcc-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="60bcc-107">Чтобы разрешить доступ, используйте [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) для синхронизации локальной службы Active Directory с Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="60bcc-107">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="60bcc-108">Чтобы узнать больше, ознакомьтесь со статьей общие сведения об [управлении устройствами в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span><span class="sxs-lookup"><span data-stu-id="60bcc-108">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="60bcc-109">Эти действия также описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="60bcc-109">The steps are also summarized in the following sections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60bcc-110">Эта процедура относится только к OAuth и NTLM.</span><span class="sxs-lookup"><span data-stu-id="60bcc-110">This procedure is only applicable to OAuth and NTLM.</span></span> <span data-ttu-id="60bcc-111">Проверка подлинности Kerberos не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="60bcc-111">Kerberos is not supported.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="60bcc-112">Запуск Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="60bcc-112">Run Azure AD Connect</span></span>

<span data-ttu-id="60bcc-113">Выполните следующие действия, чтобы разрешить подключенным устройствам Azure AD в организации получать доступ к локальным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="60bcc-113">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="60bcc-114">Чтобы синхронизировать пользователей, группы и контакты из локальной службы Active Directory с Azure Active Directory, запустите мастер синхронизации каталогов и Azure AD Connect, как описано в статье [Настройка синхронизации каталогов для Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="60bcc-114">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span></span>
    
2. <span data-ttu-id="60bcc-115">По завершении синхронизации службы каталогов убедитесь, что устройства Windows 10 в вашей организации присоединены к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="60bcc-115">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="60bcc-116">Этот шаг выполняется отдельно для каждого устройства с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="60bcc-116">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="60bcc-117">Для получения дополнительных сведений см. раздел [Настройка устройств Windows для пользователей Microsoft 365 Business Premium](set-up-windows-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="60bcc-117">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="60bcc-118">Когда устройства с Windows 10 будут присоединены к Azure AD, каждый пользователь должен перезагрузить свои устройства и войти с помощью учетных данных Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="60bcc-118">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="60bcc-119">Теперь все устройства имеют доступ к локальным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="60bcc-119">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="60bcc-120">Для получения доступа к локальным ресурсам для устройств с присоединением Azure AD дополнительные действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="60bcc-120">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="60bcc-121">Эта функция встроена в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="60bcc-121">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="60bcc-122">Если вы планируете выполнить вход на устройство ААДЖ, отличное от пароля, например PIN/Bio-Metric, с помощью учетных данных для входа в ВХФБ и затем доступ к локальным ресурсам (Shares, Printers.. и т. д.), выполните следующие действия https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="60bcc-122">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="60bcc-123">Если ваша организация не готова к развертыванию в описанной выше конфигурации устройства с подключением Azure AD, рассмотрите возможность настройки [конфигурации гибридного устройства с присоединенной службой Azure AD](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="60bcc-123">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="60bcc-124">Рекомендации по присоединению устройств Windows к Azure AD</span><span class="sxs-lookup"><span data-stu-id="60bcc-124">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="60bcc-125">Если устройство Windows, к которому присоединена служба Azure AD, было ранее присоединено к домену или в Рабочей группе, учитывайте следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="60bcc-125">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="60bcc-126">Когда устройство Azure AD присоединяется, оно создает нового пользователя без обращения к существующему профилю.</span><span class="sxs-lookup"><span data-stu-id="60bcc-126">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="60bcc-127">Профили необходимо перенести вручную.</span><span class="sxs-lookup"><span data-stu-id="60bcc-127">Profiles must be manually migrated.</span></span> <span data-ttu-id="60bcc-128">Профиль пользователя содержит такие сведения, как "Избранное", "Локальные файлы", "Параметры браузера" и "Параметры меню" Пуск ".</span><span class="sxs-lookup"><span data-stu-id="60bcc-128">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="60bcc-129">Лучший подход — найти стороннее средство для сопоставления существующих файлов и параметров с новым профилем.</span><span class="sxs-lookup"><span data-stu-id="60bcc-129">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="60bcc-130">Если устройство использует объекты групповой политики (GPO), некоторые объекты групповой политики не могут иметь сравнимого [поставщика службы конфигурации](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) в Intune.</span><span class="sxs-lookup"><span data-stu-id="60bcc-130">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="60bcc-131">Запустите [средство ммат](https://www.microsoft.com/download/details.aspx?id=45520) , чтобы найти сравниваемые поставщики служб шифрования для существующих объектов групповой политики.</span><span class="sxs-lookup"><span data-stu-id="60bcc-131">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="60bcc-132">Пользователи не смогут проходить проверку подлинности в приложениях, зависящих от проверки подлинности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="60bcc-132">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="60bcc-133">Оцените старое приложение и обновите приложение, использующее современные проверки подлинности, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="60bcc-133">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="60bcc-134">Обнаружение принтеров Active Directory не работает.</span><span class="sxs-lookup"><span data-stu-id="60bcc-134">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="60bcc-135">Вы можете предоставить прямые пути к принтеру для всех пользователей или использовать [Печать в гибридном облаке](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span><span class="sxs-lookup"><span data-stu-id="60bcc-135">You can provide direct printer paths for all users or use [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
