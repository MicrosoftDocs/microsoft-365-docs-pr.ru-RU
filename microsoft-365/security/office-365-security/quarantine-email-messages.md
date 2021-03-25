---
title: Карантин сообщений электронной почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать о карантине в Exchange Online Protection (EOP), который содержит потенциально опасные или нежелательные сообщения.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd748871cc09905f9878d5917351b1c185cc1106
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205780"
---
# <a name="quarantined-email-messages-in-eop"></a>Карантин сообщений электронной почты в EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online карантин доступен для удержания потенциально опасных или нежелательных сообщений.

Политики по борьбе с вредоносными программами автоматически карантином *сообщение,* если любое вложение установлено, содержит вредоносные программы. Дополнительные сведения см. в [программе Configure anti-malware policies in EOP.](configure-anti-malware-policies.md)

По умолчанию полиция по борьбе со спамом обеспечивает карантин фишинговых сообщений и доставляет спам и массовые сообщения электронной почты в папку нежелательной почты пользователя. Но вы также можете создавать и настраивать политики по борьбе со спамом для карантиного спама и массовых сообщений электронной почты. Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).

Как пользователи, так и администраторы могут работать с карантинными сообщениями:

- Администраторы могут работать со всеми типами карантинов для всех пользователей. Только администраторы могут работать с сообщениями, которые были на карантине в качестве вредоносных программ, фишинга с высокой уверенностью или в результате правил потока почты (также известных как правила транспорта). Дополнительные сведения см. в разделе [Управление сообщениями и файлами на карантине в качестве администратора в EOP](manage-quarantined-messages-and-files.md).

- Пользователи могут работать с карантинными сообщениями, в которых они являются получателем, если сообщение было на карантине в качестве спама, массовой электронной почты или (по апрель 2020 г.) фишинга. Дополнительные сведения см. в [сообщении Find and release quarantined messages as a user in EOP.](find-and-release-quarantined-messages-as-a-user.md)

  Чтобы запретить пользователям управлять собственными фишинговыми сообщениями с карантином, администраторы  могут настроить другое действие для решения о фильтрации электронной почты фишинга в политиках по борьбе со спамом. Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).

- Администраторы и пользователи могут сообщать о ложных срабатывающих в Microsoft на карантине.

Дополнительные сведения о карантине см. в [faq quarantine.](quarantine-faq.md)
