---
title: Таблица AADSignInEventsBeta в продвинутой схеме охоты
description: Сведения о сведениях, связанных с таблицей событий регистрации Azure Active Directory, в таблице расширенных схем охоты
keywords: продвинутая охота, охота на угрозы, охота на киберугрозы, защита от угроз Майкрософт, Microsoft 365, mtp, m365, поиск, запрос, телеметрия, ссылка на схему, kusto, таблица, столбец, тип данных, описание, файл, IP-адрес, устройство, машина, пользователь, учетная запись, удостоверение, AAD
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
ms.openlocfilehash: 50f112f6e7198136171d070dc483ad5f84d20d57
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925766"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Область применения:**

- Microsoft 365 Defender

>[!IMPORTANT]
> В настоящее время таблица находится в стадии бета-версии и предлагается на краткосрочной основе, чтобы разрешить вам охотиться через события регистрации `AADSignInEventsBeta` Azure Active Directory (AAD). В конечном итоге мы переместим все сведения о схеме входов в `IdentityLogonEvents` таблицу.<br><br>
> Пользователи, которые могут получить доступ к Microsoft 365 Defender через интегрированное решение Microsoft Defender для конечной точки Центра безопасности Azure, но не имеют лицензий для Microsoft Defender для Office, Microsoft Defender for Identity или Microsoft Cloud App Security, не смогут просмотреть эту схему. 

 

Таблица в продвинутой схеме охоты содержит сведения об интерактивных и неинактивных входных знаках `AADSignInEventsBeta` Azure Active Directory. Дополнительные новости о входе в Azure Active Directory в отчетах о действиях для входов [— предварительный просмотр.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Используйте этот справочник для создания запросов, возвращающих данные из таблицы.
Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).

 

 

| Имя столбца                 | Тип данных | Описание          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | datetime      | Дата и время создания записи                                                                                                                                         |
| `Application`                     | string        | Приложение, которое выполнило записанную акцию                                                                                                                                       |
| `ApplicationId`                   | string        | Уникальный идентификатор для приложения                                                                                                                                               |
| `LogonType`                       | string        | Тип сеанса логотипа, в частности интерактивного, удаленного интерактивного (RDP), сети, пакета и службы                                                                              |
| `ErrorCode`                       | int        | Содержит код ошибки при ошибке при входе. Чтобы найти описание определенного кода ошибки, посетите <https://aka.ms/AADsigninsErrorCodes> .                                     |
| `CorrelationId`                   | string        | Уникальный идентификатор события входной записи                                                                                                                                              |
| `SessionId`                       | string        | Уникальный номер, присвоенный пользователю сервером веб-сайта на время посещения или сеанса                                                                                     |
| `AccountDisplayName`              | string        | Имя пользователя учетной записи, отображаемого в адресной книге. Как правило, сочетание данного или имени, среднего начального и фамилии.                             |
| `AccountObjectId`                 | string        | Уникальный идентификатор учетной записи в Azure AD                                                                                                                                       |
| `AccountUpn`                      | string        | Основное имя пользователя (UPN) учетной записи                                                                                                                                            |
| `IsExternalUser`                  | int        | Указывает, является ли пользователь, вписався, внешним. Возможные значения: -1 (не установлено), 0 (не внешние), 1 (внешние).                                                                   |
| `IsGuestUser`                     | boolean       | Указывает, является ли пользователь, вписався, гостем в клиенте                                                                                                                  |
| `AlternateSignInName`             | string        | Локальное основное имя пользователя (UPN) пользователя, входив в Azure AD                                                                                                            |
| `LastPasswordChangeTimestamp`     | datetime        | Дата и время, когда пользователь, который в последний раз изменил пароль                                                                                                              |
| `ResourceDisplayName`             | string        | Отображение имени доступного ресурса                                                                                                                                               |
| `ResourceId`                      | string        | Уникальный идентификатор доступного ресурса                                                                                                                                          |
| `ResourceTenantId`                | string        | Уникальный идентификатор клиента доступного ресурса                                                                                                                            |
| `DeviceName`                      | string        | Полное доменное имя компьютера                                                                                                                                   |
| `AadDeviceId`                     | string   |      Уникальный идентификатор устройства в Azure AD                                                                                                                                                                               |
| `OSPlatform`                      | string        | Платформа операционной системы, используемой на компьютере. Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.  |
| `DeviceTrustType`                 | string        | Указывает тип доверия устройства, в которое вписались. Только для сценариев управляемых устройств. Возможные значения : Workplace, AzureAd и ServerAd.                                     |
| `IsManaged`                       | int       | Указывает, является ли устройство, которое инициировал вход управляемым устройством (1) или не управляемым устройством (0)                                                                         |
| `IsCompliant`                     | int       | Указывает, соответствует ли устройство, которое инициировал вход (1) или не соответствует требованиям (0)                                                                                       |
| `AuthenticationProcessingDetails` | string        | Сведения об процессоре проверки подлинности                                                                                                                                          |
| `AuthenticationRequirement`       | string        | Тип проверки подлинности, необходимой для регистрации. Возможные значения: multiFactorAuthentication (MFA был необходим) и singleFactorAuthentication (не требуется MFA).                |
| `TokenIssuerType`                 | int        | Указывает, является ли эмитент маркера службами Федерации Azure Active Directory (0) или Active Directory Federation Services (1)                                                                             |
| `RiskLevelAggregated`                       | int        | Совокупный уровень риска при входе. Возможные значения: 0 (совокупный уровень риска не установлен), 1 (нет), 10 (низкий), 50 (средний) или 100 (высокий).                               |
| `RiskDetails`                      | int        | Сведения о рискованном состоянии пользователя, подписав                                                                                                                            |
| `RiskState`                       | int        | Указывает состояние пользователя с риском. Возможные значения: 0 (нет), 1 (подтвержденный безопасный), 2 (исправлено), 3 (отклонено), 4 (в опасности) или 5 (подтверждено компрометация).                                |
| `UserAgent`                       | string        | Сведения агента пользователя из веб-браузера или другого клиентского приложения                                                                                                             |
| `ClientAppUsed`                   | string        | Указывает используемого клиентского приложения                                                                                                                                                       |
| `Browser`                         | string        | Сведения о версии браузера, используемой для входов                                                                                                                            |
| `ConditionalAccessPolicies`       | string        | Сведения о политиках условного доступа, применяемых к событию для регистрации                                                                                                             |
| `ConditionalAccessStatus`         | int        | Состояние политик условного доступа, применяемых к входу. Возможные значения: 0 (примененные политики), 1 (попытка применить политики не удалось) или 2 (политики не применяются).      |
| `IPAddress`                       | string        | IP-адрес, присвоенный конечной точке и используемый во время связанных сетевых коммуникаций                                                                                                  |
| `Country`                     | string        | Код из двух букв, указывающий страну, в которой расположен IP-адрес клиента                                                                                                    |
| `State`                           | string        | Состояние, в котором произошла входная информация при наличии                                                                                                                                      |
| `City`                            | string        | Город, в котором находится пользователь учетной записи                                                                                                                                              |
| `Latitude`                        | string        | Координаты расположения входного знака с севера на юг                                                                                                                              |
| `Longitude`                       | string        | Координаты расположения входного знака с востока на запад                                                                                                                                |
| `NetworkLocationDetails`          | string        | Сведения о расположении сети обработчика проверки подлинности события входного                                                                                                       |
| `RequestId`                       | string        |  Уникальный идентификатор запроса                                                                                                                                                   |
|`ReportId` | string | Уникальный идентификатор события |

 

 

## <a name="related-articles"></a>Статьи по теме

-   [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
-   [Обзор расширенной охоты на угрозы](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Изучение языка запросов](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Сведения о схеме](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 