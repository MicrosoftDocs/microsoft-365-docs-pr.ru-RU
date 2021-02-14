---
title: Управление устройствами с Windows 10, которые присоединились к домену, с помощью Microsoft 365 для бизнеса
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Узнайте, как включить Microsoft 365 для защиты локальных устройств с Windows 10, которые присоединились к Active Directory, всего за несколько шагов.
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560850"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="37ea9-103">Управление устройствами с Windows 10, которые присоединились к домену, с помощью Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="37ea9-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="37ea9-104">Если в вашей организации используется локальная служба Windows Server Active Directory, вы можете настроить Microsoft 365 бизнес премиум для защиты устройств с Windows 10, сохранив при этом доступ к локальным ресурсам, которые требуют локальной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="37ea9-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="37ea9-105">Чтобы настроить эту защиту, можно реализовать гибридные устройства, **присоединимые к Azure AD.**</span><span class="sxs-lookup"><span data-stu-id="37ea9-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="37ea9-106">Эти устройства присоединяются к локальной службе Active Directory и Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="37ea9-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="37ea9-107">В этом видео описаны действия по его настройкам для наиболее распространенных сценариев, которые также подробно описаны в последующих действиях.</span><span class="sxs-lookup"><span data-stu-id="37ea9-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="37ea9-108">Перед началом работы выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="37ea9-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="37ea9-109">Синхронизация пользователей с Azure AD с помощью Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="37ea9-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="37ea9-110">Завершите синхронизацию подразделения Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="37ea9-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="37ea9-111">Убедитесь, что все синхронизированные пользователи домена имеют лицензии на Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="37ea9-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="37ea9-112">См. действия по синхронизации [пользователей домена с Корпорацией](manage-domain-users.md) Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="37ea9-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="37ea9-113">1. Проверка MDM Authority в Intune</span><span class="sxs-lookup"><span data-stu-id="37ea9-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="37ea9-114">Перейдите [в Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) и на странице Microsoft Intune  выберите регистрацию **устройств,** а затем на странице "Обзор" убедитесь, что в **MDM** есть **Intune.**</span><span class="sxs-lookup"><span data-stu-id="37ea9-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="37ea9-115">Если **полномочия MDM не**  **установлены,** щелкните его, чтобы установить для него **intune.**</span><span class="sxs-lookup"><span data-stu-id="37ea9-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="37ea9-116">Если для **MDM** установлено право **Microsoft Office 365,** перейдите на сайт "Регистрация устройств" и используйте диалоговое окно "Добавление полномочий MDM" справа для добавления полномочий Intune MDM (диалоговое окно "Добавление полномочий MDM" доступно, только если для управления  >   **MDM** установлено Microsoft Office 365).   </span><span class="sxs-lookup"><span data-stu-id="37ea9-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="37ea9-117">2. Убедитесь, что azure AD включен для присоединения к компьютерам</span><span class="sxs-lookup"><span data-stu-id="37ea9-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="37ea9-118">Перейдите в Центр администрирования и выберите <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Azure Active Directory** (выберите "Показать все", если Azure Active Directory не отображается) в списке центров **администрирования.**</span><span class="sxs-lookup"><span data-stu-id="37ea9-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="37ea9-119">В Центре **администрирования Azure Active Directory** перейдите в **Azure Active Directory,** выберите **"Устройства",** а затем **параметры устройства.**</span><span class="sxs-lookup"><span data-stu-id="37ea9-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="37ea9-120">Проверка **того, что пользователи могут присоединять устройства к Azure AD,** включена</span><span class="sxs-lookup"><span data-stu-id="37ea9-120">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="37ea9-121">Чтобы включить всех пользователей, установите **для** них все.</span><span class="sxs-lookup"><span data-stu-id="37ea9-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="37ea9-122">Чтобы включить определенных пользователей, установите **"Выбрано",** чтобы включить определенную группу пользователей.</span><span class="sxs-lookup"><span data-stu-id="37ea9-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="37ea9-123">Добавьте нужных пользователей домена, синхронизированных в Azure AD, в [группу безопасности.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="37ea9-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="37ea9-124">Выберите **"Выбрать группы",** чтобы включить область пользователей MDM для этой группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="37ea9-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="37ea9-125">3. Убедитесь, что Azure AD включен для MDM</span><span class="sxs-lookup"><span data-stu-id="37ea9-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="37ea9-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span><span class="sxs-lookup"><span data-stu-id="37ea9-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="37ea9-127">В Центре **администрирования Microsoft Endpoint Manager** перейдите на **устройства с** автоматической регистрацией  >    >  **Windows.**  >  </span><span class="sxs-lookup"><span data-stu-id="37ea9-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="37ea9-128">Убедитесь, что область пользователя MDM включена.</span><span class="sxs-lookup"><span data-stu-id="37ea9-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="37ea9-129">Чтобы зарегистрировать все компьютеры, установите для этого все, чтобы автоматически зарегистрировать все компьютеры пользователей, которые присоединились к Azure AD, и новые компьютеры при добавлении пользователями учетной записи в Windows. </span><span class="sxs-lookup"><span data-stu-id="37ea9-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="37ea9-130">Установите для **некоторых** зарегистрировать компьютеры определенной группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="37ea9-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="37ea9-131">Добавьте нужных пользователей домена, синхронизированных в Azure AD, в [группу безопасности.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="37ea9-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="37ea9-132">Выберите **"Выбрать группы",** чтобы включить область пользователей MDM для этой группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="37ea9-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="37ea9-133">4. Создайте необходимые ресурсы</span><span class="sxs-lookup"><span data-stu-id="37ea9-133">4. Create the required resources</span></span> 

<span data-ttu-id="37ea9-134">Выполнение необходимых задач для настройки гибридного пользования [Azure AD](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) было упрощено с помощью командлета [Initialize-SecMgmtHybirdDeviceEnrollment,](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) найденного в модуле [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37ea9-134">Performing the required tasks to [configure hybrid Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="37ea9-135">При вызове этого cmdlet он создаст и настроит необходимую точку подключения службы и групповую политику.</span><span class="sxs-lookup"><span data-stu-id="37ea9-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="37ea9-136">Чтобы установить этот модуль, вы можете с помощью экземпляра PowerShell:</span><span class="sxs-lookup"><span data-stu-id="37ea9-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="37ea9-137">Рекомендуется установить этот модуль на windows Server с Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="37ea9-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="37ea9-138">Чтобы создать необходимую точку подключения службы и групповую политику, вы вызываете [cmdlet Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)</span><span class="sxs-lookup"><span data-stu-id="37ea9-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="37ea9-139">При выполнении этой задачи вам потребуется учетные данные глобального администратора Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="37ea9-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="37ea9-140">Когда вы будете готовы создать ресурсы, вы можете вызвать следующее:</span><span class="sxs-lookup"><span data-stu-id="37ea9-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="37ea9-141">Первая команда установит подключение к Облаку Майкрософт, и при запросе укажите учетные данные глобального администратора Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="37ea9-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="37ea9-142">5. Связывать групповую политику</span><span class="sxs-lookup"><span data-stu-id="37ea9-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="37ea9-143">В консоли управления групповыми политиками (GPMC) щелкните правой кнопкой мыши расположение, в котором нужно связать политику, и выберите ссылку на существующий *GPO...* в контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="37ea9-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="37ea9-144">Выберите политику, созданную на этапе выше, и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="37ea9-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="37ea9-145">Получить последние административные шаблоны</span><span class="sxs-lookup"><span data-stu-id="37ea9-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="37ea9-146">Если вы не видите политику "Включить автоматическую регистрацию **в MDM** с использованием учетных данных Azure AD по умолчанию", возможно, У вас нет ADMX, установленной для Windows 10 версии 1803, версии 1809 или версии 1903.</span><span class="sxs-lookup"><span data-stu-id="37ea9-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="37ea9-147">Чтобы устранить проблему, выполните следующие действия (обратите внимание: последняя версия MDM.admx совместима с обратной совместимость):</span><span class="sxs-lookup"><span data-stu-id="37ea9-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="37ea9-148">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span><span class="sxs-lookup"><span data-stu-id="37ea9-148">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="37ea9-149">Установите пакет на основном контроллере домена (PDC).</span><span class="sxs-lookup"><span data-stu-id="37ea9-149">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="37ea9-150">Перейдите в зависимости от версии папки: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span><span class="sxs-lookup"><span data-stu-id="37ea9-150">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="37ea9-151">Переименуем папку **"Определения политик"** в вышеуказанном пути в **PolicyDefinitions.**</span><span class="sxs-lookup"><span data-stu-id="37ea9-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="37ea9-152">**Скопируйте папку PolicyDefinitions** **в папку C:\Windows\SYSVOL\domain\Policies.**</span><span class="sxs-lookup"><span data-stu-id="37ea9-152">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="37ea9-153">Если вы планируете использовать центральное хранилище политик для всего домена, добавьте в нее содержимое policyDefinitions.</span><span class="sxs-lookup"><span data-stu-id="37ea9-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="37ea9-154">Перезапустите основной контроллер домена, чтобы политика была доступна.</span><span class="sxs-lookup"><span data-stu-id="37ea9-154">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="37ea9-155">Эта процедура также будет работать для любой будущей версии.</span><span class="sxs-lookup"><span data-stu-id="37ea9-155">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="37ea9-156">На этом этапе вы сможете увидеть политику "Включить автоматическую регистрацию **в MDM"** с помощью учетных данных Azure AD по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="37ea9-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>
