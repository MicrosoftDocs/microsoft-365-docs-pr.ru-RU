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
ms.openlocfilehash: 425c465262c266ca764ae8c7a52130903fa635a5
ms.sourcegitcommit: 8fda7852b2a5baa92b8a365865b014ea6d100bbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "39812785"
---
# <a name="overview-of-setup"></a><span data-ttu-id="2f567-103">Обзор настройки</span><span class="sxs-lookup"><span data-stu-id="2f567-103">Overview of setup</span></span>

<span data-ttu-id="2f567-104">Большинство действий по настройке можно выполнить в мастере установки, но Кроме того, указаны другие параметры.</span><span class="sxs-lookup"><span data-stu-id="2f567-104">Most of the setup steps can be done in the setup wizard, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="2f567-105">Шаг 1: Добавление домена и пользователей</span><span class="sxs-lookup"><span data-stu-id="2f567-105">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="2f567-106">**[Добавьте свой домен](set-up.md#add-your-domain-to-personalize-sign-in)** (если вы приобрели свой домен во время [регистрации](sign-up.md), этот шаг уже выполнен).</span><span class="sxs-lookup"><span data-stu-id="2f567-106">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="2f567-107">**Добавление пользователей**.</span><span class="sxs-lookup"><span data-stu-id="2f567-107">**Add users**.</span></span> <span data-ttu-id="2f567-108">Вы можете добавить пользователей одним из трех способов:</span><span class="sxs-lookup"><span data-stu-id="2f567-108">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="2f567-109">В [мастере](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="2f567-109">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="2f567-110">Используйте синхронизацию службы каталогов для [добавления пользователей с помощью Azure AD Connect,](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) если у вас есть локальная служба Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2f567-110">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="2f567-111">Вы также можете [Добавить пользователей позже](add-users-m365b.md) в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="2f567-111">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="2f567-112">Шаг 2: Настройка политик безопасности и настройка устройств</span><span class="sxs-lookup"><span data-stu-id="2f567-112">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="2f567-113">Используйте [Мастер установки](set-up.md#protect-your-organization) для настройки политик устройств.</span><span class="sxs-lookup"><span data-stu-id="2f567-113">Use the [Setup wizard](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="2f567-114">Вы также можете добавить дополнительные или изменить их позже в [центре администрирования](view-policies-and-devices.md) и [портале Intune](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span><span class="sxs-lookup"><span data-stu-id="2f567-114">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="2f567-115">Мастер установки также настроит основные параметры защиты от угроз и защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="2f567-115">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="2f567-116">В дополнение к параметрам безопасности в мастере установки вы можете повысить уровень безопасности, добавив следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2f567-116">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

      - <span data-ttu-id="2f567-117">**Защита от вредоносных программ электронной почты**</span><span class="sxs-lookup"><span data-stu-id="2f567-117">**Email malware protection**</span></span>
      - <span data-ttu-id="2f567-118">**Защита от фишинга ATP**</span><span class="sxs-lookup"><span data-stu-id="2f567-118">**ATP anti-phishing**</span></span>
      - <span data-ttu-id="2f567-119">**Архивация на базе Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="2f567-119">**Exchange Online Archiving**</span></span>
      - <span data-ttu-id="2f567-120">**Azure Information Protection (Plan1**)</span><span class="sxs-lookup"><span data-stu-id="2f567-120">**Azure Information Protection (Plan1**)</span></span>

          <span data-ttu-id="2f567-121">Чтобы приступить к работе, [Настройте дополнительные политики безопасности](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="2f567-121">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

        <span data-ttu-id="2f567-122">Кроме того, вы можете ознакомиться с десятью рекомендациями по [обеспечению безопасности Microsoft 365 для бизнеса](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) в плане рекомендаций по обеспечению безопасности.</span><span class="sxs-lookup"><span data-stu-id="2f567-122">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="2f567-123">Шаг 3: Настройка устройств с Windows 10 и управление ими</span><span class="sxs-lookup"><span data-stu-id="2f567-123">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="2f567-124">После запуска мастера настройки вам потребуется проктект все компьютеры в Организации Виндвос 10.</span><span class="sxs-lookup"><span data-stu-id="2f567-124">After you run the set up wizard, you will want to proctect all the Windwos 10 computers in your organization.</span></span>
  
- <span data-ttu-id="2f567-125">Windows 10 профессиональная является [необходимым условием](pre-requisites-for-data-protection.md) для Microsoft 365 Business, но если у вас есть Windows 7 Профессиональная, Windows 8 Профессиональная или Windows 8,1 Pro, ваша подписка позволит вам выполнить [обновление до Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span><span class="sxs-lookup"><span data-stu-id="2f567-125">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
- <span data-ttu-id="2f567-126">Выполните действия, описанные в статье [Защита компьютеров с Windows 10](secure-win-10-pcs.md) , чтобы настроить политики для устройств с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2f567-126">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="2f567-127">Когда вы присоединяете устройство Windows 10 к Azure AD, политики, заданные для компьютеров с Windows 10, будут применены к нему.</span><span class="sxs-lookup"><span data-stu-id="2f567-127">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="2f567-128">Дополнительную информацию можно узнать в [статье Настройка устройств Windows для Microsoft 365 Business Users](set-up-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="2f567-128">For more information, see [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-office-365-business"></a><span data-ttu-id="2f567-129">Шаг 4: установка Office 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2f567-129">Step 4: Install Office 365 Business</span></span>
- <span data-ttu-id="2f567-130">Вы можете автоматически установить Office на устройствах с Windows с помощью [мастера установки](set-up.md#deploy-office-365-client-apps).</span><span class="sxs-lookup"><span data-stu-id="2f567-130">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="2f567-131">Разрешите пользователям [устанавливать приложения Office](https://docs.microsoft.com/office365/admin/setup/install-applications) для Windows и устройств.</span><span class="sxs-lookup"><span data-stu-id="2f567-131">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="2f567-132">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="2f567-132">Advanced</span></span>
- <span data-ttu-id="2f567-133">**Использование автопилота для настройки новых устройств**</span><span class="sxs-lookup"><span data-stu-id="2f567-133">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="2f567-134">Вы можете использовать [автопилот Windows](add-autopilot-devices-and-profile.md) для автоматической предварительной настройки **новых** устройств с Windows 10 для пользователя, но вам может быть проще получить [партнера](https://www.microsoft.com/solution-providers/search) , который может сделать это.</span><span class="sxs-lookup"><span data-stu-id="2f567-134">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="2f567-135">Вы также можете перейти в [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)и попросить эксперта по облачным технологиям настроить новые устройства, которые вы приобрели.</span><span class="sxs-lookup"><span data-stu-id="2f567-135">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="2f567-136">**Доступ к локальным ресурсам**</span><span class="sxs-lookup"><span data-stu-id="2f567-136">**Access on-premises resources**</span></span>

     - <span data-ttu-id="2f567-137">Если ваша организация использует локальную службу Windows Server Active Directory, вы можете настроить Microsoft 365 бизнес для защиты устройств с Windows 10, сохраняя доступ к локальным ресурсам, требующим локальной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2f567-137">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="2f567-138">Выполните действия, описанные в разделе " [Включение устройств, присоединенных к домену" с Windows 10 для управления в Microsoft 365 Business](manage-windows-devices.md) , чтобы настроить.</span><span class="sxs-lookup"><span data-stu-id="2f567-138">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="2f567-139">Это рекомендуемый метод, и устройства в этом состоянии называются гибридными подключенными устройствами Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2f567-139">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="2f567-140">Если в вашей организации есть локальная служба Active Directory, содержащая некоторые локальные ресурсы (например, файловые ресурсы и принтеры), вы можете предоставить подключенным устройствам Azure AD доступ к этим ресурсам, выполнив действия, описанные здесь: [доступ к локальным ресурсам из устройства, подключенного к Azure AD, в Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="2f567-140">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2f567-141">См. также</span><span class="sxs-lookup"><span data-stu-id="2f567-141">See also</span></span>

[<span data-ttu-id="2f567-142">Видеоролики по бизнес-обучению Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2f567-142">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
