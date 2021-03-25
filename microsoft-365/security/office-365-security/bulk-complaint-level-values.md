---
title: Объемные значения уровня жалоб
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать о массовых значениях соответствия требованиям,которые используются в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d85dca6e18ebdad4d8f2a5c5f6c5b613c23b47d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205081"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Уровень массовой жалобы (BCL) в EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online EOP назначает входящие сообщения из массовых почтовых ящиков на уровне, удовлетворяемом требованиям. BCL добавляется в сообщение в X-header и похож на уровень доверия нежелательной почты [(SCL),](spam-confidence-levels.md) который используется для идентификации сообщений как нежелательной почты. Более высокий уровень BCL указывает на то, что массовое сообщение с большей вероятностью вызывает жалобы (и, следовательно, чаще является нежелательной почтой). Корпорация Майкрософт использует внутренние и сторонние источники для идентификации массовой почты и определения соответствующего BCL.

Массовые почтовые ящики различаются по шаблонам отправки, созданию контента и приему получателей. Хорошие массовые почтовые ящики отправляют нужные сообщения с соответствующим контентом своим подписчикам. Такие сообщения вызывают очень мало жалоб со стороны получателей. Другие же системы массовой рассылки распространяют нежелательные сообщения, похожие на спам, и тем самым вызывают множество жалоб от получателей. Сообщения из массовой почты называются массовой почтой или серой почтой.

 Фильтрация нежелательной почты отмечает сообщения как массовая электронная почта, основанная на пороге BCL (значение по умолчанию или указанное значение) и принимает указанное действие в сообщении (действие по умолчанию — доставка сообщения в папку нежелательной почты получателя).  Дополнительные сведения см. в [рублях Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Пороговые значения BCL описаны в следующей таблице.

****

|BCL|Описание|
|:---:|---|
|0|Сообщение отправлено без использования систем массовой рассылки.|
|1, 2, 3|Сообщение от системы массовой рассылки, которое вызывает малое количество жалоб.|
|4, 5, 6, 7<sup>\*</sup>|Сообщение от системы массовой рассылки, которое может вызвать как малое, так и большое количество жалоб.|
|8, 9|Сообщение от отправитель массы, который генерирует большое количество жалоб.|
|

<sup>\*</sup> Это пороговое значение по умолчанию, используемого в политиках по борьбе со спамом.
