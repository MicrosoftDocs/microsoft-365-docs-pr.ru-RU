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
description: Сводка. Дополнительные сведения об службах устройств при переходе из Microsoft Cloud Germany (Microsoft Cloud Deutschland) в Office 365 службы в новом немецком регионе центра обработки данных.
ms.openlocfilehash: 21188372f03af394fe1c0e227c1adeabbad02a85
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928160"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="4d736-103">Дополнительные сведения об устройстве для миграции из Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="4d736-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="4d736-104">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="4d736-104">Frequently asked questions</span></span>

<span data-ttu-id="4d736-105">**Как узнать, затронута ли моя организация?**</span><span class="sxs-lookup"><span data-stu-id="4d736-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="4d736-106">Администраторы должны проверить, есть ли `https://portal.microsoftazure.de` у них зарегистрированные устройства.</span><span class="sxs-lookup"><span data-stu-id="4d736-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="4d736-107">Если в организации зарегистрированы устройства, это влияет на вас.</span><span class="sxs-lookup"><span data-stu-id="4d736-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="4d736-108">**Какое влияние оказывает на пользователей?**</span><span class="sxs-lookup"><span data-stu-id="4d736-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="4d736-109">Пользователи с зарегистрированного устройства больше не смогут войти после того, как миграция вступает в этап переноса [Azure AD.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="4d736-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="4d736-110">Убедитесь, что все ваши устройства зарегистрированы в конечной точке во всем мире до отключения организации от Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="4d736-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="4d736-111">**Когда пользователи перерегистрируют свои устройства?**</span><span class="sxs-lookup"><span data-stu-id="4d736-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="4d736-112">Для вашего успеха важно, чтобы вы только отрегистрируете и перерегистрируете устройства на этапе миграции Отдельно от [Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="4d736-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="4d736-113">**Как восстановить состояние устройства после миграции?**</span><span class="sxs-lookup"><span data-stu-id="4d736-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="4d736-114">Для гибридных устройств Azure AD и Windows, зарегистрированных в Azure AD, администраторы смогут управлять миграцией этих устройств с помощью удаленных процессов, которые будут регистрировать старые состояния устройств.</span><span class="sxs-lookup"><span data-stu-id="4d736-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="4d736-115">Для всех других устройств, включая Windows устройства, зарегистрированные в Azure AD, конечный пользователь должен выполнять эти действия вручную.</span><span class="sxs-lookup"><span data-stu-id="4d736-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="4d736-116">Для устройств, присоединив Azure AD, пользователям необходимо иметь учетную запись локального администратора, чтобы отозарегистрировать их, а затем перерегистрируйте свои устройства.</span><span class="sxs-lookup"><span data-stu-id="4d736-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="4d736-117">Корпорация Майкрософт опубликует инструкции по успешному восстановлению состояния устройства.</span><span class="sxs-lookup"><span data-stu-id="4d736-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="4d736-118">**Как узнать, что все мои устройства зарегистрированы в общедоступных облаках?**</span><span class="sxs-lookup"><span data-stu-id="4d736-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="4d736-119">Чтобы проверить, зарегистрированы ли устройства в общеобязуемом облаке, необходимо экспортировать и загружать список устройств с портала Azure AD в Excel таблицу.</span><span class="sxs-lookup"><span data-stu-id="4d736-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="4d736-120">Затем фильтруем устройства, зарегистрированные (с помощью столбца _registeredTime)_ после этапа миграции Отдельно от [Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="4d736-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="4d736-121">Регистрация устройства отключается после миграции клиента и не может быть включена или отключена.</span><span class="sxs-lookup"><span data-stu-id="4d736-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="4d736-122">Если Intune не используется, включите подписку и запустите эту команду, чтобы повторно активировать параметр:</span><span class="sxs-lookup"><span data-stu-id="4d736-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a><span data-ttu-id="4d736-123">Гибридное присоединение к Azure AD</span><span class="sxs-lookup"><span data-stu-id="4d736-123">Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="4d736-124">Windows уровня</span><span class="sxs-lookup"><span data-stu-id="4d736-124">Windows down-level</span></span>

<span data-ttu-id="4d736-125">_Windows_ — это устройства Windows, которые в настоящее время запускают более ранние версии Windows (например, Windows 8.1 или Windows 7), или которые запускаются в Windows Server раньше 2019 и 2016 годов.</span><span class="sxs-lookup"><span data-stu-id="4d736-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="4d736-126">Если такие устройства были зарегистрированы ранее, необходимо оторегистрируйте и перерегистрируйте эти устройства.</span><span class="sxs-lookup"><span data-stu-id="4d736-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="4d736-127">Чтобы определить, было ли Windows ранее соединялось с Azure AD, используйте следующую команду на устройстве:</span><span class="sxs-lookup"><span data-stu-id="4d736-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="4d736-128">Если устройство ранее было подключено к Azure AD и если устройство подключено к глобальным конечным точкам Azure AD, вы увидите следующий вывод:</span><span class="sxs-lookup"><span data-stu-id="4d736-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

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

<span data-ttu-id="4d736-129">На затронутых устройствах будет "Состояние устройства" со значением "Unknown".</span><span class="sxs-lookup"><span data-stu-id="4d736-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="4d736-130">Если вывод "Устройство не присоединилось" или значение "Состояние устройства" является "Хорошо", игнорируйте следующие указания.</span><span class="sxs-lookup"><span data-stu-id="4d736-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="4d736-131">Только для устройств, которые показывают, что устройство соединено (в силу deviceId, thumbprint и так далее) и чье значение "Состояние устройства" является "Неизвестным", администраторы должны выполнить следующую команду в контексте регистрации пользователя домена на таком устройстве ниже уровня:</span><span class="sxs-lookup"><span data-stu-id="4d736-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="4d736-132">Предыдущей команде необходимо выполнить только один раз для каждого пользователя домена, входиющего на Windows на устройстве с Windows уровней.</span><span class="sxs-lookup"><span data-stu-id="4d736-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="4d736-133">Эта команда должна запускаться в контексте регистрации пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="4d736-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="4d736-134">Необходимо заботиться о том, чтобы не запускать эту команду, когда пользователь впоследствии войду.</span><span class="sxs-lookup"><span data-stu-id="4d736-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="4d736-135">При запуске предыдущей команды будет очищаться присоединилось состояние локального гибридного компьютера Azure AD,присоединившегося к пользователю, который вошел.</span><span class="sxs-lookup"><span data-stu-id="4d736-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="4d736-136">И если компьютер по-прежнему настроен как гибридный Azure AD,присоединився к клиенту, он будет пытаться присоединиться, когда пользователь снова войдет.</span><span class="sxs-lookup"><span data-stu-id="4d736-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="4d736-137">Windows Current</span><span class="sxs-lookup"><span data-stu-id="4d736-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="4d736-138">Unjoin</span><span class="sxs-lookup"><span data-stu-id="4d736-138">Unjoin</span></span>

<span data-ttu-id="4d736-139">Чтобы определить, было ли Windows 10 ранее соединено с Azure AD, запустите следующую команду на устройстве:</span><span class="sxs-lookup"><span data-stu-id="4d736-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="4d736-140">Если устройство является гибридным Azure AD-joined, администратор увидит следующий вывод:</span><span class="sxs-lookup"><span data-stu-id="4d736-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="4d736-141">Если вывод "AzureAdJoined: Нет", игнорируйте следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="4d736-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="4d736-142">Только для устройств, которые показывают, что устройство присоединяется к Azure AD, запустите следующую команду в качестве администратора, чтобы удалить соединяемого состояния устройства.</span><span class="sxs-lookup"><span data-stu-id="4d736-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="4d736-143">Предыдущей команде необходимо выполнить только один раз в административном контексте на Windows устройстве.</span><span class="sxs-lookup"><span data-stu-id="4d736-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="4d736-144">Гибридная регистрация AD\Re-Registration</span><span class="sxs-lookup"><span data-stu-id="4d736-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="4d736-145">Устройство автоматически присоединяется к Azure AD без вмешательства пользователя или администратора до тех пор, пока устройство подключено к глобальным конечным точкам Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4d736-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="azure-ad-join"></a><span data-ttu-id="4d736-146">Регистрация Azure AD</span><span class="sxs-lookup"><span data-stu-id="4d736-146">Azure AD Join</span></span>

<span data-ttu-id="4d736-147">**ВАЖНО:** Принцип службы Intune будет включен после миграции коммерции, которая подразумевает активацию регистрации устройств Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4d736-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="4d736-148">Если вы заблокировали регистрацию устройств Azure AD перед миграцией, необходимо отключить главу службы Intune с PowerShell, чтобы снова отключить регистрацию устройств Azure AD на портале Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4d736-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="4d736-149">Вы можете отключить главу службы Intune с этой командой в Azure Active Directory PowerShell для Graph модуля.</span><span class="sxs-lookup"><span data-stu-id="4d736-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="4d736-150">Unjoin</span><span class="sxs-lookup"><span data-stu-id="4d736-150">Unjoin</span></span>

<span data-ttu-id="4d736-151">Чтобы определить, было ли Windows 10 ранее соединялось с Azure AD, пользователь или администратор может выполнить следующую команду на устройстве:</span><span class="sxs-lookup"><span data-stu-id="4d736-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="4d736-152">Если устройство присоединяется к Azure AD, пользователь или администратор увидят следующий вывод:</span><span class="sxs-lookup"><span data-stu-id="4d736-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="4d736-153">Если вывод "AzureAdJoined: НЕТ", игнорируйте следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="4d736-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="4d736-154">Пользователь. Если к устройству присоединилась Azure AD, пользователь может отсоединять устройство от параметров.</span><span class="sxs-lookup"><span data-stu-id="4d736-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="4d736-155">Убедитесь, что на устройстве есть учетная запись локального администратора, прежде чем отсоединять устройство от Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4d736-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="4d736-156">Для регистрации на устройстве требуется учетная запись локального администратора.</span><span class="sxs-lookup"><span data-stu-id="4d736-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="4d736-157">Администратор. Если администратор организации хочет отсоединять устройства пользователей, присоединив к Azure AD, они могут сделать это, выдав следующую команду на каждом из устройств с помощью механизма, например групповой политики.</span><span class="sxs-lookup"><span data-stu-id="4d736-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="4d736-158">Администратор должен убедиться, что на устройстве есть учетная запись локального администратора, прежде чем отсоединять устройство от Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4d736-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="4d736-159">Чтобы войти в устройство, требуется учетная запись локального администратора.</span><span class="sxs-lookup"><span data-stu-id="4d736-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="4d736-160">Предыдущей команде необходимо выполнить только один раз в административном контексте на Windows устройстве.</span><span class="sxs-lookup"><span data-stu-id="4d736-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="4d736-161">Azure AD Join/Re-Registration</span><span class="sxs-lookup"><span data-stu-id="4d736-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="4d736-162">Пользователь может присоединиться к устройству Azure AD из параметров Windows: Параметры > учетных записей > доступа или школьных **> Подключение.**</span><span class="sxs-lookup"><span data-stu-id="4d736-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="4d736-163">Azure AD Registered (Company owned)</span><span class="sxs-lookup"><span data-stu-id="4d736-163">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="4d736-164">Чтобы определить, Windows 10 зарегистрировано ли устройство Azure AD, запустите следующую команду на устройстве:</span><span class="sxs-lookup"><span data-stu-id="4d736-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="4d736-165">Если устройство зарегистрировано Azure AD, вы увидите следующий вывод:</span><span class="sxs-lookup"><span data-stu-id="4d736-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="4d736-166">Удаление существующей учетной записи Azure AD на устройстве:</span><span class="sxs-lookup"><span data-stu-id="4d736-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="4d736-167">Чтобы удалить учетную запись Azure AD на устройстве, используйте Средство CleanupWPJ, которое можно скачать [ здесь:CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="4d736-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="4d736-168">Извлеките файл ZIP и запустите **WPJCleanup.cmd**.</span><span class="sxs-lookup"><span data-stu-id="4d736-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="4d736-169">Этот инструмент запустит правильный исполняемый на основе версии Windows на устройстве.</span><span class="sxs-lookup"><span data-stu-id="4d736-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="4d736-170">С помощью такого механизма, как групповой политики, администратор может запустить команду на устройстве в контексте любого пользователя, который подписан на устройстве.</span><span class="sxs-lookup"><span data-stu-id="4d736-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="4d736-171">Чтобы отключить запросы диспетчера веб-учетных записей для регистрации устройства в Azure AD, добавьте это значение реестра:</span><span class="sxs-lookup"><span data-stu-id="4d736-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="4d736-172">Расположение: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="4d736-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="4d736-173">Тип: DWORD (32 бита)</span><span class="sxs-lookup"><span data-stu-id="4d736-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="4d736-174">Имя: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="4d736-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="4d736-175">Данные значения: 1</span><span class="sxs-lookup"><span data-stu-id="4d736-175">Value data: 1</span></span>

<span data-ttu-id="4d736-176">Наличие этого значения реестра должно блокировать вступление на рабочем месте и запретить пользователям видеть подсказки для перейти на устройство.</span><span class="sxs-lookup"><span data-stu-id="4d736-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="4d736-177">Android</span><span class="sxs-lookup"><span data-stu-id="4d736-177">Android</span></span>

<span data-ttu-id="4d736-178">Для Android пользователям потребуется оторегистрируйте и перерегистрируйте свои устройства.</span><span class="sxs-lookup"><span data-stu-id="4d736-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="4d736-179">Это можно сделать с помощью Microsoft Authenticator или Корпоративный портал приложения.</span><span class="sxs-lookup"><span data-stu-id="4d736-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="4d736-180">В приложении Microsoft Authenticator пользователи могут перейти к Параметры > **регистрации устройств.**</span><span class="sxs-lookup"><span data-stu-id="4d736-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="4d736-181">Оттуда пользователи могут отрегистрируйте и перерегистрируйте свое устройство.</span><span class="sxs-lookup"><span data-stu-id="4d736-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="4d736-182">С Корпоративный портал пользователи могут перейти на вкладку **Devices** и удалить устройство.</span><span class="sxs-lookup"><span data-stu-id="4d736-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="4d736-183">После этого повторно зарегистрив устройство с помощью Корпоративный портал.</span><span class="sxs-lookup"><span data-stu-id="4d736-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="4d736-184">Пользователи также могут отрегистрируйтесь и перерегистрируйтесь, удалив учетную запись со страницы параметров учетной записи, а затем повторно добавив учетную запись.</span><span class="sxs-lookup"><span data-stu-id="4d736-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="4d736-185">Для регистрации и перерегистрации устройства на Android с помощью Microsoft Authenticator приложения:</span><span class="sxs-lookup"><span data-stu-id="4d736-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="4d736-186">Откройте приложение Microsoft Authenticator и перейдите **в Параметры**.</span><span class="sxs-lookup"><span data-stu-id="4d736-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="4d736-187">Выберите **регистрацию устройства.**</span><span class="sxs-lookup"><span data-stu-id="4d736-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="4d736-188">Незарегистрированное устройство, выбрав **Unregister**.</span><span class="sxs-lookup"><span data-stu-id="4d736-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="4d736-189">Для **регистрации устройства** перерегистрируйте устройство, введя адрес электронной почты, а затем выберите **Register**.</span><span class="sxs-lookup"><span data-stu-id="4d736-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="4d736-190">Для регистрации и перерегистрации устройства Android на странице Android Параметры:</span><span class="sxs-lookup"><span data-stu-id="4d736-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="4d736-191">Откройте **устройство Параметры** и перейдите к **учетным записям.**</span><span class="sxs-lookup"><span data-stu-id="4d736-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="4d736-192">Выберите учетную запись работы, которую необходимо перерегистрируйте, и выберите **учетную запись Remove.**</span><span class="sxs-lookup"><span data-stu-id="4d736-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="4d736-193">После удаления учетной записи со страницы **Учетные** записи выберите учетную запись **Add Account > work account.**</span><span class="sxs-lookup"><span data-stu-id="4d736-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="4d736-194">Для **workplace Join** введите адрес электронной почты и выберите **Присоединиться,** чтобы завершить регистрацию устройства.</span><span class="sxs-lookup"><span data-stu-id="4d736-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="4d736-195">Для регистрации и перерегистрации устройства на Android с Корпоративный портал:</span><span class="sxs-lookup"><span data-stu-id="4d736-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="4d736-196">Запустите Корпоративный портал и перейдите на **вкладку Devices.**</span><span class="sxs-lookup"><span data-stu-id="4d736-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="4d736-197">Выберите устройство, чтобы увидеть сведения об устройстве.</span><span class="sxs-lookup"><span data-stu-id="4d736-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="4d736-198">Из меню эллипсов (три точки) выберите **Remove Device** и выполните удаление, подтвердив в диалоговом окантовке.</span><span class="sxs-lookup"><span data-stu-id="4d736-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="4d736-199">Теперь вы должны войти в систему из Корпоративный портал приложения.</span><span class="sxs-lookup"><span data-stu-id="4d736-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="4d736-200">Выберите **вход для** повторной регистрации устройства.</span><span class="sxs-lookup"><span data-stu-id="4d736-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="4d736-201">Дополнительные сведения о любых действиях, необходимых на этапе миграции этой рабочей нагрузки или воздействии на администрирование или использование, см. в Azure Active Directory (Azure AD) в дополнительных сведениях Azure AD для миграции из [Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span><span class="sxs-lookup"><span data-stu-id="4d736-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="4d736-202">iOS</span><span class="sxs-lookup"><span data-stu-id="4d736-202">iOS</span></span>

<span data-ttu-id="4d736-203">На устройствах iOS пользователю необходимо вручную удалить все кэшированные учетные записи из Microsoft Authenticator, отрегистрить устройство и выйти из любых родных приложений на устройстве.</span><span class="sxs-lookup"><span data-stu-id="4d736-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="4d736-204">Шаг 1. Если она присутствует, удалите учетную запись из Microsoft Authenticator приложения</span><span class="sxs-lookup"><span data-stu-id="4d736-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="4d736-205">Нажмите на учетную запись в Microsoft Authenticator приложении.</span><span class="sxs-lookup"><span data-stu-id="4d736-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="4d736-206">Нажмите **значок Параметры** в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="4d736-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="4d736-207">Если вы не видите значок **Параметры,** возможно, вы не используете последнюю версию Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="4d736-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="4d736-208">Нажмите **кнопку Удалить учетную запись.**</span><span class="sxs-lookup"><span data-stu-id="4d736-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="4d736-209">Нажмите **кнопку Все приложения на этом устройстве**.</span><span class="sxs-lookup"><span data-stu-id="4d736-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="4d736-210">Шаг 2. Незарегистрированное устройство из Microsoft Authenticator приложения</span><span class="sxs-lookup"><span data-stu-id="4d736-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="4d736-211">Нажмите значок меню в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="4d736-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="4d736-212">Нажмите **кнопку Параметры,** а затем **регистрация устройств.**</span><span class="sxs-lookup"><span data-stu-id="4d736-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="4d736-213">Если учетная запись отображается, нажмите **кнопку Незарегистрированное устройство** **и продолжайте** в диалоговом окте.</span><span class="sxs-lookup"><span data-stu-id="4d736-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="4d736-214">После этого вы не должны видеть учетную запись.</span><span class="sxs-lookup"><span data-stu-id="4d736-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="4d736-215">Шаг 3. При необходимости выпишитесь из отдельных приложений</span><span class="sxs-lookup"><span data-stu-id="4d736-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="4d736-216">Пользователи могут перейти к отдельным приложениям, Outlook, Teams и OneDrive, а также удалить учетные записи из этих приложений.</span><span class="sxs-lookup"><span data-stu-id="4d736-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="4d736-217">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="4d736-217">More information</span></span>

<span data-ttu-id="4d736-218">Начало работы:</span><span class="sxs-lookup"><span data-stu-id="4d736-218">Getting started:</span></span>

- [<span data-ttu-id="4d736-219">Миграция из Microsoft Cloud Deutschland в Office 365 службы в новых немецких регионах центра обработки данных</span><span class="sxs-lookup"><span data-stu-id="4d736-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="4d736-220">Помощь по миграции Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="4d736-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="4d736-221">Как принять участие в миграции</span><span class="sxs-lookup"><span data-stu-id="4d736-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="4d736-222">Опыт работы с клиентами во время миграции</span><span class="sxs-lookup"><span data-stu-id="4d736-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="4d736-223">Перемещение по переходу:</span><span class="sxs-lookup"><span data-stu-id="4d736-223">Moving through the transition:</span></span>

- [<span data-ttu-id="4d736-224">Действия и влияние этапов миграции</span><span class="sxs-lookup"><span data-stu-id="4d736-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="4d736-225">Дополнительная предварительная работа</span><span class="sxs-lookup"><span data-stu-id="4d736-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="4d736-226">Дополнительные сведения [для Azure AD,](ms-cloud-germany-transition-azure-ad.md) [устройств,](ms-cloud-germany-transition-add-devices.md) [опытом](ms-cloud-germany-transition-add-experience.md)и [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="4d736-226">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="4d736-227">Облачные приложения:</span><span class="sxs-lookup"><span data-stu-id="4d736-227">Cloud apps:</span></span>

- [<span data-ttu-id="4d736-228">Сведения о программе миграции Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="4d736-228">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="4d736-229">Сведения о программе миграции Power BI</span><span class="sxs-lookup"><span data-stu-id="4d736-229">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="4d736-230">Начало перехода на Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4d736-230">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)