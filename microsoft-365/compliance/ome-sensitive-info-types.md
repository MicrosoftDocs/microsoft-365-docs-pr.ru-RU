---
title: Создание политики типов конфиденциальной информации с помощью шифрования сообщений Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: Узнайте, как создать политику типов конфиденциальной информации для организации с помощью шифрования сообщений Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfc77fa88ff798f98d260682dfbdbdd57b17af69
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545989"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>Создание политики типов конфиденциальной информации для организации с помощью шифрования сообщений

Для создания политики типов конфиденциальной информации с шифрованием сообщений Office 365 можно использовать правила потока обработки почты Exchange или DLP. Чтобы создать правило потока обработки почты Exchange, можно использовать Центр администрирования Exchange (EAC) или PowerShell.

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>Создание политики с помощью правил потока почты в EAC

Войдите в Центр администрирования Exchange (EAC) и перейдите к **правилам потока обработки**  >  **почты.** На странице "Правила" создайте правило, применяя шифрование сообщений Office 365. Правило можно создать на основе таких условий, как наличие определенных ключевых слов или типов конфиденциальной информации в сообщении или вложении.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>Создание политики с помощью правил потока почты в PowerShell

Используйте учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, запустите сеанс Windows PowerShell и подключите его к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell). Используйте Set-IRMConfiguration и New-TransportRule для создания политики.

## <a name="example-mail-flow-rule-created-with-powershell"></a>Пример правила потока почты, созданного с помощью PowerShell

Запустите следующие команды в PowerShell, чтобы создать правило потока почты Exchange, которое  автоматически шифрует сообщения, отправленные за пределы организации, с помощью политики "Только шифрование", если сообщения электронной почты или их вложения содержат следующие типы конфиденциальной информации:

- Номер маршрутки ABA
- Номер кредитной карты
- Номер агентства по правоохранительным органам (DEA)
- США и Сша passport number
- Номер банковского счета в США
- Идентификационный номер налогоплательщика для США (ITIN)
- Страховой номер для США (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

Дополнительные сведения [см. в настройках Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration) и [New-TransportRule.](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)

## <a name="how-recipients-access-attachments"></a>Как получатели имеют доступ к вложениям

После шифрования сообщения корпорацией Майкрософт у получателей будет неограниченный доступ к вложениям, когда они будут получать доступ к зашифрованной электронной почте и открывать ее.

## <a name="to-prepare-for-this-change"></a>Подготовка к этому изменению

Вам может потребоваться обновить все применимые документацию и обучающие материалы для подготовки сотрудников организации к этому изменению. При необходимости поделитесь этими ресурсами шифрования сообщений Office 365 с пользователями:

- [Отправка, просмотр зашифрованных сообщений и ответ на них в Outlook для ПК](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Видео о Microsoft 365 essentials: шифрование сообщений Office](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>Просмотр этих изменений в журнале аудита

Microsoft 365 проводит аудит этого действия и делает его доступным для администраторов. Операция " New-TransportRule" и фрагмент примера записи аудита из поиска в журнале аудита в центре безопасности & соответствия требованиям ниже:

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>Отключение или настройка политики типов конфиденциальной информации

После создания правила потока обработки почты [](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) Exchange вы можете отключить или изменить правило, переходить к правилам потока обработки почты в Центре администрирования  >   Exchange (EAC) и отключить правило *"Шифровать* исходящие конфиденциальные сообщения электронной почты (из правила").
