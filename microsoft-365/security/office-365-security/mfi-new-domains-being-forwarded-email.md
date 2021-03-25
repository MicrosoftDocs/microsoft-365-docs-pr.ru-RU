---
title: Анализ новых доменов, на которые пересылаются сообщения электронной почты
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Администраторы могут узнать, как использовать новые домены, передав данные электронной почты в панели мониторинга потока почты в Центре соответствия требованиям & безопасности, чтобы выяснить, когда их пользователи переадружали сообщения на внешние домены, которые никогда не были переадружались.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2f3a5f125a045176f152ccd079ebe7f7e40bc39f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205138"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Новые домены, которые будут отправлены по электронной почте в Центре & безопасности

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Существуют веские бизнес-причины для отправки сообщений электронной почты внешним получателям в определенных доменах. Однако подозрительным является то, что пользователи в вашей организации внезапно начинают отправлять сообщения на домен, в котором никто из вашей организации никогда не переадверял сообщения в (новый домен).

Это условие может указывать на то, что учетные записи пользователей скомпрометированы. Если вы подозреваете, что учетные записи были скомпрометированы, см. в сообщении [Responding to a compromised email account.](responding-to-a-compromised-email-account.md)

Сведения **о новых доменах,** [которые](https://protection.office.com) будут перенаадють по электронной почте в Центре соответствия требованиям & безопасности, будут извещение о том, когда пользователи в вашей организации перенаадлиют сообщения в новые домены.

Это представление появляется только при обнаружении проблемы и отображается на странице [отчета о переадпорте.](view-mail-flow-reports.md#forwarding-report)

![Анализ новых доменов, на которые пересылаются сообщения электронной почты](../../media/mfi-new-domains-being-forwarded.png)

При нажатии на виджет появляется флажок, в котором можно найти дополнительные сведения о переадпортных сообщениях, включая ссылку на отчет [о переадпорте.](view-mail-flow-reports.md#forwarding-report)

![Подробные сведения, которые появляются после нажатия на новые домены, отправленные по электронной почте.](../../media/mfi-new-domains-being-forwarded-details.png)

Вы также можете получить эту страницу сведений,  когда вы  выберите представление после нажатия Просмотреть все в области & рекомендации на (**Отчеты** \> **панель мониторинга** или <https://protection.office.com/insightdashboard> ).

Чтобы предотвратить автоматическую передачу сообщений во внешние домены, настройте удаленный домен для некоторых или всех внешних доменов. Дополнительные сведения см. в [рублях Управление удаленными доменами в Exchange Online.](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)

## <a name="related-topics"></a>Статьи по теме

Сведения о других сведениях в панели мониторинга потока почты см. в странице Анализ потока почты в Центре [& соответствия](mail-flow-insights-v2.md)требованиям.