---
title: Таблица идентитилогоневентс в схеме расширенного поискового окна
description: Сведения о событиях проверки подлинности, регистрируемых Active Directory в таблице Идентитилогоневентс расширенной схемы подсчета
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Идентитилогоневентс, Azure AD, Active Directory, Azure ATP, удостоверения
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
ms.openlocfilehash: 2116d8f6f1006f5acf9d468006fa07a04e13087b
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2020
ms.locfileid: "45046032"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

**Область применения:**
- Защита от угроз (Майкрософт)

`IdentityLogonEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о действиях проверки подлинности, выполненных в локальной службе Active Directory, захваченных службой Azure ATP и действиями проверки подлинности, связанными со службами Microsoft Online, записанными в Microsoft Cloud App Security. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действия, вызвавшего событие |
| `LogonType` | string | Тип сеанса входа в систему, в частности:<br><br> - **Интерактивный** пользователь физически взаимодействует с компьютером с помощью локальной клавиатуры и экрана<br><br> - **Удаленный интерактивный вход (RDP)** — пользователь взаимодействует с компьютером удаленно с помощью удаленного рабочего стола, служб терминалов, удаленного помощника или других клиентов RDP<br><br> - **Network** — сеанс, запущенный при доступе к компьютеру с помощью PsExec или при доступе к общим ресурсам на компьютере, например принтерам и общим папкам.<br><br> - **Пакетный** сеанс, инициированный запланированными задачами<br><br> - **Служба** — сеанс, инициированный службами при запуске |
| `Application` | string | Приложение, которое выполнило записанное действие |
| `Protocol` | string | Протокол, используемый при обмене данными |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountDomain` | string | Домен учетной записи |
| `AccountUpn` | string | Имя участника-пользователя (UPN) учетной записи |
| `AccountSid` | string | Идентификатор безопасности (SID) учетной записи |
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure AD |
| `AccountDisplayName` | string | Имя пользователя учетной записи, отображаемое в адресной книге. Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия. |
| `DeviceName` | string | Полное доменное имя компьютера |
| `DeviceType` | string | Тип устройства |
| `OSPlatform` | string | Платформа операционной системы, используемой на компьютере. Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7. |
| `IPAddress` | string | IP-адрес, назначенный конечной точке и используемый во время связанных сетевых коммуникаций |
| `Location` | string | Город, страна или другое географическое расположение, связанное с событием |
| `Isp` | string | Поставщик услуг Интернета (ISP), связанный с IP-адресом конечной точки. |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
