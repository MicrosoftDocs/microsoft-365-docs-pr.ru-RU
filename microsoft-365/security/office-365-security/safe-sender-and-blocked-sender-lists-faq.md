---
title: Списки надежных и заблокированных отправителей в Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Чтобы пересылаемые через службу сообщения не помечались как спам, администратор Exchange Online или Exchange Online Protection (EOP) может создать списки надежных и заблокированных отправителей для пользователей в вашей организации.
ms.openlocfilehash: 5530fa8c8ee5a83c4e8515a8f31f91e45b2ec97b
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971677"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Списки надежных и заблокированных отправителей в Exchange Online

Чтобы пересылаемые через службу сообщения не помечались как спам, администратор Exchange Online или Exchange Online Protection (EOP) может создать списки надежных и заблокированных отправителей для пользователей в вашей организации.

*Ознакомьтесь с обновленной версией советов и процедур для работы с этими списками в качестве администратора* , [чтобы предотвратить пометку сообщений электронной почты как спама в Office 365](https://docs.microsoft.com/microsoft-365/compliance/prevent-email-from-being-marked-as-spam).

Если вы не являетесь администратором и хотите управлять собственной нежелательной почтой в Outlook с помощью списка надежных отправителей, ознакомьтесь с инструкциями в статье[Обзор фильтра нежелательной почты](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>Сколько надежных и заблокированных отправителей можно добавить в Exchange Online?

Ограничения на количество надежных и заблокированных отправителей в Exchange Online, Active Directory и Outlook отличаются. Они представлены ниже.

- Лимит надежного отправителя: 1 024

- Предельное количество заблокированных отправителей: 500

Примечание.

Вы можете столкнуться с ошибкой, описанной в статье [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app). Чтобы устранить эту проблему, снимите флажок "доверять сообщениям от контактов". Кроме того, уменьшите количество адресов электронной почты в папке "Контакты" по умолчанию, чтобы оно прибыло в пределах максимально допустимого значения 1024 в Exchange Online, для которого задан атрибут "Макссафесендерс". Для получения дополнительных сведений об этом атрибуте и командлете Set – Mailbox Сисе следующий раздел:

[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a>См. также

[Фильтрация отправителей в Exchange Server](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
