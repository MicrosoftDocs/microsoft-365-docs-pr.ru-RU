---
title: Функция FileProfile() в продвинутой охоте на Microsoft Defender для конечной точки
description: Узнайте, как использовать FileProfile() для обогащения сведений о файлах в результатах запроса на расширенные запросы на охоту
keywords: передовая охота, охота на угрозы, поиск киберугроз, mdatp, Microsoft Defender ATP, Microsoft Defender для endpoint, Защитник Windows, Защитник Windows ATP, Защитник Windows Advanced Threat Protection, search, query, telemetry, schema reference, kusto, FileProfile, fileProfile, file profile, function, enrichment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 668b3fe503268c46e4a1313f0c4cfb8a6a3dd602
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076006"
---
# <a name="fileprofile"></a>FileProfile()

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

Функция является функцией обогащения в продвинутой охоте, которая добавляет следующие данные в `FileProfile()` файлы, найденные в [](advanced-hunting-overview.md) запросе.

Column | Тип данных | Описание
-|-|-
SHA1 | string | SHA-1 файла, к которому было применено записанное действие
SHA256 | строка | SHA-256 файла, к который было применено записанное действие
MD5 | строка | Hash MD5 файла, к который было применено записано действие
FileSize | int | Размер файла в bytes
GlobalPrevalence | int | Количество экземпляров объекта, наблюдаемого Корпорацией Майкрософт во всем мире
GlobalFirstSeen | datetime | Дата и время, когда сущность впервые была замечена Корпорацией Майкрософт во всем мире
GlobalLastSeen | datetime | Дата и время, когда объект в последний раз наблюдался Корпорацией Майкрософт во всем мире
Signer | строка | Сведения о подписывщике файла
Издатель | строка | Сведения о полномочиях по выдаче сертификатов (CA)
SignerHash | строка | Уникальное значение hash, определяющие подписавщика
IsCertificateValid | boolean | Допустим ли сертификат, используемый для подписи файла
IsRootSignerMicrosoft | boolean | Указывает, является ли подписатель корневого сертификата Корпорацией Майкрософт
IsExecutable | boolean | Является ли файл портативным исполняемым (PE) файлом
ThreatName | строка | Имя обнаружения любых найденных вредоносных программ или других угроз
Publisher | строка | Имя организации, которая опубликовала файл
SoftwareName | string | Название программного продукта

## <a name="syntax"></a>Синтаксис

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Аргументы

- **x** — столбец ID файла для использования: , , или ; использование `SHA1` `SHA256` функции, если `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` неустановлено
- **y** — ограничение количества записей для обогащения, 1-1000; функция использует 100, если неустановлено

## <a name="examples"></a>Примеры

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Проект только столбца SHA1 и его обогащение

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Обогащение первых 500 записей и списков файлов с низкой распространенностью

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a>Статьи по теме

- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-reference.md)
