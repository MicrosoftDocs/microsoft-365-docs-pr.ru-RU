---
title: DeviceFileCertificateInfo table in the advanced hunting schema
description: Сведения о подписании файлов в таблице DeviceFileCertificateInfo в продвинутой схеме охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, digital signature, certificate, file signing, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1f894f3fc8cff2113004ff9c9e34ec2ca0144799
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023217"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender
- Microsoft Defender для конечной точки

Таблица `DeviceFileCertificateInfo` в [продвинутой схеме охоты](advanced-hunting-overview.md) содержит сведения о сертификатах подписи файлов. В этой таблице используются данные, полученные в ходе регулярной проверки сертификатов в файлах конечных точек.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `DeviceName` | string | Полное доменное имя компьютера |
| `SHA1` | string | SHA-1 файла, к которому было применено записанное действие |
| `IsSigned` | boolean | Указывает, подписан ли файл |
| `SignatureType` | Строка | Указывает, была ли информация подписи прочитана как встроенное содержимое в самом файле или считывается из внешнего файла каталога. |
| `Signer` | Строка | Сведения о подписывщике файла |
| `SignerHash` | Строка | Уникальное значение hash, определяющие подписавщика |
| `Issuer` | Строка | Сведения о полномочиях по выдаче сертификатов (CA) |
| `IssuerHash` | Строка | Уникальное значение hash identifying issuing certificate authority (CA) |
| `CertificateSerialNumber` | Строка | Идентификатор сертификата, который является уникальным для органа по выдаче сертификатов (CA) |
| `CrlDistributionPointUrls` | Строка |  Массив JSON с перечислением URL-адресов сетевых акций, содержащих сертификаты и списки отзывов сертификатов (CRLs) |
| `CertificateCreationTime` | datetime | Дата и время создания сертификата |
| `CertificateExpirationTime` | datetime | Дата и время истечения срока действия сертификата |
| `CertificateCountersignatureTime` | datetime | Дата и время, когда сертификат был подписан |
| `IsTrusted` | boolean | Указывает, доверяют ли файлу результаты функции WinVerifyTrust, которая проверяет неизвестные сведения корневого сертификата, недействительные подписи, отозванные сертификаты и другие сомнительные атрибуты. |
| `IsRootSignerMicrosoft` | boolean | Указывает, является ли подписатель корневого сертификата Корпорацией Майкрософт |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp. | 

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)
