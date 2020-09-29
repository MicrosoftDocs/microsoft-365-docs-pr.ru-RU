---
title: Таблица идентитидиректоревентс в схеме расширенного поискового окна
description: Сведения о контроллере домена и событиях Active Directory в таблице Идентитидиректоревентс расширенной схемы подпоиска
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Идентитидиректоревентс, контроллер домена, Active Directory, Azure ATP, удостоверения
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
ms.openlocfilehash: 118d96b797e9d46b4a9912f919cafbba680a9609
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "48305286"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защита от угроз (Майкрософт)

`IdentityDirectoryEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит события, связанные с локальным контроллером домена, на котором работает Active Directory (AD). В этой таблице записаны различные события, связанные с удостоверениями, такие как изменение паролей, срок действия пароля и имя участника-пользователя (UPN). Он также захватывает системные события на контроллере домена, например планирование задач и действий PowerShell. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!TIP]
> Для получения подробных сведений о типах событий ( `ActionType` значений), поддерживаемых таблицей, используйте [встроенную справочную](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) информацию о схеме, доступную в центре обеспечения безопасности.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действия, вызвавшего событие. Дополнительные сведения см. [в справочнике по схемам на портале](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | string | Приложение, которое выполнило записанное действие |
| `TargetAccountUpn` | string | Имя участника-пользователя (UPN) учетной записи, к которой было применено записанное действие |
| `TargetAccountDisplayName` | string | Отображаемое имя учетной записи, к которой было применено записанное действие |
| `TargetDeviceName` | string | Полное доменное имя (FQDN) устройства, к которому было применено записанное действие |
| `DestinationDeviceName` | string | Имя устройства, на котором работает серверное приложение, которое обработало записанное действие |
| `DestinationIPAddress` | string | IP-адрес устройства, на котором запущено серверное приложение, которое обработало записанное действие |
| `DestinationPort` | string | Конечный порт действия |
| `Protocol` | string | Протокол, используемый при обмене данными |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountDomain` | string | Домен учетной записи |
| `AccountUpn` | string | Имя участника-пользователя (UPN) учетной записи |
| `AccountSid` | string | Идентификатор безопасности (SID) учетной записи |
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure Active Directory |
| `AccountDisplayName` | string | Имя пользователя учетной записи, отображаемое в адресной книге. Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия. |
| `DeviceName` | string | Полное доменное имя (FQDN) устройства |
| `IPAddress` | string | IP-адрес, назначенный устройству при обмене данными |
| `Port` | string | TCP-порт, используемый при обмене данными |
| `Location` | string | Город, страна или другое географическое расположение, связанное с событием |
| `ISP` | string | Поставщик услуг Интернета, связанный с IP-адресом |
| `ReportId` | long | Уникальный идентификатор для события |
| `AdditionalFields` | string | Дополнительные сведения о сущности или событии |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
