---
title: Таблица IdentityLogonEvents в продвинутой схеме охоты
description: Узнайте о событиях проверки подлинности, записанных Active Directory в таблице IdentityLogonEvents в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, защита от угроз Майкрософт, Microsoft 365, mtp, m365, поиск, запрос, телеметрия, ссылка схемы, kusto, таблица, столбец, тип данных, описание, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, identitys
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 556e408eb176a2c215252379d539ec82b67e85cc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076358"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица в схеме расширенных схем охоты содержит сведения о действиях проверки подлинности, сделанных с помощью локального Active Directory, захваченного Microsoft Defender для удостоверений и действий проверки подлинности, связанных с сетевыми службами Microsoft, захваченными службами Microsoft `IdentityLogonEvents` Cloud App Security. [](advanced-hunting-overview.md) Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!TIP]
> Подробные сведения о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в центре безопасности.

>[!NOTE]
>В этой таблице охватываются действия логотипа Azure Active Directory (AD), отслеживаемые службой безопасности облачных приложений, в частности интерактивные входы и действия по проверке подлинности с помощью ActiveSync и других устаревших протоколов. Не интерактивные логотипы, недоступные в этой таблице, можно просмотреть в журнале аудита Azure AD. [Дополнительные информацию о подключении безопасности облачных приложений к Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действий, которые вызвали событие. Подробные [сведения см. в](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) справке по схеме на портале |
| `LogonType` | строка | Тип сеанса логотипа, в частности:<br><br> - **Interactive** — пользователь физически взаимодействует с машиной с помощью локальной клавиатуры и экрана<br><br> - Логотипы удаленного интерактивного **(RDP)** — пользователь взаимодействует с машиной удаленно с помощью удаленного рабочего стола, служб терминалов, удаленной помощи или других клиентов RDP.<br><br> - **Network** - Сеанс, инициированный при доступе к машине с помощью PsExec или при доступе к общим ресурсам на машине, таким как принтеры и общие папки.<br><br> - **Batch** — Сеанс, инициированный запланированными задачами<br><br> - **Служба** — сеанс, инициированный службами при запуске |
| `Application` | строка | Приложение, которое выполнило записанную акцию |
| `Protocol` | строка | Используемый сетевой протокол |
| `FailureReason` | строка | Сведения, объясняющие причины сбой записанного действия |
| `AccountName` | строка | Имя пользователя учетной записи |
| `AccountDomain` | строка | Домен учетной записи |
| `AccountUpn` | строка | Основное имя пользователя (UPN) учетной записи |
| `AccountSid` | строка | Идентификатор безопасности (SID) учетной записи |
| `AccountObjectId` | строка | Уникальный идентификатор учетной записи в Azure AD |
| `AccountDisplayName` | строка | Имя пользователя учетной записи, отображаемого в адресной книге. Как правило, сочетание данной или имени, среднего посвящения и фамилии или фамилии. |
| `DeviceName` | строка | Полное доменное имя (FQDN) устройства |
| `DeviceType` | строка | Тип устройства |
| `OSPlatform` | string | Платформа операционной системы, используемой на компьютере. Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7. |
| `IPAddress` | string | IP-адрес, присвоенный конечной точке и используемый во время связанных сетевых коммуникаций |
| `Port` | строка | Порт TCP, используемый во время связи |
| `DestinationDeviceName` | строка | Имя устройства под управлением серверного приложения, обрабатываемого записанным действием |
| `DestinationIPAddress` | строка | IP-адрес устройства под управлением серверного приложения, обработав записанное действие |
| `DestinationPort` | строка | Порт назначения связанных сетевых коммуникаций |
| `TargetDeviceName` | строка | Полное доменное имя (FQDN) устройства, на которое было применено записанное действие |
| `TargetAccountDisplayName` | строка | Отображение имени учетной записи, к которую было применено записанное действие |
| `Location` | строка | Город, страна или другое географическое расположение, связанное с событием |
| `Isp` | строка | Поставщик интернет-услуг (ISP), связанный с IP-адресом конечной точки |
| `ReportId` | long | Уникальный идентификатор события |
| `AdditionalFields` | строка | Дополнительные сведения об объекте или событии |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)