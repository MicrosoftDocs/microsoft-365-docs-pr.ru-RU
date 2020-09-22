---
title: Добавление поддержки анонимных входящих писем по протоколу IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администратор может узнать, как настроить поддержку анонимной входящей электронной почты из источников IPv6 в Exchange Online и Exchange Online Protection.
ms.openlocfilehash: be226bf9814b0fcfadaaeb5b4bdda0ff133dd0c8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202153"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Добавление поддержки анонимной входящей электронной почты по протоколу IPv6 в Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Организации Microsoft 365 с почтовыми ящиками Exchange Online и отдельными организациями Exchange Online Protection (EOP) без почтовых ящиков Exchange Online поддерживают анонимную входящую почту через IPv6. Исходный сервер электронной почты на базе протокола IPv6 должен соответствовать следующим требованиям:

- Исходный IPv6-адрес должен иметь действительную обратную запись DNS (PTR), которая позволяет конечному объекту найти доменное имя из IPv6-адреса.

- Отправитель должен пройти проверку инфраструктуры политики отправителей (определенную в документе [RFC 7208](https://tools.ietf.org/html/rfc7208)) или [проверку DKIM](http://dkim.org/) (которая описана в документе [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).

Прежде чем Организация сможет получить анонимную входящую почту по протоколу IPv6, администратору необходимо обратиться в службу поддержки Майкрософт и запросить ее. Инструкции по открытию запроса в службу поддержки можно найти в разделе [Contact support for Business Products — Справка для администраторов](../../admin/contact-support-for-business-products.md).

После включения поддержки анонимных входящих сообщений IPv6 в Организации сообщение будет проходить через обычную фильтрацию сообщений, предоставляемую службой.

## <a name="troubleshooting"></a>Устранение неполадок

- Если исходный сервер электронной почты не имеет записи поиска обратной DNS в IPv6, сообщения будут отклонены со следующей ошибкой:

  > 450 служба 4.7.25 недоступна, отправка IPv6-адреса [2a01:111: F200:2004:: 240] должна иметь обратную запись DNS.

- Если отправитель не передает SPF или DKIM проверку подлинности, сообщения будут отклонены со следующей ошибкой:

  > 450 служба 4.7.26 недоступна, сообщение, отправленное по протоколу IPv6 [2a01:111: F200:2004:: 240], должен быть прошел проверку SPF или DKIM.

- Если вы попытаетесь получить анонимные IPv6-сообщения до того, как вы настроили ее, сообщение будет отклонено со следующей ошибкой:

  > 550 5.2.1 служба недоступна, [contoso.com] не принимает сообщения электронной почты по протоколу IPv6.

## <a name="related-topics"></a>Связанные статьи

[Поддержка проверки сообщений, подписанных с помощью DKIM](support-for-validation-of-dkim-signed-messages.md)
