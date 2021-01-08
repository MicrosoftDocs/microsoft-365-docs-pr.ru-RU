---
title: Таблица AADSpnSignInEventsBeta в схеме advanced hunting
description: Сведения о сведениях, связанных с участником-службой Azure Active Directory и таблицой событий управляемого удостоверения для регистрации в службе advanced hunting schema
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, user, account, identity, AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 42acf24ce9b941fffb1ce0ed4b67216bd8c1de47
ms.sourcegitcommit: 4482c174e0e68e0fbbc7ad9ef6b0e78dc34ac85a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2021
ms.locfileid: "49784303"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Область применения:**

- Microsoft 365 Defender

>[!IMPORTANT]
> Таблица в настоящее время находится в бета-версии и предлагается на краткосрочной основе, чтобы вы могли использовать события регистрации в azure `AADSpnSignInEventsBeta` Active Directory (AAD) и основного пользователя службы и управляемого удостоверения. Со временем все сведения о схеме для входов будут перемещаться в `IdentityLogonEvents` таблицу.<br><br>
> Клиенты, которые могут получить доступ к Microsoft 365 Defender через интегрированное решение Microsoft Defender для конечных точек в Центре безопасности Azure, но не имеют лицензий на Microsoft Defender для Office, Microsoft Defender для удостоверений или Microsoft Cloud App Security, не смогут просматривать эту схему. 



Таблица в схеме advanced hunting содержит сведения о основном службе Azure Active Directory и управляемых входов `AADSpnSignInEventsBeta` удостоверений. Вы можете узнать больше о различных типах входов в Отчеты о действиях при входе [в Azure Active Directory ( предварительная версия).](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).





| Имя столбца     | Тип данных | Описание   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | Дата и время создания записи                                                                                                     |
| `Application`          | string        | Приложение, которое выполнило записанную действие                                                                                                   |
| `ApplicationId`        | Строка        | Уникальный идентификатор приложения                                                                                                           |
| `IsManagedIdentity`    | boolean       | Указывает, инициировался ли вход с помощью управляемого удостоверения                                                                               |
| `ErrorCode`            | int        | Содержит код ошибки при ошибке при входе. Чтобы найти описание определенного кода ошибки, посетите <https://aka.ms/AADsigninsErrorCodes> сайт . |
| `CorrelationId`        | Строка        | Уникальный идентификатор события для регистрации                                                                                                          |
| `ServicePrincipalName` | Строка        | Имя основного службы, инициа которого был инициирован вход                                                                                        |
| `ServicePrincipalId`   | Строка        | Уникальный идентификатор основного службы, инициировал вход                                                                           |
| `ResourceDisplayName`  | Строка        | Отображаемого имени ресурса, к который был доступ                                                                                                           |
| `ResourceId`           | Строка        | Уникальный идентификатор доступного ресурса                                                                                                      |
| `ResourceTenantId`     | Строка        | Уникальный идентификатор клиента доступного ресурса                                                                                        |
| `IPAddress`            | Строка        | IP-адрес, присвоенный конечной точке и используемый при связанных сетевых коммуникациях                                                              |
| `CountryCode`          | Строка        | Двух буквный код, указывающий страну, в которой расположен IP-адрес клиента                                                                |
| `State`                | Строка        | Состояние, в котором произошел вход, если доступно                                                                                                  |
| `City`                 | Строка        | Город, где находится пользователь учетной записи                                                                                                          |
| `Latitude`             | Строка        | Координаты расположения для входов с севера на север и на север                                                                                          |
| `Longitude`            | Строка        | Координаты расположения для входов с востока на запад                                                                                            |
| `RequestId`            | Строка        | Уникальный идентификатор запроса                                                                                                                |
|`ReportId` | Строка | Уникальный идентификатор события | 

 

## <a name="related-articles"></a>Статьи по теме

-   [AADSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [Обзор расширенной охоты на угрозы](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Изучение языка запросов](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Сведения о схеме](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

