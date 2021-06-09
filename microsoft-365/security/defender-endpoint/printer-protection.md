---
title: Microsoft Defender для защиты принтера управления конечными устройствами
description: Защита принтера управления устройствами Microsoft Defender для конечных устройств блокирует печать с помощью не корпоративных принтеров или не утвержденного USB-принтера.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 431497ded684543c33d91c49a0da47e92297321f
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809264"
---
# <a name="device-control-printer-protection"></a><span data-ttu-id="9f601-103">Защита принтера для управления устройством</span><span class="sxs-lookup"><span data-stu-id="9f601-103">Device Control Printer Protection</span></span> 

<span data-ttu-id="9f601-104">Защита принтера управления устройствами Microsoft Defender для конечных устройств блокирует печать с помощью не корпоративных принтеров или не утвержденного USB-принтера.</span><span class="sxs-lookup"><span data-stu-id="9f601-104">Microsoft Defender for Endpoint Device Control Printer Protection blocks people from printing via non-corporate printers or non-approved USB printer.</span></span>

## <a name="licensing"></a><span data-ttu-id="9f601-105">Лицензирование</span><span class="sxs-lookup"><span data-stu-id="9f601-105">Licensing</span></span> 

<span data-ttu-id="9f601-106">Перед началом работы с Службой защиты принтеров необходимо подтвердить [Microsoft 365 подписку.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="9f601-106">Before you get started with Printer Protection, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="9f601-107">Чтобы получить доступ к средствам защиты принтеров и использовать их, необходимо иметь следующее:</span><span class="sxs-lookup"><span data-stu-id="9f601-107">To access and use Printer Protection, you must have the following:</span></span>

- <span data-ttu-id="9f601-108">Microsoft 365 E3 для развертывания функциональности и политики</span><span class="sxs-lookup"><span data-stu-id="9f601-108">Microsoft 365 E3 for functionality/policy deployment</span></span> 
- <span data-ttu-id="9f601-109">Microsoft 365 E5 отчетов</span><span class="sxs-lookup"><span data-stu-id="9f601-109">Microsoft 365 E5 for reporting</span></span> 

## <a name="permission"></a><span data-ttu-id="9f601-110">Разрешение</span><span class="sxs-lookup"><span data-stu-id="9f601-110">Permission</span></span> 

<span data-ttu-id="9f601-111">Для развертывания политики в Intune для развертывания политики с помощью OMA-URI учетная запись должна иметь разрешения на создание, редактирование, обновление или удаление профилей конфигурации устройств.</span><span class="sxs-lookup"><span data-stu-id="9f601-111">For Policy deployment in Intune, to deploy policy via OMA-URI, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="9f601-112">Вы можете создавать настраиваемые роли или использовать любую из встроенных ролей с помощью этих разрешений:</span><span class="sxs-lookup"><span data-stu-id="9f601-112">You can create custom roles or use any of the built-in roles with these permissions:</span></span>  

- <span data-ttu-id="9f601-113">Роль диспетчера политик и профилей.</span><span class="sxs-lookup"><span data-stu-id="9f601-113">Policy and profile Manager role.</span></span> 
- <span data-ttu-id="9f601-114">Или настраиваемая роль с разрешениями Create/Edit/Update/Read/Delete/View Reports, включенными для профилей конфигурации устройств</span><span class="sxs-lookup"><span data-stu-id="9f601-114">Or custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>  
- <span data-ttu-id="9f601-115">Или глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="9f601-115">Or Global admin</span></span>

<span data-ttu-id="9f601-116">Чтобы просмотреть отчеты о конфигурации устройства, у учетной записи должны быть разрешения на просмотр отчетов.</span><span class="sxs-lookup"><span data-stu-id="9f601-116">To see device configuration reports, the account must have view reports permissions.</span></span> <span data-ttu-id="9f601-117">Вы можете создавать настраиваемые роли или использовать встроенные роли с помощью этих разрешений:</span><span class="sxs-lookup"><span data-stu-id="9f601-117">You can create custom roles or use the built-in roles with these permissions:</span></span>  

- <span data-ttu-id="9f601-118">Администратор глобальной безопасности</span><span class="sxs-lookup"><span data-stu-id="9f601-118">Global security admin</span></span>
- <span data-ttu-id="9f601-119">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="9f601-119">Security admin</span></span>
- <span data-ttu-id="9f601-120">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="9f601-120">Security Reader</span></span> 

## <a name="prepare-your-endpoints"></a><span data-ttu-id="9f601-121">Подготовка конечных точек</span><span class="sxs-lookup"><span data-stu-id="9f601-121">Prepare your endpoints</span></span>

<span data-ttu-id="9f601-122">Убедитесь, что Windows 10 устройства, которые планируется развернуть для защиты принтеров, чтобы соответствовать этим требованиям.</span><span class="sxs-lookup"><span data-stu-id="9f601-122">Make sure that the Windows 10 devices that you plan on deploying Printer Protection to meet these requirements.</span></span>

1. <span data-ttu-id="9f601-123">Присоединяйтесь к программе insider.</span><span class="sxs-lookup"><span data-stu-id="9f601-123">Join the Insider Program.</span></span>

1. <span data-ttu-id="9f601-124">Устанавливаются следующие обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="9f601-124">The following Windows Updates are installed.</span></span> 

    - <span data-ttu-id="9f601-125">Для Windows 1809: установка Windows [обновления KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span><span class="sxs-lookup"><span data-stu-id="9f601-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span></span> 
    - <span data-ttu-id="9f601-126">Для Windows 1909: установите Windows обновления [KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span><span class="sxs-lookup"><span data-stu-id="9f601-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span></span>
    - <span data-ttu-id="9f601-127">Для Windows 2004 или более поздней</span><span class="sxs-lookup"><span data-stu-id="9f601-127">For Windows 2004 or later</span></span> 
    
1. <span data-ttu-id="9f601-128">Если вы планируете развертывать политику с помощью групповой политики, устройство должно быть MDATP; если вы планируете развертывать политику через MEM, устройство должно быть соединено с Intune.</span><span class="sxs-lookup"><span data-stu-id="9f601-128">If you're planning to deploy policy via Group Policy, the device must be MDATP joined; if you're planning to deploy policy via MEM, the device must be Intune joined.</span></span>

## <a name="deploy-device-control-printer-protection-policy"></a><span data-ttu-id="9f601-129">Развертывание политики защиты принтеров управления устройствами</span><span class="sxs-lookup"><span data-stu-id="9f601-129">Deploy Device Control Printer Protection policy</span></span>

<span data-ttu-id="9f601-130">Вы можете развернуть политику с помощью групповой политики или Intune.</span><span class="sxs-lookup"><span data-stu-id="9f601-130">You can deploy the policy via Group Policy or Intune.</span></span>

| <span data-ttu-id="9f601-131">Название</span><span class="sxs-lookup"><span data-stu-id="9f601-131">Title</span></span> | <span data-ttu-id="9f601-132">Описание</span><span class="sxs-lookup"><span data-stu-id="9f601-132">Description</span></span> | <span data-ttu-id="9f601-133">Поддержка CSP</span><span class="sxs-lookup"><span data-stu-id="9f601-133">CSP Support</span></span> | <span data-ttu-id="9f601-134">Поддержка GPO</span><span class="sxs-lookup"><span data-stu-id="9f601-134">GPO Support</span></span> | <span data-ttu-id="9f601-135">Поддержка на основе пользователя</span><span class="sxs-lookup"><span data-stu-id="9f601-135">User-based Support</span></span> | <span data-ttu-id="9f601-136">Поддержка на основе машин</span><span class="sxs-lookup"><span data-stu-id="9f601-136">Machine-based Support</span></span> |
|:--|:--|:--|:--|:--|:--|
|<span data-ttu-id="9f601-137">**Включить ограничения печати управления устройствами**</span><span class="sxs-lookup"><span data-stu-id="9f601-137">**Enable Device control Printing Restrictions**</span></span>|<span data-ttu-id="9f601-138">Блокировка печати с помощью не корпоративного принтера</span><span class="sxs-lookup"><span data-stu-id="9f601-138">Block people from printing via non-corporate printer</span></span>|<span data-ttu-id="9f601-139">Да</span><span class="sxs-lookup"><span data-stu-id="9f601-139">Yes</span></span>|<span data-ttu-id="9f601-140">Да</span><span class="sxs-lookup"><span data-stu-id="9f601-140">Yes</span></span>|<span data-ttu-id="9f601-141">Да</span><span class="sxs-lookup"><span data-stu-id="9f601-141">Yes</span></span>|<span data-ttu-id="9f601-142">Да</span><span class="sxs-lookup"><span data-stu-id="9f601-142">Yes</span></span>|
|<span data-ttu-id="9f601-143">**Список устройств печати с подключением к USB**\*</span><span class="sxs-lookup"><span data-stu-id="9f601-143">**List of Approved USB-connected print devices** \*</span></span>|<span data-ttu-id="9f601-144">Разрешить определенный USB-принтер</span><span class="sxs-lookup"><span data-stu-id="9f601-144">Allow specific USB printer</span></span>|<span data-ttu-id="9f601-145">Да</span><span class="sxs-lookup"><span data-stu-id="9f601-145">Yes</span></span>|<span data-ttu-id="9f601-146">Да</span><span class="sxs-lookup"><span data-stu-id="9f601-146">Yes</span></span>|<span data-ttu-id="9f601-147">Да</span><span class="sxs-lookup"><span data-stu-id="9f601-147">Yes</span></span>|<span data-ttu-id="9f601-148">Да</span><span class="sxs-lookup"><span data-stu-id="9f601-148">Yes</span></span>|
|||||||

<span data-ttu-id="9f601-149">\* Эта политика должна использоваться вместе с ограничениями печати управления **устройствами**</span><span class="sxs-lookup"><span data-stu-id="9f601-149">\* This policy must be used together with **Enable Device control Printing Restrictions**</span></span>
## <a name="deploy-policy-via-intune"></a><span data-ttu-id="9f601-150">Развертывание политики через Intune</span><span class="sxs-lookup"><span data-stu-id="9f601-150">Deploy policy via Intune</span></span> 

<span data-ttu-id="9f601-151">Для Intune в настоящее время защита принтера управления устройствами поддерживает только OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="9f601-151">For Intune, currently Device Control Printer Protection supports OMA-URI only.</span></span>

<span data-ttu-id="9f601-152">**Сценарий 1. Блокировка печати с помощью любого не корпоративного принтера**</span><span class="sxs-lookup"><span data-stu-id="9f601-152">**Scenario 1: Block people from printing via any non-corporate printer**</span></span> 

 - <span data-ttu-id="9f601-153">Применение политики на компьютере:</span><span class="sxs-lookup"><span data-stu-id="9f601-153">Apply policy over machine:</span></span> 

    - <span data-ttu-id="9f601-154">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl</span><span class="sxs-lookup"><span data-stu-id="9f601-154">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl</span></span> 

- <span data-ttu-id="9f601-155">Применить политику к пользователю:</span><span class="sxs-lookup"><span data-stu-id="9f601-155">Apply policy over user:</span></span> 

    - <span data-ttu-id="9f601-156">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser</span><span class="sxs-lookup"><span data-stu-id="9f601-156">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser</span></span> 

<span data-ttu-id="9f601-157">Строка поддержки CSP `` <enabled/>`` с:</span><span class="sxs-lookup"><span data-stu-id="9f601-157">The CSP support string with `` <enabled/>``:</span></span> 

:::image type="content" source="../../media/customeditrow.png" alt-text="настраиваемая строка редактирования":::

<span data-ttu-id="9f601-159">**Сценарий 2. Разрешить специальные утвержденные USB-принтеры**</span><span class="sxs-lookup"><span data-stu-id="9f601-159">**Scenario 2: Allow specific approved USB printers**</span></span>

- <span data-ttu-id="9f601-160">Применение политики на компьютере:</span><span class="sxs-lookup"><span data-stu-id="9f601-160">Apply policy over machine:</span></span> 

    - <span data-ttu-id="9f601-161">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices</span><span class="sxs-lookup"><span data-stu-id="9f601-161">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices</span></span> 

- <span data-ttu-id="9f601-162">Применить политику к пользователю:</span><span class="sxs-lookup"><span data-stu-id="9f601-162">Apply policy over user:</span></span> 

    - <span data-ttu-id="9f601-163">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser</span><span class="sxs-lookup"><span data-stu-id="9f601-163">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser</span></span>  

<span data-ttu-id="9f601-164">Строка поддержки CSP с утвержденными USB-принтерами с помощью свойства "ApprovedUsbPrintDevices", `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>`` например:</span><span class="sxs-lookup"><span data-stu-id="9f601-164">The CSP support string with approved USB printers via ‘ApprovedUsbPrintDevices’ property, example `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>``:</span></span> 

:::image type="content" source="../../media/editrow.png" alt-text="изменение строки":::

## <a name="deploy-policy-via-group-policy"></a><span data-ttu-id="9f601-166">Развертывание политики с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="9f601-166">Deploy policy via Group Policy</span></span> 

<span data-ttu-id="9f601-167">Если устройство не присоединилось к Intune, вы также можете развернуть политику с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="9f601-167">If the device isn't Intune joined, you can also deploy the policy via Group Policy.</span></span> 

<span data-ttu-id="9f601-168">**Сценарий 1. Блокировка печати с помощью любого не корпоративного принтера**</span><span class="sxs-lookup"><span data-stu-id="9f601-168">**Scenario 1: Block people from printing via any non-corporate printer**</span></span> 

- <span data-ttu-id="9f601-169">Применение политики на компьютере:</span><span class="sxs-lookup"><span data-stu-id="9f601-169">Apply policy over machine:</span></span> 

    - <span data-ttu-id="9f601-170">Конфигурация компьютера > административных шаблонов > принтера: включить ограничения печати управления устройствами</span><span class="sxs-lookup"><span data-stu-id="9f601-170">Computer Configuration > Administrative Templates > Printer: Enable Device control Printing Restrictions</span></span> 

- <span data-ttu-id="9f601-171">Применить политику к пользователю:</span><span class="sxs-lookup"><span data-stu-id="9f601-171">Apply policy over user:</span></span> 

    - <span data-ttu-id="9f601-172">Настройка пользователей > административных шаблонов > панели управления > принтеров: включить ограничения печати управления устройствами</span><span class="sxs-lookup"><span data-stu-id="9f601-172">User Configuration > Administrative Templates > Control Panel > Printers: Enable Device control Printing Restrictions</span></span> 

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="включить ограничения печати устройств":::
 

<span data-ttu-id="9f601-174">**Сценарий 2. Разрешить специальные утвержденные USB-принтеры**</span><span class="sxs-lookup"><span data-stu-id="9f601-174">**Scenario 2: Allow specific approved USB printers**</span></span>

- <span data-ttu-id="9f601-175">Применение политики на компьютере:</span><span class="sxs-lookup"><span data-stu-id="9f601-175">Apply policy over machine:</span></span> 

    - <span data-ttu-id="9f601-176">Конфигурация > административных шаблонов > принтера: список утвержденных устройств печати с подключением к USB</span><span class="sxs-lookup"><span data-stu-id="9f601-176">Computer Configuration > Administrative Templates > Printer:  List of Approved USB-connected print devices</span></span> 

- <span data-ttu-id="9f601-177">Применить политику к пользователю:</span><span class="sxs-lookup"><span data-stu-id="9f601-177">Apply policy over user:</span></span>  

    - <span data-ttu-id="9f601-178">Конфигурация пользователей > административных шаблонов > панели > принтеров: список утвержденных устройств печати с подключением к USB</span><span class="sxs-lookup"><span data-stu-id="9f601-178">User Configuration > Administrative Templates > Control Panel > Printers: List of Approved USB-connected print devices</span></span> 
 
 :::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="список утвержденных подключенных к usb печатным устройствам":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a><span data-ttu-id="9f601-180">Просмотр данных о защите принтеров управления устройствами на портале Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9f601-180">View Device Control Printer Protection data in Microsoft Defender for Endpoint portal</span></span> 

<span data-ttu-id="9f601-181">В [Microsoft 365 центра безопасности](https://security.microsoft.com) показана печать, заблокированная политикой защиты принтеров управления устройствами выше.</span><span class="sxs-lookup"><span data-stu-id="9f601-181">The [Microsoft 365 security center](https://security.microsoft.com) shows printing blocked by the Device Control Printer Protection policy above.</span></span>
 
```sql
DeviceEvents 

|where ActionType == 'PrintJobBlocked' 

| extend parsed=parse_json(AdditionalFields) 

| extend PrintedFile=tostring(parsed.JobOrDocumentName) 

| extend PrintPortName=tostring(parsed.PortName) 

| extend PrinterName=tostring(parsed.PrinterName) 

| extend Policy=tostring(parsed.RestrictionReason)  

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields 

| order by Timestamp desc 
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="передовая охота":::
