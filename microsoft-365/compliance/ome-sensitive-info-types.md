---
title: Создание политики типов конфиденциальной информации для организации с помощью шифрования сообщений Office 365
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
description: 'Сводка: политика шифрования сообщений Office 365 для типов конфиденциальной информации.'
ms.openlocfilehash: d74712798ba9d46614b5fc916e4b1ce111582304
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091176"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-office-365-message-encryption"></a>Создание политики типов конфиденциальной информации для организации с помощью шифрования сообщений Office 365

Для создания политики типов конфиденциальной информации с помощью шифрования сообщений Office 365 можно использовать правила для обработки почты Exchange или предотвращение потери данных (DLP) Office 365. Чтобы создать правило для процесса обработки почты Exchange, можно использовать центр администрирования Exchange или PowerShell.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>Создание политики с помощью правил для почтового процесса в центре администрирования Exchange

Войдите в центр администрирования Exchange и перейдите к разделу**правила**для обработки **почтового процесса** > . На странице Правила создайте правило, которое применяет шифрование сообщений Office 365. Вы можете создать правило на основе таких условий, как присутствие определенных ключевых слов или типов конфиденциальной информации в сообщении или вложении.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>Создание политики с помощью правил для почтового процесса в PowerShell

Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в организации Office 365, запустите сеанс Windows PowerShell и подключитесь к Exchange Online. Инструкции можно найти [в статье подключение к Exchange Online PowerShell](https://aka.ms/exopowershell). Используйте командлеты Set – IRMConfiguration и New – TransportRule для создания политики.

### <a name="example-mail-flow-rule-created-with-powershell"></a>Пример правила для процесса обработки почты, созданного с помощью PowerShell

Выполните следующие команды в PowerShell, чтобы создать правило потока обработки почты Exchange, которое автоматически шифрует сообщения, отправляемые за границы Организации, с помощью политики *только для шифрования* , если сообщения электронной почты или их вложения содержат следующие конфиденциальные сведения типом

- Номер маршрутизации код банка ABA
- Номер кредитной карты
- Номер агентства для применения наркотиков (DEA)
- США/ВЕЛИКОБРИТАНИЯ passport number
- Номер банковского счета США
- Идентификационный номер налогоплательщика для США (ITIN)
- Страховой номер для США (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

Дополнительные сведения см. в статье [Set – IRMConfiguration](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps) и [New – TransportRule](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps).

## <a name="how-recipients-access-attachments"></a>Как получатели обращаются к вложениям

После того как Office 365 шифрует сообщение, получатели имеют неограниченный доступ к вложениям при обращении к зашифрованным электронным сообщениям и их открытии.

## <a name="to-prepare-for-this-change"></a>Подготовка к выполнению этого изменения

Вам может потребоваться обновить любую документацию конечного пользователя и обучающие материалы, чтобы подготовить пользователей в Организации к этому изменению. Предоставьте им доступ к этим ресурсам по шифрованию сообщений Office 365, используя соответствующие пользователи:

- [Отправка, просмотр зашифрованных сообщений и ответ на них в Outlook для компьютера](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Видео Office 365 Essentials: шифрование сообщений Office](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>Просмотр изменений в журнале аудита

Office 365 выполняет аудит этого действия и делает его доступным для администраторов Office 365. Операция — "New-TransportRule", а фрагмент примера записи аудита из поиска в журнале аудита в центре безопасности & соответствия требованиям ниже:

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>Отключение или Настройка политики типов конфиденциальной информации

После создания правила для почтовых ящиков Exchange вы можете [отключить или изменить правило](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) , перейдя к**правилам** обработки **почтового ящика** > в центре администрирования Exchange, и отключить правило "*шифровать исходящие сообщения электронной почты от"* . ".
