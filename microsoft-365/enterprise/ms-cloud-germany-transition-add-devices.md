---
title: Дополнительные сведения об устройстве для миграции из Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: Сводка. Дополнительные сведения об устройствах в службах при переходе с Microsoft Cloud в Германии (Microsoft Cloud Deutschland) на службы Office 365 в новом регионе центра обработки данных в Германии.
ms.openlocfilehash: 151fcac882dc91d96df3ece000c28d1a7abe1d1f
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780300"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="ee861-103">Дополнительные сведения об устройстве для миграции из Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="ee861-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="ee861-104">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="ee861-104">Frequently asked questions</span></span>

<span data-ttu-id="ee861-105">**Как узнать, затронута ли моя организация?**</span><span class="sxs-lookup"><span data-stu-id="ee861-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="ee861-106">Администраторам следует проверить, есть ли `https://portal.microsoftazure.de` у них зарегистрированные устройства.</span><span class="sxs-lookup"><span data-stu-id="ee861-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="ee861-107">Если в вашей организации зарегистрированы устройства, это влияет на вас.</span><span class="sxs-lookup"><span data-stu-id="ee861-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="ee861-108">**Как это повлияет на пользователей?**</span><span class="sxs-lookup"><span data-stu-id="ee861-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="ee861-109">Пользователи с зарегистрированного устройства больше не смогут входить в учетную запись после того, как миграция будет завершена на этапе миграции [Azure AD.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="ee861-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="ee861-110">Убедитесь, что все ваши устройства зарегистрированы в конечной точке по всему миру, прежде чем организация будет отключена от Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="ee861-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="ee861-111">**Когда пользователи повторно регистрируют свои устройства?**</span><span class="sxs-lookup"><span data-stu-id="ee861-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="ee861-112">Для успешной миграции крайне важно только отозарегистрировать и повторно зарегистрировать устройства на этапе миграции "Отдельно от [Microsoft Cloud Deutschland".](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="ee861-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="ee861-113">**Как восстановить состояние устройства после миграции?**</span><span class="sxs-lookup"><span data-stu-id="ee861-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="ee861-114">Для гибридных устройств с Azure AD и устройств с Windows, которые принадлежат компании, зарегистрированным в Azure AD, администраторы смогут управлять миграцией этих устройств с помощью удаленно активированных процессов, которые будут отрегистрируют старые состояния устройств.</span><span class="sxs-lookup"><span data-stu-id="ee861-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="ee861-115">Для всех остальных устройств, включая личные устройства с Windows, зарегистрированные в Azure AD, конечный пользователь должен выполнить эти действия вручную.</span><span class="sxs-lookup"><span data-stu-id="ee861-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="ee861-116">Для устройств, которые присоединились к Azure AD, пользователям необходимо иметь учетную запись локального администратора, чтобы отозарегистрировать, а затем повторно зарегистрировать свои устройства.</span><span class="sxs-lookup"><span data-stu-id="ee861-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="ee861-117">Корпорация Майкрософт опубликует инструкции по успешному восстановлению состояния устройства.</span><span class="sxs-lookup"><span data-stu-id="ee861-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="ee861-118">**Как узнать, что все мои устройства зарегистрированы в общедоступных облаках?**</span><span class="sxs-lookup"><span data-stu-id="ee861-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="ee861-119">Чтобы проверить, зарегистрированы ли устройства в общечном облаке, необходимо экспортировать и скачать список устройств с портала Azure AD в таблицу Excel.</span><span class="sxs-lookup"><span data-stu-id="ee861-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="ee861-120">Затем отфильтруем устройства, зарегистрированные (с помощью столбца _registeredTime)_ после этапа миграции "Отдельно от [Microsoft Cloud Deutschland".](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="ee861-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="ee861-121">Регистрация устройств деактивируется после миграции клиента и не может быть включена или отключена.</span><span class="sxs-lookup"><span data-stu-id="ee861-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="ee861-122">Если Intune не используется, во sign in to your subscription and run this command to re-activate the option:</span><span class="sxs-lookup"><span data-stu-id="ee861-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a><span data-ttu-id="ee861-123">Гибридное присоединение к Azure AD</span><span class="sxs-lookup"><span data-stu-id="ee861-123">Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="ee861-124">Windows более высокого уровня</span><span class="sxs-lookup"><span data-stu-id="ee861-124">Windows down-level</span></span>

<span data-ttu-id="ee861-125"> Устройства более ранней версии Windows — это устройства с Windows, которые в настоящее время работают под более ранними версиями Windows (например, Windows 8.1 или Windows 7) или windows Server более ранних версий, чем 2019 и 2016.</span><span class="sxs-lookup"><span data-stu-id="ee861-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="ee861-126">Если такие устройства были зарегистрированы ранее, вам потребуется отозарегистрировать и повторно зарегистрировать эти устройства.</span><span class="sxs-lookup"><span data-stu-id="ee861-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="ee861-127">Чтобы определить, было ли устройство более высокого уровня Windows ранее присоединяться к Azure AD, используйте следующую команду на устройстве:</span><span class="sxs-lookup"><span data-stu-id="ee861-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="ee861-128">Если устройство ранее было подключено к Azure AD и имеет сетевое подключение к глобальным конечным точкам Azure AD, вы увидите следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="ee861-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

<span data-ttu-id="ee861-129">Затронутые устройства будут иметь состояние "Устройство" со значением "Неизвестно".</span><span class="sxs-lookup"><span data-stu-id="ee861-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="ee861-130">Если вы выводит "Устройство не присоединилось" или "Состояние устройства" имеет значение "Окей", игнорируйте следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="ee861-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="ee861-131">Только для устройств, которые показывают, что устройство присоединилось (с учетом deviceId, thumbprint и так далее) и состояние устройства "Неизвестно", администраторам следует выполнить следующую команду в контексте пользователя домена, который вошел на такое устройство более высокого уровня:</span><span class="sxs-lookup"><span data-stu-id="ee861-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="ee861-132">Предыдущее команду необходимо выполнить только один раз для каждого пользователя домена, который войт на устройстве более высокого уровня Windows.</span><span class="sxs-lookup"><span data-stu-id="ee861-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="ee861-133">Эту команду следует выполнить в контексте пользователя домена, который войт.</span><span class="sxs-lookup"><span data-stu-id="ee861-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="ee861-134">Чтобы не запускать эту команду при последующем под учетной записи пользователя, необходимо соблюдать достаточное внимание.</span><span class="sxs-lookup"><span data-stu-id="ee861-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="ee861-135">При запуске предыдущей команды очищается состояние местного гибридного компьютера, присоединившегося к Azure AD, для пользователя, который вошел в службу.</span><span class="sxs-lookup"><span data-stu-id="ee861-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="ee861-136">Кроме того, если компьютер по-прежнему настроен на гибридное использование Azure AD в клиенте, он попытается присоединиться, когда пользователь снова войдет.</span><span class="sxs-lookup"><span data-stu-id="ee861-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="ee861-137">Windows Current</span><span class="sxs-lookup"><span data-stu-id="ee861-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="ee861-138">Unjoin</span><span class="sxs-lookup"><span data-stu-id="ee861-138">Unjoin</span></span>

<span data-ttu-id="ee861-139">Чтобы определить, было ли устройство с Windows 10 ранее присоединяться к Azure AD, запустите следующую команду на устройстве:</span><span class="sxs-lookup"><span data-stu-id="ee861-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="ee861-140">Если устройство гибридное с azure AD, администратор увидит следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="ee861-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="ee861-141">Если вы выводит "AzureAdJoined : Нет", игнорируйте следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="ee861-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="ee861-142">Только для устройств, которые показывают, что устройство присоединилось к Azure AD, запустите следующую команду от имени администратора, чтобы удалить его.</span><span class="sxs-lookup"><span data-stu-id="ee861-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="ee861-143">Предыдущее команду необходимо выполнить только один раз в административном контексте на устройстве с Windows.</span><span class="sxs-lookup"><span data-stu-id="ee861-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="ee861-144">Hybrid AD Join\Re-Registration</span><span class="sxs-lookup"><span data-stu-id="ee861-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="ee861-145">Устройство автоматически присоединяется к Azure AD без вмешательства пользователя или администратора, если устройство подключено к глобальным конечным точкам Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ee861-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="azure-ad-join"></a><span data-ttu-id="ee861-146">Присоединиться к Azure AD</span><span class="sxs-lookup"><span data-stu-id="ee861-146">Azure AD Join</span></span>

<span data-ttu-id="ee861-147">**ВАЖНО!** После коммерческой миграции, которая подразумевает активацию регистрации устройств Azure AD, будет включена основная служба Intune.</span><span class="sxs-lookup"><span data-stu-id="ee861-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="ee861-148">Если вы заблокировали регистрацию устройств Azure AD перед миграцией, необходимо отключить участников-служб Intune с помощью PowerShell, чтобы снова отключить регистрацию устройств Azure AD на портале Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ee861-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="ee861-149">Вы можете отключить основное обслуживание Intune с помощью этой команды в модуле Azure Active Directory PowerShell для Graph.</span><span class="sxs-lookup"><span data-stu-id="ee861-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="ee861-150">Unjoin</span><span class="sxs-lookup"><span data-stu-id="ee861-150">Unjoin</span></span>

<span data-ttu-id="ee861-151">Чтобы определить, было ли устройство с Windows 10 ранее присоединяться к Azure AD, пользователь или администратор может выполнить следующую команду на устройстве:</span><span class="sxs-lookup"><span data-stu-id="ee861-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="ee861-152">Если устройство присоединяется к Azure AD, пользователь или администратор увидят следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="ee861-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="ee861-153">Если вы выводит "AzureAdJoined : NO", игнорируйте следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="ee861-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="ee861-154">Пользователь: если устройство присоединилось к Azure AD, пользователь может отсоединить устройство от параметров.</span><span class="sxs-lookup"><span data-stu-id="ee861-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="ee861-155">Убедитесь, что на устройстве есть учетная запись локального администратора, прежде чем отсоединять устройство от Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ee861-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="ee861-156">Учетная запись локального администратора необходима для обратного вход в устройство.</span><span class="sxs-lookup"><span data-stu-id="ee861-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="ee861-157">Администратор: если администратору организации требуется отсоедидинять устройства пользователей, которые являются устройствами, которые являются устройствами, которые являются службами Azure AD, он может сделать это, выдав следующую команду на каждом устройстве с помощью такого механизма, как групповая политика.</span><span class="sxs-lookup"><span data-stu-id="ee861-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="ee861-158">Администратор должен убедиться, что на устройстве есть учетная запись локального администратора, прежде чем отсоединять устройство от Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ee861-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="ee861-159">Для обратного вход в устройство необходима учетная запись локального администратора.</span><span class="sxs-lookup"><span data-stu-id="ee861-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="ee861-160">Предыдущее команду необходимо выполнить только один раз в административном контексте на устройстве с Windows.</span><span class="sxs-lookup"><span data-stu-id="ee861-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="ee861-161">Регистрация и регистрация в Azure AD</span><span class="sxs-lookup"><span data-stu-id="ee861-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="ee861-162">Пользователь может присоединить устройство к Azure AD из параметров Windows: параметры > учетные записи > **Access Work or School > Connect.**</span><span class="sxs-lookup"><span data-stu-id="ee861-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="ee861-163">Azure AD Registered (компания принадлежит)</span><span class="sxs-lookup"><span data-stu-id="ee861-163">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="ee861-164">Чтобы определить, зарегистрировано ли устройство с Windows 10 в Azure AD, запустите следующую команду на устройстве:</span><span class="sxs-lookup"><span data-stu-id="ee861-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="ee861-165">Если устройство зарегистрировано в Azure AD, вы увидите следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="ee861-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="ee861-166">Чтобы удалить существующую учетную запись, зарегистрированную в Azure AD, на устройстве:</span><span class="sxs-lookup"><span data-stu-id="ee861-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="ee861-167">Чтобы удалить зарегистрированную в Azure AD учетную запись на устройстве, используйте CleanupWPJ, средство, которое можно скачать здесь: [CleanupWPJ.zip. ](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)</span><span class="sxs-lookup"><span data-stu-id="ee861-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="ee861-168">Извлеките ZIP-файл и запустите **файл WPJCleanup.cmd.**</span><span class="sxs-lookup"><span data-stu-id="ee861-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="ee861-169">Это средство запустит нужный исполняемый исполняемый инструмент в зависимости от версии Windows на устройстве.</span><span class="sxs-lookup"><span data-stu-id="ee861-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="ee861-170">Используя такой механизм, как групповая политика, администратор может выполнить команду на устройстве в контексте любого пользователя, который ввел учетные данные на устройстве.</span><span class="sxs-lookup"><span data-stu-id="ee861-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="ee861-171">Чтобы отключить запросы диспетчера учетных записей на регистрацию устройства в Azure AD, добавьте это значение реестра:</span><span class="sxs-lookup"><span data-stu-id="ee861-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="ee861-172">Расположение: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="ee861-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="ee861-173">Тип: DWORD (32 бита)</span><span class="sxs-lookup"><span data-stu-id="ee861-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="ee861-174">Имя: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="ee861-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="ee861-175">Значение: 1</span><span class="sxs-lookup"><span data-stu-id="ee861-175">Value data: 1</span></span>

<span data-ttu-id="ee861-176">Наличие этого значения реестра должно блокировать участие на рабочем месте и запретить пользователям видеть запросы на присоединиться к устройству.</span><span class="sxs-lookup"><span data-stu-id="ee861-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="ee861-177">Android</span><span class="sxs-lookup"><span data-stu-id="ee861-177">Android</span></span>

<span data-ttu-id="ee861-178">Для Android пользователям потребуется отозарегистрировать и повторно зарегистрировать свои устройства.</span><span class="sxs-lookup"><span data-stu-id="ee861-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="ee861-179">Это можно сделать с помощью приложения Microsoft Authenticator или приложения "Портал компании".</span><span class="sxs-lookup"><span data-stu-id="ee861-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="ee861-180">В приложении Microsoft Authenticator пользователи могут перейти в > **регистрации устройств.**</span><span class="sxs-lookup"><span data-stu-id="ee861-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="ee861-181">После этого пользователи могут отозарегистрировать и повторно зарегистрировать свое устройство.</span><span class="sxs-lookup"><span data-stu-id="ee861-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="ee861-182">На портале компании пользователи могут перейти на вкладку **"Устройства"** и удалить устройство.</span><span class="sxs-lookup"><span data-stu-id="ee861-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="ee861-183">После этого повторно зарегистрите устройство с помощью портала компании.</span><span class="sxs-lookup"><span data-stu-id="ee861-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="ee861-184">Пользователи также могут отозарегистрировать и повторно зарегистрироваться, удалив учетную запись со страницы параметров учетной записи, а затем повторно добавив эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="ee861-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="ee861-185">Чтобы отозарегистрировать и повторно зарегистрировать устройство на Android с помощью приложения Microsoft Authenticator:</span><span class="sxs-lookup"><span data-stu-id="ee861-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="ee861-186">Откройте приложение Microsoft Authenticator и перейдите в **"Параметры".**</span><span class="sxs-lookup"><span data-stu-id="ee861-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="ee861-187">Выберите **регистрацию устройства.**</span><span class="sxs-lookup"><span data-stu-id="ee861-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="ee861-188">Отоберем регистрацию устройства, выбрав **"Отрегистрить".**</span><span class="sxs-lookup"><span data-stu-id="ee861-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="ee861-189">Для **регистрации устройства** повторно зарегистрируйте устройство, введя свой адрес электронной почты, а затем выберите **"Регистрация".**</span><span class="sxs-lookup"><span data-stu-id="ee861-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="ee861-190">Чтобы отозарегистрировать и повторно зарегистрировать устройство Android на странице "Параметры Android":</span><span class="sxs-lookup"><span data-stu-id="ee861-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="ee861-191">Откройте **"Параметры устройства"** и перейдите в **"Учетные записи".**</span><span class="sxs-lookup"><span data-stu-id="ee861-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="ee861-192">Выберите учетную запись, которую нужно повторно зарегистрировать, и выберите **"Удалить учетную запись".**</span><span class="sxs-lookup"><span data-stu-id="ee861-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="ee861-193">После удаления учетной записи  на странице "Учетные записи" выберите "Добавить учетную **запись > work".**</span><span class="sxs-lookup"><span data-stu-id="ee861-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="ee861-194">Для **workplace Join** введите адрес электронной почты и выберите **"Присоединиться",** чтобы завершить регистрацию устройства.</span><span class="sxs-lookup"><span data-stu-id="ee861-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="ee861-195">Чтобы отозарегистрировать и повторно зарегистрировать устройство на Android с портала компании:</span><span class="sxs-lookup"><span data-stu-id="ee861-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="ee861-196">Запустите портал компании и перейдите на **вкладку "Устройства".**</span><span class="sxs-lookup"><span data-stu-id="ee861-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="ee861-197">Выберите устройство, чтобы увидеть сведения об устройстве.</span><span class="sxs-lookup"><span data-stu-id="ee861-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="ee861-198">В меню многоточий (три точки) выберите "Удалить устройство" и завершите удаление, подтвердив это в диалоговом окле. </span><span class="sxs-lookup"><span data-stu-id="ee861-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="ee861-199">Теперь вы должны выйти из приложения "Портал компании".</span><span class="sxs-lookup"><span data-stu-id="ee861-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="ee861-200">Выберите **"Войти",** чтобы повторно зарегистрировать устройство.</span><span class="sxs-lookup"><span data-stu-id="ee861-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="ee861-201">Дополнительные сведения о любых действиях, необходимых на этапе миграции этой рабочей нагрузки, а также о влиянии на администрирование или использование, см. в дополнительных сведениях о Azure AD для миграции из [Microsoft Cloud Deutschland.](ms-cloud-germany-transition-azure-ad.md)</span><span class="sxs-lookup"><span data-stu-id="ee861-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="ee861-202">iOS</span><span class="sxs-lookup"><span data-stu-id="ee861-202">iOS</span></span>

<span data-ttu-id="ee861-203">На устройствах с iOS пользователю потребуется вручную удалить кэшированные учетные записи из Средства проверки подлинности Майкрософт, отрегистратора устройства и выйти из любых приложений на устройстве.</span><span class="sxs-lookup"><span data-stu-id="ee861-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="ee861-204">Шаг 1. При его наступлению удалите учетную запись из приложения Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="ee861-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="ee861-205">Коснитесь учетной записи в приложении Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="ee861-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="ee861-206">**Коснитесь значка "Параметры"** в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="ee861-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="ee861-207">Если вы не видите значок **"Параметры",** возможно, вы не используете последнюю версию Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="ee861-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="ee861-208">Нажмите **кнопку "Удалить учетную запись".**</span><span class="sxs-lookup"><span data-stu-id="ee861-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="ee861-209">**Коснитесь всех приложений на этом устройстве.**</span><span class="sxs-lookup"><span data-stu-id="ee861-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="ee861-210">Шаг 2. Unregister the device from the Microsoft Authenticator app</span><span class="sxs-lookup"><span data-stu-id="ee861-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="ee861-211">Коснитесь значка меню в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="ee861-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="ee861-212">**Коснитесь параметров,** а **затем регистрация устройства.**</span><span class="sxs-lookup"><span data-stu-id="ee861-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="ee861-213">Если отображается ваша учетная запись, коснитесь устройства **"Unregister"** и **"Continue** in the dialog".</span><span class="sxs-lookup"><span data-stu-id="ee861-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="ee861-214">После этого учетная запись не должна отсвеяться.</span><span class="sxs-lookup"><span data-stu-id="ee861-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="ee861-215">Шаг 3. При необходимости выход из отдельных приложений</span><span class="sxs-lookup"><span data-stu-id="ee861-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="ee861-216">Пользователи могут перейти к отдельным приложениям, например Outlook, Teams и OneDrive, и удалить учетные записи из этих приложений.</span><span class="sxs-lookup"><span data-stu-id="ee861-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="ee861-217">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="ee861-217">More information</span></span>

<span data-ttu-id="ee861-218">Начало работы:</span><span class="sxs-lookup"><span data-stu-id="ee861-218">Getting started:</span></span>

- [<span data-ttu-id="ee861-219">Миграция из Microsoft Cloud Deutschland в службы Office 365 в новых регионах центра обработки данных в Германии</span><span class="sxs-lookup"><span data-stu-id="ee861-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="ee861-220">Помощь по миграции Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="ee861-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="ee861-221">Как принять участие в миграции</span><span class="sxs-lookup"><span data-stu-id="ee861-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="ee861-222">Опыт работы с клиентами во время миграции</span><span class="sxs-lookup"><span data-stu-id="ee861-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="ee861-223">Переход:</span><span class="sxs-lookup"><span data-stu-id="ee861-223">Moving through the transition:</span></span>

- [<span data-ttu-id="ee861-224">Действия и влияние этапов миграции</span><span class="sxs-lookup"><span data-stu-id="ee861-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="ee861-225">Дополнительная предварительная работа</span><span class="sxs-lookup"><span data-stu-id="ee861-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="ee861-226">Дополнительные сведения [для Azure AD,](ms-cloud-germany-transition-azure-ad.md) [устройств,](ms-cloud-germany-transition-add-devices.md) [функций](ms-cloud-germany-transition-add-experience.md)и [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="ee861-226">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="ee861-227">Облачные приложения:</span><span class="sxs-lookup"><span data-stu-id="ee861-227">Cloud apps:</span></span>

- [<span data-ttu-id="ee861-228">Сведения о программе миграции Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ee861-228">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="ee861-229">Сведения о программе миграции Power BI</span><span class="sxs-lookup"><span data-stu-id="ee861-229">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="ee861-230">Начало перехода на Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ee861-230">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
