---
title: Функция FileProfile() в advanced hunting for Microsoft 365 Defender
description: Узнайте, как использовать FileProfile() для получения дополнительных сведений о файлах в результатах запроса на расширенный поиск
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function, enrichment
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
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929554"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Функция является функцией обогащения в расширенных охотах, которая добавляет следующие данные в файлы, `FileProfile()` найденные в [](advanced-hunting-overview.md) запросе.

| Столбец | Тип данных | Описание |
|------------|-------------|-------------|
| SHA1 | string | SHA-1 файла, к которому было применено записанное действие |
| SHA256 | string | SHA-256 файла, к который было применено записанное действие |
| MD5 | string | Hash MD5 файла, к который было применено записано действие |
| FileSize | int | Размер файла в ветвях |
| GlobalPrevalence | int | Количество экземпляров сущности, наблюдаемой корпорацией Майкрософт на глобальном уровне |
| GlobalFirstSeen | datetime | Дата и время первого глобального наблюдения сущности корпорацией Майкрософт |
| GlobalLastSeen | datetime | Дата и время последнего наблюдения сущности корпорацией Майкрософт на глобальном уровне |
| Подписыватель | string | Сведения о подписании файла |
| Издатель | string | Сведения о выдаче ЦС |
| SignerHash | string | Уникальное значение hash, определяющие подписывающий |
| IsCertificateValid | boolean | Является ли сертификат, используемый для подписи файла, допустимым |
| IsRootSignerMicrosoft | boolean | Указывает, является ли подписыватель корневого сертификата корпорацией Майкрософт |
| IsExecutable | boolean | Является ли файл переносимым исполняемым файлом (PE) |
| ThreatName | string | Имя обнаружения вредоносных программ или других найденных угроз |
| Publisher | string | Название организации, которая опубликовала файл |
| SoftwareName | string | Название программного продукта |

## <a name="syntax"></a>Синтаксис

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Аргументы

- **x**— столбец ИД файла для использования: , , , , или ; функция `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` использует, если не засекречены
- **y**— ограничение на количество записей для обогащения, 1–1000; функция использует 100, если не закален

## <a name="examples"></a>Примеры

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Проецируемый только столбец SHA1 и его обогащение

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Обогащение первых 500 записей и списков файлов с низким уровнем преобладаний

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Получить дополнительные примеры запросов](advanced-hunting-shared-queries.md)
