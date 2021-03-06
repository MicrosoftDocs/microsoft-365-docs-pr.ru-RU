---
title: Вероятность нежелательной почты
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
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать об уровне доверия к нежелательной почте (SCL), который применяется к сообщениям в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 55e64c72cc472e98baa8eb71e23dafb6b276ba01
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625285"
---
# <a name="spam-confidence-level-scl-in-eop"></a>Уровень доверия к нежелательной почте (SCL) в EOP

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без Exchange Online почтовых ящиков входящие сообщения проходят фильтрацию нежелательной почты в EOP и за них назначена оценка нежелательной почты. Этот показатель соединялся с отдельным уровнем доверия к нежелательной почте (SCL), который добавляется к сообщению в X-header. Более высокий уровень SCL указывает на то, что сообщение чаще является нежелательной почтой. EOP принимает меры по сообщению на основе SCL.

Значение SCL и действия по умолчанию, которые принимаются в сообщениях, описаны в следующей таблице. Дополнительные сведения о действиях, которые можно принять для сообщений на основе вердикта по фильтрации нежелательной почты, см. в статью Настройка политик по борьбе со спамом [в EOP.](configure-your-spam-filter-policies.md)

****

|SCL|Определение|Действие по умолчанию|
|:---:|---|---|
|–1|В сообщении была пропущена фильтрация нежелательной почты. Например, сообщение от безопасного отправитель, было отправлено безопасному получателю или находится с сервера источника электронной почты в списке ip Allow. Дополнительные сведения см. в [списке Создание безопасных списков](create-safe-sender-lists-in-office-365.md)отправитель в EOP.|Доставка сообщения в папку входящих сообщений.|
|0, 1|Фильтрация нежелательной почты определила, что сообщение не является спамом.|Доставка сообщения в папку входящих сообщений.|
|5, 6|Фильтрация нежелательной почты помечена как **спам**|Доставка сообщения в папку нежелательной почты получателя.|
|9 |Фильтрация нежелательной почты помечена как спам **с высокой уверенностью**|Доставка сообщения в папку нежелательной почты получателя.|
|

Вы заметите, что SCL 2, 3, 4, 7 и 8 не используются для фильтрации нежелательной почты.

Для штамповки SCL в сообщениях можно использовать правила потока почты (также известные как правила транспорта). Если для набора SCL используется правило потока почты, значения 5 или 6 вызывают действие фильтрации нежелательной почты для нежелательной почты, а значения 7, 8 или 9 вызывают действие фильтрации нежелательной почты для нежелательной почты с высокой **уверенностью.** Дополнительные сведения см. в тексте Правила потока почты, чтобы установить уровень доверия к нежелательной почте [(SCL) в сообщениях.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)

Как и в SCL, уровень массовой жалобы (BCL) определяет плохое массовое сообщение электронной почты (также известное как _серая почта)._ Более высокий уровень BCL указывает, что массово рассылаемое сообщение часто вызовет жалобы (и поэтому скорее всего является спамом). Порог BCL настраивается в политиках по борьбе со спамом. Дополнительные сведения см. в перенастройке политик защиты от нежелательной почты в [EOP,](configure-your-spam-filter-policies.md)уровне массовой [жалобы (BCL) в EOP)](bulk-complaint-level-values.md)и в чем разница между нежелательной электронной почтой и массовой электронной [почтой?](what-s-the-difference-between-junk-email-and-bulk-email.md).

****

![Короткий значок для LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Откройте для себя бесплатные видео-курсы **для Microsoft 365 администраторов** и ИТ-специалистов, которые будут доставлены в LinkedIn Learning.
