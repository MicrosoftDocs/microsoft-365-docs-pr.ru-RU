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
ms.openlocfilehash: 3cdc556a8cc193466d150fc82298796779841cca
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165959"
---
# <a name="backscatter-in-eop"></a>Подложное уведомление о недоставленном сообщении в EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender для Office 365 (план 1 и план 2)](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

*Подкадровка* — это отчеты о неотвечаемой доставке (также известные как сообщения о возврате), которые вы получаете для сообщений, которые вы не отправили. Спамеры подделывают (подделывают) адрес от: адреса своих сообщений, и они часто используют реальные адреса электронной почты, чтобы сузить доверие к своим сообщениям. Таким образом, когда отправители нежелательной почты неизбежно отправляют сообщения несуществующим получателям (нежелательная почта является большой объемной операцией), почтовый сервер назначения, по сути, обманным образом возвращает недостижимое сообщение в сообщении о недоверенном сообщении поддельной отправителю в адресе Отправитель.

В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online EOP делает все возможное для определения и передачи сообщений из неявных источников без создания NDR. Но в зависимости от объема электронной почты, которая проходит через службу, всегда существует вероятность, что EOP непреднамеренно отправит подкадровые сообщения.

Backscatterer.org списке заблокированных (также известных как список заблокированных DNS или DNSBL) почтовых серверов, отвечающих за отправку подкадров, и в этом списке могут появиться серверы EOP. Но мы не пытаемся удалить нас из списка заблокированных Backscatterer.org, так как он не является списком лиц, рассыланий нежелательной почты (по их собственному признанию).

> [!TIP]
> Веб-сайт Backscatter.org () рекомендует использовать свою службу для проверки входящих сообщений электронной почты в безопасном режиме вместо режима "Отклонить" (крупные почтовые службы почти всегда отправляют <http://www.backscatterer.org/?target=usage> подмену).
