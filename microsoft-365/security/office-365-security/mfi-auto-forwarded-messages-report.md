---
title: Анализ автоматически пересылаемых сообщений
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Администраторы могут узнать о отчете о автоматических пересылаемом сообщении на панели мониторинга потока почты в Центре & соответствия требованиям.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1882c0506093816e9bb85ae3ba90decd4e0e0d74
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206407"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Сведения о автоматических сообщениях в Центре & безопасности

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

В **информационной** панели потока почты в Центре обеспечения соответствия требованиям & автоматически переадружаемой из организации сообщения получателям во внешние [](mail-flow-insights-v2.md) домены. [](https://protection.office.com)

![Виджет автопроизводимых сообщений в Центре & соответствия требованиям](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Сведения о автоматических сообщениях

При нажатии на количество сообщений в виджете появляется поле для вылетов, которое отображает дополнительные сведения о автоматически переададных сообщениях:

- **Автопроизводимые сообщения путем переададки методов:**

  - **По правилам потока почты**
  - **По правилам "Входящие"**
  - **По SMTP** пересылания : Этот метод указывает автоматическую пересылку, что администраторы могут настроить на почтовый ящик, как описано в Настройка пересылания электронной почты [для почтового ящика](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).
  - Дополнительные сведения по ссылке [на отчет о переадпорте.](view-mail-flow-reports.md#forwarding-report)

- **Автопроизводимые сообщения доменов и пользователей:**

  - **Топ-5 доменов, переад**
  - **Новые домены (на прошлой неделе)**
  - **Топ-5 пользователей переададки**
  - **Новые пользователи (на прошлой неделе)**
  - Дополнительные сведения по ссылке на отчет об [изменениях](mfi-new-users-forwarding-email.md#forwarding-modifications-report) в переадпорте.

![Подробные сведения о отчете о автоматических сообщениях в Центре & безопасности](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Наблюдения

На основе данных отчета создаются два анализа:

- [Новые пользователи, переададные электронной почте](mfi-new-users-forwarding-email.md)
- [Новые домены, отправленные по электронной почте](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>См. также

Сведения о других сведениях в панели мониторинга потока почты см. в странице Анализ потока почты в Центре [& соответствия](mail-flow-insights-v2.md)требованиям.