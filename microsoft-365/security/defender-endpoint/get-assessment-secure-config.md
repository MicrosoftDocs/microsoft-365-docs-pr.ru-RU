---
title: Экспорт безопасной оценки конфигурации на устройство
description: Возвращает запись для каждой уникальной комбинации DeviceId, ConfigurationId.
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
ms.openlocfilehash: fe6a4604852965bdcc563ac0e410ca165bc5a088
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789407"
---
# <a name="export-secure-configuration-assessment-per-device"></a>Экспорт безопасной оценки конфигурации на устройство

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
Возвращает все конфигурации и их состояние на основе каждого устройства.

Существуют различные вызовы API для получения различных типов данных. Так как объем данных может быть большим, их можно получить двумя способами:

- [Экспортная оценка **OData**](#1-export-secure-configuration-assessment-odata)для безопасной конфигурации: API передает все данные в организации в качестве ответов Json, следуя протоколу OData. Этот метод лучше всего используется для _небольших организаций с менее чем 100-K устройствами._ Ответ paginated, поэтому вы можете использовать поле odata.nextLink из ответа, чтобы \@ получить следующие результаты.

- [Экспорт безопасной оценки **конфигурации**](#2-export-secure-configuration-assessment-via-files)с помощью файлов. Это решение API позволяет быстрее и надежнее тянуть большие объемы данных. Поэтому рекомендуется для крупных организаций с более чем 100-K устройствами. Этот API извлекает все данные в организации в качестве файлов загрузки. Ответ содержит URL-адреса для загрузки всех данных из служба хранилища Azure. Этот API позволяет загружать все данные из служба хранилища Azure следующим образом:

  - Позвоните в API, чтобы получить список загружаемых URL-адресов со всеми данными организации.

  - Скачайте все файлы с помощью URL-адресов загрузки и обработать данные, как вам нравится.

Собранные данные (с помощью _OData_ или _с_ помощью файлов) являются текущим снимком текущего состояния и не содержат исторических данных. Чтобы собрать исторические данные, клиенты должны сохранять данные в собственных хранилищах данных.

> [!Note]
>
> Если не указано обратное, все **** перечисленные методы оценки экспорта являются полным экспортом и по устройству **_(также_** именуемой как **_на устройстве)._**

## <a name="1-export-secure-configuration-assessment-odata"></a>1. Оценка безопасной конфигурации экспорта (OData)

### <a name="11-api-method-description"></a>Описание метода API 1.1

Этот ответ API содержит оценку безопасной конфигурации на выставленных устройствах и возвращает запись для каждой уникальной комбинации DeviceId, ConfigurationId.

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
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a>1.4 Параметры

- по умолчанию pageSize \( = 50 000 \) — количество результатов в ответе

- \$верхняя часть — количество возвращаемого результата не \( возвращает odata.nextLink и, следовательно, не вытягивает \@ все данные\)

### <a name="15-properties"></a>1.5 Свойства

>[!Note]
>
>- Свойства, определенные в следующей таблице, перечислены в алфавитном порядке по ID свойства.  При запуске этого API результат не обязательно возвращается в том же порядке, который указан в этой таблице.
>
>- Некоторые дополнительные столбцы могут быть возвращены в ответе. Эти столбцы являются временными и могут быть удалены, используйте только задокументированные столбцы.
>

Свойство (ID) | Тип данных | Описание | Пример возвращенного значения
:---|:---|:---|:---
ConfigurationCategory | string | Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности | Элементы управления безопасностью
ConfigurationId | string | Уникальный идентификатор определенной настройки | scid-10000
ConfigurationImpact | string | Оценка влияния настройки на общую оценку конфигурации (1–10) | 9 
ConfigurationName | string | Отображение названия настройки | Подключение устройств к Microsoft Defender для конечной точки
ConfigurationSubcategory | string | Подкатегория или подгруппа, к которой относится настройка. Во многих случаях здесь описываются конкретные возможности или функции. | Бортовых устройств
DeviceId | Строка | Уникальный идентификатор устройства в службе. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | Строка | Полное доменное имя (FQDN) устройства. | johnlaptop.europe.contoso.com
IsApplicable | bool | Указывает, применима ли конфигурация или политика | true
IsCompliant | bool | Указывает, правильно ли настроена конфигурация или политика | false
IsExpectedUserImpact | bool | Указывает, будет ли влияние пользователя, если конфигурация будет применена | true
OSPlatform | Строка | Платформа операционной системы, запущенной на устройстве. Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7. Подробные сведения см. в материале tvm supported operating systems and platforms. | Windows10
RbacGroupName | Строка | Группа управления доступом на основе ролей (RBAC). Если это устройство не назначено какой-либо группе RBAC, значение будет "Unassigned". Если организация не содержит групп RBAC, значение будет "Нет". | Servers
RecommendationReference | Строка | Ссылка на номер рекомендации, связанный с этим программным обеспечением. | sca-_-scid-20000
Timestamp | Строка | Последний раз, когда конфигурация была замечена на устройстве | 2020-11-03 10:13:34.8476880

### <a name="16-examples"></a>1.6 Примеры

#### <a name="161-request-example"></a>Пример запроса 1.6.1

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a>1.6.2 Пример ответа

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a>2. Экспорт безопасной оценки конфигурации (с помощью файлов)

### <a name="21-api-method-description"></a>Описание метода API 2.1

Этот ответ API содержит оценку безопасной конфигурации на выставленных устройствах и возвращает запись для каждой уникальной комбинации DeviceId, ConfigurationId.

#### <a name="212-limitations"></a>2.1.2 Ограничения

Ограничения скорости для этого API : 5 вызовов в минуту и 20 вызовов в час.

### <a name="22-permissions"></a>2.2 Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)

Тип разрешения | Разрешение | Имя отображения разрешений
---|---|---
Приложение | Vulnerability.Read.All | \'Сведения об уязвимости контроль угроз и уязвимостей "контроль угроз и уязвимостей"\'
Делегированные (рабочая или учебная учетная запись) | Vulnerability.Read | \'Сведения об уязвимости контроль угроз и уязвимостей "контроль угроз и уязвимостей"\'

### <a name="23-url"></a>2.3 URL-адрес

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a>Parameters

- sasValidHours — количество часов, на которые будут действительны URL-адреса загрузки (не более 24 часов).

### <a name="25-properties"></a>2.5 Свойства

>[!Note]
>
>- Файлы являются сжатой gzip & в многолинейном формате Json.
>
>- Url-адреса загрузки действительны только в течение 3 часов; в противном случае параметр можно использовать.
>
>- Для максимальной скорости скачивания данных можно убедиться, что вы скачиваете из того же региона Azure, в котором находятся ваши данные.
>
Свойство (ID) | Тип данных | Описание | Пример возвращенного значения
:---|:---|:---|:---
Экспорт файлов | строка \[ массива\] | Список загрузок URL-адресов для файлов с текущим снимком организации | [  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]
GeneratedTime | Строка | Время, за которое был создан экспорт. | 2021-05-20T08:00:00Z ]

### <a name="26-examples"></a>2.6 Примеры

#### <a name="261-request-example"></a>Пример запроса 2.6.1

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a>2.6.2 Пример ответа

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Дополнительные материалы

- [Методы и свойства экспортной оценки на устройство](get-assessment-methods-properties.md)

- [Экспорт оценки инвентаризации программного обеспечения на устройство](get-assessment-software-inventory.md)

- [Экспорт оценки уязвимостей программного обеспечения на устройство](get-assessment-software-vulnerabilities.md)

Другие связанные

- [Риск на основе угрозы & управление уязвимостями](next-gen-threat-and-vuln-mgt.md)

- [Уязвимости в организации](tvm-weaknesses.md)
