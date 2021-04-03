---
title: Таблица DeviceInfo в продвинутой схеме охоты
description: Сведения об ОС, имени компьютера и других сведениях об устройстве в таблице DeviceInfo в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, поиск, запрос, телеметрия, справочная схема, кусто, таблица, столбец, тип данных, описание, deviceinfo, устройство, ОС, платформа, пользователи, DeviceInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e6a11af94a5d2b2099d14b660cf65c846532ebd1
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500836"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Таблица в продвинутой схеме охоты содержит сведения о устройствах в организации, включая их версию ОС, активных пользователей `DeviceInfo` и имя компьютера. [](advanced-hunting-overview.md) Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

Сведения о других таблицах в продвинутой схеме охоты см. в справке [о схеме охоты.](advanced-hunting-schema-reference.md)

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор устройства в службе |
| `DeviceName` | string | Полное доменное имя (FQDN) устройства |
| `ClientVersion` | string | Версия агента конечной точки или датчика, запущенного на устройстве |
| `PublicIP` | string | Общедоступный IP-адрес, используемый на бортовом устройстве для подключения к службе Defender для конечных точек. Это может быть IP-адрес самого устройства, устройство NAT или прокси-сервер |
| `OSArchitecture` | string | Архитектура операционной системы, запущенной на устройстве |
| `OSPlatform` | string | Платформа операционной системы, запущенной на устройстве. Это указывает на определенные операционные системы, в том числе варианты в одной семье, например Windows 10 и Windows 7. |
| `OSBuild` | string | Сборка версии операционной системы, запущенной на устройстве |
| `IsAzureADJoined` | boolean | Индикатор Boolean о том, присоединяется ли устройство к Azure Active Directory |
| `LoggedOnUsers` | string | Список всех пользователей, зарегистрированных на устройстве во время события в формате массива JSON |
| `RegistryDeviceTag` | string | Тег устройства, добавленный в реестр |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp. |
| `OSVersion` | string | Версия операционной системы, запущенной на устройстве |
| `MachineGroup` | string | Машинная группа машины. Эта группа используется управлением доступом на основе ролей для определения доступа к машине |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-reference.md)
