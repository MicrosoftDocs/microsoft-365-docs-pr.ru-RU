---
title: Таблица AADSpnSignInEventsBeta в продвинутой схеме охоты
description: Сведения о сведениях, связанных с руководителем службы Azure Active Directory и таблицой событий, связанных с управляемым входом удостоверений, в таблице расширенных схем охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft threat protection, Microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account, identity, AAD
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
ms.openlocfilehash: 5050f4f91d61369e927eae15ca7c156a17792c24
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924544"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Область применения:**

- Microsoft 365 Defender

>[!IMPORTANT]
> В настоящее время таблица находится в стадии бета-версии и предлагается на краткосрочной основе, чтобы разрешить вам охотиться на руководителя `AADSpnSignInEventsBeta` службы Azure Active Directory (AAD) и управляемых событий регистрации удостоверений. В конечном итоге мы переместим все сведения о схеме входов в `IdentityLogonEvents` таблицу.<br><br>
> Пользователи, которые могут получить доступ к Microsoft 365 Defender через интегрированное решение Microsoft Defender для конечной точки Центра безопасности Azure, но не имеют лицензий для Microsoft Defender для Office, Microsoft Defender for Identity или Microsoft Cloud App Security, не смогут просмотреть эту схему. 



Таблица в продвинутой схеме охоты содержит сведения о директоре службы Azure Active Directory и управляемых входных знаках `AADSpnSignInEventsBeta` удостоверений. Дополнительные новости о различных типах входных входов можно узнать в отчетах о действиях для регистрации [Azure Active Directory — предварительный просмотр.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).





| Имя столбца     | Тип данных | Описание   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | Дата и время создания записи                                                                                                     |
| `Application`          | string        | Приложение, которое выполнило записанную акцию                                                                                                   |
| `ApplicationId`        | string        | Уникальный идентификатор для приложения                                                                                                           |
| `IsManagedIdentity`    | boolean       | Указывает, был ли вход инициирован управляемым удостоверением                                                                               |
| `ErrorCode`            | int        | Содержит код ошибки при ошибке при входе. Чтобы найти описание определенного кода ошибки, посетите <https://aka.ms/AADsigninsErrorCodes> . |
| `CorrelationId`        | string        | Уникальный идентификатор события входной записи                                                                                                          |
| `ServicePrincipalName` | string        | Имя директора службы, который инициировал вход                                                                                        |
| `ServicePrincipalId`   | string        | Уникальный идентификатор директора службы, который инициировал вход                                                                           |
| `ResourceDisplayName`  | string        | Отображение имени доступного ресурса                                                                                                           |
| `ResourceId`           | string        | Уникальный идентификатор доступного ресурса                                                                                                      |
| `ResourceTenantId`     | string        | Уникальный идентификатор клиента доступного ресурса                                                                                        |
| `IPAddress`            | string        | IP-адрес, присвоенный конечной точке и используемый во время связанных сетевых коммуникаций                                                              |
| `Country`          | string        | Код из двух букв, указывающий страну, в которой расположен IP-адрес клиента                                                                |
| `State`                | string        | Состояние, в котором произошла входная информация при наличии                                                                                                  |
| `City`                 | string        | Город, в котором находится пользователь учетной записи                                                                                                          |
| `Latitude`             | string        | Координаты расположения входного знака с севера на юг                                                                                          |
| `Longitude`            | string        | Координаты расположения входного знака с востока на запад                                                                                            |
| `RequestId`            | string        | Уникальный идентификатор запроса                                                                                                                |
|`ReportId` | string | Уникальный идентификатор события | 

 

## <a name="related-articles"></a>Статьи по теме

-   [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
-   [Обзор расширенной охоты на угрозы](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Изучение языка запросов](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Сведения о схеме](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)