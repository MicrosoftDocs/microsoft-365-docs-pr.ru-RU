---
title: Доступ к локальным ресурсам с Azure присоединился к AD устройства в Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Узнайте, как получить доступ к локальным ресурсам, как приложения бизнес-систем, общих файлов и принтеры с Azure Active Directory в состав Windows 10 устройства.
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870466"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="fc53b-103">Доступ к локальным ресурсам с Azure присоединился к AD устройства в Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="fc53b-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="fc53b-p101">Все устройства Windows 10 Azure Active Directory в состав будут иметь доступ ко всем ресурсам, на основе облака, такие как приложения Office 365 и могут быть защищены Microsoft 365 для бизнеса. Разрешения на доступ к локальным ресурсам как строки из БИЗНЕС-приложений, общих файлов и принтеров, при синхронизации Active Directory локальной с Azure Active Directory с помощью [Azure AD подключение](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). В разделе [Общие сведения об управлении устройства в Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="fc53b-p101">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business. To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span> 
  
## <a name="run-azure-ad-connect"></a><span data-ttu-id="fc53b-107">Подключение выполнения Azure AD</span><span class="sxs-lookup"><span data-stu-id="fc53b-107">Run Azure AD Connect</span></span>

<span data-ttu-id="fc53b-108">Выполните следующие действия для включения в состав Azure AD устройствах вашей организации для доступа к локальным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="fc53b-108">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="fc53b-109">Чтобы синхронизировать пользователей, групп и контактов из локального Active Directory в Azure Active Directory, запустите мастер синхронизации каталогов и Azure AD подключиться, как описано в [Настройка синхронизации службы каталогов для Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="fc53b-109">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="fc53b-p102">После завершения синхронизации службы каталогов, убедитесь в том, что устройствах вашей организации Windows 10 Azure AD в состав. Этот шаг выполняется по отдельности на каждом устройстве Windows 10. [Устройства Windows для пользователей Microsoft 365 Business](set-up-windows-devices.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="fc53b-p102">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined. This step is done individually on each Windows 10 device. See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="fc53b-p103">Имеющееся оборудование Windows 10 Azure AD в состав, каждому пользователю необходимо перезагрузить компьютер, их устройств и входа в систему с помощью их учетных данных в Microsoft 365 Business. Теперь все устройства будут иметь доступ к локальным ресурсам также.</span><span class="sxs-lookup"><span data-stu-id="fc53b-p103">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials. All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="fc53b-p104">Не дополнительные действия, необходимые для получения доступа к локальным, ресурсы, необходимые для Azure AD в состав устройств. Это встроенные функциональные возможности, доступные в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="fc53b-p104">No additional steps are required to get access to on-premise resources for Azure AD joined devices. This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="fc53b-117">Если ваша организация не готова для развертывания в Azure AD присоединился к конфигурации устройства описанных выше, рассмотрите возможность настройки [конфигурации устройства Соединяемая гибридного Azure AD](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="fc53b-117">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="fc53b-118">Вопросы при присоединении устройство Windows Azure AD</span><span class="sxs-lookup"><span data-stu-id="fc53b-118">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="fc53b-119">При наличии Azure AD присоединения устройства Windows, которое ранее было присоединенный к домену или в рабочей группе, необходимо учитывать следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="fc53b-119">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="fc53b-p105">При присоединении устройства Azure AD, он создает новый пользователь без ссылки на существующий профиль. Чтобы устранить эту проблему, необходимо вручную перенести профили. Профиль пользователя содержит сведения, например, "Избранное", локальных файлов, параметров браузера, параметры главного меню, и т.д. — Это лучший подход для поиска средства сторонних производителей для сопоставления существующих файлов и параметров в новый профиль</span><span class="sxs-lookup"><span data-stu-id="fc53b-p105">When a device Azure AD joins, it creates a new user without referencing an existing profile. To fix this, profiles need to be manually migrated. A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>
    
- <span data-ttu-id="fc53b-p106">Если устройство использует объекты групповой политики (GPO), некоторые объекты групповой политики может отсутствовать сравнимые [Конфигурации поставщика услуг](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) в Intune. Запустите [средство MMAT](https://www.microsoft.com/download/details.aspx?id=45520) , чтобы найти соответствующее CSP для существующих объектов групповой политики.</span><span class="sxs-lookup"><span data-stu-id="fc53b-p106">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune. Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span> 
    
- <span data-ttu-id="fc53b-p107">Пользователи не смогут проходить проверку подлинности в приложениях, зависящих от проверки подлинности Active Directory. Для работы с оценить с помощью прежних версий приложения и рассмотрите возможность обновления приложения, использующего проверкой подлинности на основе современных, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="fc53b-p107">Users will not be able to authenticate to applications that depend on Active Directory authentication. To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>
    
- <span data-ttu-id="fc53b-p108">Обнаружение принтера Active Directory не будут работать. Чтобы устранить эту проблему, обеспечивают прямое принтера пути для всех пользователей или использовать [Print облачных гибридного](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span><span class="sxs-lookup"><span data-stu-id="fc53b-p108">Active Directory printer discovery will not work. To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
    

