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
ms.openlocfilehash: 0b0f7c5a4a75fdc80509dbc02a43d28f7c93fd7c
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327051"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender для управления конечными точками управления устройствами, служба хранилища управления доступом

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender для управления конечными устройствами съемные служба хранилища управления доступом позволяет вам сделать следующую задачу:

- аудит, разрешение или предотвращение чтения, записи или выполнения доступа к съемным хранилищам с исключением или без него

|Привилегии |Разрешение  |
|---------|---------|
|Access    |  Чтение, Запись, Выполнение       |
|Режим действия    |    Аудит, разрешить, предотвратить     |
|Поддержка CSP   |   Да      |
|Поддержка GPO    |   Да      |
|Поддержка на основе пользователя     |   Да      |
|Поддержка на основе машин    |    Да     |

## <a name="prepare-your-endpoints"></a>Подготовка конечных точек

Развертывание служба хранилища управления доступом Windows 10 устройствах с клиентской версией **4.18.2103.3** или более поздней версии .

- **4.18.2104** или более поздние : Добавление SerialNumberId, VID_PID, поддержка GPO на основе filepath, ComputerSid

- **4.18.2105** или более поздний: Добавьте поддержку wildcard для HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, сочетание определенного пользователя на определенном компьютере, удаляемая поддержка SSD (SSD SanDisk Extreme)/USB, присоединенная к SCSI (UAS).

- **4.18.2107** или более поздний вариант: добавление поддержки Windows портативного устройства (WPD) (для мобильных устройств, например планшетов)

:::image type="content" source="images/powershell.png" alt-text="Интерфейс PowerShell":::

> [!NOTE]
> Ни один Безопасность Windows не должен быть активным, вы можете запускать съемные служба хранилища управления доступом независимо от Безопасность Windows состояния.

## <a name="policy-properties"></a>Свойства политики

Для создания съемной группы хранения можно использовать следующие свойства:

**Имя свойства: Group Id**

1. Описание: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), уникальный ID, представляет группу и будет использоваться в политике.

**Имя свойства: DescriptorIdList**

2. Описание. Список свойств устройств, которые необходимо использовать для покрытия в группе.
Дополнительные подробности см. в разделе **Свойства** устройства.

3. Параметры:
    - PrimaryId
        - RemovableMediaDevices
        - CdRomDevices
        - WpdDevices
    - DeviceId
    - HardwareId
    - InstancePathId: InstancePathId — это строка, которая однозначно идентифицирует устройство в системе, например USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0. Номер в конце **(например,&0)** представляет доступный слот и может изменяться с устройства на устройство. Для наилучших результатов используйте под диктовую карточку в конце. Например, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*
    - FriendlyNameId
    - SerialNumberId
    - VID
    - PID
    - VID_PID
        - 0751_55E0: соответствует именно этой паре VID/PID
        - _55E0: соотнося все носители с PID=55E0
        - 0751_: совпадает с любыми носители с VID=0751
        
**Имя свойства: MatchType** 

1. Описание. Если в descriptorIDList используется несколько свойств устройств, MatchType определяет связь.

2. Параметры:

    - MatchAll: Любые атрибуты в descriptorIdList **будут** и отношения; например, если администратор ставит DeviceID и InstancePathID, для каждого подключенного USB система будет проверять, соответствует ли USB обоим значениям.
    - MatchAny: атрибуты в descriptorIdList будут **или отношения;** например, если администратор ставит DeviceID и InstancePathID, для каждого подключенного USB система будет работать с исполнением до тех пор, пока USB имеет одинаковое значение **DeviceID** или **InstanceID.**

Ниже следующую ниже следующую следующую политику политики управления доступом:

**Имя свойства: PolicyRuleId**

1. Описание. [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), уникальный ID, представляет политику и будет использоваться в отчетности и устранении неполадок.

**Имя свойства: IncludedIdList**

1. Описание. Группа(ы), к которую будет применена политика. Если добавлено несколько групп, политика будет применяться к любым средствам массовой информации во всех этих группах.

2. Параметры. В этом экземпляре необходимо использовать групповой ID/GUID.

В следующем примере показано использование GroupID:

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

**Имя свойства: ExcludedIDList**

Описание. Группа(ы), к которую политика не будет применяться.

Параметры. В этом экземпляре необходимо использовать групповой ID/GUID.

**Имя свойства: Id записи**

1. Описание. One PolicyRule может иметь несколько записей; каждая запись с уникальным GUID сообщает устройству Управление одним ограничением.

**Имя свойства. Введите**

1. Описание. Определяет действие для съемных групп хранения в IncludedIDList.
    - Правоприменители: разрешить или запретить
    - Аудит: AuditAllowed или AuditDenied 

2. Параметры:

    - Разрешить
    - "Запретить"
    - AuditAllowed: определяет уведомление и событие при разрешенных доступах
    - AuditDenied: определяет уведомление и событие при отказе в доступе; должна работать вместе с **отказом во** входе.

Если существуют типы конфликтов для одного и того же носитела, система применяет первый в политике. Пример типа конфликта — **Разрешить и** **запретить.**

**Имя свойства: Sid**

Описание. Локальный компьютер Sid или Sid объекта AD определяет, следует ли применять эту политику к определенной группе пользователей или пользователей; одна запись может иметь максимум один Sid и запись без каких-либо средств Sid применения политики на компьютере.

**Имя свойства: ComputerSid**

Описание. Локальный компьютер Sid или Sid объекта AD определяет, следует ли применять эту политику к определенной группе машин или машин; одна запись может иметь максимум один ComputerSid и запись без средств ComputerSid, применяющих политику на компьютере. Если вы хотите применить запись к определенному пользователю и определенной машине, добавьте и Sid, и ComputerSid в ту же запись.

**Имя свойства: Параметры**

Описание. Определяет, следует ли отображать уведомление или нет.

   :::image type="content" source="images/device-status.png" alt-text="Экран, на котором можно увидеть состояние устройства":::

Параметры: 0-4. При выборе типа Разрешить или Запретить:

   - 0: ничего
   - 4. отключить **AuditAllowed и** **AuditDenied для** этой записи. Даже если **произойдет блокировка** и **настроен параметр AuditDenied,** система не будет показывать уведомления.

   Когда выбран **тип AuditAllowed** или **AuditDenied:**

   - 0: ничего
   - 1. уведомление о показе
   - 2. Событие отправки
   - 3. показать уведомление и отправить событие

**Имя свойства: AccessMask**

Описание. Определяет доступ.

Параметры 1-7:
  - 1. Чтение
  - 2. Записыв
  - 3. Чтение и написание
  - 4. Выполнение
  - 5. Чтение и выполнение
  - 6. Написать и выполнить
  - 7. Чтение и написание и выполнение

## <a name="common-removable-storage-access-control-scenarios"></a>Распространенные сценарии служба хранилища управления доступом

Чтобы помочь вам ознакомиться с Microsoft Defender для конечной точки съемной служба хранилища управления доступом, мы собрали несколько распространенных сценариев для вас, чтобы следовать.

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>Сценарий 1. Предотвращение записи и выполнения доступа ко всем пользователям, но разрешить определенные утвержденные usBs

1. Создание групп

    1. Группа 1. Любое съемное хранилище и CD/DVD. Пример съемного хранилища и CD/DVD: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** в примере Any Removable служба хранилища и [CD-DVD Group.xmlфайл.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)
    
    2. Группа 2. Утвержденные usBs на основе свойств устройств. Пример для этого случая использования: Экземпляр ID — Group **65fa649a-a111-4912-9294-fb6337a25038** в примере утвержденных [usBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) файл.

    > [!NOTE]
    > Вы должны `&` заменить `&amp;` в значении.

2. Создание политики

    1. Политика 1. Заблокировать записи и выполнить доступ, но разрешить утвержденные usBs. Пример этого примера использования: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** в примере [Scenario 1 Block Write and Execute Access,](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) но разрешает утвержденный USBs.xmlфайл.
    
    2. Политика 2. Проверка записи и выполнения доступа к разрешенным usBs. Пример этого примера использования: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** в примере [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>Сценарий 2. Проверка записи и выполнения доступа ко всем, кроме блокировки определенных неодобренных usBs

1. Создание групп

    1. Группа 1. Любое съемное хранилище и CD/DVD. Пример этого примера использования: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** в примере Любые съемные служба хранилища и [CD-DVD-Group.xmlфайл.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)
    
    2. Группа 2. [Unapproved](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) USBs на основе свойств устройств, например, ID поставщика / ID продукта, Friendly Name — Group **65fa649a-a111-4912-9294-fb6337a25038** в примере неаппровотных usBs Group.xmlфайле. 

    > [!NOTE]
    > Вы должны `&` заменить `&amp;` в значении.

2. Создание политики

    1. Политика 1. Блокировка записи и выполнения доступа ко всем, кроме блокировки определенных неодобренных ОКБ. Пример этого примера использования: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** в примере [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    
    2. Политика 2. Проверка записи и выполнения доступа к другим. Пример этого примера использования: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** в примере [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.

## <a name="deploying-and-managing-policy-via-group-policy"></a>Развертывание и управление политикой с помощью групповой политики

Функция управления служба хранилища доступа позволяет применять политику с помощью групповой политики либо к пользователю, либо к устройству, либо к обоим.

### <a name="licensing"></a>Лицензирование

Перед началом работы со съемными служба хранилища управления доступом необходимо подтвердить Microsoft 365 [подписку.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2) Для доступа и использования служба хранилища управления доступом необходимо иметь Microsoft 365 E3 или Microsoft 365 E5.

### <a name="deploying-policy-via-group-policy"></a>Развертывание политики с помощью групповой политики

1. Объединяйте все группы `<Groups>` `</Groups>` в одном xml-файле. 

    На следующем изображении иллюстрируется пример сценария 1: предотвращение записи и выполнения доступа ко всем, но разрешить определенные утвержденные [ОКБ.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Экран, отображающий параметры конфигурации, разрешающие определенные утвержденные usBs на устройствах":::
    
2. Объединяйте все правила `<PolicyRules>` `</PolicyRules>` в одном xml-файле. 

    Если вы хотите ограничить конкретного пользователя, используйте свойство SID в записи. Если в записи политики нет SID, запись будет применяться к экземпляру входа для компьютера.
    
    На следующем изображении иллюстрируется использование свойства SID, а также пример сценария 1: предотвращение записи и выполнения доступа ко всем пользователям, но только к определенным утвержденным [usBs.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Экран, отображающий код, который указывает использование атрибута свойства SID":::

3. Сохраните файлы XML правил и групп в папке сетевого обмена и вставьте путь папки сетевого обмена в параметр Групповой политики: конфигурация компьютера -> Административные шаблоны -> Windows Компоненты **-> антивирусная программа в Microsoft Defender->** Управление устройствами: "Определение групп политики управления устройствами" и "Определение правил политики управления устройствами".

    - Целевая машина должна иметь доступ к сетевой доской, чтобы иметь политику. Однако после прочтия политики подключение к сетевой совместной сети больше не требуется даже после перезагрузки компьютера.

    :::image type="content" source="images/device-control.png" alt-text="Экран управления устройствами":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>Развертывание и управление политикой через Intune OMA-URI

Функция управления служба хранилища доступа позволяет применять политику с помощью OMA-URI либо к пользователю, либо к устройству, либо к обоим.

### <a name="licensing"></a>Лицензирование

Перед началом работы со съемными служба хранилища управления доступом необходимо подтвердить Microsoft 365 [подписку.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2) Для доступа и использования служба хранилища управления доступом необходимо иметь Microsoft 365 E3 или Microsoft 365 E5.

### <a name="permission"></a>Разрешение

Для развертывания политики в Intune учетная запись должна иметь разрешения на создание, редактирование, обновление или удаление профилей конфигурации устройств. С помощью этих разрешений можно создавать настраиваемые роли или использовать любые встроенные роли.

- Роль диспетчера политик и профилей
- Настраиваемая роль с разрешениями Create/Edit/Update/Read/Delete/View Reports, включенными для профилей конфигурации устройств
- Глобальный администратор

### <a name="deploying-policy-via-oma-uri"></a>Развертывание политики через OMA-URI

**Microsoft Endpoint Manager центра администрирования (-> Devices -> Профили конфигурации -> Создание профиля -> Платформа: Windows 10 и более поздний & Профиль: Настраиваемый https://endpoint.microsoft.com/)**

1. Для каждой группы создайте правило OMA-URI:
    - OMA-URI: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData

      Например, для любой съемной группы хранения и **CD/DVD** в примере ссылка должна быть:

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData

    - Тип данных: String (XML-файл)
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="XML-файл для типа данных STRING":::

2. Для каждой политики также создайте OMA-URI:

    - OMA-URI: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBF68E1%7d/RuleData

      Например, для блокировки записи и выполнения доступа, но разрешить утвержденное правило **USBs** в примере, ссылка должна быть: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.

    - Тип данных: String (XML-файл)

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Отображение XML-файла для типа данных STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>Развертывание и управление политикой с помощью пользовательского интерфейса Intune

Эта возможность (в центре администрирования Microsoft Endpoint Manager (> Устройства > Профили конфигурации > Создание профиля > Платформа: Windows 10 и более поздние https://endpoint.microsoft.com/) & Profile: Device Control) еще недоступна. 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Просмотр съемных данных управления устройствами служба хранилища управления доступом в Microsoft Defender для конечной точки

На Microsoft 365 портале безопасности показаны съемные хранилища, заблокированные съемным служба хранилища управления доступом. Чтобы получить доступ к Microsoft 365 безопасности, необходимо иметь следующую подписку:

- Microsoft 365 отчетов по E5

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

## <a name="frequently-asked-questions"></a>Вопросы и ответы

**Какое ограничение для съемных носители хранения для максимального числа пользователей?**

Мы проверили одну группу USB со 100 000 мультимедиа размером до 7 МБ. Политика работает как в Intune, так и в GPO без проблем с производительностью.

**Почему политика не работает?**

Наиболее частой причиной является отсутствие обязательной клиентской версии [антивирусного программного обеспечения.](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)

Другая причина может быть в том, что XML-файл неправильно отформатирован, например, не использует правильный формат разметки для символа "&" в XML-файле, или текстовый редактор может добавить метку заказа в 0xEF 0xBB 0xBF в начале файлов, из-за чего разбор XML не работает. Одним из простых решений является [скачивание](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) примера файла (выберите **Raw,** а затем **Сохранить как),** а затем обновить.

Если имеется значение и политика управляется с помощью групповой политики, проверьте, может ли клиентское устройство получить доступ к пути XML политики.

**Как узнать, какая машина использует устарелую клиентскую версию антивирусных программ в организации?**

Следующий запрос можно использовать для получения клиентской версии антивирусных программ на Microsoft 365 безопасности:
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
