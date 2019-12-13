---
title: Обзор установки
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
description: Обзор действий по установке Microsoft 365 бизнес.
ms.openlocfilehash: f531830bffbe1cb6ce4e39ee2ba12da5738a2684
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967630"
---
# <a name="overview-of-setup"></a><span data-ttu-id="e1713-103">Обзор установки</span><span class="sxs-lookup"><span data-stu-id="e1713-103">Overview of setup</span></span>

<span data-ttu-id="e1713-104">Большинство действий по установке можно выполнить с помощью мастера установки, но есть и другие варианты.</span><span class="sxs-lookup"><span data-stu-id="e1713-104">Most of the setup steps can be done in the setup wizard, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="e1713-105">Действие 1. Добавление домена и пользователей</span><span class="sxs-lookup"><span data-stu-id="e1713-105">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="e1713-106">**[Добавьте домен](set-up.md#add-your-domain-to-personalize-sign-in)** (если вы приобрели домен в ходе[регистрации](sign-up.md), то это действие уже выполнено.)</span><span class="sxs-lookup"><span data-stu-id="e1713-106">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="e1713-107">**Добавление пользователей**.</span><span class="sxs-lookup"><span data-stu-id="e1713-107">**Add users**</span></span> <span data-ttu-id="e1713-108">Добавить пользователей можно тремя способами:</span><span class="sxs-lookup"><span data-stu-id="e1713-108">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="e1713-109">В этом [мастере](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="e1713-109">In the wizard:</span></span>
        - <span data-ttu-id="e1713-110">Воспользуйтесь синхронизацией каталогов, чтобы [добавить пользователей с помощью Azure AD Connect ](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization), если у вас есть локальная служба каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e1713-110">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="e1713-111">Кроме того, вы сможете [добавить пользователей позже](add-users-m365b.md) в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="e1713-111">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="e1713-112">Действие 2. Настройка политик безопасности и настройка устройств</span><span class="sxs-lookup"><span data-stu-id="e1713-112">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="e1713-113">Чтобы настроить политики устройств, воспользуйтесь этим [мастером установки](set-up.md#protect-your-organization).</span><span class="sxs-lookup"><span data-stu-id="e1713-113">Use the [Setup wizard](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="e1713-114">Кроме того, вы сможете добавлять новых пользователей или редактировать их в [Центре администрирования](view-policies-and-devices.md) и на [портале Intune](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span><span class="sxs-lookup"><span data-stu-id="e1713-114">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="e1713-115">Мастер установки также настроит основные параметры защиты от угроз и защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="e1713-115">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="e1713-116">Помимо параметров безопасности, в мастере установки вы можете повысить уровень безопасности, добавив следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e1713-116">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>


- <span data-ttu-id="e1713-117">**Защита от вредоносных программ в электронной почте**</span><span class="sxs-lookup"><span data-stu-id="e1713-117">**Email malware protection**</span></span>
- <span data-ttu-id="e1713-118">**Защита от фишинга ATP**</span><span class="sxs-lookup"><span data-stu-id="e1713-118">**ATP anti-phishing**</span></span>
- <span data-ttu-id="e1713-119">**Архивация на базе Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="e1713-119">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="e1713-120">**Azure Information Protection (план 1**)</span><span class="sxs-lookup"><span data-stu-id="e1713-120">**Azure Information Protection**</span></span>


<span data-ttu-id="e1713-121">Для этого см. [настройка дополнительных политик безопасности](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="e1713-121">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

<span data-ttu-id="e1713-122">См. также[10 основных способов защиты Microsoft 365 бизнес](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data), где содержится план рекомендаций в области безопасности.</span><span class="sxs-lookup"><span data-stu-id="e1713-122">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="e1713-123">Действие 3. Настройка устройств с Windows 10 и управление ими</span><span class="sxs-lookup"><span data-stu-id="e1713-123">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="e1713-124">После запуска мастера установки рекомендуется обеспечить защиту всех компьютеров с Windwos 10 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e1713-124">After you run the set up wizard, you will want to proctect all the Windwos 10 computers in your organization.</span></span>
  
- <span data-ttu-id="e1713-125">Windows 10 Профессиональная является[необходимым компонентом](pre-requisites-for-data-protection.md) для Microsoft 365 бизнес, но если у вас есть подписка на Windows 7 Профессиональная, Windows 8 Профессиональная или Windows 8.1 Профессиональная, вы можете [перейти на Windows 10 Профессиональная](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span><span class="sxs-lookup"><span data-stu-id="e1713-125">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
- <span data-ttu-id="e1713-126">Чтобы настроить политики для устройств с Windows 10, выполните действия, описанные в разделе [защита компьютеров с Windows 10](secure-win-10-pcs.md).</span><span class="sxs-lookup"><span data-stu-id="e1713-126">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="e1713-127">При присоединении устройства с Windows 10 к Azure AD применяются политики, установленные для компьютеров с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e1713-127">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="e1713-128">Для получения дополнительной информации см. [Настройка устройств с Windows для пользователей Microsoft 365 бизнес](set-up-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="e1713-128">[](set-up-windows-devices.md)Set up Windows devices for Microsoft 365 Business users</span></span>

## <a name="step-4-install-office-365-business"></a><span data-ttu-id="e1713-129">Действие 4. Установка Office 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="e1713-129">Step 4: Install Office 365 Business</span></span>
- <span data-ttu-id="e1713-130">Вы можете автоматически установить Office на устройствах с Windows с помощью[мастера установки](set-up.md#deploy-office-365-client-apps).</span><span class="sxs-lookup"><span data-stu-id="e1713-130">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="e1713-131">Разрешите пользователям [устанавливать приложения Office](https://docs.microsoft.com/office365/admin/setup/install-applications) для Windows и устройств.</span><span class="sxs-lookup"><span data-stu-id="e1713-131">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="e1713-132">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="e1713-132">Advanced</span></span>
- <span data-ttu-id="e1713-133">**Использование Autopilot для настройки новых устройств**</span><span class="sxs-lookup"><span data-stu-id="e1713-133">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="e1713-134">Вы можете воспользоваться[Windows Autopilot](add-autopilot-devices-and-profile.md)для автоматической предварительной настройки **новых** устройств с Windows 10 для пользователя, но возможно, что будет проще найти [партнера](https://www.microsoft.com/solution-providers/search), который сделает это за вас.</span><span class="sxs-lookup"><span data-stu-id="e1713-134">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="e1713-135">Кроме того, вы можете перейти в [магазин Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) и попросить эксперта по облачным технологиям настроить приобретаемые вами новые устройства.</span><span class="sxs-lookup"><span data-stu-id="e1713-135">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="e1713-136">**Доступ к локальным ресурсам**</span><span class="sxs-lookup"><span data-stu-id="e1713-136">**Access on-premises resources**</span></span>

     - <span data-ttu-id="e1713-137">Если в вашей организации используется локальная версия Windows Server Active Directory, вы можете настроить Microsoft 365 бизнес для защиты устройств с Windows 10, сохранив при этом доступ к локальным ресурсам, для которых требуется локальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e1713-137">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="e1713-138">Для такой настройки выполните действия, перечисленные в разделе [Разрешение Microsoft 365 бизнес управлять устройствами с Windows 10, присоединенными к домену](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="e1713-138">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="e1713-139">Это предпочтительный способ, а устройства в этом состоянии называются устройствами с гибридным присоединением к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e1713-139">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="e1713-140">Если в вашей организации есть локальная служба каталогов Active Directory, содержащая определенные локальные ресурсы (например, общие папки и принтеры), вы можете предоставить устройствам, присоединенным к Azure AD, доступ к этим ресурсам, выполнив действия, описанные в разделе [Доступ к локальным ресурсам с устройства, присоединенного к Azure AD, в Microsoft 365 бизнес](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="e1713-140">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e1713-141">См. также</span><span class="sxs-lookup"><span data-stu-id="e1713-141">See also</span></span>

[<span data-ttu-id="e1713-142">учебные видео по Microsoft 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="e1713-142">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
