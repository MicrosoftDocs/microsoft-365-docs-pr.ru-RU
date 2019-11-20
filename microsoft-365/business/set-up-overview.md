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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Обзор действий по настройке Microsoft 365 Business.
ms.openlocfilehash: 3447f06d031462a7bebc6f129238de9f0c5dee41
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2019
ms.locfileid: "38721566"
---
# <a name="overview-of-setup"></a><span data-ttu-id="76c91-103">Обзор настройки</span><span class="sxs-lookup"><span data-stu-id="76c91-103">Overview of setup</span></span>

<span data-ttu-id="76c91-104">Большинство действий по настройке можно выполнить в мастере установки, но Кроме того, указаны другие параметры.</span><span class="sxs-lookup"><span data-stu-id="76c91-104">Most of the setup steps can be done in the setup wizard, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="76c91-105">Шаг 1: Добавление домена и пользователей</span><span class="sxs-lookup"><span data-stu-id="76c91-105">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="76c91-106">**[Добавьте свой домен](set-up.md#add-your-domain-to-personalize-sign-in)** (если вы приобрели свой домен во время [регистрации](sign-up.md), этот шаг уже выполнен).</span><span class="sxs-lookup"><span data-stu-id="76c91-106">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="76c91-107">**Добавление пользователей**.</span><span class="sxs-lookup"><span data-stu-id="76c91-107">**Add users**.</span></span> <span data-ttu-id="76c91-108">Вы можете добавить пользователей одним из трех способов:</span><span class="sxs-lookup"><span data-stu-id="76c91-108">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="76c91-109">В [мастере](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="76c91-109">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="76c91-110">Используйте синхронизацию службы каталогов для [добавления пользователей с помощью Azure AD Connect,](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) если у вас есть локальная служба Active Directory.</span><span class="sxs-lookup"><span data-stu-id="76c91-110">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="76c91-111">Вы также можете [Добавить пользователей позже](add-users-m365b.md) в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="76c91-111">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="76c91-112">Шаг 2: Настройка политик безопасности и настройка устройств</span><span class="sxs-lookup"><span data-stu-id="76c91-112">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="76c91-113">Используйте [Мастер установки](set-up.md#protect-data-and-devices) для настройки политик устройств и безопасности.</span><span class="sxs-lookup"><span data-stu-id="76c91-113">Use the [Setup wizard](set-up.md#protect-data-and-devices) to configure device and security policies.</span></span> 
  - <span data-ttu-id="76c91-114">Вы также можете добавить дополнительные или изменить их позже в [центре администрирования](view-policies-and-devices.md) и [портале Intune](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span><span class="sxs-lookup"><span data-stu-id="76c91-114">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="76c91-115">В дополнение к параметрам безопасности в мастере установки вы можете повысить уровень безопасности, добавив следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="76c91-115">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

      - <span data-ttu-id="76c91-116">**Защита от вредоносных программ электронной почты**</span><span class="sxs-lookup"><span data-stu-id="76c91-116">**Email malware protection**</span></span>
      - <span data-ttu-id="76c91-117">**Безопасные ссылки расширенной защиты от угроз (ATP)**</span><span class="sxs-lookup"><span data-stu-id="76c91-117">**Advanced Threat Protection (ATP) Safe links**</span></span>
      - <span data-ttu-id="76c91-118">**Безопасные вложения ATP**</span><span class="sxs-lookup"><span data-stu-id="76c91-118">**ATP Safe Attachments**</span></span>
      - <span data-ttu-id="76c91-119">**Защита от фишинга ATP**</span><span class="sxs-lookup"><span data-stu-id="76c91-119">**ATP anti-phishing**</span></span>
      - <span data-ttu-id="76c91-120">**Архивация на базе Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="76c91-120">**Exchange Online Archiving**</span></span>
      - <span data-ttu-id="76c91-121">**Data Loss Prevention (DLP)**</span><span class="sxs-lookup"><span data-stu-id="76c91-121">**Data Loss Prevention (DLP)**</span></span>
      - <span data-ttu-id="76c91-122">**Azure Information Protection (Plan1**)</span><span class="sxs-lookup"><span data-stu-id="76c91-122">**Azure Information Protection (Plan1**)</span></span>

          <span data-ttu-id="76c91-123">Чтобы приступить к работе, [Настройте дополнительные политики безопасности](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="76c91-123">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

        <span data-ttu-id="76c91-124">Кроме того, вы можете ознакомиться с десятью рекомендациями по [обеспечению безопасности Microsoft 365 для бизнеса](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) в плане рекомендаций по обеспечению безопасности.</span><span class="sxs-lookup"><span data-stu-id="76c91-124">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="76c91-125">Шаг 3: Настройка устройств с Windows 10 и управление ими</span><span class="sxs-lookup"><span data-stu-id="76c91-125">Step 3: Set up and manage Windows 10 devices</span></span>

   <span data-ttu-id="76c91-126">Когда вы присоединяете устройство Windows 10 к Azure AD, политики, которые вы настроили в [шаге 2](#step-2-set-up-security-policies-and-configure-devices) , будут применены к нему.</span><span class="sxs-lookup"><span data-stu-id="76c91-126">When you join a Windows 10 device to Azure AD, the policies you set up in [Step 2](#step-2-set-up-security-policies-and-configure-devices) get applied to it.</span></span>

   - <span data-ttu-id="76c91-127">Windows 10 профессиональная является [необходимым условием](pre-requisites-for-data-protection.md) для Microsoft 365 Business, но если у вас есть Windows 7 Профессиональная, Windows 8 Профессиональная или Windows 8,1 Pro, ваша подписка позволит вам выполнить [обновление до Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span><span class="sxs-lookup"><span data-stu-id="76c91-127">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
    - <span data-ttu-id="76c91-128">Используйте [Мастер установки](set-up.md#protect-data-and-devices) для настройки политик для устройств с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="76c91-128">Use the [Setup wizard](set-up.md#protect-data-and-devices) to configure policies for Windows 10 devices.</span></span>

## <a name="step-4-install-office-365-business"></a><span data-ttu-id="76c91-129">Шаг 4: установка Office 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="76c91-129">Step 4: Install Office 365 Business</span></span>
- <span data-ttu-id="76c91-130">Вы можете автоматически установить Office на устройствах с Windows с помощью [мастера установки](set-up.md#deploy-office-365-client-apps).</span><span class="sxs-lookup"><span data-stu-id="76c91-130">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="76c91-131">Разрешите пользователям [устанавливать приложения Office](https://docs.microsoft.com/office365/admin/setup/install-applications) для Windows и устройств.</span><span class="sxs-lookup"><span data-stu-id="76c91-131">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="76c91-132">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="76c91-132">Advanced</span></span>
- <span data-ttu-id="76c91-133">**Использование автопилота для настройки новых устройств**</span><span class="sxs-lookup"><span data-stu-id="76c91-133">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="76c91-134">Вы можете использовать [автопилот Windows](add-autopilot-devices-and-profile.md) для автоматической предварительной настройки **новых** устройств с Windows 10 для пользователя, но вам может быть проще получить [партнера](https://www.microsoft.com/solution-providers/search) , который может сделать это.</span><span class="sxs-lookup"><span data-stu-id="76c91-134">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="76c91-135">Вы также можете перейти в [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)и попросить эксперта по облачным технологиям настроить новые устройства, которые вы приобрели.</span><span class="sxs-lookup"><span data-stu-id="76c91-135">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="76c91-136">**Доступ к локальным ресурсам**</span><span class="sxs-lookup"><span data-stu-id="76c91-136">**Access on-premises resources**</span></span>

     - <span data-ttu-id="76c91-137">Если ваша организация использует локальную службу Windows Server Active Directory, вы можете настроить Microsoft 365 бизнес для защиты устройств с Windows 10, сохраняя доступ к локальным ресурсам, требующим локальной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="76c91-137">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="76c91-138">Выполните действия, описанные в разделе " [Включение устройств, присоединенных к домену" с Windows 10 для управления в Microsoft 365 Business](manage-windows-devices.md) , чтобы настроить.</span><span class="sxs-lookup"><span data-stu-id="76c91-138">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="76c91-139">Это рекомендуемый метод, и устройства в этом состоянии называются гибридными подключенными устройствами Azure AD.</span><span class="sxs-lookup"><span data-stu-id="76c91-139">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="76c91-140">Если в вашей организации есть локальная служба Active Directory, содержащая некоторые локальные ресурсы (например, файловые ресурсы и принтеры), вы можете предоставить подключенным устройствам Azure AD доступ к этим ресурсам, выполнив действия, описанные здесь: [доступ к локальным ресурсам из устройства, подключенного к Azure AD, в Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="76c91-140">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

  