---
title: Установка срока действия для электронных писем, зашифрованных с помощью расширенного шифрования сообщений Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Используйте расширенное шифрование сообщений Office 365, чтобы расширить безопасность электронной почты, задав дату окончания срока действия сообщений электронной почты с помощью пользовательского шаблона с фирмой.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bbd018e55592e5b17149edf1a4dc0907c0184417
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769169"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Установка срока действия для электронных писем, зашифрованных с помощью расширенного шифрования сообщений Office 365

Office 365 Advanced Message Encryption входит в [состав Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/home)корпоративный E5, Office 365 E5, Microsoft 365 E5 (цены для некоммерческих сотрудников), Office 365 корпоративный E5 (цены для некоммерческих сотрудников) и Office 365 для образования A5. Если у вашей организации есть подписка, не включаемая в расширенный шифрование сообщений Office 365, вы можете приобрести ее с помощью надстройки SKU соответствия требованиям Microsoft 365 E5 для Microsoft 365 E3, Microsoft 365 E3 (цены для некоммерческих сотрудников) или надстройки Office 365 Advanced Compliance SKU для Microsoft 365 E3, Microsoft 365 E3 (цены для некоммерческих сотрудников) или SKU Office 365.

Срок действия сообщений можно использовать для сообщений электронной почты, отправляемой пользователями внешним получателям, которые используют портал OME для доступа к зашифрованным электронным письмам. Получатели должны использовать портал OME для просмотра зашифрованных сообщений электронной почты, отправленных вашей организацией, и ответа на них с помощью настраиваемого шаблона с фирменной Windows PowerShell.

Как глобальный администратор Office 365, при применении фирменой марки компании для настройки внешний вид сообщений электронной почты организации вы также можете указать срок действия этих сообщений электронной почты. С помощью office 365 Advanced Message Encryption можно создать несколько шаблонов для зашифрованных сообщений электронной почты, отправленных из вашей организации. С помощью шаблона можно контролировать, как долго получатели имеют доступ к почте, отправленной вашими пользователями.

Когда конечный пользователь получает почту с установленным сроком действия, пользователь видит дату окончания срока действия в сообщении-оболочке. Если пользователь попытается открыть почту с истекшим сроком действия, на портале OME появится сообщение об ошибке.

Вы можете установить только даты окончания срока действия сообщений электронной почты для внешних получателей.

В Office 365 Advanced Message Encryption каждый раз, когда вы применяли настраиваемую фирмевую марку, Office 365 применяет оболочку к электронной почте, которая соответствует правилу потока почты, к которому применяется шаблон. Кроме того, срок действия можно использовать только в том случае, если вы используете настраиваемую фирменую марку.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Создание пользовательского шаблона фирменой настройки для принудительного истечения срока действия почты с помощью PowerShell

1. [Подключите Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) с помощью учетной записи с разрешениями глобального администратора в вашей организации.

2. Запустите New-OMEConfiguration управления.

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

Где:

- `Identity` — имя настраиваемого шаблона.

- `ExternalMailExpiryInDays` определяет количество дней, в течение которых получатели могут хранить почту до истечения срока ее действия. Можно использовать любое значение от 1 до 730 дней.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Дополнительные сведения о службе Office 365 Advanced Message Encryption

- [Расширенное шифрование сообщений Office 365](ome-advanced-message-encryption.md)

- [Отзыв электронных писем, зашифрованных с помощью расширенного шифрования сообщений Office 365](revoke-ome-encrypted-mail.md)

- [Описание политики сообщений и службы соответствия требованиям](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
