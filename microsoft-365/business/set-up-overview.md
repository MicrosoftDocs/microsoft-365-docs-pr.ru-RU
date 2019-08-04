---
title: Обзор настройки
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Обзор процедуры настройки для Microsoft 365 Business.
ms.openlocfilehash: ae7ed0aab36a6e759e0f0c1fbc3d3183273a284e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074409"
---
# <a name="overview-of-setup"></a><span data-ttu-id="7931a-103">Обзор программы установки</span><span class="sxs-lookup"><span data-stu-id="7931a-103">Overview of setup</span></span>

<span data-ttu-id="7931a-104">Большинство этапов настройки можно выполнить в мастере установки, но Кроме того, указаны другие параметры.</span><span class="sxs-lookup"><span data-stu-id="7931a-104">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>


## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="7931a-105">Шаг 1: Добавление домена и пользователей</span><span class="sxs-lookup"><span data-stu-id="7931a-105">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="7931a-106">**[Добавление домена](set-up.md#add-your-domain-to-personalize-sign-in)** (если вы приобрели свой домен во время [регистрации](sign-up.md), этот шаг уже выполнен.)</span><span class="sxs-lookup"><span data-stu-id="7931a-106">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="7931a-107">**Добавление пользователей**.</span><span class="sxs-lookup"><span data-stu-id="7931a-107">**Add users**.</span></span> <span data-ttu-id="7931a-108">Это можно сделать одним из трех способов:</span><span class="sxs-lookup"><span data-stu-id="7931a-108">You can do this in any of the three ways:</span></span>
        - <span data-ttu-id="7931a-109">В [мастере](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="7931a-109">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="7931a-110">Используйте синхронизацию службы каталогов для [добавления пользователей с помощью Azure AD Connect,](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) если у вас есть локальная служба Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7931a-110">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="7931a-111">Вы также можете [Добавить пользователей позже](add-users-m365b.md) в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="7931a-111">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="7931a-112">Шаг 2: Настройка политик безопасности и настройка устройств</span><span class="sxs-lookup"><span data-stu-id="7931a-112">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="7931a-113">Используйте [Мастер установки](set-up.md#set-up-security-policies-and-device-configurations) для настройки политик устройств и безопасности.</span><span class="sxs-lookup"><span data-stu-id="7931a-113">Use the [Setup wizard](set-up.md#set-up-security-policies-and-device-configurations) to configure device and security policies.</span></span> 
  - <span data-ttu-id="7931a-114">Вы также можете добавить дополнительные или изменить их позже в [центре администрирования](view-policies-and-devices.md) и [портале Intune](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span><span class="sxs-lookup"><span data-stu-id="7931a-114">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="7931a-115">В дополнение к параметрам безопасности в мастере установки вы можете повысить уровень безопасности, добавив следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="7931a-115">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

      - <span data-ttu-id="7931a-116">**Защита от вредоносных программ электронной почты**</span><span class="sxs-lookup"><span data-stu-id="7931a-116">**Email malware protection**</span></span>
      - <span data-ttu-id="7931a-117">**Безопасные ссылки расширенной защиты от угроз (ATP)**</span><span class="sxs-lookup"><span data-stu-id="7931a-117">**Advanced Threat Protection (ATP) Safe links**</span></span>
      - <span data-ttu-id="7931a-118">**Безопасные вложения ATP**</span><span class="sxs-lookup"><span data-stu-id="7931a-118">**ATP Safe Attachments**</span></span>
      - <span data-ttu-id="7931a-119">**Защита от фишинга ATP**</span><span class="sxs-lookup"><span data-stu-id="7931a-119">**ATP anti-phishing**</span></span>
      - <span data-ttu-id="7931a-120">**Архивация на базе Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="7931a-120">**Exchange Online Archiving**</span></span>
      - <span data-ttu-id="7931a-121">**Data Loss Prevention (DLP)**</span><span class="sxs-lookup"><span data-stu-id="7931a-121">**Data Loss Prevention (DLP)**</span></span>
      - <span data-ttu-id="7931a-122">**Azure Information Protection (Plan1**)</span><span class="sxs-lookup"><span data-stu-id="7931a-122">**Azure Information Protection (Plan1**)</span></span>

          <span data-ttu-id="7931a-123">Чтобы приступить к работе, [Настройте дополнительные политики безопасности](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="7931a-123">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

        <span data-ttu-id="7931a-124">Кроме того, вы можете ознакомиться с десятью рекомендациями по обеспечению безопасности [Microsoft 365 для бизнеса](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) в плане рекомендаций по обеспечению безопасности.</span><span class="sxs-lookup"><span data-stu-id="7931a-124">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="7931a-125">Шаг 3: Настройка устройств с Windows 10 и управление ими</span><span class="sxs-lookup"><span data-stu-id="7931a-125">Step 3: Set up and manage Windows 10 devices</span></span>

   <span data-ttu-id="7931a-126">Когда вы присоединяете устройство Windows 10 к Azure AD, политики, которые вы настроили в [шаге 2](#step-2-set-up-security-policies-and-configure-devices) , будут применены к нему.</span><span class="sxs-lookup"><span data-stu-id="7931a-126">When you join a Windows 10 device to Azure AD, the policies you set up in [Step 2](#step-2-set-up-security-policies-and-configure-devices) get applied to it.</span></span>

   - <span data-ttu-id="7931a-127">Windows 10 профессиональная — это [Предварительный компонент](pre-requisites-for-data-protection.md) для Microsoft 365 Business, но если у вас есть Windows 7 Профессиональная, Windows 8 Профессиональная или Windows 8,1 Pro, ваша подписка дает вам возможность [выполнить обновление до Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span><span class="sxs-lookup"><span data-stu-id="7931a-127">Windows 10 Pro is a [pre-requisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
    - <span data-ttu-id="7931a-128">Используйте [Мастер установки](set-up.md#set-up-security-policies-and-device-configurations) для настройки политик для устройств с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="7931a-128">Use the [setup wizard](set-up.md#set-up-security-policies-and-device-configurations) to configure policies for Windows 10 devices.</span></span>

## <a name="stes-4-install-office-365-business"></a><span data-ttu-id="7931a-129">Стес 4: установка Office 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7931a-129">Stes 4: Install Office 365 Business</span></span>
- <span data-ttu-id="7931a-130">Вы можете автоматически установить Office на устройствах с Windows с помощью [мастера установки](set-up.md#deploy-office-365-client-apps).</span><span class="sxs-lookup"><span data-stu-id="7931a-130">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="7931a-131">Автоматическая [Установка Office](auto-install-or-uninstall-office.md) из центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="7931a-131">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
- <span data-ttu-id="7931a-132">Разрешите пользователям [устанавливать приложения Office](https://docs.microsoft.com/office365/admin/setup/install-applications) для Windows и устройств.</span><span class="sxs-lookup"><span data-stu-id="7931a-132">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="7931a-133">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="7931a-133">Advanced</span></span>
- <span data-ttu-id="7931a-134">**Использование автопилота для настройки новых устройств**</span><span class="sxs-lookup"><span data-stu-id="7931a-134">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="7931a-135">Вы можете использовать [автопилот Windows](add-autopilot-devices-and-profile.md) для автоматической предварительной настройки **новых** устройств с Windows 10 для пользователя, но вам может быть проще получить [партнера](https://www.microsoft.com/solution-providers/search) , который может сделать это.</span><span class="sxs-lookup"><span data-stu-id="7931a-135">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="7931a-136">Вы также можете перейти в [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) и попросить специалиста по облачным технологиям настроить новые устройства, которые вы приобрели.</span><span class="sxs-lookup"><span data-stu-id="7931a-136">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

- <span data-ttu-id="7931a-137">**Доступ к локальным ресурсам**</span><span class="sxs-lookup"><span data-stu-id="7931a-137">**Access on-premises resources**</span></span>

     - <span data-ttu-id="7931a-138">Если ваша организация использует локальную службу Windows Server Active Directory, вы можете настроить Microsoft 365 бизнес для защиты устройств с Windows 10, сохраняя доступ к локальным ресурсам, требующим локальной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="7931a-138">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="7931a-139">Выполните действия, описанные в разделе " [Включение устройств, присоединенных к домену" с Windows 10 для управления в Microsoft 365 Business](manage-windows-devices.md) , чтобы настроить.</span><span class="sxs-lookup"><span data-stu-id="7931a-139">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="7931a-140">Это предпочитаемый метод и устройства в этом состоянии называются гибридными подключенными устройствами Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7931a-140">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="7931a-141">Если в вашей организации есть локальная служба Active Directory, содержащая некоторые локальные ресурсы (например, файловые ресурсы и принтеры), вы можете предоставить подключенным устройствам Azure AD доступ к этим ресурсам, выполнив действия, описанные здесь: [доступ к локальным ресурсам из Подключенное к Azure AD устройство в Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="7931a-141">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

  