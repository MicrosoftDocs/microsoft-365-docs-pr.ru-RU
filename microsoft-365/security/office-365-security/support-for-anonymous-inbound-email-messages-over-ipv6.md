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
ms.openlocfilehash: 63c9434fbd1f69c0cbd3145717b712857eb17e28
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290277"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Добавление поддержки анонимной входящие сообщения электронной почты по IPv6 в Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Организации Microsoft 365 с почтовыми ящиками Exchange Online и автономные организации Exchange Online Protection (EOP) без почтовых ящиков Exchange Online поддерживают анонимную входящие сообщения электронной почты по IPv6. Исходный почтовый сервер IPv6 должен соответствовать следующим требованиям:

- Исходный IPv6-адрес должен иметь допустимую запись обратного DNS-поиска (PTR), которая позволяет месту назначения найти доменное имя из IPv6-адреса.

- Отправитель должен пройти проверку инфраструктуры политики отправителей (определенную в документе [RFC 7208](https://tools.ietf.org/html/rfc7208)) или [проверку DKIM](http://dkim.org/) (которая описана в документе [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).

Прежде чем ваша организация сможет получать анонимную входящие сообщения электронной почты по IPv6, администратору необходимо обратиться в службу поддержки Майкрософт и запросить ее. Инструкции о том, как открыть запрос в службу поддержки, см. в справке для администраторов в службе поддержки для [бизнеса.](../../admin/contact-support-for-business-products.md)

После включения поддержки анонимных сообщений IPv6 в организации сообщение проходит обычную фильтрацию сообщений, предоставляемую службой.

## <a name="troubleshooting"></a>Устранение неполадок

- Если исходный почтовый сервер не имеет записи обратного DNS-сервера IPv6, сообщения будут отклонены со следующей ошибкой:

  > Служба 450 4.7.25 недоступна, при отправке IPv6-адреса [2a01:111:f200:2004::240] должна быть обратная запись DNS.

- Если отправитель не прошел проверку SPF или DKIM, сообщения будут отклонены со следующей ошибкой:

  > 450 4.7.26 Служба недоступна, сообщение, отправленное по IPv6 [2a01:111:f200:2004::240], должно пройти проверку SPF или DKIM.

- Если вы попытались получить анонимные сообщения IPv6 до получения отказа, сообщение будет отклонено со следующей ошибкой:

  > Служба 550 5.2.1 недоступна, [contoso.com] не принимает электронную почту по IPv6.

## <a name="related-topics"></a>Статьи по теме

[Поддержка проверки сообщений, подписанных с помощью DKIM](support-for-validation-of-dkim-signed-messages.md)
