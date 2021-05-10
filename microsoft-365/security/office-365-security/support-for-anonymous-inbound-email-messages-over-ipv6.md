---
title: Добавление поддержки анонимных входящих писем по протоколу IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администратор может узнать, как настроить поддержку анонимной входящие сообщения электронной почты из источников IPv6 в Exchange Online и Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80fdcc9dcfe3006ef8b21aa19856fe8c0ea3ff70
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300053"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Добавьте поддержку анонимной входящие сообщения электронной почты над IPv6 в Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 с Exchange Online почтовыми ящиками и автономными Exchange Online Protection (EOP) без Exchange Online почтовых ящиков поддерживают анонимные входящие сообщения электронной почты по IPv6. Исходный сервер электронной почты IPv6 должен соответствовать следующим требованиям:

- Исходный адрес IPv6 должен иметь допустимую обратную запись поиска DNS (PTR), которая позволяет пункту назначения находить доменное имя с адреса IPv6.

- Отправитель должен пройти проверку инфраструктуры политики отправителей (определенную в документе [RFC 7208](https://tools.ietf.org/html/rfc7208)) или [проверку DKIM](http://dkim.org/) (которая описана в документе [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).

Прежде чем ваша организация сможет получать анонимные входящие сообщения электронной почты по IPv6, администратору необходимо обратиться в службу поддержки Майкрософт и попросить ее. Инструкции о том, как открыть запрос на поддержку, см. в справке [Contact support for business products - Admin Help.](../../business-video/get-help-support.md)

После включения анонимной поддержки сообщений IPv6 в организации сообщение будет проходить обычную фильтрацию сообщений, предоставляемую службой.

## <a name="troubleshooting"></a>Устранение неполадок

- Если исходный сервер электронной почты не имеет записи обратного DNS-сервера IPv6, сообщения будут отклонены со следующей ошибкой:

  > Служба 450 4.7.25 недоступна, отправка адреса IPv6 [2a01:111:f200:2004::240] должна иметь обратную запись DNS.

- Если отправитель не пройдет проверку SPF или DKIM, сообщения будут отклонены со следующей ошибкой:

  > 450 4.7.26 Служба недоступна, сообщение, отправленное по IPv6 [2a01:111:f200:2004:240], должно пройти проверку SPF или DKIM.

- Если вы пытаетесь получить анонимные сообщения IPv6 до выбора, сообщение будет отклонено со следующей ошибкой:

  > Служба 550 5.2.1 недоступна, [contoso.com] не принимает электронную почту по IPv6.

## <a name="related-topics"></a>Статьи по теме

[Поддержка проверки сообщений, подписанных с помощью DKIM](support-for-validation-of-dkim-signed-messages.md)
