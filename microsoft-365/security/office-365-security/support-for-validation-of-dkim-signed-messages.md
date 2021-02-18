---
title: Поддержка проверки сообщений с подписью DKIM
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
description: Проверка сообщений с подписью DKIM в Exchange Online Protection и Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9da41cc7918b36e1aa6a4a8cc48aea6cd2a865c6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290265"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Поддержка проверки сообщений, подписанных с помощью DKIM

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online Protection (EOP) и Exchange Online поддерживают входящие проверки сообщений почты с идентифицированными ключами домена[(DKIM).](https://www.rfc-editor.org/rfc/rfc6376.txt)

DKIM проверяет, не было ли  сообщение электронной почты подменой другими  и отправлено из домена, с него поступило сообщение. Оно связывает сообщение электронной почты с организацией, которая его отправила. Проверка DKIM используется автоматически для всех сообщений, отправленных с помощью IPv6. Microsoft 365 также поддерживает DKIM при пересылке почты по IPv4. (Дополнительные сведения о поддержке IPv6 см. в поддержке анонимных входящие сообщения электронной почты [по IPv6.)](support-for-anonymous-inbound-email-messages-over-ipv6.md)

DKIM проверяет сообщение с цифровой подписью, которое отображается в DKIM-Signature в его загоне. Результаты проверки DKIM-Signature помеются в Authentication-Results. Текст заголовка сообщения имеет указанные ниже формат (где contoso.com  отправитель).

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Дополнительные сведения о Authentication-Results сообщений см. в документе RFC 7001 ( Поле загона сообщения для указания состояния проверки[подлинности сообщений.](https://www.rfc-editor.org/rfc/rfc7001.txt) Реализация DKIM корпорации Майкрософт соответствует этому RFC.

Администраторы могут создавать правила [потока](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) почты Exchange (также известные как правила транспорта) по результатам проверки DKIM. Эти правила потока почты позволяют администраторам фильтровать или маршрутить сообщения по мере необходимости.
