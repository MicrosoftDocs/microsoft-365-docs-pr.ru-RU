---
title: Microsoft Defender для управления конечными точками управления устройствами, служба хранилища управления доступом
description: A walk-through about Microsoft Defender for Endpoint
keywords: съемное хранилище
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8b32ab5162e0022d9500f7ddba2fe5bbca1017e7
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229579"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="eb2d3-104">Microsoft Defender для управления конечными точками управления устройствами, служба хранилища управления доступом</span><span class="sxs-lookup"><span data-stu-id="eb2d3-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="eb2d3-105">Microsoft Defender для управления конечными устройствами съемные служба хранилища управления доступом позволяет вам сделать следующую задачу:</span><span class="sxs-lookup"><span data-stu-id="eb2d3-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="eb2d3-106">аудит, разрешение или предотвращение чтения, записи или выполнения доступа к съемным хранилищам с исключением или без него</span><span class="sxs-lookup"><span data-stu-id="eb2d3-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="eb2d3-107">Привилегии</span><span class="sxs-lookup"><span data-stu-id="eb2d3-107">Privilege</span></span> |<span data-ttu-id="eb2d3-108">Разрешение</span><span class="sxs-lookup"><span data-stu-id="eb2d3-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="eb2d3-109">Доступ</span><span class="sxs-lookup"><span data-stu-id="eb2d3-109">Access</span></span>    |  <span data-ttu-id="eb2d3-110">Чтение, Запись, Выполнение</span><span class="sxs-lookup"><span data-stu-id="eb2d3-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="eb2d3-111">Режим действия</span><span class="sxs-lookup"><span data-stu-id="eb2d3-111">Action Mode</span></span>    |    <span data-ttu-id="eb2d3-112">Аудит, разрешить, предотвратить</span><span class="sxs-lookup"><span data-stu-id="eb2d3-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="eb2d3-113">Поддержка CSP</span><span class="sxs-lookup"><span data-stu-id="eb2d3-113">CSP Support</span></span>   |   <span data-ttu-id="eb2d3-114">Да</span><span class="sxs-lookup"><span data-stu-id="eb2d3-114">Yes</span></span>      |
|<span data-ttu-id="eb2d3-115">Поддержка GPO</span><span class="sxs-lookup"><span data-stu-id="eb2d3-115">GPO Support</span></span>    |   <span data-ttu-id="eb2d3-116">Да</span><span class="sxs-lookup"><span data-stu-id="eb2d3-116">Yes</span></span>      |
|<span data-ttu-id="eb2d3-117">Поддержка на основе пользователя</span><span class="sxs-lookup"><span data-stu-id="eb2d3-117">User-based Support</span></span>     |   <span data-ttu-id="eb2d3-118">Да</span><span class="sxs-lookup"><span data-stu-id="eb2d3-118">Yes</span></span>      |
|<span data-ttu-id="eb2d3-119">Поддержка на основе машин</span><span class="sxs-lookup"><span data-stu-id="eb2d3-119">Machine-based Support</span></span>    |    <span data-ttu-id="eb2d3-120">Да</span><span class="sxs-lookup"><span data-stu-id="eb2d3-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="eb2d3-121">Подготовка конечных точек</span><span class="sxs-lookup"><span data-stu-id="eb2d3-121">Prepare your endpoints</span></span>

<span data-ttu-id="eb2d3-122">Развертывание служба хранилища управления доступом Windows 10 устройствах с клиентской версией **4.18.2103.3** или более поздней версии .</span><span class="sxs-lookup"><span data-stu-id="eb2d3-122">Deploy Removable Storage Access Control on Windows 10 devices that have antimalware client version **4.18.2103.3 or later**.</span></span>

- <span data-ttu-id="eb2d3-123">**4.18.2104** или более поздние : Добавление SerialNumberId, VID_PID, поддержка GPO на основе filepath, ComputerSid</span><span class="sxs-lookup"><span data-stu-id="eb2d3-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span></span>

- <span data-ttu-id="eb2d3-124">**4.18.2105** или более поздний: Добавьте поддержку wildcard для HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, сочетание определенного пользователя на определенном компьютере, удаляемая поддержка SSD (SSD SanDisk Extreme)/USB, присоединенная к SCSI (UAS).</span><span class="sxs-lookup"><span data-stu-id="eb2d3-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="Интерфейс PowerShell":::

> [!NOTE]
> <span data-ttu-id="eb2d3-126">Ни один Безопасность Windows не должен быть активным, вы можете запускать съемные служба хранилища управления доступом независимо от Безопасность Windows состояния.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-126">None of Windows Security components need to be active, you can run Removable Storage Access Control independent of Windows Security status.</span></span>

## <a name="policy-properties"></a><span data-ttu-id="eb2d3-127">Свойства политики</span><span class="sxs-lookup"><span data-stu-id="eb2d3-127">Policy properties</span></span>

<span data-ttu-id="eb2d3-128">Для создания съемной группы хранения можно использовать следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="eb2d3-128">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="eb2d3-129">**Имя свойства: Group Id**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-129">**Property name: Group Id**</span></span>

1. <span data-ttu-id="eb2d3-130">Описание: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), уникальный ID, представляет группу и будет использоваться в политике.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-130">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="eb2d3-131">**Имя свойства: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-131">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="eb2d3-132">Описание. Список свойств устройств, которые необходимо использовать для покрытия в группе.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-132">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="eb2d3-133">Список свойств устройств, которые необходимо использовать для покрытия в группе.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-133">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="eb2d3-134">Дополнительные подробности см. в разделе **Свойства** устройства.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-134">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="eb2d3-135">Параметры:</span><span class="sxs-lookup"><span data-stu-id="eb2d3-135">Options:</span></span>

    - <span data-ttu-id="eb2d3-136">Основной ID</span><span class="sxs-lookup"><span data-stu-id="eb2d3-136">Primary ID</span></span>
        - <span data-ttu-id="eb2d3-137">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="eb2d3-137">RemovableMediaDevices</span></span>
        - <span data-ttu-id="eb2d3-138">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="eb2d3-138">CdRomDevices</span></span>
    - <span data-ttu-id="eb2d3-139">DeviceId</span><span class="sxs-lookup"><span data-stu-id="eb2d3-139">DeviceId</span></span>
    - <span data-ttu-id="eb2d3-140">HardwareId</span><span class="sxs-lookup"><span data-stu-id="eb2d3-140">HardwareId</span></span>
    - <span data-ttu-id="eb2d3-141">InstancePathId: InstancePathId — это строка, которая однозначно идентифицирует устройство в системе, например USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-141">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="eb2d3-142">Номер в конце **(например,&0)** представляет доступный слот и может изменяться с устройства на устройство.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-142">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="eb2d3-143">Для наилучших результатов используйте под диктовую карточку в конце.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-143">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="eb2d3-144">Например, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="eb2d3-144">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="eb2d3-145">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="eb2d3-145">FriendlyNameId</span></span>
    - <span data-ttu-id="eb2d3-146">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="eb2d3-146">SerialNumberId</span></span>
    - <span data-ttu-id="eb2d3-147">VID</span><span class="sxs-lookup"><span data-stu-id="eb2d3-147">VID</span></span>
    - <span data-ttu-id="eb2d3-148">PID</span><span class="sxs-lookup"><span data-stu-id="eb2d3-148">PID</span></span>
    - <span data-ttu-id="eb2d3-149">VID_PID</span><span class="sxs-lookup"><span data-stu-id="eb2d3-149">VID_PID</span></span>
        - <span data-ttu-id="eb2d3-150">0751_55E0: соответствует именно этой паре VID/PID</span><span class="sxs-lookup"><span data-stu-id="eb2d3-150">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="eb2d3-151">_55E0: соотнося все носители с PID=55E0</span><span class="sxs-lookup"><span data-stu-id="eb2d3-151">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="eb2d3-152">0751_: совпадает с любыми носители с VID=0751</span><span class="sxs-lookup"><span data-stu-id="eb2d3-152">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="eb2d3-153">**Имя свойства: MatchType**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-153">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="eb2d3-154">Описание. Если в descriptorIDList используется несколько свойств устройств, MatchType определяет связь.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-154">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="eb2d3-155">Параметры:</span><span class="sxs-lookup"><span data-stu-id="eb2d3-155">Options:</span></span>

    - <span data-ttu-id="eb2d3-156">MatchAll: Любые атрибуты в descriptorIdList **будут** и отношения; например, если администратор ставит DeviceID и InstancePathID, для каждого подключенного USB система будет проверять, соответствует ли USB обоим значениям.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-156">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>
    - <span data-ttu-id="eb2d3-157">MatchAny: атрибуты в descriptorIdList будут **или отношения;** например, если администратор ставит DeviceID и InstancePathID, для каждого подключенного USB система будет работать с исполнением до тех пор, пока USB имеет одинаковое значение **DeviceID** или **InstanceID.**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-157">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="eb2d3-158">Ниже следующую ниже следующую следующую политику политики управления доступом:</span><span class="sxs-lookup"><span data-stu-id="eb2d3-158">Following are the access control policy properties:</span></span>

<span data-ttu-id="eb2d3-159">**Имя свойства: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-159">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="eb2d3-160">Описание. [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), уникальный ID, представляет политику и будет использоваться в отчетности и устранении неполадок.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-160">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="eb2d3-161">**Имя свойства: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-161">**Property name: IncludedIdList**</span></span>

2. <span data-ttu-id="eb2d3-162">Описание. Группа(ы), к которую будет применена политика.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-162">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="eb2d3-163">Если добавлено несколько групп, политика будет применяться к любым средствам массовой информации во всех этих группах.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-163">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

3. <span data-ttu-id="eb2d3-164">Параметры. В этом экземпляре необходимо использовать групповой ID/GUID.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-164">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="eb2d3-165">В следующем примере показано использование GroupID:</span><span class="sxs-lookup"><span data-stu-id="eb2d3-165">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="eb2d3-166">**Имя свойства: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-166">**Property name: ExcludedIDList**</span></span>

<span data-ttu-id="eb2d3-167">Описание. Группа(ы), к которую политика не будет применяться.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-167">Description: The group(s) that the policy will not be applied to.</span></span>

<span data-ttu-id="eb2d3-168">Параметры. В этом экземпляре необходимо использовать групповой ID/GUID.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-168">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="eb2d3-169">**Имя свойства: Id записи**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-169">**Property name: Entry Id**</span></span>

1. <span data-ttu-id="eb2d3-170">Описание. One PolicyRule может иметь несколько записей; каждая запись с уникальным GUID сообщает устройству Управление одним ограничением.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-170">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="eb2d3-171">**Имя свойства. Введите**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-171">**Property name: Type**</span></span>

1. <span data-ttu-id="eb2d3-172">Описание. Определяет действие для съемных групп хранения в IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-172">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="eb2d3-173">Правоприменители: разрешить или запретить</span><span class="sxs-lookup"><span data-stu-id="eb2d3-173">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="eb2d3-174">Аудит: AuditAllowed или AuditDenied</span><span class="sxs-lookup"><span data-stu-id="eb2d3-174">Audit: AuditAllowed or AuditDenied</span></span> 

2. <span data-ttu-id="eb2d3-175">Параметры:</span><span class="sxs-lookup"><span data-stu-id="eb2d3-175">Options:</span></span>

    - <span data-ttu-id="eb2d3-176">Разрешить</span><span class="sxs-lookup"><span data-stu-id="eb2d3-176">Allow</span></span>
    - <span data-ttu-id="eb2d3-177">"Запретить"</span><span class="sxs-lookup"><span data-stu-id="eb2d3-177">Deny</span></span>
    - <span data-ttu-id="eb2d3-178">AuditAllowed: определяет уведомление и событие при разрешенных доступах</span><span class="sxs-lookup"><span data-stu-id="eb2d3-178">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="eb2d3-179">AuditDenied: определяет уведомление и событие при отказе в доступе; должна работать вместе с **отказом во** входе.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-179">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="eb2d3-180">Если существуют типы конфликтов для одного и того же носитела, система применяет первый в политике.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-180">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="eb2d3-181">Пример типа конфликта — **Разрешить и** **запретить.**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-181">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="eb2d3-182">**Имя свойства: Sid**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-182">**Property name: Sid**</span></span>

<span data-ttu-id="eb2d3-183">Описание. Определяет, применяется ли эта политика к определенной группе пользователей или пользователей; одна запись может иметь максимум один Sid и запись без каких-либо средств Sid применения политики на машине.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-183">Description: Defines whether apply this policy over specific user or user group; one entry can have maximum one Sid and an entry without any Sid means applying the policy over the machine.</span></span>

<span data-ttu-id="eb2d3-184">**Имя свойства: ComputerSid**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-184">**Property name: ComputerSid**</span></span>

<span data-ttu-id="eb2d3-185">Описание. Определяет, применяется ли эта политика к определенной группе машин или машин; одна запись может иметь максимум один ComputerSid и запись без средств ComputerSid, применяющих политику на компьютере.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-185">Description: Defines whether apply this policy over specific machine or machine group; one entry can have maximum one ComputerSid and an entry without any ComputerSid means applying the policy over the machine.</span></span> <span data-ttu-id="eb2d3-186">Если вы хотите применить запись к определенному пользователю и определенной машине, добавьте и Sid, и ComputerSid в ту же запись.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-186">If you want to apply an Entry to a specific user and specific machine, add both Sid and ComputerSid into the same Entry.</span></span>

<span data-ttu-id="eb2d3-187">**Имя свойства: Параметры**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-187">**Property name: Options**</span></span>

<span data-ttu-id="eb2d3-188">Описание. Определяет, следует ли отображать уведомление или нет.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-188">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="Экран, на котором можно увидеть состояние устройства":::

<span data-ttu-id="eb2d3-190">Параметры: 0-4.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-190">Options: 0-4.</span></span> <span data-ttu-id="eb2d3-191">При выборе типа Разрешить или Запретить:</span><span class="sxs-lookup"><span data-stu-id="eb2d3-191">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="eb2d3-192">0: ничего</span><span class="sxs-lookup"><span data-stu-id="eb2d3-192">0: nothing</span></span>
   - <span data-ttu-id="eb2d3-193">4. отключить **AuditAllowed и** **AuditDenied для** этой записи.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-193">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="eb2d3-194">Даже если **произойдет блокировка** и **настроен параметр AuditDenied,** система не будет показывать уведомления.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-194">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="eb2d3-195">Когда выбран **тип AuditAllowed** или **AuditDenied:**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-195">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="eb2d3-196">0: ничего</span><span class="sxs-lookup"><span data-stu-id="eb2d3-196">0: nothing</span></span>
   - <span data-ttu-id="eb2d3-197">1. уведомление о показе</span><span class="sxs-lookup"><span data-stu-id="eb2d3-197">1: show notification</span></span>
   - <span data-ttu-id="eb2d3-198">2. Событие отправки</span><span class="sxs-lookup"><span data-stu-id="eb2d3-198">2: send event</span></span>
   - <span data-ttu-id="eb2d3-199">3. показать уведомление и отправить событие</span><span class="sxs-lookup"><span data-stu-id="eb2d3-199">3: show notification and send event</span></span>

<span data-ttu-id="eb2d3-200">**Имя свойства: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-200">**Property name: AccessMask**</span></span>

<span data-ttu-id="eb2d3-201">Описание. Определяет доступ.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-201">Description: Defines the access.</span></span>

<span data-ttu-id="eb2d3-202">Параметры 1-7:</span><span class="sxs-lookup"><span data-stu-id="eb2d3-202">Options 1-7:</span></span>
  - <span data-ttu-id="eb2d3-203">1. Чтение</span><span class="sxs-lookup"><span data-stu-id="eb2d3-203">1: Read</span></span>
  - <span data-ttu-id="eb2d3-204">2. Записыв</span><span class="sxs-lookup"><span data-stu-id="eb2d3-204">2: Write</span></span>
  - <span data-ttu-id="eb2d3-205">3. Чтение и написание</span><span class="sxs-lookup"><span data-stu-id="eb2d3-205">3: Read and Write</span></span>
  - <span data-ttu-id="eb2d3-206">4. Выполнение</span><span class="sxs-lookup"><span data-stu-id="eb2d3-206">4: Execute</span></span>
  - <span data-ttu-id="eb2d3-207">5. Чтение и выполнение</span><span class="sxs-lookup"><span data-stu-id="eb2d3-207">5: Read and Execute</span></span>
  - <span data-ttu-id="eb2d3-208">6. Написать и выполнить</span><span class="sxs-lookup"><span data-stu-id="eb2d3-208">6: Write and Execute</span></span>
  - <span data-ttu-id="eb2d3-209">7. Чтение и написание и выполнение</span><span class="sxs-lookup"><span data-stu-id="eb2d3-209">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="eb2d3-210">Распространенные сценарии служба хранилища управления доступом</span><span class="sxs-lookup"><span data-stu-id="eb2d3-210">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="eb2d3-211">Чтобы помочь вам ознакомиться с Microsoft Defender для конечной точки съемной служба хранилища управления доступом, мы собрали несколько распространенных сценариев для вас, чтобы следовать.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-211">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="eb2d3-212">Сценарий 1. Предотвращение записи и выполнения доступа ко всем пользователям, но разрешить определенные утвержденные usBs</span><span class="sxs-lookup"><span data-stu-id="eb2d3-212">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="eb2d3-213">Создание групп</span><span class="sxs-lookup"><span data-stu-id="eb2d3-213">Create groups</span></span>

    1. <span data-ttu-id="eb2d3-214">Группа 1. Любое съемное хранилище и CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-214">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="eb2d3-215">Пример съемного хранилища и CD/DVD: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** в примере Any Removable служба хранилища и [CD-DVD Group.xmlфайл.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="eb2d3-215">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="eb2d3-216">Группа 2. Утвержденные usBs на основе свойств устройств.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-216">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="eb2d3-217">Пример для этого случая использования: Экземпляр ID — Group **65fa649a-a111-4912-9294-fb6337a25038** в примере утвержденных [usBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) файл.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-217">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eb2d3-218">Вы должны `&` заменить `&amp;` в значении.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-218">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="eb2d3-219">Создание политики</span><span class="sxs-lookup"><span data-stu-id="eb2d3-219">Create policy</span></span>

    1. <span data-ttu-id="eb2d3-220">Политика 1. Заблокировать записи и выполнить доступ, но разрешить утвержденные usBs.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-220">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="eb2d3-221">Пример этого примера использования: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** в примере [Scenario 1 Block Write and Execute Access,](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) но разрешает утвержденный USBs.xmlфайл.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-221">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="eb2d3-222">Политика 2. Проверка записи и выполнения доступа к разрешенным usBs.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-222">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="eb2d3-223">Пример этого примера использования: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** в примере [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-223">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="eb2d3-224">Сценарий 2. Проверка записи и выполнения доступа ко всем, кроме блокировки определенных неодобренных usBs</span><span class="sxs-lookup"><span data-stu-id="eb2d3-224">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="eb2d3-225">Создание групп</span><span class="sxs-lookup"><span data-stu-id="eb2d3-225">Create groups</span></span>

    1. <span data-ttu-id="eb2d3-226">Группа 1. Любое съемное хранилище и CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-226">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="eb2d3-227">Пример этого примера использования: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** в примере Любые съемные служба хранилища и [CD-DVD-Group.xmlфайл.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="eb2d3-227">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="eb2d3-228">Группа 2. [Unapproved](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) USBs на основе свойств устройств, например, ID поставщика / ID продукта, Friendly Name — Group **65fa649a-a111-4912-9294-fb6337a25038** в примере неаппровотных usBs Group.xmlфайле.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-228">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="eb2d3-229">Вы должны `&` заменить `&amp;` в значении.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-229">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="eb2d3-230">Создание политики</span><span class="sxs-lookup"><span data-stu-id="eb2d3-230">Create policy</span></span>

    1. <span data-ttu-id="eb2d3-231">Политика 1. Блокировка записи и выполнения доступа ко всем, кроме блокировки определенных неодобренных ОКБ.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-231">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="eb2d3-232">Пример этого примера использования: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** в примере [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-232">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="eb2d3-233">Политика 2. Проверка записи и выполнения доступа к другим.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-233">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="eb2d3-234">Пример этого примера использования: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** в примере [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-234">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="eb2d3-235">Развертывание и управление политикой с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="eb2d3-235">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="eb2d3-236">Функция управления служба хранилища доступа позволяет применять политику с помощью групповой политики либо к пользователю, либо к устройству, либо к обоим.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-236">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="eb2d3-237">Лицензирование</span><span class="sxs-lookup"><span data-stu-id="eb2d3-237">Licensing</span></span>

<span data-ttu-id="eb2d3-238">Перед началом работы со съемными служба хранилища управления доступом необходимо подтвердить Microsoft 365 [подписку.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="eb2d3-238">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="eb2d3-239">Для доступа и использования служба хранилища управления доступом необходимо иметь Microsoft 365 E3 или Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-239">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="eb2d3-240">Развертывание политики с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="eb2d3-240">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="eb2d3-241">Объединяйте все группы `<Groups>` `</Groups>` в одном xml-файле.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-241">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="eb2d3-242">На следующем изображении иллюстрируется пример сценария 1: предотвращение записи и выполнения доступа ко всем, но разрешить определенные утвержденные [ОКБ.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)</span><span class="sxs-lookup"><span data-stu-id="eb2d3-242">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Экран, отображающий параметры конфигурации, разрешающие определенные утвержденные usBs на устройствах":::
    
2. <span data-ttu-id="eb2d3-244">Объединяйте все правила `<PolicyRules>` `</PolicyRules>` в одном xml-файле.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-244">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="eb2d3-245">Если вы хотите ограничить конкретного пользователя, используйте свойство SID в записи.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-245">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="eb2d3-246">Если в записи политики нет SID, запись будет применяться к экземпляру входа для компьютера.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-246">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="eb2d3-247">На следующем изображении иллюстрируется использование свойства SID, а также пример сценария 1: предотвращение записи и выполнения доступа ко всем пользователям, но только к определенным утвержденным [usBs.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)</span><span class="sxs-lookup"><span data-stu-id="eb2d3-247">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Экран, отображающий код, который указывает использование атрибута свойства SID":::

3. <span data-ttu-id="eb2d3-249">Сохраните файлы XML правил и групп в папке сетевого обмена и вставьте путь папки сетевого обмена в параметр Групповой политики: конфигурация компьютера -> Административные шаблоны -> Windows Компоненты **-> антивирусная программа в Microsoft Defender->** Управление устройствами: "Определение групп политики управления устройствами" и "Определение правил политики управления устройствами".</span><span class="sxs-lookup"><span data-stu-id="eb2d3-249">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="eb2d3-250">Целевая машина должна иметь доступ к сетевой доской, чтобы иметь политику.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-250">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="eb2d3-251">Однако после прочтия политики подключение к сетевой совместной сети больше не требуется даже после перезагрузки компьютера.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-251">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="Экран управления устройствами":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="eb2d3-253">Развертывание и управление политикой через Intune OMA-URI</span><span class="sxs-lookup"><span data-stu-id="eb2d3-253">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="eb2d3-254">Функция управления служба хранилища доступа позволяет применять политику с помощью OMA-URI либо к пользователю, либо к устройству, либо к обоим.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-254">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="eb2d3-255">Лицензирование</span><span class="sxs-lookup"><span data-stu-id="eb2d3-255">Licensing</span></span>

<span data-ttu-id="eb2d3-256">Перед началом работы со съемными служба хранилища управления доступом необходимо подтвердить Microsoft 365 [подписку.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="eb2d3-256">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="eb2d3-257">Для доступа и использования служба хранилища управления доступом необходимо иметь Microsoft 365 E3 или Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-257">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="eb2d3-258">Разрешение</span><span class="sxs-lookup"><span data-stu-id="eb2d3-258">Permission</span></span>

<span data-ttu-id="eb2d3-259">Для развертывания политики в Intune учетная запись должна иметь разрешения на создание, редактирование, обновление или удаление профилей конфигурации устройств.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-259">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="eb2d3-260">С помощью этих разрешений можно создавать настраиваемые роли или использовать любые встроенные роли.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-260">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="eb2d3-261">Роль диспетчера политик и профилей</span><span class="sxs-lookup"><span data-stu-id="eb2d3-261">Policy and profile Manager role</span></span>
- <span data-ttu-id="eb2d3-262">Настраиваемая роль с разрешениями Create/Edit/Update/Read/Delete/View Reports, включенными для профилей конфигурации устройств</span><span class="sxs-lookup"><span data-stu-id="eb2d3-262">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="eb2d3-263">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="eb2d3-263">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="eb2d3-264">Развертывание политики через OMA-URI</span><span class="sxs-lookup"><span data-stu-id="eb2d3-264">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="eb2d3-265">**Microsoft Endpoint Manager центра администрирования (-> Devices -> Профили конфигурации -> Создание профиля -> Платформа: Windows 10 и более поздний & Профиль: Настраиваемый https://endpoint.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-265">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="eb2d3-266">Для каждой группы создайте правило OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="eb2d3-266">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="eb2d3-267">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="eb2d3-267">OMA-URI:</span></span>

      <span data-ttu-id="eb2d3-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="eb2d3-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="eb2d3-269">Например, для любой съемной группы хранения и **CD/DVD** в примере ссылка должна быть:</span><span class="sxs-lookup"><span data-stu-id="eb2d3-269">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="eb2d3-270">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="eb2d3-270">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="eb2d3-271">Тип данных: String (XML-файл)</span><span class="sxs-lookup"><span data-stu-id="eb2d3-271">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="XML-файл для типа данных STRING":::

2. <span data-ttu-id="eb2d3-273">Для каждой политики также создайте OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="eb2d3-273">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="eb2d3-274">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="eb2d3-274">OMA-URI:</span></span>

      <span data-ttu-id="eb2d3-275">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="eb2d3-275">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="eb2d3-276">Например, для блокировки записи и выполнения доступа, но разрешить утвержденное правило **USBs** в примере, ссылка должна быть:</span><span class="sxs-lookup"><span data-stu-id="eb2d3-276">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="eb2d3-277">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-277">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="eb2d3-278">Тип данных: String (XML-файл)</span><span class="sxs-lookup"><span data-stu-id="eb2d3-278">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Отображение XML-файла для типа данных STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="eb2d3-280">Развертывание и управление политикой с помощью пользовательского интерфейса Intune</span><span class="sxs-lookup"><span data-stu-id="eb2d3-280">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="eb2d3-281">Эта возможность (в центре администрирования Microsoft Endpoint Manager (> Устройства > Профили конфигурации > Создание профиля > Платформа: Windows 10 и более поздние https://endpoint.microsoft.com/) & Profile: Device Control) еще недоступна.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-281">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="eb2d3-282">Просмотр съемных данных управления устройствами служба хранилища управления доступом в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="eb2d3-282">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="eb2d3-283">На Microsoft 365 портале безопасности показаны съемные хранилища, заблокированные съемным служба хранилища управления доступом.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-283">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="eb2d3-284">Чтобы получить доступ к Microsoft 365 безопасности, необходимо иметь следующую подписку:</span><span class="sxs-lookup"><span data-stu-id="eb2d3-284">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="eb2d3-285">Microsoft 365 отчетов по E5</span><span class="sxs-lookup"><span data-stu-id="eb2d3-285">Microsoft 365 for E5 reporting</span></span>

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="Экран, на котором запечатлена блокировка съемного хранилища":::

## <a name="frequently-asked-questions"></a><span data-ttu-id="eb2d3-287">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="eb2d3-287">Frequently asked questions</span></span>
<span data-ttu-id="eb2d3-288">**Какое ограничение для съемных носители хранения для максимального числа пользователей?**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-288">**What is the removable storage media limitation for the maximum number of USBs?**</span></span>

<span data-ttu-id="eb2d3-289">Мы проверили одну группу USB со 100 000 мультимедиа размером до 7 МБ.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-289">We have validated one USB group with 100,000 media - up to 7 MB in size.</span></span> <span data-ttu-id="eb2d3-290">Политика работает как в Intune, так и в GPO без проблем с производительностью.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-290">The policy works in both Intune and GPO without performance issues.</span></span>

<span data-ttu-id="eb2d3-291">**Почему политика не работает?**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-291">**Why does the policy not work?**</span></span>

<span data-ttu-id="eb2d3-292">Наиболее частой причиной является отсутствие обязательной клиентской версии [антивирусного программного обеспечения.](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)</span><span class="sxs-lookup"><span data-stu-id="eb2d3-292">The most common reason is there is no required [antimalware client version](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints).</span></span>

<span data-ttu-id="eb2d3-293">Другая причина может быть в том, что XML-файл неправильно отформатирован, например, не использует правильный формат разметки для символа "&" в XML-файле, или текстовый редактор может добавить метку заказа в 0xEF 0xBB 0xBF в начале файлов, из-за чего разбор XML не работает.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-293">Another reason could be that the XML file is not correctly formatted, for example, not using the correct markdown formatting for the "&" character in the XML file, or the text editor might add a byte order mark (BOM) 0xEF 0xBB 0xBF at the beginning of the files which causes the XML parsing not to work.</span></span> <span data-ttu-id="eb2d3-294">Одним из простых решений является [скачивание](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) примера файла (выберите **Raw,** а затем **Сохранить как),** а затем обновить.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-294">One simple solution is to download the [sample file](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (select **Raw** and then **Save as**) and then update.</span></span>

<span data-ttu-id="eb2d3-295">Если имеется значение и политика управляется с помощью групповой политики, проверьте, может ли клиентское устройство получить доступ к пути XML политики.</span><span class="sxs-lookup"><span data-stu-id="eb2d3-295">If there is a value and the policy is managed via Group Policy, check whether the client device can access the policy XML path.</span></span>

<span data-ttu-id="eb2d3-296">**Как узнать, какая машина использует устарелую клиентскую версию антивирусных программ в организации?**</span><span class="sxs-lookup"><span data-stu-id="eb2d3-296">**How can I know which machine is using out of date antimalware client version in the organization?**</span></span>

<span data-ttu-id="eb2d3-297">Следующий запрос можно использовать для получения клиентской версии антивирусных программ на Microsoft 365 безопасности:</span><span class="sxs-lookup"><span data-stu-id="eb2d3-297">You can use following query to get antimalware client version on the Microsoft 365 security portal:</span></span>
```kusto
//check the antimalware client version
DeviceFileEvents
| where FileName == "MsMpEng.exe"
| where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
| extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//| project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
| summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
| order by PlatformVersion desc
```

