---
title: Microsoft Defender для управления конечными устройствами, которые можно служба хранилища защиты
description: Понимание возможностей, которые помогают запретить пользователю или компьютеру использовать несанкционированные съемные носитли хранения
keywords: съемное хранилище
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c9b97c2157ba8090628af23b2ab54cf38f04d8c6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538391"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a><span data-ttu-id="c3411-104">Microsoft Defender для управления конечными устройствами, которые можно служба хранилища защиты</span><span class="sxs-lookup"><span data-stu-id="c3411-104">Microsoft Defender for Endpoint Device Control Removable Storage Protection</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="c3411-105">Защита Microsoft Defender для удаления служба хранилища устройств с конечными точками не позволяет пользователю или машине или обоим использовать несанкционированные съемные носитли хранения.</span><span class="sxs-lookup"><span data-stu-id="c3411-105">Microsoft Defender for Endpoint Device Control Removable Storage Protection prevents user or machine or both from using unauthorized removable storage media.</span></span>

## <a name="protection-policies"></a><span data-ttu-id="c3411-106">Политики защиты</span><span class="sxs-lookup"><span data-stu-id="c3411-106">Protection policies</span></span>

### <a name="device-installation"></a><span data-ttu-id="c3411-107">Установка устройства</span><span class="sxs-lookup"><span data-stu-id="c3411-107">Device installation</span></span>

<span data-ttu-id="c3411-108">**Возможности** . Предотвратить установку с исключением или без исключения на основе различных свойств устройства.</span><span class="sxs-lookup"><span data-stu-id="c3411-108">**Capabilities** - Prevent installation with or without exclusion based on various device properties.</span></span>

<span data-ttu-id="c3411-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c3411-109">**Description**</span></span>
- <span data-ttu-id="c3411-110">Применяется на уровне машины: та же политика применяется и для любого пользователя, зарегистрированного в журнале.</span><span class="sxs-lookup"><span data-stu-id="c3411-110">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="c3411-111">Поддерживает MEM и GPO.</span><span class="sxs-lookup"><span data-stu-id="c3411-111">Supports MEM and GPO.</span></span>
- <span data-ttu-id="c3411-112">Поддерживаемые свойства[устройств,](#device-properties)как указано в списке.</span><span class="sxs-lookup"><span data-stu-id="c3411-112">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="c3411-113">Дополнительные сведения о Windows см. в веб-сайте [How to control USB devices and other removable media using Microsoft Defender for Endpoint.](control-usb-devices-using-intune.md)</span><span class="sxs-lookup"><span data-stu-id="c3411-113">For more information on Windows, see [How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).</span></span>

<span data-ttu-id="c3411-114">**Поддерживаемая платформа** — Windows 10</span><span class="sxs-lookup"><span data-stu-id="c3411-114">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="c3411-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c3411-115">**Description**</span></span>
- <span data-ttu-id="c3411-116">Применяется на уровне машины: та же политика применяется и для любого пользователя, зарегистрированного в журнале.</span><span class="sxs-lookup"><span data-stu-id="c3411-116">Applied at machine level: the same policy applies for any logged on user</span></span>
- <span data-ttu-id="c3411-117">Сведения о macOS см. в [специальном см. для управления устройствами macOS.](mac-device-control-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c3411-117">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="c3411-118">**Поддерживаемая платформа** — macOS Catalina 10.15.4+ (с включенными расширениями системы)</span><span class="sxs-lookup"><span data-stu-id="c3411-118">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="removable-storage-access-control"></a><span data-ttu-id="c3411-119">Управление доступом к съемным хранилищам</span><span class="sxs-lookup"><span data-stu-id="c3411-119">Removable storage Access Control</span></span>

<span data-ttu-id="c3411-120">**Capabilities**</span><span class="sxs-lookup"><span data-stu-id="c3411-120">**Capabilities**</span></span>
- <span data-ttu-id="c3411-121">*Аудит* Чтение или написание или выполнение доступа к съемным хранилищам на основе различных свойств устройства с исключением или без него.</span><span class="sxs-lookup"><span data-stu-id="c3411-121">*Audit* Read or Write or Execute access to removable storage based on various device properties, with or without an exclusion.</span></span>
- <span data-ttu-id="c3411-122">*Предотвращение* Чтение или написание или выполнение доступа с исключением или без него . Разрешить определенное устройство на основе различных свойств устройства.</span><span class="sxs-lookup"><span data-stu-id="c3411-122">*Prevent* Read or Write or Execute access with or without an exclusion - Allow specific device based on various device properties.</span></span>

<span data-ttu-id="c3411-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c3411-123">**Description**</span></span>
- <span data-ttu-id="c3411-124">Применяется либо на компьютере, либо на пользователе, либо на обоих устройствах — только разрешить определенным пользователям, которые выполняют чтение/записи или выполняют доступ к определенному съемного хранилища на определенном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c3411-124">Applied at either machine or user or both – only allow specific people performing Read/Write/Execute access to specific removable storage on specific machine.</span></span>
- <span data-ttu-id="c3411-125">Поддержка MEM OMA-URI и GPO.</span><span class="sxs-lookup"><span data-stu-id="c3411-125">Support MEM OMA-URI and GPO.</span></span>
- <span data-ttu-id="c3411-126">Поддерживаемые свойства[устройств,](#device-properties)как указано в списке.</span><span class="sxs-lookup"><span data-stu-id="c3411-126">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="c3411-127">Для функции в Windows см. в этой Windows [Элемент управления доступом к хранилищам.](device-control-removable-storage-access-control.md)</span><span class="sxs-lookup"><span data-stu-id="c3411-127">For feature in Windows, see [Removable storage Access Control](device-control-removable-storage-access-control.md).</span></span>

<span data-ttu-id="c3411-128">**Поддерживаемая платформа** — Windows 10</span><span class="sxs-lookup"><span data-stu-id="c3411-128">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="c3411-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c3411-129">**Description**</span></span>
- <span data-ttu-id="c3411-130">Применяется на уровне машины: та же политика применяется и для любого пользователя, зарегистрированного в журнале.</span><span class="sxs-lookup"><span data-stu-id="c3411-130">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="c3411-131">Сведения о macOS см. в [специальном см. для управления устройствами macOS.](mac-device-control-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c3411-131">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="c3411-132">**Поддерживаемая платформа** — macOS Catalina 10.15.4+ (с включенными расширениями системы)</span><span class="sxs-lookup"><span data-stu-id="c3411-132">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="windows-portable-device-access-control"></a><span data-ttu-id="c3411-133">Windows Управление доступом к портативному устройству</span><span class="sxs-lookup"><span data-stu-id="c3411-133">Windows Portable Device Access Control</span></span>

<span data-ttu-id="c3411-134">**Возможности** — запретить чтение или [](/windows-hardware/drivers/portable/)записывать доступ к Windows портативному устройству, например: Планшет, iPhone.</span><span class="sxs-lookup"><span data-stu-id="c3411-134">**Capabilities** - Deny Read or Write access to any [Windows Portable Device](/windows-hardware/drivers/portable/), for example: Tablet, iPhone.</span></span>

<span data-ttu-id="c3411-135">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c3411-135">**Description**</span></span>
- <span data-ttu-id="c3411-136">Применяется либо на компьютере, либо на пользователе, либо на обоих устройствах.</span><span class="sxs-lookup"><span data-stu-id="c3411-136">Applied at either machine or user or both.</span></span>
- <span data-ttu-id="c3411-137">Поддержка MEM OMA-URI и GPO.</span><span class="sxs-lookup"><span data-stu-id="c3411-137">Support MEM OMA-URI and GPO.</span></span>

<span data-ttu-id="c3411-138">**Поддерживаемая платформа** — Windows 10</span><span class="sxs-lookup"><span data-stu-id="c3411-138">**Supported Platform** - Windows 10</span></span>

### <a name="endpoint-dlp-removable-storage"></a><span data-ttu-id="c3411-139">Съемное хранилище конечной точки DLP</span><span class="sxs-lookup"><span data-stu-id="c3411-139">Endpoint DLP Removable storage</span></span>

<span data-ttu-id="c3411-140">**Возможности** — аудит или предупреждение или предотвращение копирования элемента или сведений на съемное мультимедиа или USB-устройство.</span><span class="sxs-lookup"><span data-stu-id="c3411-140">**Capabilities** - Audit or Warn or Prevent a user from copying an item or information to removable media or USB device.</span></span>

<span data-ttu-id="c3411-141">**Описание** . Дополнительные сведения о Windows см. в Microsoft 365 [предотвращении потери данных конечной точки.](../../compliance/endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="c3411-141">**Description** - For more information on Windows, see [Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).</span></span>

<span data-ttu-id="c3411-142">**Поддерживаемая платформа** — Windows 10</span><span class="sxs-lookup"><span data-stu-id="c3411-142">**Supported Platform** - Windows 10</span></span>

### <a name="bitlocker"></a><span data-ttu-id="c3411-143">BitLocker</span><span class="sxs-lookup"><span data-stu-id="c3411-143">BitLocker</span></span> 

<span data-ttu-id="c3411-144">**Capabilities**</span><span class="sxs-lookup"><span data-stu-id="c3411-144">**Capabilities**</span></span>
- <span data-ttu-id="c3411-145">Блокируют данные, которые будут записаны на съемные диски, которые BitLocker защищены.</span><span class="sxs-lookup"><span data-stu-id="c3411-145">Block data to be written to removable drives that aren't BitLocker protected.</span></span>
- <span data-ttu-id="c3411-146">Блокируют доступ к съемным дискам, если они не зашифрованы на компьютере, который принадлежит вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c3411-146">Block access to removable drives unless they were encrypted on a computer owned by your organization</span></span>
 
<span data-ttu-id="c3411-147">**Описание** . Дополнительные сведения о Windows см. в [BitLocker - Съемный диск Параметры](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span><span class="sxs-lookup"><span data-stu-id="c3411-147">**Description** - For more information on Windows, see [BitLocker – Removable Drive Settings](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span></span>

<span data-ttu-id="c3411-148">**Поддерживаемая платформа** — Windows 10</span><span class="sxs-lookup"><span data-stu-id="c3411-148">**Supported Platform** - Windows 10</span></span>

## <a name="device-properties"></a><span data-ttu-id="c3411-149">Свойства устройства</span><span class="sxs-lookup"><span data-stu-id="c3411-149">Device properties</span></span>

<span data-ttu-id="c3411-150">Защита microsoft Defender для управления конечными устройствами служба хранилища позволяет ограничить съемный доступ к хранилищам в зависимости от свойств, описанных в таблице ниже:</span><span class="sxs-lookup"><span data-stu-id="c3411-150">Microsoft Defender for Endpoint Device Control Removable Storage Protection allows you to restrict the removable storage access based on the properties described in the table below:</span></span>


|<span data-ttu-id="c3411-151">Имя свойства</span><span class="sxs-lookup"><span data-stu-id="c3411-151">Property Name</span></span>  |<span data-ttu-id="c3411-152">Применимые политики</span><span class="sxs-lookup"><span data-stu-id="c3411-152">Applicable Policies</span></span>  |<span data-ttu-id="c3411-153">Применяется к операционным системам</span><span class="sxs-lookup"><span data-stu-id="c3411-153">Applies to Operating Systems</span></span>  |<span data-ttu-id="c3411-154">Описание</span><span class="sxs-lookup"><span data-stu-id="c3411-154">Description</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="c3411-155">Класс устройства</span><span class="sxs-lookup"><span data-stu-id="c3411-155">Device Class</span></span>    |     [<span data-ttu-id="c3411-156">Управление USB-устройствами и другими съемными носителями с помощью Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c3411-156">How to control USB devices and other removable media using Microsoft Defender for Endpoint</span></span>](control-usb-devices-using-intune.md)     |   <span data-ttu-id="c3411-157">Windows</span><span class="sxs-lookup"><span data-stu-id="c3411-157">Windows</span></span>      |  <span data-ttu-id="c3411-158">Сведения о форматах ID устройств см. в [классе установки устройства.](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)</span><span class="sxs-lookup"><span data-stu-id="c3411-158">For information about Device ID formats, see [device setup class](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span></span> <span data-ttu-id="c3411-159">**Примечание.** Установка устройств может применяться к любым устройствам, а не только к съемным хранилищам.</span><span class="sxs-lookup"><span data-stu-id="c3411-159">**Note**: Device Installation can be applied to any devices, not only Removable storage.</span></span>       |
|<span data-ttu-id="c3411-160">Основной ID</span><span class="sxs-lookup"><span data-stu-id="c3411-160">Primary ID</span></span>   |     <span data-ttu-id="c3411-161">Управление доступом к съемным хранилищам</span><span class="sxs-lookup"><span data-stu-id="c3411-161">Removable storage Access Control</span></span>    |   <span data-ttu-id="c3411-162">Windows</span><span class="sxs-lookup"><span data-stu-id="c3411-162">Windows</span></span>      |      <span data-ttu-id="c3411-163">Основной ID включает съемное хранилище и CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="c3411-163">The Primary ID includes removable storage and CD/DVD.</span></span>   |
|<span data-ttu-id="c3411-164">ID устройства</span><span class="sxs-lookup"><span data-stu-id="c3411-164">Device ID</span></span>     |  <span data-ttu-id="c3411-165">[Управление USB-устройствами и другими съемными носителями с помощью Microsoft Defender для конечной точки;](control-usb-devices-using-intune.md) Управление доступом к съемным хранилищам</span><span class="sxs-lookup"><span data-stu-id="c3411-165">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>       |      <span data-ttu-id="c3411-166">Windows</span><span class="sxs-lookup"><span data-stu-id="c3411-166">Windows</span></span>   |    <span data-ttu-id="c3411-167">Сведения о форматах идентификаторов устройств см. в примере [Стандартные идентификаторы USB,](/windows-hardware/drivers/install/standard-usb-identifiers)например USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07.</span><span class="sxs-lookup"><span data-stu-id="c3411-167">For information about Device ID formats, see [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span></span>      |
|<span data-ttu-id="c3411-168">Аппаратный ID</span><span class="sxs-lookup"><span data-stu-id="c3411-168">Hardware ID</span></span>     |     <span data-ttu-id="c3411-169">[Управление USB-устройствами и другими съемными носителями с помощью Microsoft Defender для конечной точки;](control-usb-devices-using-intune.md) Управление доступом к съемным хранилищам</span><span class="sxs-lookup"><span data-stu-id="c3411-169">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>    |     <span data-ttu-id="c3411-170">Windows</span><span class="sxs-lookup"><span data-stu-id="c3411-170">Windows</span></span>    |    <span data-ttu-id="c3411-171">Строка определила устройство в системе, например USBSTOR\DiskGeneric_Flash_Disk______8.07; **Примечание.** ID оборудования не является уникальным; разные устройства могут иметь одно и то же значение.</span><span class="sxs-lookup"><span data-stu-id="c3411-171">A string identified the device in the system, for example, USBSTOR\DiskGeneric_Flash_Disk______8.07; **Note**: Hardware ID is not unique; different devices may share same value.</span></span>|
|<span data-ttu-id="c3411-172">Экземпляр ID</span><span class="sxs-lookup"><span data-stu-id="c3411-172">Instance ID</span></span>    | <span data-ttu-id="c3411-173">Установка устройства; Управление доступом к съемным хранилищам</span><span class="sxs-lookup"><span data-stu-id="c3411-173">Device Installation; Removable storage Access Control</span></span>     |     <span data-ttu-id="c3411-174">Windows</span><span class="sxs-lookup"><span data-stu-id="c3411-174">Windows</span></span>    |   <span data-ttu-id="c3411-175">Строка уникально идентифицирует устройство в системе, например USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span><span class="sxs-lookup"><span data-stu-id="c3411-175">A string uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span></span>      |
|<span data-ttu-id="c3411-176">Понятное имя</span><span class="sxs-lookup"><span data-stu-id="c3411-176">Friendly Name</span></span>     |     <span data-ttu-id="c3411-177">Управление доступом к съемным хранилищам</span><span class="sxs-lookup"><span data-stu-id="c3411-177">Removable storage Access Control</span></span>    |   <span data-ttu-id="c3411-178">Windows</span><span class="sxs-lookup"><span data-stu-id="c3411-178">Windows</span></span>      |    <span data-ttu-id="c3411-179">Строка, присоединенная к устройству, например, универсальное usb-устройство flash Disk</span><span class="sxs-lookup"><span data-stu-id="c3411-179">A string attached to the device, for example, Generic Flash Disk USB Device</span></span>     |
|<span data-ttu-id="c3411-180">ID поставщика / ID продукта</span><span class="sxs-lookup"><span data-stu-id="c3411-180">Vendor ID / Product ID</span></span>     |  <span data-ttu-id="c3411-181">Управление доступом к съемным хранилищам</span><span class="sxs-lookup"><span data-stu-id="c3411-181">Removable storage Access Control</span></span>       |   <span data-ttu-id="c3411-182">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="c3411-182">Windows Mac</span></span>      |     <span data-ttu-id="c3411-183">ID поставщика — это четырехзначный код поставщика, который комитет USB назначает поставщику.</span><span class="sxs-lookup"><span data-stu-id="c3411-183">Vendor ID is the four-digit vendor code that the USB committee assigns to the vendor.</span></span> <span data-ttu-id="c3411-184">Код продукта — это четырехзначный код продукта, который поставщик назначает устройству; Поддержка под диктовки.</span><span class="sxs-lookup"><span data-stu-id="c3411-184">Product ID is the four-digit product code that the vendor assigns to the device; Support wildcard.</span></span>    |
|<span data-ttu-id="c3411-185">Serial NumberId</span><span class="sxs-lookup"><span data-stu-id="c3411-185">Serial NumberId</span></span>     |     <span data-ttu-id="c3411-186">Управление доступом к съемным хранилищам</span><span class="sxs-lookup"><span data-stu-id="c3411-186">Removable storage Access Control</span></span>    |      <span data-ttu-id="c3411-187">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="c3411-187">Windows Mac</span></span>   |     <span data-ttu-id="c3411-188">Например, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span><span class="sxs-lookup"><span data-stu-id="c3411-188">For example, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span></span>    |

## <a name="related-topic"></a><span data-ttu-id="c3411-189">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="c3411-189">Related topic</span></span>

- [<span data-ttu-id="c3411-190">Microsoft Defender для управления конечными точками управления устройствами, служба хранилища управления доступом</span><span class="sxs-lookup"><span data-stu-id="c3411-190">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>](device-control-removable-storage-access-control.md)

