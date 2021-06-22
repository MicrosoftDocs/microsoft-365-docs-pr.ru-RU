---
title: Экспорт оценки уязвимостей программного обеспечения на устройство
description: Ответ API на устройство содержит уязвимое программное обеспечение, установленное на подверженных устройствах, а также любые известные уязвимости в этих программных продуктах. Эта таблица также содержит сведения об операционной системе, ИД CVE и сведения о серьезности уязвимости.
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
ms.openlocfilehash: 87fb5c62b520168a686cc0b95a321becdd4656ba
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "53052967"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a>Экспорт оценки уязвимостей программного обеспечения на устройство

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
Возвращает все известные уязвимости программного обеспечения и их сведения для всех устройств на основе каждого устройства.

Существуют различные вызовы API для получения различных типов данных. Так как объем данных может быть очень большим, их можно получить двумя способами:

1. [Оценка уязвимостей по экспорту **программного обеспечения JSON**](#1-export-software-vulnerabilities-assessment-json-response)  API извлекет все данные в организации в качестве ответов Json. Этот метод лучше всего используется для небольших организаций с устройствами _менее 100 К._ Ответ paginated, поэтому вы можете использовать поле odata.nextLink из ответа, чтобы \@ получить следующие результаты.

2. [Экспорт оценки уязвимостей программного **обеспечения с помощью файлов**](#2-export-software-vulnerabilities-assessment-via-files) Это решение API позволяет быстрее и более надежно тянуть большие объемы данных. Виа-файлы рекомендуется использовать для крупных организаций с более чем 100 устройствами K. Этот API извлекает все данные в организации в качестве файлов загрузки. Ответ содержит URL-адреса для загрузки всех данных из служба хранилища Azure. Этот API позволяет загружать все данные из служба хранилища Azure следующим образом:

   - Позвоните в API, чтобы получить список загружаемых URL-адресов со всеми данными организации.

   - Скачайте все файлы с помощью URL-адресов загрузки и обработать данные, как вам нравится.

3. [Оценка уязвимостей **JSON**](#3-delta-export-software-vulnerabilities-assessment-json-response) по оценке уязвимостей экспортного программного обеспечения Delta  Возвращает таблицу с записью для каждого уникального сочетания: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId и EventTimestamp.
API извлекет данные в организации в качестве ответов Json. Ответ paginated, поэтому вы можете использовать поле @odata.nextLink из ответа, чтобы получить следующие результаты. <br><br> В отличие от полной "оценки уязвимостей программного обеспечения (ответ JSON)", которая используется для получения полного снимка оценки уязвимостей программного обеспечения вашей организации с помощью устройства, вызов API экспорта дельты используется для получения только изменений, которые произошли между выбранной датой и текущей датой (вызов API delta). Вместо того чтобы получать полный экспорт с большим объемом данных каждый раз, вы получите только конкретные сведения о новых, исправленных и обновленных уязвимостях. Вызов API API API ответов JSON экспорта Delta также можно использовать для вычисления различных KPI, таких как "сколько уязвимостей было исправлено?" или "сколько новых уязвимостей было добавлено в мою организацию?" <br><br> Так как вызов API API ответов JSON экспорта Delta для уязвимостей программного обеспечения возвращает данные только для целевого диапазона дат, он не считается _полным экспортом._

Собранные данные (с помощью ответа _Json_ или с помощью _файлов)_ являются текущим снимком текущего состояния и не содержат исторических данных. Чтобы собрать исторические данные, клиенты должны сохранять данные в собственных хранилищах данных.

> [!Note]
>
> Если не указано обратное, все **** перечисленные методы оценки экспорта являются полным экспортом и по устройству **_(также_** именуемой как **_на устройстве)._**

## <a name="1-export-software-vulnerabilities-assessment-json-response"></a>1. Оценка уязвимостей по экспорту программного обеспечения (ответ JSON)

### <a name="11-api-method-description"></a>Описание метода API 1.1

Этот ответ API содержит все данные установленного программного обеспечения на устройство. Возвращает таблицу с записью для каждой уникальной комбинации DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.

#### <a name="111-limitations"></a>1.1.1 Ограничения

- Максимальный размер страницы — 200 000.

- Ограничения скорости для этого API : 30 вызовов в минуту и 1000 вызовов в час.

### <a name="12-permissions"></a>1.2 Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)

Тип разрешения | Разрешение | Имя отображения разрешений
---|---|---
Приложение | Vulnerability.Read.All | \'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'
Делегированные (рабочая или учебная учетная запись) | Vulnerability.Read | \'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'

### <a name="13-url"></a>1.3 URL-адрес

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a>1.4 Параметры

- pageSize (по умолчанию = 50 000) — количество результатов в ответе
- $top — количество возвращаемого результата (не возвращает @odata.nextLink и, следовательно, не вытягивает все данные)

### <a name="15-properties"></a>1.5 Свойства

>[!Note]
>
>- Каждая запись — это примерно 1 КБ данных. Это следует учитывать при выборе правильного параметра PageSize для вас.
>
>- Некоторые дополнительные столбцы могут быть возвращены в ответе. Эти столбцы являются временными и могут быть удалены, используйте только задокументированные столбцы.
>
>- Свойства, определенные в следующей таблице, перечислены в алфавитном порядке по ID свойства.  При запуске этого API результат не обязательно возвращается в том же порядке, который указан в этой таблице.

<br/>

Свойство (ID) | Тип данных | Описание | Пример возвращенного значения
:---|:---|:---|:---
CveId | string | Уникальный идентификатор, присвоенный уязвимости безопасности в системе Common Vulnerabilities and Exposures (CVE). | CVE-2020-15992
CvssScore | string | Оценка CVSS CVE. | 6.2
DeviceId | string | Уникальный идентификатор устройства в службе. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | string | Полное доменное имя (FQDN) устройства. | johnlaptop.europe.contoso.com
DiskPaths  | Строка \[ Array\] | Дисковые данные о том, что продукт установлен на устройстве. | [ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]
ExploitabilityLevel | string | Уровень эксплуатации этой уязвимости (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit) | ExploitIsInKit
FirstSeenTimestamp | string | Впервые CVE этого продукта был замечен на устройстве. | 2020-11-03 10:13:34.8476880
Id | string | Уникальный идентификатор для записи. | 123ABG55_573AG&mnp!
LastSeenTimestamp | string | Последний раз CVE был замечен на устройстве. | 2020-11-03 10:13:34.8476880
OSPlatform | string | Платформа операционной системы, запущенной на устройстве. Это свойство указывает на определенные операционные системы, в том числе варианты в одной семье, например Windows 10 и Windows 7. Подробные сведения см. в материале tvm supported operating systems and platforms. | Windows10
RbacGroupName  | string | Группа управления доступом на основе ролей (RBAC). Если это устройство не назначено какой-либо группе RBAC, значение будет "Unassigned". Если организация не содержит групп RBAC, значение будет "Нет". | Servers
RecommendationReference | string | Ссылка на номер рекомендации, связанный с этим программным обеспечением. | va-_-microsoft-silverlight_
RecommendedSecurityUpdate (необязательный) | string | Имя или описание обновления безопасности, предоставляемого поставщиком программного обеспечения для устранения уязвимости. | Обновления безопасности за апрель 2020 г.
RecommendedSecurityUpdateId (необязательный) | string | Идентификатор применимых обновлений или идентификаторов безопасности для соответствующих статей руководства или базы знаний (KB). | 4550961
RegistryPaths  | Строка \[ Array\] | Свидетельство реестра о том, что продукт установлен на устройстве. | [ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]
SoftwareName | string | Имя программного продукта. | chrome
SoftwareVendor | string | Имя поставщика программного обеспечения. | Google
SoftwareVersion | string | Номер версии программного продукта. | 81.0.4044.138
VulnerabilitySeverityLevel  | string | Уровень серьезности, присвоенный уязвимости безопасности на основе показателей CVSS и динамических факторов, влияющих на ландшафт угроз. | Средний

### <a name="16-examples"></a>1.6 Примеры

#### <a name="161-request-example"></a>Пример запроса 1.6.1

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a>1.6.2 Пример ответа

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a>2. Экспорт оценки уязвимостей программного обеспечения (с помощью файлов)

### <a name="21-api-method-description"></a>Описание метода API 2.1

Этот ответ API содержит все данные установленного программного обеспечения на устройство. Возвращает таблицу с записью для каждой уникальной комбинации DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.

#### <a name="212-limitations"></a>2.1.2 Ограничения

Ограничения скорости для этого API : 5 вызовов в минуту и 20 вызовов в час.

### <a name="22-permissions"></a>2.2 Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные сведения, в том числе о выборе разрешений, см. в дополнительных сведениях: [Использование API API](apis-intro.md)конечных точек Microsoft Defender.

Тип разрешения | Разрешение | Имя отображения разрешений
---|---|---
Приложение | Vulnerability.Read.All | \'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'
Делегированные (рабочая или учебная учетная запись) | Vulnerability.Read | \'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'

### <a name="23-url"></a>2.3 URL-адрес

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a>2.4 Параметры

- sasValidHours — количество часов, за которые будут действительны URL-адреса загрузки (максимум 24 часа)

### <a name="25-properties"></a>2.5 Свойства

>[!Note]
>
>- Файлы являются сжатой gzip & в многолинейном формате Json.
>
>- Url-адреса загрузки действительны только в течение 3 часов; в противном случае параметр можно использовать.
>
>- Для максимальной скорости скачивания данных можно убедиться, что вы скачиваете из того же региона Azure, в который находятся ваши данные.
>

>[!Note]
>
>- Каждая запись — это примерно 1KB данных. Это следует учитывать при выборе правильного параметра PageSize для вас.
>
>- Некоторые дополнительные столбцы могут быть возвращены в ответе. Эти столбцы являются временными и могут быть удалены, используйте только задокументированные столбцы.
>

Свойство (ID) | Тип данных | Описание | Пример возвращенного значения
:---|:---|:---|:---
Экспорт файлов | строка \[ массива\]  | Список загрузок URL-адресов для файлов с текущим снимком организации. | [  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]
GeneratedTime | string | Время, за которое был создан экспорт. | 2021-05-20T08:00:00Z

### <a name="26-examples"></a>2.6 Примеры

#### <a name="261-request-example"></a>Пример запроса 2.6.1

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a>2.6.2 Пример ответа

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="3-delta-export-software-vulnerabilities-assessment-json-response"></a>3. Оценка уязвимостей экспортного программного обеспечения Delta (ответ JSON)

### <a name="31-api-method-description"></a>Описание метода API 3.1

Возвращает таблицу с записью для каждой уникальной комбинации DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. API извлекет данные в организации в качестве ответов Json. Ответ paginated, поэтому вы можете использовать поле @odata.nextLink из ответа, чтобы получить следующие результаты. В отличие от полной оценки уязвимостей программного обеспечения (ответ JSON), которая используется для получения полного снимка оценки уязвимостей программного обеспечения вашей организации с помощью устройства, вызов API API ответов JSON экспорта delta используется для получения только изменений, которые произошли между выбранной датой и текущей датой (вызов API delta). Вместо того чтобы получать полный экспорт с большим объемом данных каждый раз, вы получите только конкретные сведения о новых, исправленных и обновленных уязвимостях. Вызов API API API ответов JSON экспорта Delta также можно использовать для вычисления различных KPI, таких как "сколько уязвимостей было исправлено?" или "сколько новых уязвимостей было добавлено в мою организацию?"

>[!NOTE]
>
>Рекомендуется использовать полную оценку уязвимостей экспортируемого программного обеспечения по вызову API устройств по крайней мере один раз в неделю, и этот дополнительный экспорт уязвимостей программного обеспечения изменяется при вызове API устройства (delta) все остальные дни недели.  В отличие от других API ответов JSON, "дельта экспорт" не является полным экспортом. Экспорт дельты включает только изменения, которые произошли между выбранной датой и текущей датой (вызов API дельты).

#### <a name="311-limitations"></a>3.1.1 Ограничения

- Максимальный размер страницы — 200 000.

- Параметр sinceTime имеет максимум 14 дней.

- Ограничения скорости для этого API : 30 вызовов в минуту и 1000 вызовов в час.

### <a name="32-permissions"></a>3.2 Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)

Тип разрешения | Разрешение | Имя отображения разрешений
---|---|---
Приложение | Vulnerability.Read.All | 'Read Threat and Vulnerability Management vulnerability information'
Делегированные (рабочая или учебная учетная запись) | Vulnerability.Read | 'Read Threat and Vulnerability Management vulnerability information'

### <a name="33-url"></a>3.3 URL-адрес

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine 
```

### <a name="34-parameters"></a>3.4 Параметры

- sinceTime (обязательно) — данные между выбранным временем и сегодняшним днем.
- pageSize (по умолчанию = 50 000) — количество результатов в ответе
- $top — количество возвращаемого результата (не возвращает @odata.nextLink и, следовательно, не вытягивает все данные)

### <a name="35-properties"></a>3.5 Свойства

Каждая возвращенная запись содержит все данные из полной оценки уязвимостей программного обеспечения для экспорта по API устройства, а также два дополнительных поля: _**EventTimestamp**_ и _**Status.**_

>[!NOTE]
>- Некоторые дополнительные столбцы могут быть возвращены в ответе. Эти столбцы являются временными и могут быть удалены, поэтому используйте только задокументированные столбцы.
>
>- Свойства, определенные в следующей таблице, перечислены в алфавитном порядке по ID свойства.  При запуске этого API результат не обязательно возвращается в том же порядке, который указан в этой таблице.
<br><br/>

Свойство (ID) | Тип данных | Описание | Пример возвращенного значения
:---|:---|:---|:---
CveId | string | Уникальный идентификатор, присвоенный уязвимости безопасности в системе Common Vulnerabilities and Exposures (CVE). | CVE-2020-15992  
CvssScore | string | Оценка CVSS CVE. | 6.2  
DeviceId | string | Уникальный идентификатор устройства в службе. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1  
DeviceName | string | Полное доменное имя (FQDN) устройства. | johnlaptop.europe.contoso.com  
DiskPaths | Array[string] | Дисковые данные о том, что продукт установлен на устройстве. | [ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]  
EventTimestamp | Строка | Время, когда это событие дельты было найдено. | 2021-01-11T11:06:08.291Z
ExploitabilityLevel | string | Уровень эксплуатации этой уязвимости (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit) | ExploitIsInKit  
FirstSeenTimestamp | string | Впервые CVE этого продукта был замечен на устройстве. | 2020-11-03 10:13:34.8476880  
Id | string | Уникальный идентификатор для записи. | 123ABG55_573AG&mnp!  
LastSeenTimestamp | string | Последний раз CVE был замечен на устройстве. | 2020-11-03 10:13:34.8476880  
OSPlatform | string | Платформа операционной системы, запущенной на устройстве. Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7. Подробные сведения см. в материале tvm supported operating systems and platforms. | Windows10  
RbacGroupName | string | Группа управления доступом на основе ролей (RBAC). Если это устройство не назначено какой-либо группе RBAC, значение будет "Unassigned". Если организация не содержит групп RBAC, значение будет "Нет". | Servers  
RecommendationReference | string | Ссылка на номер рекомендации, связанный с этим программным обеспечением. | va--microsoft--silverlight  
RecommendedSecurityUpdate  | string | Имя или описание обновления безопасности, предоставляемого поставщиком программного обеспечения для устранения уязвимости. | Обновления безопасности за апрель 2020 г.  
RecommendedSecurityUpdateId  | string | Идентификатор применимых обновлений или идентификаторов безопасности для соответствующих статей руководства или базы знаний (KB). | 4550961  
RegistryPaths  | Array[string] | Свидетельство реестра о том, что продукт установлен на устройстве. | [ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]  
SoftwareName | string | Имя программного продукта. | chrome  
SoftwareVendor | string | Имя поставщика программного обеспечения. | Google  
SoftwareVersion | string | Номер версии программного продукта. | 81.0.4044.138  
Состояние | Строка | **Новые**   (для новой уязвимости, введенной на устройстве)  (1) **Исправлено**(если эта уязвимость больше не существует на устройстве, что означает   ее исправление). (2)  **Обновлено**   (если уязвимость на устройстве изменилась. Возможные изменения: оценка CVSS, уровень эксплуатации, уровень серьезности, DiskPaths, RegistryPaths, RecommendedSecurityUpdate). | ИСПРАВЛЕНО
VulnerabilitySeverityLevel | string | Уровень серьезности, присвоенный уязвимости безопасности на основе показателей CVSS и динамических факторов, влияющих на ландшафт угроз. | Средний  

#### <a name="clarifications"></a>Уточнения

- Если программное обеспечение было обновлено с версии 1.0 до версии 2.0 и обе версии будут подвергаться воздействию CVE-A, вы получите 2 отдельных события:  
   1. Исправлено . Исправлена CVE-A в версии 1.0  
   1. New — добавлен CVE-A в версии 2.0

- Если определенная уязвимость (например, CVE-A) впервые была замечена в определенное время (например, 10 января) в программном обеспечении с версией 1.0, а через несколько дней это программное обеспечение было обновлено до версии 2.0, которая также подверглась воздействию того же CVE-A, вы получите эти два разделенных события:  
   1. Исправлено : CVE-X, FirstSeenTimestamp 10 января, версия 1,0.  
   1. New — CVE-X, FirstSeenTimestamp 10 января, версия 2.0.

### <a name="36-examples"></a>3.6 Примеры

#### <a name="361-request-example"></a>Пример запроса 3.6.1

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a>Пример ответа 3.6.2

```json
{ 
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)", 
    "value": [ 
        { 
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__", 
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "87.0.4280.88", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome" 
            ], 
            "lastSeenTimestamp": "2021-01-04 00:29:42", 
            "firstSeenTimestamp": "2020-11-06 03:12:44", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__", 
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "onedrive", 
            "softwareVersion": "20.64.329.3", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe" 
            ], 
            "lastSeenTimestamp": "2020-12-11 19:49:48", 
            "firstSeenTimestamp": "2020-12-07 18:25:47", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-onedrive", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_", 
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "mozilla", 
            "softwareName": "firefox", 
            "softwareVersion": "83.0.0.0", 
            "cveId": "CVE-2020-26971", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "193220", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)" 
            ], 
            "lastSeenTimestamp": "2021-01-05 17:04:30", 
            "firstSeenTimestamp": "2020-05-06 12:42:19", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-mozilla-_-firefox", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__", 
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "project", 
            "softwareVersion": "16.0.13701.20000", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us" 
            ], 
            "lastSeenTimestamp": "2021-01-03 23:38:03", 
            "firstSeenTimestamp": "2019-08-01 22:56:12", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-project", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_", 
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "81.0.4044.138", 
            "cveId": "CVE-2020-16011", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "ADV 200002", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}" 
            ], 
            "lastSeenTimestamp": "2020-12-10 22:45:41", 
            "firstSeenTimestamp": "2020-07-26 02:13:43", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        } 
    ], 
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9" 
} 
```

## <a name="see-also"></a>См. также

- [Методы и свойства экспортной оценки на устройство](get-assessment-methods-properties.md)

- [Экспорт безопасной оценки конфигурации на устройство](get-assessment-secure-config.md)

- [Экспорт оценки инвентаризации программного обеспечения на устройство](get-assessment-software-inventory.md)

Другие связанные

- [Риск на основе угрозы & управление уязвимостями](next-gen-threat-and-vuln-mgt.md)

- [Уязвимости в организации](tvm-weaknesses.md)
