---
title: Таблица AADSpnSignInEventsBeta в продвинутой схеме охоты
description: Сведения о сведениях, связанных Azure Active Directory и управляемой таблице событий для регистрации удостоверений в таблице расширенных схем охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account, identity, AAD
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
ms.openlocfilehash: f74972bcd5d0ddaab58d82b72a55991fda44e3b1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583548"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Область применения:**

- Microsoft 365 Defender

>[!IMPORTANT]
> В настоящее время таблица находится в бета-версии и предлагается на краткосрочной основе, чтобы разрешить вам охотиться через Azure Active Directory (AAD) главного и управляемых событий регистрации `AADSpnSignInEventsBeta` удостоверений. В конечном итоге мы переместим все сведения о схеме входов в `IdentityLogonEvents` таблицу.



Таблица в продвинутой схеме охоты содержит сведения о Azure Active Directory и управляемых входных знаках `AADSpnSignInEventsBeta` удостоверений. Дополнительные новости о различных типах входов можно узнать в отчетах о Azure Active Directory действий для регистрации [.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).





| Имя столбца     | Тип данных | Описание   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | Дата и время создания записи                                                                                                     |
| `Application`          | string        | Приложение, которое выполнило записанную акцию                                                                                                   |
| `ApplicationId`        | строка        | Уникальный идентификатор для приложения                                                                                                           |
| `IsManagedIdentity`    | boolean       | Указывает, был ли вход инициирован управляемым удостоверением                                                                               |
| `ErrorCode`            | int        | Содержит код ошибки при ошибке при входе. Чтобы найти описание определенного кода ошибки, посетите <https://aka.ms/AADsigninsErrorCodes> . |
| `CorrelationId`        | строка        | Уникальный идентификатор события входной записи                                                                                                          |
| `ServicePrincipalName` | строка        | Имя директора службы, который инициировал вход                                                                                        |
| `ServicePrincipalId`   | строка        | Уникальный идентификатор директора службы, который инициировал вход                                                                           |
| `ResourceDisplayName`  | строка        | Отображение имени доступного ресурса                                                                                                           |
| `ResourceId`           | строка        | Уникальный идентификатор доступного ресурса                                                                                                      |
| `ResourceTenantId`     | строка        | Уникальный идентификатор клиента доступного ресурса                                                                                        |
| `IPAddress`            | строка        | IP-адрес, присвоенный конечной точке и используемый во время связанных сетевых коммуникаций                                                              |
| `Country`          | строка        | Код из двух букв, указывающий страну, в которой расположен IP-адрес клиента                                                                |
| `State`                | строка        | Состояние, в котором произошла входная информация при наличии                                                                                                  |
| `City`                 | строка        | Город, в котором находится пользователь учетной записи                                                                                                          |
| `Latitude`             | строка        | Координаты расположения входного знака с севера на юг                                                                                          |
| `Longitude`            | строка        | Координаты расположения входного знака с востока на запад                                                                                            |
| `RequestId`            | строка        | Уникальный идентификатор запроса                                                                                                                |
|`ReportId` | строка | Уникальный идентификатор события | 

 

## <a name="related-articles"></a>Связанные статьи

-   [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
-   [Обзор расширенной охоты](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Изучение языка запросов](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Сведения о схеме](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)