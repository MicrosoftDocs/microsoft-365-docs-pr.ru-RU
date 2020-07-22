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
ms.openlocfilehash: 19437caf4f3b0dcb6eb6ccad81d1ed3917df7996
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204915"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

**Область применения:**
- Защита от угроз (Майкрософт)

`IdentityLogonEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о действиях проверки подлинности, выполненных в локальной службе Active Directory, захваченных службой Azure ATP и действиями проверки подлинности, связанными со службами Microsoft Online, записанными в Microsoft Cloud App Security. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!NOTE]
>В этой таблице рассматриваются действия входа в систему Azure Active Directory (AD), отслеживаемые Cloud App Security, а именно интерактивные входы и действия проверки подлинности с помощью ActiveSync и других устаревших протоколов. Неинтерактивные входы, недоступные в этой таблице, можно просматривать в журнале аудита Azure AD. [Дополнительные сведения о подключении Cloud App Security к Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действия, вызвавшего событие |
| `LogonType` | string | Тип сеанса входа в систему, в частности:<br><br> - **Интерактивный** пользователь физически взаимодействует с компьютером с помощью локальной клавиатуры и экрана<br><br> - **Удаленный интерактивный вход (RDP)** — пользователь взаимодействует с компьютером удаленно с помощью удаленного рабочего стола, служб терминалов, удаленного помощника или других клиентов RDP<br><br> - **Network** — сеанс, запущенный при доступе к компьютеру с помощью PsExec или при доступе к общим ресурсам на компьютере, например принтерам и общим папкам.<br><br> - **Пакетный** сеанс, инициированный запланированными задачами<br><br> - **Служба** — сеанс, инициированный службами при запуске |
| `Application` | string | Приложение, которое выполнило записанное действие |
| `Protocol` | string | Используемый сетевой протокол |
| `FailureReason` | string | Сведения о том, почему не удалось выполнить записанное действие |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountDomain` | string | Домен учетной записи |
| `AccountUpn` | string | Имя участника-пользователя (UPN) учетной записи |
| `AccountSid` | string | Идентификатор безопасности (SID) учетной записи |
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure AD |
| `AccountDisplayName` | string | Имя пользователя учетной записи, отображаемое в адресной книге. Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия. |
| `DeviceName` | string | Полное доменное имя (FQDN) устройства |
| `DeviceType` | string | Тип устройства |
| `OSPlatform` | string | Платформа операционной системы, используемой на компьютере. Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7. |
| `IPAddress` | string | IP-адрес, назначенный конечной точке и используемый во время связанных сетевых коммуникаций |
| `DestinationDeviceName` | string | Имя устройства, на котором работает серверное приложение, которое обработало записанное действие |
| `DestinationIPAddress` | string | IP-адрес устройства, на котором запущено серверное приложение, которое обработало записанное действие |
| `TargetDeviceName` | string | Полное доменное имя (FQDN) устройства, к которому было применено записанное действие |
| `TargetAccountDisplayName` | string | Отображаемое имя учетной записи, к которой было применено записанное действие |
| `Location` | string | Город, страна или другое географическое расположение, связанное с событием |
| `Isp` | string | Поставщик услуг Интернета (ISP), связанный с IP-адресом конечной точки. |
| `ReportId` | long | Уникальный идентификатор для события |
| `AdditionalFields` | string | Дополнительные сведения о сущности или событии |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)