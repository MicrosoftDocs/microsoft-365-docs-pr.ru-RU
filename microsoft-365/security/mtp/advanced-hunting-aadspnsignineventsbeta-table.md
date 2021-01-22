---
title: Таблица AADSpnSignInEventsBeta в схеме advanced hunting
description: Сведения о сведениях, связанных с участником-службой Azure Active Directory и таблицой событий управляемого удостоверения для регистрации в службе advanced hunting schema
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, file, IP address, device, user, account, identity, AAD
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 172c400df3adea70a2e2d2e37547fa39e0d3b9cf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928622"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Область применения:**

- Microsoft 365 Defender

>[!IMPORTANT]
> В настоящее время таблица находится в бета-версии и предлагается на краткосрочной основе, чтобы разрешить вам искать события для основного пользователя службы `AADSpnSignInEventsBeta` Azure Active Directory (AAD) и управляемого удостоверения. Со временем все сведения о схеме для входов будут перемещаться в `IdentityLogonEvents` таблицу.<br><br>
> Пользователи, которые могут получить доступ к Microsoft 365 Defender через интегрированное решение Microsoft Defender для конечных точек в Центре безопасности Azure, но не имеют лицензий на Microsoft Defender для Office, Microsoft Defender для удостоверений или Microsoft Cloud App Security, не смогут просмотреть эту схему. 



Таблица в схеме advanced hunting содержит сведения о основном и управляемом входе в службу `AADSpnSignInEventsBeta` Azure Active Directory. Вы можете узнать больше о различных типах входов в Отчеты о действиях при входе [в Azure Active Directory —](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)предварительная версия.

Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).





| Имя столбца     | Тип данных | Описание   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | Дата и время создания записи                                                                                                     |
| `Application`          | string        | Приложение, которое выполнило записанную действие                                                                                                   |
| `ApplicationId`        | string        | Уникальный идентификатор приложения                                                                                                           |
| `IsManagedIdentity`    | boolean       | Указывает, инициировался ли вход с помощью управляемого удостоверения                                                                               |
| `ErrorCode`            | int        | Содержит код ошибки при ошибке при входе. Чтобы найти описание определенного кода ошибки, посетите <https://aka.ms/AADsigninsErrorCodes> сайт . |
| `CorrelationId`        | string        | Уникальный идентификатор события для регистрации                                                                                                          |
| `ServicePrincipalName` | string        | Имя основного службы, инициа которого был инициирован вход                                                                                        |
| `ServicePrincipalId`   | string        | Уникальный идентификатор основного службы, инициировал вход                                                                           |
| `ResourceDisplayName`  | string        | Отображаемого имени ресурса, к который был доступ                                                                                                           |
| `ResourceId`           | string        | Уникальный идентификатор доступного ресурса                                                                                                      |
| `ResourceTenantId`     | string        | Уникальный идентификатор клиента доступного ресурса                                                                                        |
| `IPAddress`            | string        | IP-адрес, присвоенный конечной точке и используемый при связанных сетевых коммуникациях                                                              |
| `CountryCode`          | string        | Двух буквный код, указывающий страну, в которой расположен IP-адрес клиента                                                                |
| `State`                | string        | Состояние, в котором произошел вход, если доступно                                                                                                  |
| `City`                 | string        | Город, где находится пользователь учетной записи                                                                                                          |
| `Latitude`             | string        | Координаты расположения для входов с севера на север и на север                                                                                          |
| `Longitude`            | string        | Координаты расположения для входов с востока на запад                                                                                            |
| `RequestId`            | string        | Уникальный идентификатор запроса                                                                                                                |
|`ReportId` | string | Уникальный идентификатор события | 

 

## <a name="related-articles"></a>Статьи по теме

-   [AADSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [Обзор расширенной охоты на угрозы](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Изучение языка запросов](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Сведения о схеме](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

