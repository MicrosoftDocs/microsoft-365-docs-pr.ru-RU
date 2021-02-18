---
title: Анализ состояния потока почты верхнего домена на панели мониторинга потока почты
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать анализ состояния потока обработки почты верхнего домена на панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям & для устранения неполадок потока обработки почты, связанных с их записями MX.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ecda78047384a581a1043d0049b8dd25fadbe27
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290625"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Анализ состояния потока обработки почты верхнего домена в Центре & соответствия требованиям

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

The **Top domain mail flow status** insight in the Mail flow [dashboard](mail-flow-insights-v2.md) in the Security & [Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.

Эти сведения помогают выявлять домены, в которые возникли проблемы с ***потоком*** почты, и устранять их неполадки. Например, домен не может получать внешнюю электронную почту, так как домен истек или домен имеет неправильную запись MX.

![Мини-приложения состояния потока обработки почты на панели мониторинга потока обработки почты в Центре безопасности & соответствия требованиям](../../media/mfi-top-domain-mail-flow-status-widget.png)

При **нажатии** кнопки "Просмотреть сведения" в мини-приложения появляется элемент "Состояние домена", который отображает дополнительные сведения о состоянии каждого домена: 

- **Домен**
- **Предыдущая запись MX**
- **Текущая запись MX**
- **Состояние получения электронной почты**
- Состояние домена: зеленая метка указывает, что текущая запись MX (на момент нажатия мини-приложения) соответствует значению, записанном в записи, а домен получил электронную почту в течение последних двух часов.

  Красный X указывает, что запись MX была изменена, а домен не получал электронной почты за последние 6 часов. Скорее всего, это указывает на то, что срок действия домена истек или что запись MX была неправильно обновлена. Обратитесь к регистратору доменных имен или службе размещения DNS, чтобы узнать, истек ли срок действия домена или запись MX домена неправильная.

Чтобы **просмотреть те** же сведения о дополнительных доменах, нажмите кнопку "Просмотреть".

![Flyout Details in the Top domain mail flow status insight](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>См. также

Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)
