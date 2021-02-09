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
description: Администраторы могут узнать об отчете об автоматической пересылке сообщений на панели мониторинга потока обработки почты в Центре безопасности & соответствия требованиям.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c95c403e0b342bf0466c45804ba3975c492b8e1b
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150606"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Анализ автоматически переад вперед сообщений в Центре безопасности & соответствия требованиям

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Относится к**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender для Office 365 (план 1) и план 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Анализ автоматически пересылаемой [](mail-flow-insights-v2.md) почты на [](https://protection.office.com) панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям & отображает сведения о сообщениях, которые автоматически пересылаются из организации получателям во внешних доменах. 

![Мини-приложения "Автооададант сообщений" в Центре & соответствия требованиям](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Сведения об автоматически переададантных сообщениях

При нажатии на количество сообщений в мини-приложения появится отображаемая войдите в нее с дополнительными сведениями о сообщениях с автоматической переадной почтой:

- **Автоматическая переададка сообщений с помощью методов переадной:**

  - **По правилам потока почты**
  - **По правилам для входящих сообщений**
  - **При пересылке SMTP** этот метод указывает автоматическую пересылку, которую администраторы могут настроить для почтового ящика, как описано в описании настройки пересылки электронной почты [для почтового ящика.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)
  - Ссылка на отчет о [переададпорте для](view-mail-flow-reports.md#forwarding-report) получения дополнительных сведений.

- **Автоматически переададантные сообщения по доменам и пользователям:**

  - **5 доменов, на которые переад.**
  - **Новые домены (на прошлой неделе)**
  - **5 пользователей, переадлицющих в первую**
  - **Новые пользователи (на прошлой неделе)**
  - Ссылка на отчет об изменениях [переададантов](mfi-new-users-forwarding-email.md#forwarding-modifications-report) для получения дополнительных сведений.

![Details flyout for the Auto-forwarded messages report in the Security & Compliance Center](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Аналитика

На основе данных отчета создаются два анализа:

- [Новые пользователи, переадлиющие электронную почту](mfi-new-users-forwarding-email.md)
- [Новые домены, переададантуемые по электронной почте](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>См. также

Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)
