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
description: Администраторы могут узнать, как использовать новые домены, пересылаемые по электронной почте, на панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям, чтобы выяснить, когда их пользователи пересылают сообщения на внешние домены, на которые никогда не пересылались сообщения. &
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a4429f1657861091082fdfaedb52c85cec3a0cc1
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150609"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Новые домены, перена которые перена электронная почта передается в Центре безопасности & соответствия требованиям

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Относится к**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender для Office 365 (план 1) и план 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Существуют допустимые бизнес-причины для переадружия сообщений электронной почты внешним получателям в определенных доменах. Тем не менее, это подозрительно, когда пользователи в вашей организации внезапно начинают переададантовку сообщений на домен, в который никто в вашей организации никогда не переадрил сообщения (новый домен).

Это условие может указывать на то, что учетные записи пользователей скомпрометированы. Если вы подозреваете, что учетные записи были скомпрометированы, см. ответ на компрометации учетной [записи электронной почты.](responding-to-a-compromised-email-account.md)

Сведения **о новых доменах,** перена которые будут перена отправляться по электронной почте в Центре безопасности и соответствия & соответствия требованиям, будут отправлять сообщения пользователям в организации на новые домены. [](https://protection.office.com)

Эта информация отображается только при обнаружении проблемы и отображается на странице отчета ["Переад](view-mail-flow-reports.md#forwarding-report) сообщений".

![Анализ новых доменов, на которые пересылаются сообщения электронной почты](../../media/mfi-new-domains-being-forwarded.png)

При нажатии мини-приложения появится элемент, в котором можно найти дополнительные сведения о переададантных сообщениях, в том числе ссылку на отчет о [переадпорте.](view-mail-flow-reports.md#forwarding-report)

![Flyout Details that appears after clicking on the New domains being forwarded email insight](../../media/mfi-new-domains-being-forwarded-details.png)

Вы также можете вернуться на эту страницу  сведений при выборе статистики после нажатия кнопки "Просмотреть все в области "Лучшие **сведения&** рекомендации"**(** панель мониторинга отчетов \>  или <https://protection.office.com/insightdashboard> ).

Чтобы запретить автоматическую переадружение сообщений на внешние домены, настройте удаленный домен для некоторых или всех внешних доменов. Дополнительные сведения см. в под [управлением удаленных доменов в Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)

## <a name="related-topics"></a>Связанные статьи

Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)
