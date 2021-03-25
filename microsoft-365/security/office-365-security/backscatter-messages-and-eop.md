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
description: В этой статье вы узнаете о backscatter и Microsoft Exchange Online защите (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205111"
---
# <a name="backscatter-in-eop"></a>Подложное уведомление о недоставленном сообщении в EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Backscatter* — это отчеты о невывозе (также известные как NDRs или сообщения отказов), которые вы получаете для сообщений, которые вы не отправили. Спамеры подделывают (так называемый спуфинг) поле От: своих сообщений, и часто используют реальные адреса электронной почты, чтобы вызвать доверие к своим сообщениям. Таким образом, когда спамеры неизбежно отправляют сообщения несуществующим получателям (спам — это операция с высоким уровнем громкости), сервер электронной почты назначения по сути обманным образом возвращает недостижимое сообщение в NDR поддельной отправительнице в адресе From: address.

В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online EOP делает все возможное для выявления и бесшумного сброса сообщений из сомнительных источников без создания NDR. Но, в зависимости от простого объема электронной почты, течет через службу, всегда есть возможность того, что EOP будет непреднамеренно отправлять backscatter.

Backscatterer.org поддерживает блок-список (также известный как список блоков DNS или DNSBL) серверов электронной почты, ответственных за отправку backscatter, и В этом списке могут появиться серверы EOP. Но мы не пытаемся удалить себя из списка Backscatterer.org, так как это не список спамеров (по их собственному признанию).

> [!TIP]
> Веб Backscatter.org веб-сайт () рекомендует использовать свою службу для проверки входящих сообщений электронной почты в безопасном режиме вместо режима Reject (крупные службы электронной почты почти всегда отправляют некоторые <http://www.backscatterer.org/?target=usage> backscatter).
