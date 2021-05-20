---
title: Таблица IdentityLogonEvents в передовой схеме охоты
description: Узнайте о событиях аутентификации, записанных Active Directory, в таблице IdentityLogonEvents передовой схемы охоты
keywords: продвинутая охота, охота за угрозами, охота на киберугроза, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, схема ссылка, кусто, таблица, колонка, тип данных, описание, IdentityLogonEvents, Azure AD, Active Directory, Microsoft Defender for Identity, идентификаторы
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3cd0c0f371c73a515704791e829be7266d400580
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572757"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица `IdentityLogonEvents` в расширенной [схеме охоты содержит](advanced-hunting-overview.md) информацию о действиях по аутентификации, сделанных через ваш активный каталог, захваченный Microsoft Defender для идентификации и аутентификации деятельности, связанные с онлайн-сервисами Майкрософт, захваченными Microsoft Cloud App Security. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!TIP]
> Для получения подробной информации о типах событий `ActionType` (значениях), поддерживаемых таблицей, используйте встроенную схему, доступную в центре безопасности.

>[!NOTE]
>Эта таблица охватывает Azure Active Directory (Azure AD) логотипные действия, отслеживаемые Cloud App Security, в частности интерактивные ва-позиции и действия аутентификации с использованием ActiveSync и других устаревших протоколов. Не интерактивные логоны, недоступные в этой таблице, можно посмотреть в журнале аудита Azure AD. [Узнайте больше о подключении Cloud App Security к Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действия, который вызвал событие. [Подробнее о схеме на портале](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | Строка | Приложение, выихавное действие |
| `LogonType` | Строка | Тип логона сессии, в частности:<br><br> - **Интерактивный** - Пользователь физически взаимодействует с машиной с помощью локальной клавиатуры и экрана<br><br> - **Удаленные интерактивные (RDP) логотипы** - Пользователь взаимодействует с машиной удаленно с помощью удаленного рабочего стола, терминальных услуг, удаленной помощи или других клиентов RDP<br><br> - **Сеть** - Сеанс, начатый при доступе к машине с помощью PsExec или при доступе к общим ресурсам на машине, таким как принтеры и общие папки<br><br> - **Пакет** - Сессия, инициированная запланированными задачами<br><br> - **Сервис** - Сессия, инициированная службами по мере их запуска |
| `Protocol` | Строка | Используемый сетевой протокол |
| `FailureReason` | Строка | Информация, объясняющая, почему записанное действие не удалось |
| `AccountName` | Строка | Имя пользователя учетной записи |
| `AccountDomain` | Строка | Домен учетной записи |
| `AccountUpn` | Строка | Основное имя пользователя (UPN) учетной записи |
| `AccountSid` | Строка | Идентификатор безопасности (SID) учетной записи |
| `AccountObjectId` | Строка | Уникальный идентификатор учетной записи в Azure AD |
| `AccountDisplayName` | Строка | Имя пользователя учетной записи, отображаемое в адресной книге. Обычно сочетание данного или имени, среднего посвящения, фамилии или фамилии. |
| `DeviceName` | Строка | Полностью квалифицированное доменное имя (F'D) устройства |
| `DeviceType` | Строка | Тип устройства |
| `OSPlatform` | string | Платформа операционной системы, используемой на компьютере. Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7. |
| `IPAddress` | string | IP-адрес, присвоенный конечной точке и используемый во время связанных сетевых коммуникаций |
| `Port` | Строка | Порт TCP, используемый во время связи |
| `DestinationDeviceName` | Строка | Название устройства, запущенного серверным приложением, обрабатывающее записанное действие |
| `DestinationIPAddress` | Строка | IP-адрес устройства, запущенного серверным приложением, обрабатывающее записанное действие |
| `DestinationPort` | Строка | Пункт назначения порта связи, связанной с сетью |
| `TargetDeviceName` | Строка | Полностью квалифицированное доменное имя (F'D) устройства, к |
| `TargetAccountDisplayName` | Строка | Отображение имени учетной записи, к которую было применено записанное действие |
| `Location` | Строка | Город, страна или другое географическое положение, связанное с событием |
| `Isp` | Строка | Поставщик услуг Интернета (ISP), связанный с IP-адресом конечной точки |
| `ReportId` | long | Уникальный идентификатор для мероприятия |
| `AdditionalFields` | Строка | Дополнительная информация о сущности или событии |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)