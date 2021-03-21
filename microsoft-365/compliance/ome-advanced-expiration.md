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
description: Используйте office 365 Advanced Message Encryption для расширения безопасности электронной почты, установив дату истечения срока действия электронной почты с помощью настраиваемой фирменой шаблона.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f936ffa62f31e47f51fc1bcb2765195b0ea809af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927789"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Установка срока действия для электронных писем, зашифрованных с помощью расширенного шифрования сообщений Office 365

Шифрование расширенных сообщений Office 365 включено в [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (некоммерческие цены на персонал), Office 365 Enterprise E5 (некоммерческие цены на персонал) и Office 365 Education A5. Если в вашей организации есть подписка, не включаемая шифрование расширенных сообщений Office 365, ее можно приобрести с помощью надстройки microsoft 365 E5 Compliance SKU для Microsoft 365 E3, Microsoft 365 E3 (некоммерческие цены персонала) или надстройки Office 365 Advanced Compliance SKU для Microsoft 365 E3, Microsoft 365 E3 (некоммерческие цены персонала) или Office 365 SKUS.

Срок действия сообщения можно использовать в сообщениях электронной почты, которые пользователи отправляют внешним получателям, которые используют портал OME для доступа к зашифрованным электронным письмам. Вы заставите получателей использовать портал OME для просмотра и ответа на зашифрованные сообщения электронной почты, отправленные вашей организацией, с помощью настраиваемого фирменого шаблона, который указывает дату истечения срока действия Windows PowerShell.

В качестве глобального администратора Office 365 при применении бренда компании для настройки внешний вид сообщений электронной почты организации можно также указать срок действия этих сообщений электронной почты. С помощью office 365 Advanced Message Encryption можно создать несколько шаблонов для зашифрованных сообщений, которые происходят из вашей организации. С помощью шаблона можно контролировать, как долго получатели имеют доступ к почте, отправленной пользователями.

Когда конечный пользователь получает почту с набором дат истечения срока действия, пользователь видит дату истечения срока действия в электронной почте обертки. Если пользователь пытается открыть просроченную почту, на портале OME появляется ошибка.

Вы можете устанавливать только даты истечения срока действия электронных писем внешним получателям.

С помощью шифрования расширенных сообщений Office 365 в любое время применения настраиваемой торговой марки Office 365 применяет оболочку к электронной почте, которая соответствует правилу потока почты, к которому применяется шаблон. Кроме того, вы можете использовать срок действия только в том случае, если используется настраиваемый брендинг.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Создайте настраиваемый шаблон брендинга для принудительного истечения срока действия почты с помощью PowerShell

1. [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) с учетной записью, которая имеет глобальные разрешения администратора в вашей организации.

2. Запустите New-OMEConfiguration.

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

Где:

- `Identity` это имя настраиваемого шаблона.

- `ExternalMailExpiryInDays` определяет количество дней, в течение которых получатели могут хранить почту до истечения срока ее действия. Вы можете использовать любое значение от 1 до 730 дней.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Дополнительные сведения о шифровании расширенных сообщений Office 365

- [Расширенное шифрование сообщений Office 365](ome-advanced-message-encryption.md)

- [Отзыв электронных писем, зашифрованных с помощью расширенного шифрования сообщений Office 365](revoke-ome-encrypted-mail.md)

- [Описание политики сообщений и службы соответствия требованиям](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)