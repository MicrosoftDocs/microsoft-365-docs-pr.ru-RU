---
title: Создание политики типа конфиденциальной информации с помощью шифрование сообщений Office 365
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
description: Узнайте, как создать политику типа конфиденциальной информации для организации с помощью шифрование сообщений Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad570f64122aecd245b912b1b6545a5950e838cc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927747"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>Создание политики типа конфиденциальной информации для организации с помощью шифрования сообщений

Вы можете использовать Exchange правила потока почты или предотвращение потери данных (DLP) для создания политики типа конфиденциальной информации с шифрование сообщений Office 365. Чтобы создать правило Exchange потока почты, можно использовать центр администрирования Exchange (EAC) или PowerShell.

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>Создание политики с помощью правил потока почты в EAC

Войдите в центр администрирования Exchange (EAC) и перейдите к **правилам потока**  >  **почты.** На странице Правила создайте правило, которое применяется шифрование сообщений Office 365. Вы можете создать правило на основе условий, таких как наличие определенных ключевых слов или типов конфиденциальной информации в сообщении или вложении.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>Создание политики с помощью правил потока почты в PowerShell

Используйте учетную запись для работы или школы с глобальными разрешениями администратора в организации, запустите сеанс Windows PowerShell и подключите к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Используйте Set-IRMConfiguration и New-TransportRule для создания политики.

## <a name="example-mail-flow-rule-created-with-powershell"></a>Пример правила потока почты, созданного с помощью PowerShell

Запустите следующие команды в PowerShell, чтобы создать правило потока почты Exchange, которое автоматически шифрует сообщения, отправленные за пределами организации, с помощью параметра только для шифрования, если сообщения электронной почты или их вложения содержат следующие типы конфиденциальной информации:

- Номер маршрутивки ABA
- Номер кредитной карты
- Номер Агентства по принудиванию к наркотикам (DEA)
- U.S. / U.K. passport number
- Номер банковского счета в США
- Идентификационный номер налогоплательщика для США (ITIN)
- Страховой номер для США (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

Дополнительные сведения см. [в set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) и [New-TransportRule.](/powershell/module/exchange/new-transportrule)

## <a name="how-recipients-access-attachments"></a>Как получатели могут получить доступ к вложениям

После шифрования сообщения Корпорацией Майкрософт получатели имеют неограниченный доступ к вложениям при доступе к зашифрованной электронной почте.

## <a name="to-prepare-for-this-change"></a>Подготовка к этому изменению

Для подготовки сотрудников организации к этим изменениям может потребоваться обновить документацию и учебные материалы для конечных пользователей. Поделитесь этими шифрование сообщений Office 365 ресурсами с пользователями по мере необходимости:

- [Отправка, просмотр и ответ на зашифрованные сообщения в Outlook для ПК](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Microsoft 365 Essentials Video: Office шифрование сообщений](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>Просмотр этих изменений в журнале аудита

Microsoft 365 аудит этого действия и делает его доступным для администраторов. Операция "New-TransportRule" и фрагмент примера записи аудита из центра поиска журналов аудита в области безопасности & ниже:

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>Отключение или настройка политики типов конфиденциальной информации

После создания правила потока Exchange вы можете отключить [](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) или изменить правило, перенаправить правила потока почты в центре администрирования Exchange (EAC) и отключить правило "Шифрование исходящие конфиденциальные сообщения (вне правила   >   *полей)*".