---
title: Таблица IdentityLogonEvents в схеме advanced hunting
description: Узнайте о событиях проверки подлинности, записанных Active Directory в таблице IdentityLogonEvents схемы advanced hunting
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, identities
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
ms.openlocfilehash: 1df1295b3386b94e3737c53ac8226c719c8bfa08
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929926"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица в схеме advanced hunting содержит сведения о действиях проверки подлинности, совершенных с помощью локальной службы Active Directory, захваченной Microsoft Defender для идентификации и действий проверки подлинности, связанных с веб-службами Майкрософт, захваченными `IdentityLogonEvents` Microsoft Cloud App Security. [](advanced-hunting-overview.md) Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!TIP]
> Для получения подробных сведений о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в Центре безопасности. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

>[!NOTE]
>В этой таблице освещаются действия по входу в Azure Active Directory (AD), отслеживаемые Cloud App Security, в частности интерактивные входы и действия проверки подлинности с помощью ActiveSync и других устаревших протоколов. Неинструктивные входы, недоступные в этой таблице, можно просмотреть в журнале аудита Azure AD. [Узнайте больше о подключении Cloud App Security к Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действия, которое вызвало событие. Подробные сведения см. в справке [по схеме портала](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `LogonType` | string | Тип сеанса для работы с логотипом, в частности:<br><br> - **Интерактивный** — пользователь физически взаимодействует с компьютером с помощью локальной клавиатуры и экрана<br><br> - **Удаленные интерактивные учетные** записи для работы с пользователями ( RDP) — пользователь удаленно взаимодействует с компьютером с помощью удаленного рабочего стола, служб терминалов, удаленной помощи или других клиентов RDP.<br><br> - **Сеть** — сеанс, инициированный при доступе к компьютеру с помощью PsExec или при доступе к общим ресурсам на компьютере, таким как принтеры и общие папки<br><br> - **Batch —** сеанс, инициированный запланированными задачами<br><br> - **Служба** — сеанс, инициированный службами при их запуске |
| `Application` | string | Приложение, которое выполнило записанную действие |
| `Protocol` | string | Используемый сетевой протокол |
| `FailureReason` | string | Сведения о причине сбой записанного действия |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountDomain` | string | Домен учетной записи |
| `AccountUpn` | string | Имя пользователя-пользователя (UPN) учетной записи |
| `AccountSid` | string | Идентификатор безопасности (SID) учетной записи |
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure AD |
| `AccountDisplayName` | string | Имя пользователя учетной записи, отображаемой в адресной книге. Обычно сочетание заданного или имени, инициации по середине и фамилии или фамилии. |
| `DeviceName` | string | Полное доменное имя устройства |
| `DeviceType` | string | Тип устройства |
| `OSPlatform` | string | Платформа операционной системы, используемой на компьютере. Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7. |
| `IPAddress` | string | IP-адрес, присвоенный конечной точке и используемый при связанных сетевых коммуникациях |
| `DestinationDeviceName` | string | Имя устройства, на которое запущено серверное приложение, обрабатывающее записанное действие |
| `DestinationIPAddress` | string | IP-адрес устройства, на которое запущено серверное приложение, обрабатывающее записанное действие |
| `TargetDeviceName` | string | Полное доменное имя (FQDN) устройства, к которого было применено записанное действие |
| `TargetAccountDisplayName` | string | Отображаемого имени учетной записи, к которую было применено записанное действие |
| `Location` | string | Город, страна или другое географическое расположение, связанное с событием |
| `Isp` | string | Поставщик услуг Интернета, связанный с IP-адресом конечной точки |
| `ReportId` | long | Уникальный идентификатор события |
| `AdditionalFields` | string | Дополнительные сведения об объекте или событии |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
