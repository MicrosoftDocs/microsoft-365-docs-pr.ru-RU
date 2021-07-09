---
title: Таблица AADSpnSignInEventsBeta в продвинутой схеме охоты
description: Сведения о сведениях, связанных Azure Active Directory и управляемой таблице событий для регистрации удостоверений в таблице расширенных схем охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account, identity, AAD
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
ms.openlocfilehash: 6aa709fe4534bf049c6f8c097bc4bd85a9d6793b
ms.sourcegitcommit: 93eeaefc0d509c75e4c2210029155298ecca7583
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53347911"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Область применения:**

- Microsoft 365 Defender

>[!IMPORTANT]
> В настоящее время таблица находится в бета-версии и предлагается на краткосрочной основе, чтобы разрешить вам охотиться через Azure Active Directory (AAD) главного и управляемых событий регистрации `AADSpnSignInEventsBeta` удостоверений. В конечном итоге мы переместим все сведения о схеме входов в `IdentityLogonEvents` таблицу.



Таблица в продвинутой схеме охоты содержит сведения о Azure Active Directory и управляемых входных знаках `AADSpnSignInEventsBeta` удостоверений. Дополнительные новости о различных типах входов можно узнать в отчетах о Azure Active Directory действий для регистрации [.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).





| Имя столбца | Тип данных | Описание |
|-----|-----|-----|
| `Timestamp` | datetime | Дата и время создания записи |
| `Application` | string | Приложение, которое выполнило записанную акцию |
| `ApplicationId` | string | Уникальный идентификатор для приложения |
| `IsManagedIdentity`    | boolean       | Указывает, был ли вход инициирован управляемым удостоверением |
| `ErrorCode`    | int | Содержит код ошибки при ошибке при входе. Чтобы найти описание определенного кода ошибки, посетите <https://aka.ms/AADsigninsErrorCodes> . |
| `CorrelationId`        | string        | Уникальный идентификатор события входной записи |
| `ServicePrincipalName` | string        | Имя директора службы, который инициировал вход  |
| `ServicePrincipalId`   | string        | Уникальный идентификатор директора службы, который инициировал вход  |
| `ResourceDisplayName`  | string        | Отображение имени доступного ресурса  |
| `ResourceId`           | string        | Уникальный идентификатор доступного ресурса  |
| `ResourceTenantId`     | string        | Уникальный идентификатор клиента доступного ресурса |
| `IPAddress`            | string        | IP-адрес, присвоенный конечной точке и используемый во время связанных сетевых коммуникаций  |
| `Country`          | string        | Код из двух букв, указывающий страну, в которой расположен IP-адрес клиента |
| `State`                | string        | Состояние, в котором произошла входная информация при наличии |
| `City`                 | string        | Город, в котором находится пользователь учетной записи  |
| `Latitude`             | string        | Координаты расположения входного знака с севера на юг |
| `Longitude`            | string        | Координаты расположения входного знака с востока на запад |
| `RequestId`            | string        | Уникальный идентификатор запроса |
|`ReportId` | string | Уникальный идентификатор события |

 

## <a name="related-articles"></a>Статьи по теме

-   [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
-   [Обзор расширенной охоты](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Изучение языка запросов](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Сведения о схеме](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
