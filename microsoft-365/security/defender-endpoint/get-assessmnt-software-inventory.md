---
title: Экспорт оценки инвентаризации программного обеспечения на устройство
description: Возвращает таблицу с записью для каждой уникальной комбинации DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.
keywords: api, api, export assessment, per device assessment, vulnerability assessment report, device vulnerability assessment, device vulnerability report, secure configuration assessment, secure configuration report, software vulnerabilities assessment, software vulnerability report, vulnerability report by machine,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 5663a17de2e601c506b4d1b9ac44eaab6ae6245f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778363"
---
# <a name="export-software-inventory-assessment-per-device"></a>Экспорт оценки инвентаризации программного обеспечения на устройство

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
Существуют различные вызовы API для получения различных типов данных. Так как объем данных может быть очень большим, их можно получить двумя способами:

- [Экспорт оценки инвентаризации **программного обеспечения OData**](#1-export-software-inventory-assessment-odata)  API передает все данные в организации в качестве ответов Json, следуя протоколу OData. Этот метод лучше всего используется для небольших организаций с устройствами _менее 100 К._ Ответ paginated, поэтому вы можете использовать поле odata.nextLink из ответа, чтобы \@ получить следующие результаты.

- [Экспорт оценки инвентаризации **программного обеспечения с помощью файлов**](#2-export-software-inventory-assessment-via-files)  Это решение API позволяет быстрее и более надежно тянуть большие объемы данных. Поэтому рекомендуется для крупных организаций с более чем 100 устройствами K. Этот API извлекает все данные в организации в качестве файлов загрузки. Ответ содержит URL-адреса для загрузки всех данных из служба хранилища Azure. Этот API позволяет загружать все данные из служба хранилища Azure следующим образом:

  - Позвоните в API, чтобы получить список загружаемых URL-адресов со всеми данными организации.

  - Скачайте все файлы с помощью URL-адресов загрузки и обработать данные, как вам нравится.

Собранные данные (с помощью _OData_ или _с_ помощью файлов) являются текущим снимком текущего состояния и не содержат исторических данных. Чтобы собрать исторические данные, клиенты должны сохранять данные в собственных хранилищах данных.

> [!Note]
>
> Если не указано обратное, все **** перечисленные методы оценки экспорта являются полным экспортом и по устройству **_(также_** именуемой как **_на устройстве)._**

## <a name="1-export-software-inventory-assessment-odata"></a>1. Оценка инвентаризации по экспорту программного обеспечения (OData)

### <a name="11-api-method-description"></a>Описание метода API 1.1

Этот ответ API содержит все данные установленного программного обеспечения на устройство. Возвращает таблицу с записью для каждой уникальной комбинации DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.

#### <a name="limitations"></a>Ограничения

- Максимальный размер страницы — 200 000.

- Ограничения скорости для этого API : 30 вызовов в минуту и 1000 вызовов в час.

### <a name="12-permissions"></a>1.2 Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)

Тип разрешения | Разрешение | Имя отображения разрешений
---|---|---
Приложение | Software.Read.All | \'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'
Делегированные (рабочая или учебная учетная запись) | Software.Read | \'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'

### <a name="13-url"></a>1.3 URL-адрес

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a>1.4 Параметры

- pageSize (по умолчанию = 50 000) — количество результатов в ответе.

- $top — количество возвращаемого результата (не возвращает @odata.nextLink и, следовательно, не вытягивает все данные)

### <a name="15-properties"></a>1.5 Свойства

>[!NOTE]
>
>-Каждая запись — это примерно 0,5 КБ данных. Это следует учитывать при выборе правильного параметра PageSize для вас.

>-Свойства, определенные в следующей таблице, перечислены в алфавитном порядке по ID свойства. При запуске этого API результат не обязательно возвращается в том же порядке, который указан в этой таблице.
>
>-Некоторые дополнительные столбцы могут быть возвращены в ответе. Эти столбцы являются временными и могут быть удалены, используйте только задокументированные столбцы.

Свойство (ID) | Тип данных | Описание | Пример возвращенного значения
:---|:---|:---|:---
DeviceId | Строка | Уникальный идентификатор устройства в службе. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | Строка | Полное доменное имя (FQDN) устройства. | johnlaptop.europe.contoso.com
DiskPaths | Array[string]  | Дисковые данные о том, что продукт установлен на устройстве. | [C: \\ Файлы программы (x86) \\ Microsoft \\ Silverlight \\ Application \\silverlight.exe" ]
EndOfSupportDate | Строка | Дата, в которой поддержка этого программного обеспечения имеет или закончится. | 2020-12-30
EndOfSupportStatus | Строка | Конец состояния поддержки. Может содержать эти возможные значения: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software. | Предстоящий EOS
Id | string | Уникальный идентификатор для записи. | 123ABG55_573AG&mnp!
NumberOfWeaknesses | int | Количество недостатков этого программного обеспечения на этом устройстве | 3
OSPlatform | Строка | Платформа операционной системы, запущенной на устройстве. Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7. Подробные сведения см. в материале tvm supported operating systems and platforms. | Windows10
RbacGroupName | Строка | Группа управления доступом на основе ролей (RBAC). Если это устройство не назначено какой-либо группе RBAC, значение будет "Unassigned". Если организация не содержит групп RBAC, значение будет "Нет". | Servers
RegistryPaths | Array[string] | Свидетельство реестра о том, что продукт установлен на устройстве. | [HKEY_LOCAL_MACHINE \\ ПРОГРАММНОЕ \\ ОБЕСПЕЧЕНИЕ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion удалить Microsoft \\ \\ Silverlight" ]
SoftwareFirstSeenTimestamp | Строка | Впервые это программное обеспечение было замечено на устройстве. | 2019-04-07 02:06:47
SoftwareName | Строка | Имя программного продукта. | Silverlight
SoftwareVendor | Строка | Имя поставщика программного обеспечения. | Microsoft
SoftwareVersion | Строка | Номер версии программного продукта. | 81.0.4044.138

### <a name="16-examples"></a>1.6 Примеры

#### <a name="161-request-example"></a>Пример запроса 1.6.1

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a>1.6.2 Пример ответа

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a>2. Экспорт инвентаризации программного обеспечения (с помощью файлов)

### <a name="21-api-method-description"></a>Описание метода API 2.1

Этот ответ API содержит все данные установленного программного обеспечения на устройство. Возвращает таблицу с записью для каждой уникальной комбинации DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.

#### <a name="211-limitations"></a>2.1.1 Ограничения

Ограничения скорости для этого API : 5 вызовов в минуту и 20 вызовов в час.

### <a name="22-permissions"></a>2.2 Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)

Тип разрешения | Разрешение | Имя отображения разрешений
---|---|---
Приложение | Software.Read.All | \'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'
Делегированные (рабочая или учебная учетная запись) | Software.Read | \'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'

### <a name="23-url"></a>2.3 URL-адрес

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a>Parameters

- sasValidHours — количество часов, за которые будут действительны URL-адреса загрузки (максимум 24 часа)

### <a name="25-properties"></a>2.5 Свойства

>[!Note]
>
>- Файлы являются сжатой gzip & в многолинейном формате Json.
>
>- Url-адреса загрузки действительны только в течение 3 часов. В противном случае можно использовать параметр.
>
>_ Для максимальной скорости скачивания данных можно убедиться, что вы скачиваете из того же региона Azure, в который находятся ваши данные.
>
Свойство (ID) | Тип данных | Описание | Пример возвращенного значения
:---|:---|:---|:---
Экспорт файлов | строка \[ массива\] | Список загрузок URL-адресов для файлов с текущим снимком организации | [  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]
GeneratedTime | Строка | Время, за которое был создан экспорт. | 2021-05-20T08:00:00Z ]

### <a name="26-examples"></a>2.6 Примеры

#### <a name="261-request-example"></a>Пример запроса 2.6.1

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a>2.6.2 Пример ответа

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>См. также

- [Методы и свойства экспортной оценки на устройство](get-assessmnt-1methods-properties.md)

- [Экспорт безопасной оценки конфигурации на устройство](get-assessmnt-secure-cfg.md)

- [Экспорт оценки уязвимостей программного обеспечения на устройство](get-assessmnt-software-vulnerabilities.md)

Другие связанные

- [Риск на основе угрозы & управление уязвимостями](next-gen-threat-and-vuln-mgt.md)

- [Уязвимости в организации](tvm-weaknesses.md)
