---
title: Доступ к локальным ресурсам из устройства, подключенного к Azure AD, в Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Узнайте, как получить доступ к локальным ресурсам, таким как бизнес-приложения, общие файловые ресурсы и принтеры из Azure Active Directory, подключенной к устройству Windows 10.
ms.openlocfilehash: 92e8ccb99dfece7687c25db84b81fc7bc7158d71
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37574685"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="db2fa-103">Доступ к локальным ресурсам из устройства, подключенного к Azure AD, в Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="db2fa-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="db2fa-104">Все устройства с Windows 10, которые присоединены к Azure Active Directory, будут иметь доступ ко всем облачным ресурсам, таким как приложения Office 365, и могут быть защищены корпорацией Майкрософт 365 Business.</span><span class="sxs-lookup"><span data-stu-id="db2fa-104">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business.</span></span> <span data-ttu-id="db2fa-105">Чтобы разрешить доступ к локальным ресурсам, таким как бизнес-приложения, общие папки и принтеры, необходимо синхронизировать локальную службу Active Directory с Azure Active Directory с помощью [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="db2fa-105">To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span></span> 

<span data-ttu-id="db2fa-106">Чтобы узнать больше, ознакомьтесь со статьей [Введение в Управление устройствами в Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) .</span><span class="sxs-lookup"><span data-stu-id="db2fa-106">See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span>
<span data-ttu-id="db2fa-107">Эти действия также описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="db2fa-107">The steps are also summarized in the following sections.</span></span>

## <a name="run-azure-ad-connect"></a><span data-ttu-id="db2fa-108">Запуск Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="db2fa-108">Run Azure AD Connect</span></span>

<span data-ttu-id="db2fa-109">Выполните следующие действия, чтобы разрешить подключенным устройствам Azure AD в организации получать доступ к локальным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="db2fa-109">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="db2fa-110">Чтобы синхронизировать пользователей, группы и контакты из локальной службы Active Directory с Azure Active Directory, запустите мастер синхронизации каталогов и Azure AD Connect, как описано в статье [Настройка синхронизации каталогов для Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="db2fa-110">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="db2fa-111">После завершения синхронизации службы каталогов убедитесь, что устройства Windows 10 в вашей организации присоединены к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="db2fa-111">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="db2fa-112">Этот шаг выполняется отдельно для каждого устройства с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="db2fa-112">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="db2fa-113">Дополнительные сведения: [Set Up Windows Devices for Microsoft 365 Business Users](set-up-windows-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="db2fa-113">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="db2fa-114">Когда устройства Windows 10 будут присоединены к Azure AD, каждый пользователь должен перезагрузить свои устройства и войти с помощью учетных данных Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="db2fa-114">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials.</span></span> <span data-ttu-id="db2fa-115">Теперь все устройства будут иметь доступ к локальным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="db2fa-115">All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="db2fa-116">Для получения доступа к локальным ресурсам для устройств с присоединением Azure AD дополнительные действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="db2fa-116">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="db2fa-117">Это встроенные функции, доступные в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="db2fa-117">This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="db2fa-118">Если ваша организация не готова к развертыванию в описанной выше конфигурации устройства с присоединением Azure AD, рассмотрите возможность настройки [конфигурации гибридного устройства с присоединенной службой Azure AD](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="db2fa-118">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="db2fa-119">Рекомендации по присоединению устройств Windows к Azure AD</span><span class="sxs-lookup"><span data-stu-id="db2fa-119">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="db2fa-120">Если вы используете Azure AD для подключения к устройству Windows, которое ранее присоединяется к домену или в Рабочей группе, необходимо учитывать следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="db2fa-120">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="db2fa-121">Когда устройство Azure AD присоединяется, оно создает нового пользователя без обращения к существующему профилю.</span><span class="sxs-lookup"><span data-stu-id="db2fa-121">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="db2fa-122">Чтобы устранить эту проблему, необходимо вручную перенести профили.</span><span class="sxs-lookup"><span data-stu-id="db2fa-122">To fix this, profiles need to be manually migrated.</span></span> <span data-ttu-id="db2fa-123">Профиль пользователя содержит такие сведения, как избранное, локальные файлы, параметры браузера, параметры меню "Пуск" и т. д. Лучший подход — найти стороннее средство для сопоставления существующих файлов и параметров с новым профилем.</span><span class="sxs-lookup"><span data-stu-id="db2fa-123">A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>

- <span data-ttu-id="db2fa-124">Если устройство использует объекты групповой политики (GPO), некоторые объекты групповой политики не могут иметь сравнимого [поставщика службы конфигурации](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) в Intune.</span><span class="sxs-lookup"><span data-stu-id="db2fa-124">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="db2fa-125">Запустите [средство ммат](https://www.microsoft.com/download/details.aspx?id=45520) , чтобы найти сравниваемые поставщики служб шифрования для существующих объектов групповой политики.</span><span class="sxs-lookup"><span data-stu-id="db2fa-125">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="db2fa-126">Пользователи не смогут проходить проверку подлинности в приложениях, зависящих от проверки подлинности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="db2fa-126">Users will not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="db2fa-127">Для этого оцените использование устаревшего приложения и при возможности обновите приложение, использующее современные проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="db2fa-127">To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>

- <span data-ttu-id="db2fa-128">Обнаружение принтеров Active Directory не будет работать.</span><span class="sxs-lookup"><span data-stu-id="db2fa-128">Active Directory printer discovery will not work.</span></span> <span data-ttu-id="db2fa-129">Чтобы устранить эту проблему, предоставьте прямые пути к принтерам для всех пользователей или используйте [Печать в гибридном облаке](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span><span class="sxs-lookup"><span data-stu-id="db2fa-129">To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
