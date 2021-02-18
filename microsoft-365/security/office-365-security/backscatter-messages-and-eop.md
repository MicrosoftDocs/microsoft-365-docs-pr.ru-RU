---
title: Подложное уведомление о недоставленном сообщении в EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: В этой статье вы узнаете о backscatter и Microsoft Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d9556c69e5db460933b355e8bf12903d56f21b5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286973"
---
# <a name="backscatter-in-eop"></a>Подложное уведомление о недоставленном сообщении в EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

*Подкадровка* — это отчеты о неотвечаемой доставке (также известные как сообщения о возврате), которые вы получаете для сообщений, которые вы не отправили. Спамеры подделывают (подделывают) адрес от: адреса своих сообщений, и они часто используют реальные адреса электронной почты, чтобы сузить доверие к своим сообщениям. Таким образом, когда отправители нежелательной почты неизбежно отправляют сообщения несуществующим получателям (нежелательная почта является большой объемной операцией), почтовый сервер назначения, по сути, обманным образом возвращает недостижимое сообщение в сообщении о недоверенном сообщении не подделанное отправитель в адресе Отправитель.

В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online EOP делает все возможное для идентификации и передачи сообщений из неявных источников без создания сообщения о неудаленном сообщении. Но в зависимости от объема электронной почты, которая проходит через службу, всегда существует вероятность того, что EOP непреднамеренно отправит подкадровые сообщения.

Backscatterer.org списке заблокированных (также известных как список заблокированных DNS или DNSBL) почтовых серверов, отвечающих за отправку подкадров, и в этом списке могут появиться серверы EOP. Но мы не пытаемся удалить нас из списка заблокированных Backscatterer.org, так как он не является списком лиц, рассыланий нежелательной почты (по их собственному допуску).

> [!TIP]
> Веб-сайт Backscatter.org ( ) рекомендует использовать свою службу для проверки входящих сообщений электронной почты в безопасном режиме вместо режима "Отклонить" (крупные почтовые службы почти всегда отправляют некоторые <http://www.backscatterer.org/?target=usage> подмены).
