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
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861310"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="04acc-103">Дополнительные сведения об устройстве для миграции из Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="04acc-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="04acc-104">Подключенные и зарегистрированные устройства Azure AD, подключенные к Microsoft Cloud Deutschland, должны быть перенесены после 9-го этапа и до 10-го этапа.</span><span class="sxs-lookup"><span data-stu-id="04acc-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="04acc-105">Миграция устройства зависит от типа устройств, операционной системы и связи AAD.</span><span class="sxs-lookup"><span data-stu-id="04acc-105">The migration of a device depends on the devices type, operating system and AAD relation.</span></span> 

## <a name="frequently-asked-questions"></a><span data-ttu-id="04acc-106">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="04acc-106">Frequently asked questions</span></span>

<span data-ttu-id="04acc-107">**Как узнать, затронута ли моя организация?**</span><span class="sxs-lookup"><span data-stu-id="04acc-107">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="04acc-108">Администраторы должны проверить, есть ли у них зарегистрированные устройства `https://portal.microsoftazure.de` или устройства Azure AD.</span><span class="sxs-lookup"><span data-stu-id="04acc-108">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered or Azure AD joined devices.</span></span> <span data-ttu-id="04acc-109">Если в организации зарегистрированы устройства, это влияет на вас.</span><span class="sxs-lookup"><span data-stu-id="04acc-109">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="04acc-110">**Какое влияние оказывает на пользователей?**</span><span class="sxs-lookup"><span data-stu-id="04acc-110">**What is the impact on my users?**</span></span>

<span data-ttu-id="04acc-111">Пользователи зарегистрированного устройства больше не смогут войти после завершения [10-го](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) этапа миграции и отключения конечных точек для Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="04acc-111">Users from a registered device will no longer be able to sign in after [migration phase 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed and the endpoints for Microsoft Cloud Deutschland have been disabled.</span></span>  

<span data-ttu-id="04acc-112">Убедитесь, что все ваши устройства зарегистрированы в конечной точке во всем мире до отключения организации от Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="04acc-112">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="04acc-113">**Когда пользователи перерегистрируют свои устройства?**</span><span class="sxs-lookup"><span data-stu-id="04acc-113">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="04acc-114">Важно, чтобы после завершения [9-го](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) этапа вы регистрируете и перерегистрируете устройства.</span><span class="sxs-lookup"><span data-stu-id="04acc-114">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="04acc-115">Перед началом 10-го этапа необходимо завершить перерегистрацию, в противном случае вы можете потерять доступ к устройству.</span><span class="sxs-lookup"><span data-stu-id="04acc-115">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="04acc-116">**Как восстановить состояние устройства после миграции?**</span><span class="sxs-lookup"><span data-stu-id="04acc-116">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="04acc-117">Для устройств, Windows, зарегистрированных в Azure AD, администраторы смогут управлять миграцией этих устройств с помощью удаленных инициированных процессов, которые будут регистрировать старые состояния устройств.</span><span class="sxs-lookup"><span data-stu-id="04acc-117">For company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="04acc-118">Для всех других устройств, включая Windows устройства, зарегистрированные в Azure AD, конечный пользователь должен выполнять эти действия вручную.</span><span class="sxs-lookup"><span data-stu-id="04acc-118">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="04acc-119">Для устройств, присоединив Azure AD, пользователям необходимо иметь учетную запись локального администратора, чтобы отозарегистрировать их, а затем перерегистрируйте свои устройства.</span><span class="sxs-lookup"><span data-stu-id="04acc-119">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="04acc-120">Ниже приведены подробные инструкции по успешному восстановлению состояния устройств.</span><span class="sxs-lookup"><span data-stu-id="04acc-120">Please refer to detailed instructions for how to successfully restore device states below.</span></span> 
 
<span data-ttu-id="04acc-121">**Как узнать, что все мои устройства зарегистрированы в общедоступных облаках?**</span><span class="sxs-lookup"><span data-stu-id="04acc-121">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="04acc-122">Чтобы проверить, зарегистрированы ли устройства в общеобязуемом облаке, необходимо экспортировать и загружать список устройств с портала Azure AD в Excel таблицу.</span><span class="sxs-lookup"><span data-stu-id="04acc-122">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="04acc-123">Затем фильтруем устройства, зарегистрированные (с помощью столбца _registeredTime)_ после этапа миграции Отдельно от [Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="04acc-123">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="04acc-124">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="04acc-124">Additional considerations</span></span>
<span data-ttu-id="04acc-125">Регистрация устройства отключается после миграции клиента и не может быть включена или отключена.</span><span class="sxs-lookup"><span data-stu-id="04acc-125">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> 

<span data-ttu-id="04acc-126">Если Intune не используется, включите подписку и запустите эту команду, чтобы повторно активировать параметр:</span><span class="sxs-lookup"><span data-stu-id="04acc-126">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
<span data-ttu-id="04acc-127">**ВАЖНО:** Принцип службы Intune будет включен после миграции коммерции, которая подразумевает активацию регистрации устройств Azure AD.</span><span class="sxs-lookup"><span data-stu-id="04acc-127">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="04acc-128">Если вы заблокировали регистрацию устройств Azure AD перед миграцией, необходимо отключить главу службы Intune с PowerShell, чтобы снова отключить регистрацию устройств Azure AD на портале Azure AD.</span><span class="sxs-lookup"><span data-stu-id="04acc-128">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="04acc-129">Вы можете отключить главу службы Intune с этой командой в Azure Active Directory PowerShell для Graph модуля.</span><span class="sxs-lookup"><span data-stu-id="04acc-129">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a><span data-ttu-id="04acc-130">Регистрация Azure AD</span><span class="sxs-lookup"><span data-stu-id="04acc-130">Azure AD Join</span></span>
<span data-ttu-id="04acc-131">Это относится к Windows 10 устройствам.</span><span class="sxs-lookup"><span data-stu-id="04acc-131">This applies to Windows 10 devices.</span></span> 

<span data-ttu-id="04acc-132">Если устройство подключено к Azure AD, оно должно быть отключено от Azure AD и снова подключено.</span><span class="sxs-lookup"><span data-stu-id="04acc-132">If a device is Azure AD joined, it must be disconnected from Azure AD and be connected again.</span></span> 

<span data-ttu-id="04acc-133">[![Устройство Azure AD ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="04acc-133">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="04acc-134">Если пользователь является администратором на Windows 10, пользователь может оторегистрить устройство из Azure AD и снова присоединиться к нему.</span><span class="sxs-lookup"><span data-stu-id="04acc-134">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again.</span></span> <span data-ttu-id="04acc-135">Если у него нет прав администратора, пользователю необходимы учетные данные учетной записи локального администратора на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="04acc-135">If he has no administrator privileges, the user needs credentials of a local administrator account on this machine.</span></span> 


<span data-ttu-id="04acc-136">Администратор может создать учетную запись локального администратора на устройстве по следующему пути настройки:</span><span class="sxs-lookup"><span data-stu-id="04acc-136">An Administrator can create an local administrator account on the device following this configuration path:</span></span>

<span data-ttu-id="04acc-137">*Параметры > учетные записи > другие учетные записи > учетные данные неизвестные > Добавить пользователя без Microsoft-Account*</span><span class="sxs-lookup"><span data-stu-id="04acc-137">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="04acc-138">Шаг 1. Определите, присоединилось ли устройство к Azure ID</span><span class="sxs-lookup"><span data-stu-id="04acc-138">Step 1: Determine if the device is Azure ID joined</span></span>
1.  <span data-ttu-id="04acc-139">Вход с помощью электронной почты и пароля пользователей.</span><span class="sxs-lookup"><span data-stu-id="04acc-139">Sign In with users E-mail and password.</span></span>
2.  <span data-ttu-id="04acc-140">Перейдите Параметры > учетные записи > работу или школу.</span><span class="sxs-lookup"><span data-stu-id="04acc-140">Go to Settings > Accounts > Access Work Or School.</span></span> 
3.  <span data-ttu-id="04acc-141">Найми пользователя в списке с **подключением к ... 's Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="04acc-141">Look for a user in the list with **connected to … ‘s Azure AD**.</span></span> 
4.  <span data-ttu-id="04acc-142">Если подключенный пользователь существует, приступить к шагу 2.</span><span class="sxs-lookup"><span data-stu-id="04acc-142">If a connected user exists, proceed with Step 2.</span></span> <span data-ttu-id="04acc-143">Если нет, никаких дальнейших действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="04acc-143">If not, no further action is required.</span></span>
### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="04acc-144">Шаг 2. Отключение устройства от Azure AD</span><span class="sxs-lookup"><span data-stu-id="04acc-144">Step 2: Disconnect the device from Azure AD</span></span>
1.  <span data-ttu-id="04acc-145">Нажмите **кнопку Отключение** на подключенной работе или учетной записи школы.</span><span class="sxs-lookup"><span data-stu-id="04acc-145">Tap **Disconnect** on the connected work or School Account.</span></span> 
2.  <span data-ttu-id="04acc-146">Дважды подтвердите отключение.</span><span class="sxs-lookup"><span data-stu-id="04acc-146">Confirm the disconnect twice.</span></span> 
3.  <span data-ttu-id="04acc-147">Введите имя пользователя и пароль местного администратора.</span><span class="sxs-lookup"><span data-stu-id="04acc-147">Enter the local administrator username and password.</span></span> <span data-ttu-id="04acc-148">Устройство отключено.</span><span class="sxs-lookup"><span data-stu-id="04acc-148">The device is disconnected.</span></span>
4.  <span data-ttu-id="04acc-149">Перезапустите устройство.</span><span class="sxs-lookup"><span data-stu-id="04acc-149">Restart the device.</span></span>
### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="04acc-150">Шаг 3. Присоединиться к устройству в Azure AD</span><span class="sxs-lookup"><span data-stu-id="04acc-150">Step 3: Join the device to Azure AD</span></span>
1.  <span data-ttu-id="04acc-151">пользователь впишется с учетными данными местного администратора</span><span class="sxs-lookup"><span data-stu-id="04acc-151">the user signs in with the credentials of the local administrator</span></span>
2.  <span data-ttu-id="04acc-152">Перейдите **в Параметры** **учетные записи,** а затем **доступ к работе или школе**</span><span class="sxs-lookup"><span data-stu-id="04acc-152">Go to **Settings** then **Accounts** then **Access Work Or School**</span></span>
3.  <span data-ttu-id="04acc-153">Нажмите **Подключение**</span><span class="sxs-lookup"><span data-stu-id="04acc-153">Tap **Connect**</span></span>
4.  <span data-ttu-id="04acc-154">**ВАЖНО:** нажмите **кнопку Присоединиться к Azure AD**</span><span class="sxs-lookup"><span data-stu-id="04acc-154">**IMPORTANT**: Tap **Join to Azure AD**</span></span>
5.  <span data-ttu-id="04acc-155">Введите адрес электронной почты и пароль пользователя.</span><span class="sxs-lookup"><span data-stu-id="04acc-155">Enter the e-mail address and password of the user.</span></span> <span data-ttu-id="04acc-156">Устройство подключено</span><span class="sxs-lookup"><span data-stu-id="04acc-156">The device is connected</span></span>
6.  <span data-ttu-id="04acc-157">Перезапуск устройства</span><span class="sxs-lookup"><span data-stu-id="04acc-157">Restart the device</span></span> 
7.  <span data-ttu-id="04acc-158">вход с адресом электронной почты и паролем</span><span class="sxs-lookup"><span data-stu-id="04acc-158">sign with your e-mail address and password</span></span>

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="04acc-159">Azure AD Registered (Company owned)</span><span class="sxs-lookup"><span data-stu-id="04acc-159">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="04acc-160">Чтобы определить, Windows 10 зарегистрировано ли устройство Azure AD, запустите следующую команду на устройстве:</span><span class="sxs-lookup"><span data-stu-id="04acc-160">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="04acc-161">Если устройство зарегистрировано Azure AD, вы увидите следующий вывод:</span><span class="sxs-lookup"><span data-stu-id="04acc-161">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="04acc-162">Удаление существующей учетной записи Azure AD на устройстве:</span><span class="sxs-lookup"><span data-stu-id="04acc-162">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="04acc-163">Чтобы удалить учетную запись Azure AD на устройстве, используйте Средство CleanupWPJ, которое можно скачать [ здесь:CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="04acc-163">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="04acc-164">Извлеките файл ZIP и запустите **WPJCleanup.cmd**.</span><span class="sxs-lookup"><span data-stu-id="04acc-164">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="04acc-165">Этот инструмент запустит правильный исполняемый на основе версии Windows на устройстве.</span><span class="sxs-lookup"><span data-stu-id="04acc-165">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="04acc-166">С помощью такого механизма, как групповой политики, администратор может запустить команду на устройстве в контексте любого пользователя, который подписан на устройстве.</span><span class="sxs-lookup"><span data-stu-id="04acc-166">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="04acc-167">Чтобы отключить запросы диспетчера веб-учетных записей для регистрации устройства в Azure AD, добавьте это значение реестра:</span><span class="sxs-lookup"><span data-stu-id="04acc-167">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="04acc-168">Расположение: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="04acc-168">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="04acc-169">Тип: DWORD (32 бита)</span><span class="sxs-lookup"><span data-stu-id="04acc-169">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="04acc-170">Имя: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="04acc-170">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="04acc-171">Данные значения: 1</span><span class="sxs-lookup"><span data-stu-id="04acc-171">Value data: 1</span></span>

<span data-ttu-id="04acc-172">Наличие этого значения реестра должно блокировать вступление на рабочем месте и запретить пользователям видеть подсказки для перейти на устройство.</span><span class="sxs-lookup"><span data-stu-id="04acc-172">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="04acc-173">Android</span><span class="sxs-lookup"><span data-stu-id="04acc-173">Android</span></span>

<span data-ttu-id="04acc-174">Для Android пользователям потребуется оторегистрируйте и перерегистрируйте свои устройства.</span><span class="sxs-lookup"><span data-stu-id="04acc-174">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="04acc-175">Это можно сделать с помощью Microsoft Authenticator или Корпоративный портал приложения.</span><span class="sxs-lookup"><span data-stu-id="04acc-175">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="04acc-176">В приложении Microsoft Authenticator пользователи могут перейти к Параметры > **регистрации устройств.**</span><span class="sxs-lookup"><span data-stu-id="04acc-176">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="04acc-177">Оттуда пользователи могут отрегистрируйте и перерегистрируйте свое устройство.</span><span class="sxs-lookup"><span data-stu-id="04acc-177">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="04acc-178">С Корпоративный портал пользователи могут перейти на вкладку **Devices** и удалить устройство.</span><span class="sxs-lookup"><span data-stu-id="04acc-178">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="04acc-179">После этого повторно зарегистрив устройство с помощью Корпоративный портал.</span><span class="sxs-lookup"><span data-stu-id="04acc-179">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="04acc-180">Пользователи также могут отрегистрируйтесь и перерегистрируйтесь, удалив учетную запись со страницы параметров учетной записи, а затем повторно добавив учетную запись.</span><span class="sxs-lookup"><span data-stu-id="04acc-180">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="04acc-181">Для регистрации и перерегистрации устройства на Android с помощью Microsoft Authenticator приложения:</span><span class="sxs-lookup"><span data-stu-id="04acc-181">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="04acc-182">Откройте приложение Microsoft Authenticator и перейдите **в Параметры**.</span><span class="sxs-lookup"><span data-stu-id="04acc-182">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="04acc-183">Выберите **регистрацию устройства.**</span><span class="sxs-lookup"><span data-stu-id="04acc-183">Select **Device registration**.</span></span>
3.  <span data-ttu-id="04acc-184">Незарегистрированное устройство, выбрав **Unregister**.</span><span class="sxs-lookup"><span data-stu-id="04acc-184">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="04acc-185">Для **регистрации устройства** перерегистрируйте устройство, введя адрес электронной почты, а затем выберите **Register**.</span><span class="sxs-lookup"><span data-stu-id="04acc-185">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="04acc-186">Для регистрации и перерегистрации устройства Android на странице Android Параметры:</span><span class="sxs-lookup"><span data-stu-id="04acc-186">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="04acc-187">Откройте **устройство Параметры** и перейдите к **учетным записям.**</span><span class="sxs-lookup"><span data-stu-id="04acc-187">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="04acc-188">Выберите учетную запись работы, которую необходимо перерегистрируйте, и выберите **учетную запись Remove.**</span><span class="sxs-lookup"><span data-stu-id="04acc-188">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="04acc-189">После удаления учетной записи со страницы **Учетные** записи выберите учетную запись **Add Account > work account.**</span><span class="sxs-lookup"><span data-stu-id="04acc-189">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="04acc-190">Для **workplace Join** введите адрес электронной почты и выберите **Присоединиться,** чтобы завершить регистрацию устройства.</span><span class="sxs-lookup"><span data-stu-id="04acc-190">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="04acc-191">Для регистрации и перерегистрации устройства на Android с Корпоративный портал:</span><span class="sxs-lookup"><span data-stu-id="04acc-191">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="04acc-192">Запустите Корпоративный портал и перейдите на **вкладку Devices.**</span><span class="sxs-lookup"><span data-stu-id="04acc-192">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="04acc-193">Выберите устройство, чтобы увидеть сведения об устройстве.</span><span class="sxs-lookup"><span data-stu-id="04acc-193">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="04acc-194">Из меню эллипсов (три точки) выберите **Remove Device** и выполните удаление, подтвердив в диалоговом окантовке.</span><span class="sxs-lookup"><span data-stu-id="04acc-194">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="04acc-195">Теперь вы должны войти в систему из Корпоративный портал приложения.</span><span class="sxs-lookup"><span data-stu-id="04acc-195">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="04acc-196">Выберите **вход для** повторной регистрации устройства.</span><span class="sxs-lookup"><span data-stu-id="04acc-196">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="04acc-197">Дополнительные сведения о любых действиях, необходимых на этапе миграции этой рабочей нагрузки или воздействии на администрирование или использование, см. в Azure Active Directory (Azure AD) в дополнительных сведениях Azure AD для миграции из [Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span><span class="sxs-lookup"><span data-stu-id="04acc-197">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="04acc-198">iOS</span><span class="sxs-lookup"><span data-stu-id="04acc-198">iOS</span></span>

<span data-ttu-id="04acc-199">На устройствах iOS пользователю необходимо вручную удалить все кэшированные учетные записи из Microsoft Authenticator, отрегистрить устройство и выйти из любых родных приложений на устройстве.</span><span class="sxs-lookup"><span data-stu-id="04acc-199">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="04acc-200">Шаг 1. Если она присутствует, удалите учетную запись из Microsoft Authenticator приложения</span><span class="sxs-lookup"><span data-stu-id="04acc-200">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="04acc-201">Нажмите на учетную запись в Microsoft Authenticator приложении.</span><span class="sxs-lookup"><span data-stu-id="04acc-201">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="04acc-202">Нажмите **значок Параметры** в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="04acc-202">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="04acc-203">Если вы не видите значок **Параметры,** возможно, вы не используете последнюю версию Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="04acc-203">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="04acc-204">Нажмите **кнопку Удалить учетную запись.**</span><span class="sxs-lookup"><span data-stu-id="04acc-204">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="04acc-205">Нажмите **кнопку Все приложения на этом устройстве**.</span><span class="sxs-lookup"><span data-stu-id="04acc-205">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="04acc-206">Шаг 2. Незарегистрированное устройство из Microsoft Authenticator приложения</span><span class="sxs-lookup"><span data-stu-id="04acc-206">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="04acc-207">Нажмите значок меню в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="04acc-207">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="04acc-208">Нажмите **кнопку Параметры,** а затем **регистрация устройств.**</span><span class="sxs-lookup"><span data-stu-id="04acc-208">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="04acc-209">Если учетная запись отображается, нажмите **кнопку Незарегистрированное устройство** **и продолжайте** в диалоговом окте.</span><span class="sxs-lookup"><span data-stu-id="04acc-209">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="04acc-210">После этого вы не должны видеть учетную запись.</span><span class="sxs-lookup"><span data-stu-id="04acc-210">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="04acc-211">Шаг 3. При необходимости выпишитесь из отдельных приложений</span><span class="sxs-lookup"><span data-stu-id="04acc-211">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="04acc-212">Пользователи могут перейти к отдельным приложениям, Outlook, Teams и OneDrive, а также удалить учетные записи из этих приложений.</span><span class="sxs-lookup"><span data-stu-id="04acc-212">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="04acc-213">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="04acc-213">More information</span></span>

<span data-ttu-id="04acc-214">Начало работы:</span><span class="sxs-lookup"><span data-stu-id="04acc-214">Getting started:</span></span>

- [<span data-ttu-id="04acc-215">Миграция из Microsoft Cloud Deutschland в Office 365 службы в новых немецких регионах центра обработки данных</span><span class="sxs-lookup"><span data-stu-id="04acc-215">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="04acc-216">Помощь по миграции Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="04acc-216">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="04acc-217">Как принять участие в миграции</span><span class="sxs-lookup"><span data-stu-id="04acc-217">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="04acc-218">Опыт работы с клиентами во время миграции</span><span class="sxs-lookup"><span data-stu-id="04acc-218">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="04acc-219">Перемещение по переходу:</span><span class="sxs-lookup"><span data-stu-id="04acc-219">Moving through the transition:</span></span>

- [<span data-ttu-id="04acc-220">Действия и влияние этапов миграции</span><span class="sxs-lookup"><span data-stu-id="04acc-220">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="04acc-221">Дополнительная предварительная работа</span><span class="sxs-lookup"><span data-stu-id="04acc-221">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="04acc-222">Дополнительные сведения [для Azure AD,](ms-cloud-germany-transition-azure-ad.md) [устройств,](ms-cloud-germany-transition-add-devices.md) [опытом](ms-cloud-germany-transition-add-experience.md)и [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="04acc-222">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="04acc-223">Облачные приложения:</span><span class="sxs-lookup"><span data-stu-id="04acc-223">Cloud apps:</span></span>

- [<span data-ttu-id="04acc-224">Сведения о программе миграции Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="04acc-224">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="04acc-225">Сведения о программе миграции Power BI</span><span class="sxs-lookup"><span data-stu-id="04acc-225">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="04acc-226">Начало перехода на Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="04acc-226">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)