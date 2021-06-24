---
title: Трассировка сообщений на Microsoft 365 Defender портале
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут использовать ссылку трассировки сообщений на портале Microsoft 365 Defender, чтобы узнать, что произошло с сообщениями.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108131"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a>Трассировка сообщений на Microsoft 365 Defender портале

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Трассировка сообщений на портале Microsoft 365 Defender сообщений электронной почты во время их перемещения по Exchange Online организации. Вы можете определить, было ли сообщение получено, отклонено, отложено или доставлено службой. В нем также показано, какие действия были приняты в сообщении до его окончательного состояния.

Вы можете использовать сведения из трассировки сообщений, чтобы эффективно отвечать на вопросы пользователей о том, что произошло с сообщениями, устранять проблемы с потоком почты и проверять изменения политики.

> [!NOTE]
> Трассировка сообщений на Microsoft 365 Defender портале — это просто пропуск трассировки сообщения в центре Exchange администрирования. Дополнительные сведения см. в сообщении в [центре администрирования Exchange.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Для использования трассировки сообщений  необходимо быть  членом групп  ролей в области управления **организацией,** управления соответствием требованиям или службы поддержки в Exchange Online. Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Примечание.** Членство в соответствующей Azure Active Directory роли в Центр администрирования Microsoft 365 предоставляет пользователям необходимые  разрешения и разрешения для других функций в Microsoft 365. Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).

- Максимальное количество сообщений, отображаемых в результатах трассировки сообщений, зависит от выбранного типа отчета (подробнее см. раздел [Выберите](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) тип отчета). Комлет [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) в Exchange Online PowerShell или автономный EOP PowerShell возвращает все сообщения в результатах.

## <a name="open-message-trace"></a>Трассировка открытого сообщения

На портале Microsoft 365 Defender () перейдите к электронной почте <https://security.microsoft.com> **&** \> **совместной Exchange сообщений**. Или, чтобы перейти непосредственно на страницу трассировки сообщений, используйте <https://admin.exchange.microsoft.com/#/messagetrace> .

На этом этапе откроется трассировка сообщений в EAC. Дополнительные сведения см. в сообщении в [центре администрирования Exchange.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)
