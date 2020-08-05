---
title: Включение управления устройствами с Windows 10, подключенными к домену, в Microsoft 365 для бизнеса
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
description: Сведения о том, как включить Microsoft 365 для защиты локальных подключенных к Active Directory устройств с Windows 10 в всего несколько этапов.
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560850"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="4fb90-103">Управление устройствами с Windows 10, подключенными к домену, с помощью Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="4fb90-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="4fb90-104">Если ваша организация использует локальную службу Windows Server Active Directory, вы можете настроить Microsoft 365 Business Premium для защиты устройств Windows 10, сохраняя доступ к локальным ресурсам, требующим локальной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4fb90-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="4fb90-105">Чтобы настроить эту защиту, можно внедрить **гибридные подключенные устройства Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="4fb90-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="4fb90-106">Эти устройства присоединяются как к локальной службе Active Directory, так и к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4fb90-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="4fb90-107">В этом видеоролике описаны действия, которые необходимо выполнить для наиболее распространенного сценария, который также содержит подробные инструкции.</span><span class="sxs-lookup"><span data-stu-id="4fb90-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="4fb90-108">Прежде чем приступить к работе, убедитесь, что выполнены следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4fb90-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="4fb90-109">Синхронизация пользователей с Azure AD с помощью Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="4fb90-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="4fb90-110">Выполните синхронизацию подразделения Azure AD Connect (OU).</span><span class="sxs-lookup"><span data-stu-id="4fb90-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="4fb90-111">Убедитесь, что у всех пользователей домена, которые вы синхронизируете, есть лицензии на Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="4fb90-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="4fb90-112">В этой статье приведены инструкции по [синхронизации пользователей домена с корпорацией Майкрософт](manage-domain-users.md) .</span><span class="sxs-lookup"><span data-stu-id="4fb90-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="4fb90-113">1. Проверка полномочий MDM в Intune</span><span class="sxs-lookup"><span data-stu-id="4fb90-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="4fb90-114">Перейдите к [диспетчеру конечной точки](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) и на странице Microsoft Intune выберите **Регистрация устройств**, а затем на странице **обзора** убедитесь, что **центр управления MDM** является **Intune**.</span><span class="sxs-lookup"><span data-stu-id="4fb90-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="4fb90-115">Если для **MDM Authority** задано значение **None (нет**), щелкните **центр MDM** , чтобы задать для него значение **Intune**.</span><span class="sxs-lookup"><span data-stu-id="4fb90-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="4fb90-116">Если в качестве **шлюза** **MDM** используется **Microsoft Office 365**, перейдите на страницу  >  **Регистрация устройств** и воспользуйтесь диалоговым окном **Добавление центра MDM** справа для добавления центра **Intune MDM** (диалоговое окно **Add MDM Authority** доступно только в том случае, если для шлюза **MDM** установлено значение Microsoft Office 365).</span><span class="sxs-lookup"><span data-stu-id="4fb90-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="4fb90-117">2. Убедитесь, что служба Azure AD включена для присоединения компьютеров</span><span class="sxs-lookup"><span data-stu-id="4fb90-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="4fb90-118">Перейдите в центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> и выберите **Azure Active Directory** (выберите Показать все, если Azure Active Directory не отображается) в списке **центры администрирования** .</span><span class="sxs-lookup"><span data-stu-id="4fb90-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="4fb90-119">В **центре администрирования Azure Active Directory**откройте **Azure Active Directory** , выберите пункт **устройства** и затем **Параметры устройства**.</span><span class="sxs-lookup"><span data-stu-id="4fb90-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="4fb90-120">Проверка того, что**пользователи могут присоединяться к устройствам для Azure AD** .</span><span class="sxs-lookup"><span data-stu-id="4fb90-120">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="4fb90-121">Чтобы включить всех пользователей, задайте значение **ALL**.</span><span class="sxs-lookup"><span data-stu-id="4fb90-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="4fb90-122">Чтобы включить определенных пользователей, установите **флажок** разрешить определенную группу пользователей.</span><span class="sxs-lookup"><span data-stu-id="4fb90-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="4fb90-123">Добавьте в [группу безопасности](../admin/create-groups/create-groups.md)требуемых пользователей домена, синхронизированных в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4fb90-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="4fb90-124">Выберите **пункт Выбрать группы** , чтобы включить область пользователя MDM для этой группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="4fb90-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="4fb90-125">3. Убедитесь, что служба Azure AD включена для MDM</span><span class="sxs-lookup"><span data-stu-id="4fb90-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="4fb90-126">Перейдите в центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> и выберите пункт выбрать **конечную точку манажемен**t (выберите **Показать все** , если **Диспетчер конечных точек** не отображается).</span><span class="sxs-lookup"><span data-stu-id="4fb90-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="4fb90-127">В **центре администрирования Microsoft Endpoint Manager**перейдите к разделу **устройства**, подаче заявки на  >  **Windows**  >  **регистрацию Windows Windows**для  >  **автоматической регистрации**.</span><span class="sxs-lookup"><span data-stu-id="4fb90-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="4fb90-128">Убедитесь, что область пользователя MDM включена.</span><span class="sxs-lookup"><span data-stu-id="4fb90-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="4fb90-129">Чтобы зарегистрировать все компьютеры, установите для параметра **ALL** значение автоматическая регистрация всех пользовательских компьютеров, присоединенных к Azure AD и новым компьютерам, когда пользователи добавляют рабочую учетную запись в Windows.</span><span class="sxs-lookup"><span data-stu-id="4fb90-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="4fb90-130">Установите значение **, чтобы** зарегистрировать компьютеры определенной группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="4fb90-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="4fb90-131">Добавьте в [группу безопасности](../admin/create-groups/create-groups.md)требуемых пользователей домена, синхронизированных в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4fb90-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="4fb90-132">Выберите **пункт Выбрать группы** , чтобы включить область пользователя MDM для этой группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="4fb90-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="4fb90-133">4. создание необходимых ресурсов</span><span class="sxs-lookup"><span data-stu-id="4fb90-133">4. Create the required resources</span></span> 

<span data-ttu-id="4fb90-134">Выполнение необходимых задач для [настройки гибридного объединения Azure AD](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) было упрощено с помощью командлета [Initialize – секмгмсибирддевицеенроллмент](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) , найденного в модуле [секмгмт](https://www.powershellgallery.com/packages/SecMgmt) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fb90-134">Performing the required tasks to [configure hybrid Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="4fb90-135">При вызове этого командлета будет создана и настроена необходимая точка подключения службы и групповая политика.</span><span class="sxs-lookup"><span data-stu-id="4fb90-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="4fb90-136">Вы можете установить этот модуль, вызвав следующий экземпляр PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4fb90-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="4fb90-137">Рекомендуется установить этот модуль на Windows Server, на котором выполняется Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="4fb90-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="4fb90-138">Для создания необходимой точки подключения службы и групповой политики необходимо вызвать командлет [Initialize – секмгмсибирддевицеенроллмент](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) .</span><span class="sxs-lookup"><span data-stu-id="4fb90-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="4fb90-139">При выполнении этой задачи вам потребуются учетные данные глобального администратора Microsoft 365 Бизнес Premium.</span><span class="sxs-lookup"><span data-stu-id="4fb90-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="4fb90-140">Когда вы будете готовы создать ресурсы, вызовите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4fb90-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="4fb90-141">Первая команда устанавливает подключение к Microsoft Cloud и при появлении соответствующего запроса укажите учетные данные глобального администратора Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="4fb90-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="4fb90-142">5. Связывание групповой политики</span><span class="sxs-lookup"><span data-stu-id="4fb90-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="4fb90-143">В консоли управления групповыми политиками щелкните правой кнопкой мыши расположение, в котором нужно связать политику, и выберите пункт *связать существующий объект групповой политики...* в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="4fb90-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="4fb90-144">Выберите политику, созданную на предыдущем шаге, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4fb90-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="4fb90-145">Получение последних административных шаблонов</span><span class="sxs-lookup"><span data-stu-id="4fb90-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="4fb90-146">Если вы не видите политику **включения автоматической регистрации MDM с использованием учетных данных Azure AD по умолчанию**, возможно, у вас нет ADMX, установленного для Windows 10, версии 1803, версии 1809 или версии 1903.</span><span class="sxs-lookup"><span data-stu-id="4fb90-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="4fb90-147">Чтобы устранить эту проблему, выполните указанные ниже действия (Примечание: последние версии MDM. ADMX совместимы с предыдущими).</span><span class="sxs-lookup"><span data-stu-id="4fb90-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="4fb90-148">Загрузка: [Административные шаблоны (ADMX) для Windows 10 май 2019 обновление (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span><span class="sxs-lookup"><span data-stu-id="4fb90-148">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="4fb90-149">Установите пакет на основном контроллере домена (PDC).</span><span class="sxs-lookup"><span data-stu-id="4fb90-149">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="4fb90-150">Навигация в зависимости от версии папки: **C:\Program Files (x86) \Microsoft Group полици\виндовс 10 май 2019 обновление (1903) v3**.</span><span class="sxs-lookup"><span data-stu-id="4fb90-150">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="4fb90-151">Переименуйте папку " **определения политик** " в указанном выше пути в **Папка PolicyDefinitions**.</span><span class="sxs-lookup"><span data-stu-id="4fb90-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="4fb90-152">Скопируйте папку **Папка PolicyDefinitions** в **к:\виндовс\сисвол\домаин\полиЦиес**.</span><span class="sxs-lookup"><span data-stu-id="4fb90-152">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="4fb90-153">Если вы планируете использовать централизованное хранилище политик для всего домена, добавьте в него содержимое папка PolicyDefinitions.</span><span class="sxs-lookup"><span data-stu-id="4fb90-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="4fb90-154">Чтобы политика была доступна, перезапустите основной контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="4fb90-154">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="4fb90-155">Эта процедура будет работать и для всех последующих версий.</span><span class="sxs-lookup"><span data-stu-id="4fb90-155">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="4fb90-156">На этом шаге вы увидите, что политика **включает автоматическую регистрацию MDM, используя доступные учетные данные Azure AD по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="4fb90-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>
