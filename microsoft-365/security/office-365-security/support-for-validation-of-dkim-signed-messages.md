---
title: Поддержка проверки подписанных сообщений с подписанными ключами домена почтой (DKIM)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Узнайте о проверке подписанных DKIM сообщений в Exchange Online Protection и Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8695e25000390cf6c5d58adf63db1984c873d75b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206458"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Поддержка проверки сообщений, подписанных с помощью DKIM

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) и Exchange Online поддерживают входящие проверки сообщений идентифицированной почты доменных ключей[(DKIM).](https://www.rfc-editor.org/rfc/rfc6376.txt)

DKIM проверяет, что сообщение электронной почты не было поддельным кем-то  другим, и было отправлено из домена, в который оно поступило.  Оно связывает сообщение электронной почты с организацией, отправив ее. Проверка DKIM автоматически используется для всех сообщений, отправленных с помощью IPv6. Microsoft 365 поддерживает DKIM при отправлении почты по IPv4. (Дополнительные сведения о поддержке IPv6 см. в сообщении [Support for anonymous inbound email messages over IPv6.)](support-for-anonymous-inbound-email-messages-over-ipv6.md)

DKIM проверяет цифровое подписанное сообщение, которое DKIM-Signature в загоне заглавных окне сообщений. Результаты проверки DKIM-Signature штампуются в Authentication-Results. Текст заголовка сообщения имеет указанные ниже формат (где contoso.com  отправитель).

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Дополнительные сведения о заглавной Authentication-Results см. в сообщении RFC 7001 (Поле загонщика сообщений для указания состояния проверки подлинности[сообщений.](https://www.rfc-editor.org/rfc/rfc7001.txt) Реализация DKIM Корпорации Майкрософт соответствует этой RFC.

Администраторы могут Exchange правила потока почты [(также](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) известные как правила транспорта) по результатам проверки DKIM. Эти правила потока почты позволят администраторам фильтровать или маршрутить сообщения по мере необходимости.