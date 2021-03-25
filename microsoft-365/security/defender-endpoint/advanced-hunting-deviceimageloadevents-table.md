---
title: Таблица DeviceImageLoadEvents в продвинутой схеме охоты
description: Узнайте о событиях загрузки DLL в таблице DeviceImageLoadEvents в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, поиск, запрос, телеметрия, ссылка на схему, кусто, таблица, столбец, тип данных, описание, deviceimageloadevents, загрузка DLL, библиотека, изображение файла, ImageLoadEvents
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
ms.technology: mde
ms.openlocfilehash: aad270a101e7052e04e4530e661e0e86c2db70d2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075109"
---
# <a name="deviceimageloadevents"></a>DeviceImageLoadEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Таблица `DeviceImageLoadEvents` в [продвинутой схеме охоты](advanced-hunting-overview.md) содержит сведения о событиях загрузки DLL. Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

Сведения о других таблицах в продвинутой схеме охоты см. в справке [о схеме охоты.](advanced-hunting-schema-reference.md)

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор устройства в службе |
| `DeviceName` | строка | Полное доменное имя (FQDN) устройства |
| `ActionType` | строка | Тип действий, которые вызвали событие |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `FolderPath` | string | Папка, содержащая файл, к котором было применено записано действие |
| `SHA1` | string | SHA-1 файла, к которому было применено записанное действие |
| `MD5` | string | Hash MD5 файла, к который было применено записано действие |
| `InitiatingProcessAccountDomain` | строка | Домен учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessAccountName` | строка | Имя пользователя учетной записи, которая запустила процесс, ответственный за событие |
| `InitiatingProcessAccountSid` | строка | Идентификатор безопасности (SID) учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessIntegrityLevel` | строка | Уровень целостности процесса, который инициировал событие. Windows назначает уровни целостности процессам, основанным на определенных характеристиках, например, если они были запущены из скачивания в Интернете. Эти уровни целостности влияют на разрешения на ресурсы |
| `InitiatingProcessTokenElevation` | строка | Тип маркера, указывающий на наличие или отсутствие высоты привилегий управления пользовательским доступом (UAC), применяемой к процессу, инициировал событие. |
| `InitiatingProcessSHA1` | строка | SHA-1 процесса (файла изображений), который инициировал событие |
| `InitiatingProcessMD5` | строка | AD5 hash of the process (image file), that initiated the event |
| `InitiatingProcessFileName` | строка | Имя процесса, который инициировал событие |
| `InitiatingProcessId` | int | Процесс ID (PID) процесса, который инициировал событие |
| `InitiatingProcessCommandLine` | строка | Командная строка, используемая для запуска процесса, инициированного событием |
| `InitiatingProcessCreationTime` | datetime | Дата и время начала процесса запуска события |
| `InitiatingProcessFolderPath` | строка | Папка, содержащая процесс (файл изображений), который инициировал событие |
| `InitiatingProcessParentId` | int | Process ID (PID) родительского процесса, который породил процесс, ответственный за событие |
| `InitiatingProcessParentFileName` | строка | Имя родительского процесса, который породил процесс, ответственный за событие |
| `InitiatingProcessParentCreationTime` | datetime | Дата и время запуска родительского процесса, ответственного за событие |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец должен использоваться совместно с `DeviceName` `Timestamp` столбцами и |
| `AppGuardContainerId` | строка | Идентификатор виртуализированного контейнера, используемого службой Application Guard для изоляции активности браузера |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-reference.md)
