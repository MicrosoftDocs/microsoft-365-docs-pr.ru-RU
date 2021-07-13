---
title: Включить доступ к Windows 10 с помощью Microsoft 365 для бизнеса
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
description: Узнайте, как Microsoft 365 защитить локальные устройства с Windows 10 active-Directory.
ms.openlocfilehash: 9cc7ca01cec667465e9114083fecdc56ef4e7ce7
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393386"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="1c6cb-103">Включить устройства с Windows 10 с помощью Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="1c6cb-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="1c6cb-104">Если организация использует Windows Server Active Directory локально, вы можете настроить Microsoft 365 бизнес премиум для защиты Windows 10 устройств, сохраняя при этом доступ к локальным ресурсам, которые требуют локальной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="1c6cb-105">Чтобы настроить эту защиту, можно реализовать устройства **hybrid Azure AD.**</span><span class="sxs-lookup"><span data-stu-id="1c6cb-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="1c6cb-106">Эти устройства присоединяются как к локальному Active Directory, так и к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

## <a name="watch-configure-hybrid-azure-active-directory-join"></a><span data-ttu-id="1c6cb-107">Watch: Настройка гибридной Azure Active Directory присоединиться</span><span class="sxs-lookup"><span data-stu-id="1c6cb-107">Watch: Configure Hybrid Azure Active Directory join</span></span>

<span data-ttu-id="1c6cb-108">В этом видео описываются действия по настройкам этого сценария для наиболее распространенных сценариев, которые также описаны в последующих действиях.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-108">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a><span data-ttu-id="1c6cb-109">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="1c6cb-109">Before you begin</span></span>

- <span data-ttu-id="1c6cb-110">Синхронизация пользователей с Azure AD с azure AD Подключение.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-110">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="1c6cb-111">Выполните синхронизацию Подключение Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-111">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="1c6cb-112">Убедитесь, что все синхронизированные пользователи домена имеют лицензии на Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-112">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="1c6cb-113">См. [в этой записи Синхронизация](manage-domain-users.md) действий пользователей домена с Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-113">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="1c6cb-114">1. Проверка управления MDM в Intune</span><span class="sxs-lookup"><span data-stu-id="1c6cb-114">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="1c6cb-115">Перейдите [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) и на странице Microsoft Intune, выберите регистрацию **устройства,** а затем на странице **Обзор** убедитесь, что **полномочия MDM** **intune**.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-115">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="1c6cb-116">Если **полномочия MDM нет,** нажмите кнопку **MDM,** чтобы настроить его **на Intune**. </span><span class="sxs-lookup"><span data-stu-id="1c6cb-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="1c6cb-117">Если полномочия **MDM** **Microsoft Office 365,** перейдите на устройства Для регистрации устройств и используйте диалоговое окно Add MDM authority справа для добавления полномочий  >   **Intune MDM** (диалоговое окно **Add MDM Authority** доступно только в том случае, если для управления **MDM** установлено Microsoft Office 365). </span><span class="sxs-lookup"><span data-stu-id="1c6cb-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="1c6cb-118">2. Проверка включения Azure AD для присоединения к компьютерам</span><span class="sxs-lookup"><span data-stu-id="1c6cb-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="1c6cb-119">Перейдите в центр администрирования и выберите Azure Active Directory (выберите Показать все, если Azure Active Directory не отображается) в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> списке **центров администрирования.** </span><span class="sxs-lookup"><span data-stu-id="1c6cb-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="1c6cb-120">В центре **Azure Active Directory администрирования** перейдите **в Azure Active Directory,** выберите **параметры Устройств** и **устройств.**</span><span class="sxs-lookup"><span data-stu-id="1c6cb-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="1c6cb-121">Проверка **того, что пользователи могут присоединяться к устройствам в Azure AD,** включена</span><span class="sxs-lookup"><span data-stu-id="1c6cb-121">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="1c6cb-122">Чтобы включить всех пользователей, установите **все**.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="1c6cb-123">Чтобы включить определенных пользователей, **установите выбранный,** чтобы включить определенную группу пользователей.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="1c6cb-124">Добавьте нужных пользователей домена, синхронизированных в Azure AD, в [группу безопасности.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="1c6cb-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="1c6cb-125">Выберите **выберите группы,** чтобы включить область пользовательского интерфейса MDM для этой группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="1c6cb-126">3. Проверка включения Azure AD для MDM</span><span class="sxs-lookup"><span data-stu-id="1c6cb-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="1c6cb-127">Перейдите в центр администрирования и выберите <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> выберите **endpoint Managemen** t (выберите **Показать** все, **если** Endpoint Manager не отображается)</span><span class="sxs-lookup"><span data-stu-id="1c6cb-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="1c6cb-128">В центре **Microsoft Endpoint Manager администрирования** перейдите к **устройствам** Windows  >    >  **Windows**  >  **регистрации.**</span><span class="sxs-lookup"><span data-stu-id="1c6cb-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="1c6cb-129">Проверка включенной пользовательской области MDM.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="1c6cb-130">Чтобы зарегистрироваться на всех  компьютерах, установите для всех автоматически зачислить все пользовательские компьютеры, которые присоединяются к Azure AD и новым компьютерам, когда пользователи добавляют учетную запись в Windows.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="1c6cb-131">Установите для **некоторых** для регистрации компьютеров определенной группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="1c6cb-132">Добавьте нужных пользователей домена, синхронизированных в Azure AD, в [группу безопасности.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="1c6cb-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="1c6cb-133">Выберите **выберите группы,** чтобы включить область пользовательского интерфейса MDM для этой группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="1c6cb-134">4. Создание необходимых ресурсов</span><span class="sxs-lookup"><span data-stu-id="1c6cb-134">4. Create the required resources</span></span> 

<span data-ttu-id="1c6cb-135">Выполнение необходимых задач по настройке гибридного присоединяния [Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) было упрощено с помощью командлета [Initialize-SecMgmtHybirdDeviceEnrollment,](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) найденного в модуле [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-135">Performing the required tasks to [configure hybrid Azure AD join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="1c6cb-136">При вызове этого комлета создается и настраивается необходимая точка подключения к службе и политика группы.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-136">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="1c6cb-137">Этот модуль можно установить, созовав следующее из экземпляра PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1c6cb-137">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="1c6cb-138">Рекомендуется установить этот модуль на сервере Windows Azure AD Подключение.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-138">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="1c6cb-139">Чтобы создать требуемую точку подключения к службе и групповую политику, необходимо вызвать групповую группу [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)</span><span class="sxs-lookup"><span data-stu-id="1c6cb-139">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="1c6cb-140">При выполнении этой задачи Microsoft 365 бизнес премиум глобальные учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-140">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="1c6cb-141">Когда вы будете готовы создать ресурсы, привяйте следующие ссылки:</span><span class="sxs-lookup"><span data-stu-id="1c6cb-141">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="1c6cb-142">Первая команда установит подключение к облаку Майкрософт, а когда вам будет предложено, укажите Microsoft 365 бизнес премиум учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-142">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="1c6cb-143">5. Ссылка групповой политики</span><span class="sxs-lookup"><span data-stu-id="1c6cb-143">5. Link the Group Policy</span></span>

1. <span data-ttu-id="1c6cb-144">В консоли управления групповой политикой (GPMC) щелкните правой кнопкой мыши по расположению, где необходимо связать политику, и выберите Ссылку существующего *GPO...* из контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-144">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="1c6cb-145">Выберите политику, созданную на вышеуказанной шаге, а затем нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-145">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="1c6cb-146">Получить последние административные шаблоны</span><span class="sxs-lookup"><span data-stu-id="1c6cb-146">Get the latest Administrative Templates</span></span>

<span data-ttu-id="1c6cb-147">Если вы не видите политику Включить автоматическую регистрацию **MDM** с помощью учетных данных Azure AD по умолчанию, это может быть из-за того, что у вас нет установки ADMX для Windows 10 версии 1803 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-147">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, or later.</span></span> <span data-ttu-id="1c6cb-148">Чтобы устранить проблему, выполните следующие действия (Примечание: последняя версия MDM.admx совместима с обратной совместимость):</span><span class="sxs-lookup"><span data-stu-id="1c6cb-148">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1. <span data-ttu-id="1c6cb-149">Загрузка: [Административные шаблоны (.admx) для Windows 10 2020 обновления (20H2).](https://www.microsoft.com/download/102157)</span><span class="sxs-lookup"><span data-stu-id="1c6cb-149">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span></span>
2. <span data-ttu-id="1c6cb-150">Установите пакет на контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-150">Install the package on a Domain Controller.</span></span>
3. <span data-ttu-id="1c6cb-151">Перейдите в зависимости от версии административных шаблонов в папку: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 октябрь 2020 г. Обновление (20H2)**.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-151">Navigate, depending on the Administrative Templates version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span></span>
4. <span data-ttu-id="1c6cb-152">Переименовать **папку Определения политики** в вышеуказанном пути в **PolicyDefinitions**.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-152">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5. <span data-ttu-id="1c6cb-153">Скопируйте **папку PolicyDefinitions** в свою долю SYSVOL по умолчанию, расположенную в **C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-153">Copy the **PolicyDefinitions** folder to your SYSVOL share, by default located at **C:\Windows\SYSVOL\domain\Policies**.</span></span>
   - <span data-ttu-id="1c6cb-154">Если вы планируете использовать центральный магазин политик для всего домена, добавьте туда содержимое PolicyDefinitions.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-154">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6. <span data-ttu-id="1c6cb-155">Если у вас есть несколько контроллеров домена, подождите, пока SYSVOL будет реплицировать доступные политики.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-155">In case you have several Domain Controllers, wait for SYSVOL to replicate for the policies to be available.</span></span> <span data-ttu-id="1c6cb-156">Эта процедура будет работать и для любой будущей версии административных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-156">This procedure will work for any future version of the Administrative Templates as well.</span></span>

<span data-ttu-id="1c6cb-157">На этом этапе вы сможете увидеть политику Включить автоматическую регистрацию **MDM** с помощью доступных учетных данных Azure AD по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-157">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

## <a name="related-content"></a><span data-ttu-id="1c6cb-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="1c6cb-158">Related content</span></span>

<span data-ttu-id="1c6cb-159">[Синхронизация пользователей домена с Microsoft 365](manage-domain-users.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="1c6cb-159">[Synchronize domain users to Microsoft 365](manage-domain-users.md) (article)</span></span>\
<span data-ttu-id="1c6cb-160">[Создание группы в центре администрирования](../admin/create-groups/create-groups.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="1c6cb-160">[Create a group in the admin center](../admin/create-groups/create-groups.md) (article)</span></span>\
<span data-ttu-id="1c6cb-161">[Руководство. Настройка гибридного Azure Active Directory для управляемых доменов](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="1c6cb-161">[Tutorial: Configure hybrid Azure Active Directory join for managed domains](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (article)</span></span>