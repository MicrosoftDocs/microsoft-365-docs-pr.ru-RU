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
# <a name="device-control-printer-protection"></a>Защита принтера для управления устройством

Защита принтера управления устройствами Microsoft Defender для конечных устройств блокирует печать с помощью не корпоративных принтеров или не утвержденного USB-принтера.

## <a name="licensing"></a>Лицензирование

Перед началом работы с Службой защиты принтеров необходимо подтвердить [Microsoft 365 подписку.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) Чтобы получить доступ к средствам защиты принтеров и использовать их, необходимо иметь следующее:

- Microsoft 365 E3 для развертывания функциональности и политики
- Microsoft 365 E5 отчетов

## <a name="permission"></a>Разрешение

Для развертывания политики в Intune для развертывания политики с помощью OMA-URI учетная запись должна иметь разрешения на создание, редактирование, обновление или удаление профилей конфигурации устройств. Вы можете создавать настраиваемые роли или использовать любую из встроенных ролей с помощью этих разрешений:

- Роль диспетчера политик и профилей.
- Или настраиваемая роль с разрешениями Create/Edit/Update/Read/Delete/View Reports, включенными для профилей конфигурации устройств
- Или глобальный администратор

Чтобы просмотреть отчеты о конфигурации устройства, у учетной записи должны быть разрешения на просмотр отчетов. Вы можете создавать настраиваемые роли или использовать встроенные роли с помощью этих разрешений:

- Администратор глобальной безопасности
- Администратор безопасности
- Читатель сведений о безопасности

## <a name="prepare-your-endpoints"></a>Подготовка конечных точек

Убедитесь, что Windows 10 устройства, которые планируется развернуть для защиты принтеров, чтобы соответствовать этим требованиям.

1. Присоединяйтесь к программе insider.

1. Устанавливаются следующие обновления Windows.
    - Для Windows 1809: установка Windows [обновления KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)
    - Для Windows 1909: установите Windows обновления [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)
    - Для Windows 2004 или более поздней

1. Если вы планируете развертывать политику с помощью групповой политики, устройство должно быть соединено с MDATP; если вы планируете развертывать политику через MEM, устройство должно быть соединено с Intune.

## <a name="deploy-device-control-printer-protection-policy"></a>Развертывание политики защиты принтеров управления устройствами

Вы можете развернуть политику с помощью групповой политики или Intune.

<br>

****

|Название|Описание|Поддержка CSP | Поддержка GPO | Поддержка на основе пользователя | Поддержка на основе машин |
|---|---|:---:|:---:|:---:|:---:|
|**Включить ограничения печати управления устройствами**|Блокировка печати с помощью не корпоративного принтера|Да|Да|Да|Да|
|**Список устройств печати с подключением к USB**\*|Разрешить определенный USB-принтер|Да|Да|Да|Да|
|

\*Эта политика должна использоваться вместе с ограничениями печати управления **устройствами.**

## <a name="deploy-policy-via-intune"></a>Развертывание политики через Intune

Для Intune в настоящее время защита принтера управления устройствами поддерживает только OMA-URI.

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a>Сценарий 1. Блокировка печати с помощью любого не корпоративного принтера с помощью Intune

- Применение политики на компьютере:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- Применить политику к пользователю:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

Строка поддержки CSP `<enabled/>` с:

:::image type="content" source="../../media/customeditrow.png" alt-text="настраиваемая строка редактирования":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a>Сценарий 2. Разрешить использование определенных утвержденных USB-принтеров с помощью Intune

- Применение политики на компьютере:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- Применить политику к пользователю:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

Строка поддержки CSP с утвержденными USB-принтерами с помощью свойства "ApprovedUsbPrintDevices", `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">` например:

:::image type="content" source="../../media/editrow.png" alt-text="изменение строки":::

## <a name="deploy-policy-via-group-policy"></a>Развертывание политики с помощью групповой политики

Если устройство не присоединилось к Intune, вы также можете развернуть политику с помощью групповой политики.

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a>Сценарий 1. Блокировка печати с помощью любого не корпоративного принтера с помощью групповой политики

- Применение политики на компьютере:

  Принтер \> административных шаблонов конфигурации \> компьютера: ввести ограничения печати для управления устройствами

- Применить политику к пользователю:

  Принтеры панели управления конфигурацией административных шаблонов \> \> пользователей: ввести ограничения печати для управления \> устройствами

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="включить ограничения печати устройств":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a>Сценарий 2. Разрешить использование определенных утвержденных USB-принтеров с помощью групповой политики

- Применение политики на компьютере:

  Принтер административных шаблонов конфигурации компьютера: список утвержденных \> \> устройств печати с подключением к USB

- Применить политику к пользователю:

  Принтеры панели управления конфигурацией административных шаблонов пользователей: список утвержденных \> \> устройств печати с \> подключением к USB

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="список утвержденных подключенных к usb печатным устройствам":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a>Просмотр данных о защите принтеров управления устройствами на портале Microsoft Defender для конечной точки

В [Microsoft 365 центра безопасности](https://security.microsoft.com) показана печать, заблокированная политикой защиты принтеров управления устройствами выше.

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
