---
title: Поддержка анонимных входящих сообщений электронной почты по протоколу IPv6
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: Узнайте, как настроить поддержку анонимных сообщений из источников IPv6 для Exchange Online Protection и Exchange Online.
ms.openlocfilehash: 1cd38798aa644b79c8f1d6362edd17a515b5c98d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598236"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a>Поддержка анонимных входящих сообщений электронной почты по протоколу IPv6

Exchange Online Protection (EOP) и Exchange Online поддерживают получение анонимных входящих сообщений электронной почты по протоколу IPv6 от отправителей, которые не отправляют сообщения по протоколу TLS. Вы можете согласиться на получение сообщений по протоколу IPv6, запросив эту функцию от службы поддержки Майкрософт, открыв Центр администрирования Microsoft [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home)365 по адресу, выбрав пункт **Поддержка**, а затем пункт **новый запрос на обслуживание**. Если вы не согласитесь на использование протокола IPv6, вы по-прежнему будете получать сообщения по протоколу IPv4.
  
Отправители, передающие сообщения в службу по протоколу IPv6, должны выполнить два приведенных ниже требования.
  
1. У IPv6-адреса, с которого отправляются сообщения, должна быть допустимая запись PTR ([обратная запись DNS](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) IPv6-адреса, с которого отправляются сообщения). 
    
2. Отправитель должен пройти проверку инфраструктуры политики отправителей (определенную в документе [RFC 7208](https://tools.ietf.org/html/rfc7208)) или [проверку DKIM](https://dkim.org/) (которая описана в документе [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).
    
Перед переходом на IPv6 обязательно выполнить эти требования независимо от конфигурации. При выполнении обоих требований сообщение пройдет обычную фильтрацию электронных сообщений, которая предоставляется службой. Если какое-либо из этих требований не выполнено, сообщение будет отклонено с одним из следующих ответов 450:
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
Если вы не согласились на получение сообщений по протоколу IPv6, а отправитель пытается принудительно отправить сообщение по этому протоколу, вручную подключившись к почтовому серверу, то сообщение будет отклонено. При этом будет получен ответ 550, похожий на следующий:
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a>Дополнительные сведения

[Поддержка проверки сообщений, подписанных с помощью DKIM](support-for-validation-of-dkim-signed-messages.md)
  

