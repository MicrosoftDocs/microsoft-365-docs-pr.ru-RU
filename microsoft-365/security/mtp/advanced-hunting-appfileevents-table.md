---
title: Таблица аппфиливентс в схеме расширенного поискового окна
description: Сведения о событиях, связанных с файлами, связанными с облачными приложениями и службами, в таблице Аппфиливентс расширенной схемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Аппфиливентс, безопасность облачных приложений, МКАС
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: da3b331d4f607aa0961e275db9444aadbec4fcf2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899343"
---
# <a name="appfileevents"></a>AppFileEvents

**Область применения:**
- Защита от угроз (Майкрософт)

`AppFileEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о действиях, связанных с файлами, в облачных приложениях и службах, отслеживаемых Microsoft Cloud App Security. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действия, вызвавшего событие |
| `Application` | string | Приложение, которое выполнило записанное действие |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `FolderPath` | string | Папка, содержащая файл, к которому было применено записанное действие |
| `PreviousFileName` | string | Исходное имя файла, переименованного в результате действия |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountDomain` | string | Домен учетной записи |
| `AccountUpn` | string | Имя участника-пользователя (UPN) учетной записи |
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure AD |
| `AccountDisplayName` | string | Имя пользователя учетной записи, отображаемое в адресной книге. Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия. |
| `IPAddress` | string | IP-адрес, назначенный конечной точке и используемый во время связанных сетевых коммуникаций |
| `Location` | string | Город, страна или другое географическое расположение, связанное с событием |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
