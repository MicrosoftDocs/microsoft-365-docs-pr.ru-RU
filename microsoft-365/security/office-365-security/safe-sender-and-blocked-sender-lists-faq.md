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
ms.openlocfilehash: 5b1082e0a8f492da1ebc559b0958a6ef76f9a70c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091371"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Списки надежных и заблокированных отправителей в Exchange Online

Чтобы пересылаемые через службу сообщения не помечались как спам, администратор Exchange Online или Exchange Online Protection (EOP) может создать списки надежных и заблокированных отправителей для пользователей в вашей организации. 
  
 *Обновленные подсказки и процедуры по работе с этими списками от имени администратора приведены в статье* [Предотвращение попадания электронной почты в спам в EOP и Office 365](https://go.microsoft.com/fwlink/p/?LinkID=534224). 
  
Если вы не администратор и просто хотите управлять нежелательной почтой в Outlook с помощью списка надежных отправителей, просмотрите общие сведения о [фильтре нежелательной почты](https://go.microsoft.com/fwlink/?LinkId=817222). 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>Сколько надежных и заблокированных отправителей можно добавить в Exchange Online?

Ограничения на количество надежных и заблокированных отправителей в Exchange Online, Active Directory и Outlook отличаются. Они представлены ниже.
  
- Лимит надежного отправителя: 1 024
    
- Предельное количество заблокированных отправителей: 500
    
Примечание.
  
Вы можете столкнуться с ошибкой, описанной в статье [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app). Чтобы устранить эту проблему, снимите флажок "доверять сообщениям от контактов". Кроме того, уменьшите количество адресов электронной почты в папке "Контакты" по умолчанию, чтобы оно прибыло в пределах максимально допустимого значения 1024 в Exchange Online, для которого задан атрибут "Макссафесендерс". Для получения дополнительных сведений об этом атрибуте и командлете Set – Mailbox Сисе следующий раздел:
  
[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)
  
## <a name="see-also"></a>См. также

[Sender filtering in Exchange 2016](http://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)

