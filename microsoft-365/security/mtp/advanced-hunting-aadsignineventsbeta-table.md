---
title: Таблица AADSignInEventsBeta в схеме advanced hunting
description: Сведения о сведениях, связанных с таблицей событий для регистрации в Azure Active Directory схемы расширенных поисков
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, file, IP address, device, user, account, identity, AAD
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
ms.openlocfilehash: 174db150920d2d95c043bb5d6e5a4593ea1ea39d
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145431"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Область применения:**

- Microsoft 365 Defender

>[!IMPORTANT]
> Таблица в настоящее время находится в бета-версии и предлагается на краткосрочной основе, чтобы вы могли использовать события для регистрации `AADSignInEventsBeta` в Azure Active Directory (AAD). Со временем все сведения о схеме для входов будут перемещаться в `IdentityLogonEvents` таблицу.<br><br>
> Пользователи, которые могут получить доступ к Microsoft 365 Defender через интегрированное решение Microsoft Defender для конечных точек в Центре безопасности Azure, но не имеют лицензий на Microsoft Defender для Office, Microsoft Defender для удостоверений или Microsoft Cloud App Security, не смогут просмотреть эту схему. 

 

Таблица в схеме advanced hunting содержит сведения об интерактивных и неин интерактивных входов `AADSignInEventsBeta` в Azure Active Directory. Узнайте больше о входе в отчеты о входе в Azure Active Directory — [предварительная версия.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Используйте этот справочник для создания запросов, возвращающих данные из таблицы.
Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).

 

 

| Имя столбца                 | Тип данных | Описание          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | datetime      | Дата и время создания записи                                                                                                                                         |
| `Application`                     | string        | Приложение, которое выполнило записанную действие                                                                                                                                       |
| `ApplicationId`                   | string        | Уникальный идентификатор приложения                                                                                                                                               |
| `LogonType`                       | string        | Тип сеанса для сеанса, в частности интерактивного, удаленного интерактивного (RDP), сети, пакета и службы                                                                              |
| `ErrorCode`                       | int        | Содержит код ошибки при ошибке при входе. Чтобы найти описание определенного кода ошибки, посетите <https://aka.ms/AADsigninsErrorCodes> сайт .                                     |
| `CorrelationId`                   | string        | Уникальный идентификатор события для регистрации                                                                                                                                              |
| `SessionId`                       | string        | Уникальный номер, присвоенный пользователю сервером веб-сайта на время посещения или сеанса                                                                                     |
| `AccountDisplayName`              | string        | Имя пользователя учетной записи, отображаемой в адресной книге. Обычно сочетание заданного или имени, отчество и фамилия или фамилия.                             |
| `AccountObjectId`                 | string        | Уникальный идентификатор учетной записи в Azure AD                                                                                                                                       |
| `AccountUpn`                      | string        | Имя пользователя-пользователя (UPN) учетной записи                                                                                                                                            |
| `IsExternalUser`                  | int        | Указывает, является ли пользователь, выписав его внешним пользователем. Возможные значения: -1 (не установлено), 0 (не внешние), 1 (внешние).                                                                   |
| `IsGuestUser`                     | boolean       | Указывает, является ли пользователь, выписав его гостем в клиенте                                                                                                                  |
| `AlternateSignInName`             | string        | Локальное имя основного пользователя (UPN) пользователя, во время которого пользователь входит в Azure AD                                                                                                            |
| `LastPasswordChangeTimestamp`     | datetime        | Дата и время последнего изменения пароля пользователем, который вписался в учетную дату и время.                                                                                                              |
| `ResourceDisplayName`             | string        | Отображаемого имени ресурса, к который был доступ                                                                                                                                               |
| `ResourceId`                      | string        | Уникальный идентификатор доступного ресурса                                                                                                                                          |
| `ResourceTenantId`                | string        | Уникальный идентификатор клиента доступного ресурса                                                                                                                            |
| `DeviceName`                      | string        | Полное доменное имя компьютера                                                                                                                                   |
| `AadDeviceId`                     | string   |      Уникальный идентификатор устройства в Azure AD                                                                                                                                                                               |
| `OSPlatform`                      | string        | Платформа операционной системы, используемой на компьютере. Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.  |
| `DeviceTrustType`                 | string        | Указывает тип доверия для устройства, выписав его. Только для сценариев управляемых устройств. Возможные значения: Workplace, AzureAd и ServerAd.                                     |
| `IsManaged`                       | int       | Указывает, является ли устройство, которое инициировал вход, управляемым устройством (1) или не управляемым устройством (0)                                                                         |
| `IsCompliant`                     | int       | Указывает, соответствует ли устройство, которое инициировал вход (1) или не соответствует (0)                                                                                       |
| `AuthenticationProcessingDetails` | string        | Сведения об обработчике проверки подлинности                                                                                                                                          |
| `AuthenticationRequirement`       | string        | Тип проверки подлинности, необходимый для регистрации. Возможные значения: multiFactorAuthentication (требуется MFA) и singleFactorAuthentication (MFA не требуется).                |
| `TokenIssuerType`                 | int        | Указывает, является ли выдавщик маркера Azure Active Directory (0) или службами федерации Active Directory (1)                                                                             |
| `RiskLevelAggregated`                       | int        | Сводный уровень риска при входе в нее. Возможные значения: 0 (совокупный уровень риска не установлен), 1 (нет), 10 (низкий), 50 (средний) или 100 (высокий).                               |
| `RiskDetails`                      | int        | Сведения о рискованных состояниях пользователя, выписав его                                                                                                                            |
| `RiskState`                       | int        | Указывает на рискованные состояния пользователя. Возможные значения: 0 (нет), 1 (подтверждено безопасно), 2 (исправлено), 3 (отклонено), 4 (под угрозой) или 5 (подтверждено компрометация).                                |
| `UserAgent`                       | string        | Сведения об агенте пользователя из веб-браузера или другого клиентского приложения                                                                                                             |
| `ClientAppUsed`                   | string        | Указывает используемого клиентского приложения                                                                                                                                                       |
| `Browser`                         | string        | Сведения о версии браузера, используемого для входов                                                                                                                            |
| `ConditionalAccessPolicies`       | string        | Сведения о политиках условного доступа, применяемых к событию для регистрации                                                                                                             |
| `ConditionalAccessStatus`         | int        | Состояние политик условного доступа, применяемых к входу. Возможные значения: 0 (применяются политики), 1 (попытка применить политики не удалось) или 2 (политики не применяются).      |
| `IPAddress`                       | string        | IP-адрес, присвоенный конечной точке и используемый при связанных сетевых коммуникациях                                                                                                  |
| `Country`                     | string        | Двух буквный код, указывающий страну, в которой расположен IP-адрес клиента                                                                                                    |
| `State`                           | string        | Состояние, в котором произошел вход, если доступно                                                                                                                                      |
| `City`                            | string        | Город, где находится пользователь учетной записи                                                                                                                                              |
| `Latitude`                        | string        | Координаты расположения для входов с севера на север и на север                                                                                                                              |
| `Longitude`                       | string        | Координаты расположения для входов с востока на запад                                                                                                                                |
| `NetworkLocationDetails`          | string        | Сведения о сетевом расположении обработчика проверки подлинности события для регистрации                                                                                                       |
| `RequestId`                       | string        |  Уникальный идентификатор запроса                                                                                                                                                   |
|`ReportId` | string | Уникальный идентификатор события |

 

 

## <a name="related-articles"></a>Статьи по теме

-   [AADSpnSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadspnsignineventsbeta-table)
-   [Обзор расширенной охоты на угрозы](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Изучение языка запросов](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Сведения о схеме](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 
