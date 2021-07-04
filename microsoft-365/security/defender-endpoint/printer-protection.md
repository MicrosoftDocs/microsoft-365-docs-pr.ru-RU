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
ms.topic: article
ms.openlocfilehash: 0f089efedef1e4fb6b146692da3f1a630f2bacac
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289695"
---
# <a name="device-control-printer-protection"></a><span data-ttu-id="50d6d-103">Защита принтера для управления устройством</span><span class="sxs-lookup"><span data-stu-id="50d6d-103">Device Control Printer Protection</span></span>

<span data-ttu-id="50d6d-104">Защита принтера управления устройствами Microsoft Defender для конечных устройств блокирует печать с помощью не корпоративных принтеров или не утвержденного USB-принтера.</span><span class="sxs-lookup"><span data-stu-id="50d6d-104">Microsoft Defender for Endpoint Device Control Printer Protection blocks people from printing via non-corporate printers or non-approved USB printer.</span></span>

## <a name="licensing"></a><span data-ttu-id="50d6d-105">Лицензирование</span><span class="sxs-lookup"><span data-stu-id="50d6d-105">Licensing</span></span>

<span data-ttu-id="50d6d-106">Перед началом работы с Службой защиты принтеров необходимо подтвердить [Microsoft 365 подписку.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="50d6d-106">Before you get started with Printer Protection, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="50d6d-107">Чтобы получить доступ к средствам защиты принтеров и использовать их, необходимо иметь следующее:</span><span class="sxs-lookup"><span data-stu-id="50d6d-107">To access and use Printer Protection, you must have the following:</span></span>

- <span data-ttu-id="50d6d-108">Microsoft 365 E3 для развертывания функциональности и политики</span><span class="sxs-lookup"><span data-stu-id="50d6d-108">Microsoft 365 E3 for functionality/policy deployment</span></span>
- <span data-ttu-id="50d6d-109">Microsoft 365 E5 отчетов</span><span class="sxs-lookup"><span data-stu-id="50d6d-109">Microsoft 365 E5 for reporting</span></span>

## <a name="permission"></a><span data-ttu-id="50d6d-110">Разрешение</span><span class="sxs-lookup"><span data-stu-id="50d6d-110">Permission</span></span>

<span data-ttu-id="50d6d-111">Для развертывания политики в Intune для развертывания политики с помощью OMA-URI учетная запись должна иметь разрешения на создание, редактирование, обновление или удаление профилей конфигурации устройств.</span><span class="sxs-lookup"><span data-stu-id="50d6d-111">For Policy deployment in Intune, to deploy policy via OMA-URI, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="50d6d-112">Вы можете создавать настраиваемые роли или использовать любую из встроенных ролей с помощью этих разрешений:</span><span class="sxs-lookup"><span data-stu-id="50d6d-112">You can create custom roles or use any of the built-in roles with these permissions:</span></span>

- <span data-ttu-id="50d6d-113">Роль диспетчера политик и профилей.</span><span class="sxs-lookup"><span data-stu-id="50d6d-113">Policy and profile Manager role.</span></span>
- <span data-ttu-id="50d6d-114">Или настраиваемая роль с разрешениями Create/Edit/Update/Read/Delete/View Reports, включенными для профилей конфигурации устройств</span><span class="sxs-lookup"><span data-stu-id="50d6d-114">Or custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="50d6d-115">Или глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="50d6d-115">Or Global admin</span></span>

<span data-ttu-id="50d6d-116">Чтобы просмотреть отчеты о конфигурации устройства, у учетной записи должны быть разрешения на просмотр отчетов.</span><span class="sxs-lookup"><span data-stu-id="50d6d-116">To see device configuration reports, the account must have view reports permissions.</span></span> <span data-ttu-id="50d6d-117">Вы можете создавать настраиваемые роли или использовать встроенные роли с помощью этих разрешений:</span><span class="sxs-lookup"><span data-stu-id="50d6d-117">You can create custom roles or use the built-in roles with these permissions:</span></span>

- <span data-ttu-id="50d6d-118">Администратор глобальной безопасности</span><span class="sxs-lookup"><span data-stu-id="50d6d-118">Global security admin</span></span>
- <span data-ttu-id="50d6d-119">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="50d6d-119">Security admin</span></span>
- <span data-ttu-id="50d6d-120">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="50d6d-120">Security Reader</span></span>

## <a name="prepare-your-endpoints"></a><span data-ttu-id="50d6d-121">Подготовка конечных точек</span><span class="sxs-lookup"><span data-stu-id="50d6d-121">Prepare your endpoints</span></span>

<span data-ttu-id="50d6d-122">Убедитесь, что Windows 10 устройства, которые планируется развернуть для защиты принтеров, чтобы соответствовать этим требованиям.</span><span class="sxs-lookup"><span data-stu-id="50d6d-122">Make sure that the Windows 10 devices that you plan on deploying Printer Protection to meet these requirements.</span></span>

1. <span data-ttu-id="50d6d-123">Присоединяйтесь к программе insider.</span><span class="sxs-lookup"><span data-stu-id="50d6d-123">Join the Insider Program.</span></span>

1. <span data-ttu-id="50d6d-124">Устанавливаются следующие обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="50d6d-124">The following Windows Updates are installed.</span></span>
    - <span data-ttu-id="50d6d-125">Для Windows 1809: установка Windows [обновления KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span><span class="sxs-lookup"><span data-stu-id="50d6d-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span></span>
    - <span data-ttu-id="50d6d-126">Для Windows 1909: установите Windows обновления [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span><span class="sxs-lookup"><span data-stu-id="50d6d-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span></span>
    - <span data-ttu-id="50d6d-127">Для Windows 2004 или более поздней</span><span class="sxs-lookup"><span data-stu-id="50d6d-127">For Windows 2004 or later</span></span>

1. <span data-ttu-id="50d6d-128">Если вы планируете развертывать политику с помощью групповой политики, устройство должно быть соединено с MDATP; если вы планируете развертывать политику через MEM, устройство должно быть соединено с Intune.</span><span class="sxs-lookup"><span data-stu-id="50d6d-128">If you're planning to deploy policy via Group Policy, the device must be MDATP joined; if you're planning to deploy policy via MEM, the device must be Intune joined.</span></span>

## <a name="deploy-device-control-printer-protection-policy"></a><span data-ttu-id="50d6d-129">Развертывание политики защиты принтеров управления устройствами</span><span class="sxs-lookup"><span data-stu-id="50d6d-129">Deploy Device Control Printer Protection policy</span></span>

<span data-ttu-id="50d6d-130">Вы можете развернуть политику с помощью групповой политики или Intune.</span><span class="sxs-lookup"><span data-stu-id="50d6d-130">You can deploy the policy via Group Policy or Intune.</span></span>

<br>

****

|<span data-ttu-id="50d6d-131">Название</span><span class="sxs-lookup"><span data-stu-id="50d6d-131">Title</span></span>|<span data-ttu-id="50d6d-132">Описание</span><span class="sxs-lookup"><span data-stu-id="50d6d-132">Description</span></span>|<span data-ttu-id="50d6d-133">Поддержка CSP</span><span class="sxs-lookup"><span data-stu-id="50d6d-133">CSP Support</span></span> | <span data-ttu-id="50d6d-134">Поддержка GPO</span><span class="sxs-lookup"><span data-stu-id="50d6d-134">GPO Support</span></span> | <span data-ttu-id="50d6d-135">Поддержка на основе пользователя</span><span class="sxs-lookup"><span data-stu-id="50d6d-135">User-based Support</span></span> | <span data-ttu-id="50d6d-136">Поддержка на основе машин</span><span class="sxs-lookup"><span data-stu-id="50d6d-136">Machine-based Support</span></span> |
|---|---|:---:|:---:|:---:|:---:|
|<span data-ttu-id="50d6d-137">**Включить ограничения печати управления устройствами**</span><span class="sxs-lookup"><span data-stu-id="50d6d-137">**Enable Device control Printing Restrictions**</span></span>|<span data-ttu-id="50d6d-138">Блокировка печати с помощью не корпоративного принтера</span><span class="sxs-lookup"><span data-stu-id="50d6d-138">Block people from printing via non-corporate printer</span></span>|<span data-ttu-id="50d6d-139">Да</span><span class="sxs-lookup"><span data-stu-id="50d6d-139">Yes</span></span>|<span data-ttu-id="50d6d-140">Да</span><span class="sxs-lookup"><span data-stu-id="50d6d-140">Yes</span></span>|<span data-ttu-id="50d6d-141">Да</span><span class="sxs-lookup"><span data-stu-id="50d6d-141">Yes</span></span>|<span data-ttu-id="50d6d-142">Да</span><span class="sxs-lookup"><span data-stu-id="50d6d-142">Yes</span></span>|
|<span data-ttu-id="50d6d-143">**Список устройств печати с подключением к USB**\*</span><span class="sxs-lookup"><span data-stu-id="50d6d-143">**List of Approved USB-connected print devices**\*</span></span>|<span data-ttu-id="50d6d-144">Разрешить определенный USB-принтер</span><span class="sxs-lookup"><span data-stu-id="50d6d-144">Allow specific USB printer</span></span>|<span data-ttu-id="50d6d-145">Да</span><span class="sxs-lookup"><span data-stu-id="50d6d-145">Yes</span></span>|<span data-ttu-id="50d6d-146">Да</span><span class="sxs-lookup"><span data-stu-id="50d6d-146">Yes</span></span>|<span data-ttu-id="50d6d-147">Да</span><span class="sxs-lookup"><span data-stu-id="50d6d-147">Yes</span></span>|<span data-ttu-id="50d6d-148">Да</span><span class="sxs-lookup"><span data-stu-id="50d6d-148">Yes</span></span>|
|

<span data-ttu-id="50d6d-149">\*Эта политика должна использоваться вместе с ограничениями печати управления **устройствами.**</span><span class="sxs-lookup"><span data-stu-id="50d6d-149">\* This policy must be used together with **Enable Device control Printing Restrictions**.</span></span>

## <a name="deploy-policy-via-intune"></a><span data-ttu-id="50d6d-150">Развертывание политики через Intune</span><span class="sxs-lookup"><span data-stu-id="50d6d-150">Deploy policy via Intune</span></span>

<span data-ttu-id="50d6d-151">Для Intune в настоящее время защита принтера управления устройствами поддерживает только OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="50d6d-151">For Intune, currently Device Control Printer Protection supports OMA-URI only.</span></span>

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a><span data-ttu-id="50d6d-152">Сценарий 1. Блокировка печати с помощью любого не корпоративного принтера с помощью Intune</span><span class="sxs-lookup"><span data-stu-id="50d6d-152">Scenario 1: Block people from printing via any non-corporate printer using Intune</span></span>

- <span data-ttu-id="50d6d-153">Применение политики на компьютере:</span><span class="sxs-lookup"><span data-stu-id="50d6d-153">Apply policy over machine:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- <span data-ttu-id="50d6d-154">Применить политику к пользователю:</span><span class="sxs-lookup"><span data-stu-id="50d6d-154">Apply policy over user:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

<span data-ttu-id="50d6d-155">Строка поддержки CSP `<enabled/>` с:</span><span class="sxs-lookup"><span data-stu-id="50d6d-155">The CSP support string with `<enabled/>`:</span></span>

:::image type="content" source="../../media/customeditrow.png" alt-text="настраиваемая строка редактирования":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a><span data-ttu-id="50d6d-157">Сценарий 2. Разрешить использование определенных утвержденных USB-принтеров с помощью Intune</span><span class="sxs-lookup"><span data-stu-id="50d6d-157">Scenario 2: Allow specific approved USB printers using Intune</span></span>

- <span data-ttu-id="50d6d-158">Применение политики на компьютере:</span><span class="sxs-lookup"><span data-stu-id="50d6d-158">Apply policy over machine:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- <span data-ttu-id="50d6d-159">Применить политику к пользователю:</span><span class="sxs-lookup"><span data-stu-id="50d6d-159">Apply policy over user:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

<span data-ttu-id="50d6d-160">Строка поддержки CSP с утвержденными USB-принтерами с помощью свойства "ApprovedUsbPrintDevices", `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">` например:</span><span class="sxs-lookup"><span data-stu-id="50d6d-160">The CSP support string with approved USB printers via 'ApprovedUsbPrintDevices' property, example `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">`:</span></span>

:::image type="content" source="../../media/editrow.png" alt-text="изменение строки":::

## <a name="deploy-policy-via-group-policy"></a><span data-ttu-id="50d6d-162">Развертывание политики с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="50d6d-162">Deploy policy via Group Policy</span></span>

<span data-ttu-id="50d6d-163">Если устройство не присоединилось к Intune, вы также можете развернуть политику с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="50d6d-163">If the device isn't Intune joined, you can also deploy the policy via Group Policy.</span></span>

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a><span data-ttu-id="50d6d-164">Сценарий 1. Блокировка печати с помощью любого не корпоративного принтера с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="50d6d-164">Scenario 1: Block people from printing via any non-corporate printer using Group Policy</span></span>

- <span data-ttu-id="50d6d-165">Применение политики на компьютере:</span><span class="sxs-lookup"><span data-stu-id="50d6d-165">Apply policy over machine:</span></span>

  <span data-ttu-id="50d6d-166">Принтер \> административных шаблонов конфигурации \> компьютера: ввести ограничения печати для управления устройствами</span><span class="sxs-lookup"><span data-stu-id="50d6d-166">Computer Configuration \> Administrative Templates \> Printer: Enable Device control Printing Restrictions</span></span>

- <span data-ttu-id="50d6d-167">Применить политику к пользователю:</span><span class="sxs-lookup"><span data-stu-id="50d6d-167">Apply policy over user:</span></span>

  <span data-ttu-id="50d6d-168">Принтеры панели управления конфигурацией административных шаблонов \> \> пользователей: ввести ограничения печати для управления \> устройствами</span><span class="sxs-lookup"><span data-stu-id="50d6d-168">User Configuration \> Administrative Templates \> Control Panel \> Printers: Enable Device control Printing Restrictions</span></span>

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="включить ограничения печати устройств":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a><span data-ttu-id="50d6d-170">Сценарий 2. Разрешить использование определенных утвержденных USB-принтеров с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="50d6d-170">Scenario 2: Allow specific approved USB printers using Group Policy</span></span>

- <span data-ttu-id="50d6d-171">Применение политики на компьютере:</span><span class="sxs-lookup"><span data-stu-id="50d6d-171">Apply policy over machine:</span></span>

  <span data-ttu-id="50d6d-172">Принтер административных шаблонов конфигурации компьютера: список утвержденных \> \> устройств печати с подключением к USB</span><span class="sxs-lookup"><span data-stu-id="50d6d-172">Computer Configuration \> Administrative Templates \> Printer:  List of Approved USB-connected print devices</span></span>

- <span data-ttu-id="50d6d-173">Применить политику к пользователю:</span><span class="sxs-lookup"><span data-stu-id="50d6d-173">Apply policy over user:</span></span>

  <span data-ttu-id="50d6d-174">Принтеры панели управления конфигурацией административных шаблонов пользователей: список утвержденных \> \> устройств печати с \> подключением к USB</span><span class="sxs-lookup"><span data-stu-id="50d6d-174">User Configuration \> Administrative Templates \> Control Panel \> Printers: List of Approved USB-connected print devices</span></span>

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="список утвержденных подключенных к usb печатным устройствам":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a><span data-ttu-id="50d6d-176">Просмотр данных о защите принтеров управления устройствами на портале Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="50d6d-176">View Device Control Printer Protection data in Microsoft Defender for Endpoint portal</span></span>

<span data-ttu-id="50d6d-177">В [Microsoft 365 центра безопасности](https://security.microsoft.com) показана печать, заблокированная политикой защиты принтеров управления устройствами выше.</span><span class="sxs-lookup"><span data-stu-id="50d6d-177">The [Microsoft 365 security center](https://security.microsoft.com) shows printing blocked by the Device Control Printer Protection policy above.</span></span>

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
