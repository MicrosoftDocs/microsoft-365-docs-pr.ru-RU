---
title: Таблица DeviceFileCertificateInfo в схеме advanced hunting
description: Сведения о подписи файлов в таблице DeviceFileCertificateInfo схемы advanced hunting
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, digital signature, certificate, file signing, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e35e8e86f6814a5f90a7921f71ccab7247fcc1bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931318"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица `DeviceFileCertificateInfo` в схеме [advanced hunting](advanced-hunting-overview.md) содержит сведения о сертификатах подписи файлов. В этой таблице используются данные, полученные из действий по проверке сертификатов, которые регулярно выполняются с файлами на конечных точках.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `DeviceName` | string | Полное доменное имя компьютера |
| `SHA1` | string | SHA-1 файла, к которому было применено записанное действие |
| `IsSigned` | boolean | Указывает, подписан ли файл |
| `SignatureType` | string | Указывает, считылась ли информация о подписи как встроенное содержимое в самом файле или из файла внешнего каталога |
| `Signer` | string | Сведения о подписании файла |
| `SignerHash` | string | Уникальное значение hash, определяющие подписывающий |
| `Issuer` | string | Сведения о выдавливом ЦС |
| `IssuerHash` | string | Уникальное значение hash, определяющие выдавающий ЦС |
| `CertificateSerialNumber` | string | Идентификатор сертификата, уникального для выдавливания сертификата (ЦС) |
| `CrlDistributionPointUrls` | string |  Массив JSON с URL-адресами сетевых сетей, которые содержат сертификаты и списки отзыва сертификатов (CRLs) |
| `CertificateCreationTime` | datetime | Дата и время создания сертификата |
| `CertificateExpirationTime` | datetime | Дата и время истечения срока действия сертификата |
| `CertificateCountersignatureTime` | datetime | Дата и время, когда сертификат был подписан |
| `IsTrusted` | boolean | Указывает, является ли файл доверенным на основе результатов функции WinVerifyTrust, которая проверяет неизвестные сведения корневого сертификата, недопустимые подписи, отозванные сертификаты и другие сомнительные атрибуты |
| `IsRootSignerMicrosoft` | boolean | Указывает, является ли подписыватель корневого сертификата корпорацией Майкрософт |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец необходимо использовать вместе со столбцами DeviceName и Timestamp. | 

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
