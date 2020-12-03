---
title: Дополнительные сведения об устройстве для миграции с Microsoft Cloud записей
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
description: Сводка. Дополнительные сведения об устройствах в службах при переходе с Microsoft Cloud Германии (Microsoft Cloud записей) на службы Office 365 в новом регионе для немецкого центра обработки данных.
ms.openlocfilehash: 941b836871f4ffb7f39f6e144675e9ee15510270
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560865"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="c07d4-103">Дополнительные сведения об устройстве для миграции с Microsoft Cloud записей</span><span class="sxs-lookup"><span data-stu-id="c07d4-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c07d4-104">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="c07d4-104">Frequently asked questions</span></span>

<span data-ttu-id="c07d4-105">**Как узнать, подвержена ли моя организация?**</span><span class="sxs-lookup"><span data-stu-id="c07d4-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="c07d4-106">Администраторы должны проверить `https://portal.microsoftazure.de` , есть ли у них зарегистрированные устройства.</span><span class="sxs-lookup"><span data-stu-id="c07d4-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="c07d4-107">Если в вашей организации есть зарегистрированные устройства, это повлияет на работу.</span><span class="sxs-lookup"><span data-stu-id="c07d4-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="c07d4-108">**Каково воздействие на пользователей?**</span><span class="sxs-lookup"><span data-stu-id="c07d4-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="c07d4-109">Пользователи из зарегистрированного устройства больше не смогут войти в систему после перехода на этап [заключительного завершения миграции Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) .</span><span class="sxs-lookup"><span data-stu-id="c07d4-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="c07d4-110">Убедитесь, что все устройства зарегистрированы в глобальной конечной точке, прежде чем ваша организация будет отключена от Microsoft Cloud записей.</span><span class="sxs-lookup"><span data-stu-id="c07d4-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="c07d4-111">**Когда мои пользователи повторно регистрируют свои устройства?**</span><span class="sxs-lookup"><span data-stu-id="c07d4-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="c07d4-112">Вам очень важно успешно выполнить регистрацию и повторно зарегистрировать ваши устройства на [отдельном этапе записей миграции Microsoft Cloud](ms-cloud-germany-transition.md#how-is-the-migration-organized) .</span><span class="sxs-lookup"><span data-stu-id="c07d4-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="c07d4-113">**Как восстановить состояние устройства после миграции?**</span><span class="sxs-lookup"><span data-stu-id="c07d4-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="c07d4-114">Для гибридных и присоединенных к домену устройств с Windows, которые зарегистрированы в Azure AD, администраторы могут управлять переносом этих устройств через удаленно запущенные рабочие процессы, которые будут отменять регистрацию старых состояний устройств.</span><span class="sxs-lookup"><span data-stu-id="c07d4-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="c07d4-115">Для всех остальных устройств, включая персональные устройства Windows, зарегистрированные в Azure AD, конечный пользователь должен выполнить эти действия вручную.</span><span class="sxs-lookup"><span data-stu-id="c07d4-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="c07d4-116">Для устройств, присоединенных к Azure AD, пользователям необходимо иметь учетную запись локального администратора для отмены регистрации и повторной регистрации своих устройств.</span><span class="sxs-lookup"><span data-stu-id="c07d4-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="c07d4-117">Корпорация Майкрософт будет публиковать инструкции о том, как успешно восстановить состояние устройства.</span><span class="sxs-lookup"><span data-stu-id="c07d4-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="c07d4-118">**Как узнать, что все мои устройства зарегистрированы в общедоступном облаке?**</span><span class="sxs-lookup"><span data-stu-id="c07d4-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="c07d4-119">Чтобы проверить, зарегистрированы ли ваши устройства в общедоступном облаке, необходимо экспортировать и скачать список устройств с портала Azure AD в электронную таблицу Excel.</span><span class="sxs-lookup"><span data-stu-id="c07d4-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="c07d4-120">Затем отфильтруйте устройства, которые зарегистрированы (с помощью столбца _регистередтиме_ ), после фазы миграции [Microsoft Cloud записей](ms-cloud-germany-transition.md#how-is-the-migration-organized) .</span><span class="sxs-lookup"><span data-stu-id="c07d4-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="c07d4-121">Регистрация устройства отключена после миграции клиента и не может быть включена или отключена.</span><span class="sxs-lookup"><span data-stu-id="c07d4-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="c07d4-122">Если Intune не используется, войдите в свою подписку и выполните следующую команду для повторной активации параметра:</span><span class="sxs-lookup"><span data-stu-id="c07d4-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a><span data-ttu-id="c07d4-123">Присоединение к гибридной службе Windows Azure AD</span><span class="sxs-lookup"><span data-stu-id="c07d4-123">Windows Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="c07d4-124">Windows Down</span><span class="sxs-lookup"><span data-stu-id="c07d4-124">Windows down-level</span></span>

<span data-ttu-id="c07d4-125">_Устройства Windows нижнего уровня_ — это устройства Windows, которые в настоящее время работают под управлением более ранних версий Windows (например, Windows 8,1 или Windows 7) или работают под управлением Windows Server версий более ранних, чем 2019 и 2016.</span><span class="sxs-lookup"><span data-stu-id="c07d4-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="c07d4-126">Если такие устройства были зарегистрированы ранее, вам потребуется отменить регистрацию и повторно зарегистрировать эти устройства.</span><span class="sxs-lookup"><span data-stu-id="c07d4-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="c07d4-127">Чтобы определить, было ли устройство нижнего уровня Windows было присоединено к Azure AD, выполните следующую команду на устройстве:</span><span class="sxs-lookup"><span data-stu-id="c07d4-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="c07d4-128">Если устройство было ранее присоединено к Azure AD, и если устройство имеет сетевое подключение к глобальным конечным точкам Azure AD, вы увидите следующий результат:</span><span class="sxs-lookup"><span data-stu-id="c07d4-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

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

<span data-ttu-id="c07d4-129">На соответствующих устройствах будет указано "состояние устройства" со значением "неизвестно".</span><span class="sxs-lookup"><span data-stu-id="c07d4-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="c07d4-130">Если выходные данные имеют значение «устройство не присоединено» или значение "состояние устройства" имеет значение "хорошо", проигнорируйте приведенные ниже рекомендации.</span><span class="sxs-lookup"><span data-stu-id="c07d4-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="c07d4-131">Только для устройств, которые показывают, что устройство присоединено (в соответствии с идентификатором deviceId, отпечатком и т. д.), а значение Device State — "Unknown", администраторы должны выполнить следующую команду в контексте входа пользователя домена на таком устройстве:</span><span class="sxs-lookup"><span data-stu-id="c07d4-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="c07d4-132">Предыдущая команда должна выполняться только один раз для входа пользователя домена на устройстве Windows нижнего уровня.</span><span class="sxs-lookup"><span data-stu-id="c07d4-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="c07d4-133">Эту команду следует выполнить в контексте входа пользователя в домен.</span><span class="sxs-lookup"><span data-stu-id="c07d4-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="c07d4-134">Необходимо принять меры, чтобы не выполнять эту команду при последующем входе пользователя.</span><span class="sxs-lookup"><span data-stu-id="c07d4-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="c07d4-135">При выполнении предыдущей команды будет снято состояние объединения локального гибридного гибридного компьютера с присоединением Azure AD — для пользователя, выполнившего вход.</span><span class="sxs-lookup"><span data-stu-id="c07d4-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="c07d4-136">Если же компьютер по-прежнему настроен для гибридной службы Azure AD — присоединяется к клиенту, он будет пытаться присоединиться при повторном входе пользователя.</span><span class="sxs-lookup"><span data-stu-id="c07d4-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="c07d4-137">Windows Current</span><span class="sxs-lookup"><span data-stu-id="c07d4-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="c07d4-138">Не присоединение</span><span class="sxs-lookup"><span data-stu-id="c07d4-138">Unjoin</span></span>

<span data-ttu-id="c07d4-139">Чтобы определить, было ли устройство Windows 10 ранее присоединено к Azure AD, выполните следующую команду на устройстве:</span><span class="sxs-lookup"><span data-stu-id="c07d4-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="c07d4-140">Если устройство является гибридной службой Azure AD — присоединено к сети, администратор увидит следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c07d4-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="c07d4-141">Если результатом является "Азуреаджоинед: No", проигнорируйте приведенные ниже рекомендации.</span><span class="sxs-lookup"><span data-stu-id="c07d4-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="c07d4-142">Только для устройств, которые показывают, что устройство присоединено к Azure AD, выполните следующую команду в качестве администратора, чтобы удалить состояние объединения устройства.</span><span class="sxs-lookup"><span data-stu-id="c07d4-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="c07d4-143">Предыдущая команда должна выполняться один раз в административном контексте на устройстве с Windows.</span><span class="sxs-lookup"><span data-stu-id="c07d4-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="c07d4-144">Гибридная служба AD Жоин\ре-регистратион</span><span class="sxs-lookup"><span data-stu-id="c07d4-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="c07d4-145">Устройство автоматически присоединяется к Azure AD без вмешательства пользователя или администратора, если устройство имеет сетевое подключение к глобальным конечным точкам Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c07d4-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="windows-azure-ad-join"></a><span data-ttu-id="c07d4-146">Присоединение к Windows Azure AD</span><span class="sxs-lookup"><span data-stu-id="c07d4-146">Windows Azure AD Join</span></span>

<span data-ttu-id="c07d4-147">**Важно!** Субъект службы Intune будет включен после миграции в Commerce, что означает активацию регистрации устройств Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c07d4-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="c07d4-148">Если вы заблокировали регистрацию устройств Azure AD перед миграцией, необходимо отключить субъект службы Intune с PowerShell, чтобы отключить регистрацию устройств Azure AD с помощью портала Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c07d4-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="c07d4-149">Вы можете отключить субъект службы Intune с помощью этой команды в модуле PowerShell Azure Active Directory PowerShell для Graph.</span><span class="sxs-lookup"><span data-stu-id="c07d4-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="c07d4-150">Не присоединение</span><span class="sxs-lookup"><span data-stu-id="c07d4-150">Unjoin</span></span>

<span data-ttu-id="c07d4-151">Чтобы определить, было ли устройство Windows 10 было ранее присоединено к Azure AD, пользователь или администратор может выполнить следующую команду на устройстве:</span><span class="sxs-lookup"><span data-stu-id="c07d4-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="c07d4-152">Если устройство присоединено к Azure AD, пользователь или администратор увидит следующий результат:</span><span class="sxs-lookup"><span data-stu-id="c07d4-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="c07d4-153">Если результатом является "Азуреаджоинед: NO", проигнорируйте приведенные ниже рекомендации.</span><span class="sxs-lookup"><span data-stu-id="c07d4-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="c07d4-154">Пользователь: Если устройство подключено к Azure AD, пользователь может отсоединить устройство от параметров.</span><span class="sxs-lookup"><span data-stu-id="c07d4-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="c07d4-155">Убедитесь, что на устройстве есть учетная запись локального администратора, прежде чем отсоединить устройство от Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c07d4-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="c07d4-156">Для обратного входа в устройство требуется учетная запись локального администратора.</span><span class="sxs-lookup"><span data-stu-id="c07d4-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="c07d4-157">Администратор: Если администратору организации требуется отсоединить устройства пользователей, которые входят в состав Azure AD — это можно сделать, выполнив следующую команду на каждом устройстве, используя такой же механизм, как групповая политика.</span><span class="sxs-lookup"><span data-stu-id="c07d4-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="c07d4-158">Администратор должен проверить наличие учетной записи локального администратора на устройстве перед отсоединением устройства от Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c07d4-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="c07d4-159">Учетная запись локального администратора необходима для обратного входа в устройство.</span><span class="sxs-lookup"><span data-stu-id="c07d4-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="c07d4-160">Предыдущая команда должна выполняться один раз в административном контексте на устройстве с Windows.</span><span class="sxs-lookup"><span data-stu-id="c07d4-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="c07d4-161">Присоединение и повторная регистрация Azure AD</span><span class="sxs-lookup"><span data-stu-id="c07d4-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="c07d4-162">Пользователь может присоединить устройство к Azure AD из параметров Windows: **параметры > учетных записей > доступ к рабочим или учебным > подключиться**.</span><span class="sxs-lookup"><span data-stu-id="c07d4-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="windows-azure-ad-registered-company-owned"></a><span data-ttu-id="c07d4-163">Зарегистрированный Windows Azure AD (владелец компании)</span><span class="sxs-lookup"><span data-stu-id="c07d4-163">Windows Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="c07d4-164">Чтобы определить, зарегистрировано ли устройство Windows 10 в Azure AD, выполните следующую команду на устройстве:</span><span class="sxs-lookup"><span data-stu-id="c07d4-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="c07d4-165">Если устройство зарегистрировано в Azure AD, вы увидите следующий результат:</span><span class="sxs-lookup"><span data-stu-id="c07d4-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="c07d4-166">Чтобы удалить существующую учетную запись, зарегистрированную в Azure AD, на устройстве:</span><span class="sxs-lookup"><span data-stu-id="c07d4-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="c07d4-167">Чтобы удалить учетную запись, зарегистрированную в Azure AD — на устройстве, используйте Клеанупвпж, средство, которое можно скачать отсюда: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="c07d4-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="c07d4-168">Извлеките ZIP-файл и запустите **впжклеануп. cmd**.</span><span class="sxs-lookup"><span data-stu-id="c07d4-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="c07d4-169">Это средство запустит правильный исполняемый файл в соответствии с версией Windows на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c07d4-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="c07d4-170">С помощью такого механизма, как групповая политика, администратор может выполнить команду на устройстве в контексте любого пользователя, выполнившего вход на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c07d4-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="c07d4-171">Чтобы отключить диспетчер учетных записей веб-записей, чтобы зарегистрировать устройство в Azure AD, добавьте следующее значение реестра:</span><span class="sxs-lookup"><span data-stu-id="c07d4-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="c07d4-172">Расположение: Хклм\софтваре\полиЦиес\микрософт\виндовс\воркплацежоин</span><span class="sxs-lookup"><span data-stu-id="c07d4-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="c07d4-173">Тип: DWORD (32 бит)</span><span class="sxs-lookup"><span data-stu-id="c07d4-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="c07d4-174">Name: Блоккаадворкплацежоин</span><span class="sxs-lookup"><span data-stu-id="c07d4-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="c07d4-175">Данные значения: 1</span><span class="sxs-lookup"><span data-stu-id="c07d4-175">Value data: 1</span></span>

<span data-ttu-id="c07d4-176">Наличие этого значения реестра должно заблокировать присоединение к рабочему месту и предотвратить отображение приглашений на присоединение к устройству.</span><span class="sxs-lookup"><span data-stu-id="c07d4-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="c07d4-177">Android</span><span class="sxs-lookup"><span data-stu-id="c07d4-177">Android</span></span>

<span data-ttu-id="c07d4-178">Для Android пользователям потребуется отменить регистрацию и повторно зарегистрировать их устройства.</span><span class="sxs-lookup"><span data-stu-id="c07d4-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="c07d4-179">Это можно сделать с помощью приложения Microsoft Authenticator или приложения корпоративного портала.</span><span class="sxs-lookup"><span data-stu-id="c07d4-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="c07d4-180">В приложении Microsoft Authenticator пользователи могут перейти к разделу **параметры > Device Registration**.</span><span class="sxs-lookup"><span data-stu-id="c07d4-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="c07d4-181">Пользователи могут отменить регистрацию и повторно зарегистрировать их устройства.</span><span class="sxs-lookup"><span data-stu-id="c07d4-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="c07d4-182">На портале компании пользователи могут перейти на вкладку **устройства** и удалить устройство.</span><span class="sxs-lookup"><span data-stu-id="c07d4-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="c07d4-183">После этого повторно зарегистрируйте устройство с помощью корпоративного портала.</span><span class="sxs-lookup"><span data-stu-id="c07d4-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="c07d4-184">Кроме того, пользователи могут отменить регистрацию и повторно зарегистрироваться, удалив учетную запись на странице параметров учетной записи, а затем повторно добавляя рабочую учетную запись.</span><span class="sxs-lookup"><span data-stu-id="c07d4-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="c07d4-185">Отмена регистрации и повторная регистрация устройства на Android с помощью приложения проверки подлинности (Майкрософт):</span><span class="sxs-lookup"><span data-stu-id="c07d4-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="c07d4-186">Откройте приложение Microsoft Authenticator и перейдите к разделу **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="c07d4-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="c07d4-187">Выберите **Device Registration (регистрация устройства**).</span><span class="sxs-lookup"><span data-stu-id="c07d4-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="c07d4-188">Отмените регистрацию устройства, выбрав **отменить регистрацию**.</span><span class="sxs-lookup"><span data-stu-id="c07d4-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="c07d4-189">Для **регистрации устройства** повторно зарегистрируйте его, введя свой адрес электронной почты, а затем нажмите кнопку **зарегистрировать**.</span><span class="sxs-lookup"><span data-stu-id="c07d4-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="c07d4-190">Чтобы отменить регистрацию и повторно зарегистрировать устройство Android на странице параметров Android, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c07d4-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="c07d4-191">Откройте **Параметры устройства** и перейдите к разделу **учетные записи**.</span><span class="sxs-lookup"><span data-stu-id="c07d4-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="c07d4-192">Выберите рабочую учетную запись, которую необходимо повторно зарегистрировать, и выберите пункт **удалить учетную запись**.</span><span class="sxs-lookup"><span data-stu-id="c07d4-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="c07d4-193">После удаления учетной записи на странице " **учетные записи** " выберите **Добавить учетную запись > рабочий учетной записи**.</span><span class="sxs-lookup"><span data-stu-id="c07d4-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="c07d4-194">Для параметра **Присоединение к рабочему месту** введите свой адрес электронной почты и нажмите кнопку **присоединиться** , чтобы завершить регистрацию устройства.</span><span class="sxs-lookup"><span data-stu-id="c07d4-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="c07d4-195">Отмена регистрации и повторная регистрация устройства на Android с корпоративного портала:</span><span class="sxs-lookup"><span data-stu-id="c07d4-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="c07d4-196">Запустите корпоративный портал и перейдите на вкладку **устройства** .</span><span class="sxs-lookup"><span data-stu-id="c07d4-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="c07d4-197">Выберите устройство, чтобы просмотреть сведения об устройстве.</span><span class="sxs-lookup"><span data-stu-id="c07d4-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="c07d4-198">В меню многоточия (три точки) выберите пункт **удалить устройство** и завершите удаление, выполнив подтверждение в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="c07d4-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="c07d4-199">Теперь необходимо выйти из приложения корпоративного портала.</span><span class="sxs-lookup"><span data-stu-id="c07d4-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="c07d4-200">Нажмите кнопку **Вход** , чтобы повторно зарегистрировать устройство.</span><span class="sxs-lookup"><span data-stu-id="c07d4-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="c07d4-201">Для получения дополнительных сведений о действиях, которые необходимо выполнить на этапе миграции данной рабочей нагрузки, или влиянии на администрирование или использование, ознакомьтесь со сведениями об Azure Active Directory в разделе [Дополнительные общие сведения о миграции с Microsoft Cloud записей](ms-cloud-germany-transition-add-general.md#azure-active-directory).</span><span class="sxs-lookup"><span data-stu-id="c07d4-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory in [Additional general information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-add-general.md#azure-active-directory).</span></span>

## <a name="ios"></a><span data-ttu-id="c07d4-202">iOS</span><span class="sxs-lookup"><span data-stu-id="c07d4-202">iOS</span></span>

<span data-ttu-id="c07d4-203">На устройствах с iOS пользователь должен вручную удалить все кэшированные учетные записи с помощью средства проверки подлинности (Майкрософт), отменить регистрацию устройства и выйти из любых собственных приложений на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c07d4-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="c07d4-204">Шаг 1: Если этот параметр указан, удалите учетную запись из приложения для проверки подлинности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="c07d4-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="c07d4-205">Коснитесь учетной записи в приложении Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="c07d4-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="c07d4-206">Коснитесь значка **Параметры** в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="c07d4-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="c07d4-207">Если значок **Параметры** не отображается, возможно, вы не используете последнюю версию средства проверки подлинности (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="c07d4-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="c07d4-208">Нажмите кнопку **удалить учетную запись** .</span><span class="sxs-lookup"><span data-stu-id="c07d4-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="c07d4-209">Коснитесь пункта **все приложения на этом устройстве**.</span><span class="sxs-lookup"><span data-stu-id="c07d4-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="c07d4-210">Шаг 2: Отмена регистрации устройства в приложении Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="c07d4-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="c07d4-211">Коснитесь значка меню в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="c07d4-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="c07d4-212">Нажмите **Параметры** , а затем **Device Registration**.</span><span class="sxs-lookup"><span data-stu-id="c07d4-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="c07d4-213">Если ваша учетная запись отображается, нажмите кнопку **Отмена регистрации устройства** и **продолжите работу** в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="c07d4-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="c07d4-214">После этого не должна отображаться учетная запись.</span><span class="sxs-lookup"><span data-stu-id="c07d4-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="c07d4-215">Шаг 3: Выйдите из отдельных приложений, если это необходимо</span><span class="sxs-lookup"><span data-stu-id="c07d4-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="c07d4-216">Пользователи могут перейти к отдельным приложениям, например Outlook, Teams и OneDrive, и удалить учетные записи из этих приложений.</span><span class="sxs-lookup"><span data-stu-id="c07d4-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="c07d4-217">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c07d4-217">More information</span></span>

<span data-ttu-id="c07d4-218">Начало работы:</span><span class="sxs-lookup"><span data-stu-id="c07d4-218">Getting started:</span></span>

- [<span data-ttu-id="c07d4-219">Миграция из Microsoft Cloud записей в службы Office 365 в новых регионах центра обработки данных на немецком языке</span><span class="sxs-lookup"><span data-stu-id="c07d4-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="c07d4-220">Помощь по миграции Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="c07d4-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="c07d4-221">Как принять участие в миграции</span><span class="sxs-lookup"><span data-stu-id="c07d4-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="c07d4-222">Взаимодействие с пользователем во время миграции</span><span class="sxs-lookup"><span data-stu-id="c07d4-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="c07d4-223">Перемещение по переходу:</span><span class="sxs-lookup"><span data-stu-id="c07d4-223">Moving through the transition:</span></span>

- [<span data-ttu-id="c07d4-224">Действия и влияние этапов миграции</span><span class="sxs-lookup"><span data-stu-id="c07d4-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="c07d4-225">Дополнительные предварительные действия</span><span class="sxs-lookup"><span data-stu-id="c07d4-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="c07d4-226">Дополнительные сведения о [службах](ms-cloud-germany-transition-add-general.md), [устройствах](ms-cloud-germany-transition-add-devices.md), [опыте](ms-cloud-germany-transition-add-experience.md)и службах [федерации Active Directory](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="c07d4-226">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="c07d4-227">Облачные приложения:</span><span class="sxs-lookup"><span data-stu-id="c07d4-227">Cloud apps:</span></span>

- [<span data-ttu-id="c07d4-228">Сведения о программе миграции Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c07d4-228">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="c07d4-229">Сведения о программе миграции Power BI</span><span class="sxs-lookup"><span data-stu-id="c07d4-229">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="c07d4-230">Начало перехода на Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c07d4-230">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
