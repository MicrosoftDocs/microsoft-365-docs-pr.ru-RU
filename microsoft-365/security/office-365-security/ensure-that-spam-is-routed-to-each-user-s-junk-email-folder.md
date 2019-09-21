---
title: Настройка гарантированной отправки нежелательной почты в соответствующую папку каждого пользователя
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/16/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Администраторы могут научиться маршрутизировать нежелательную почту в папки нежелательной почты пользователя в Exchange Online Protection.
ms.openlocfilehash: dc37f2428e009f00a2d6d9dd15d5d2cd505f267a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090112"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Настройка гарантированной отправки нежелательной почты в соответствующую папку каждого пользователя

> [!IMPORTANT]
> Сведения, представленные в этом разделе, касаются только пользователей Exchange Online Protection (EOP), чьи почтовые ящики размещаются локально в гибридном развертывании. Пользователям Exchange Online, чьи почтовые ящики размещаются в Office 365, не нужно выполнять эти команды. 
  
Для пользователей EOP нежелательная почта по умолчанию перемещается в соответствующую папку получателя. Чтобы это действие работало с локальными почтовыми ящиками, необходимо настроить правила для почтовых ящиков Exchange (также называемые правилами транспорта) на локальных пограничных серверах или серверах-концентраторах, чтобы обнаружить заголовки нежелательной почты, добавленные EOP. Эти правила для этих почтовых ящиков устанавливают степень вероятности нежелательной почты (SCL), используемую свойством SclJunkThreshold командлета Set-OrganizationConfig, для перемещения спама в папку нежелательной почты каждого почтового ящика. 
  
### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a>Добавление правил для почтового процесса для перемещения спама в папку нежелательной почты с помощью Windows PowerShell

1. Откройте командную консоль Exchange для локального сервера Exchange Server. Сведения о том, как открыть командную консоль Exchange в локальной организации Exchange, см. в статье **Open the Shell**.
    
2. Выполните следующую команду, чтобы перенаправлять отфильтрованную по содержимому нежелательную почту в папку "Нежелательная почта":
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    Где  _NameForRule_  имя нового правила, например JunkContentFilteredMail. 
    
3. Выполните следующую команду, чтобы перенаправлять сообщения, отмеченные как нежелательные, перед их попаданием в фильтр содержимого и папку нежелательной почты:
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    Где  _NameForRule_  это имя нового правила, например JunkMailBeforeReachingContentFilter. 
    
4. Выполните следующую команду, чтобы направлять сообщения от заблокированных отправителей, например в списке **блокировок отправителя**, в папку нежелательной почты: 
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    Где  _NameForRule_  это имя нового правила, например JunkMailInSenderBlockList. 
    
Если вы не хотите использовать действие **Переместить сообщение в папку нежелательной почты**, можно выбрать другое действие с помощью политик фильтрации содержимого в Центре администрирования Exchange. Дополнительные сведения см. в статье [Настройте политики защиты от спама](configure-your-spam-filter-policies.md). Дополнительные сведения об этих полях в заголовке сообщения см. в статье [Заголовки сообщений по защите от нежелательной почты](anti-spam-message-headers.md).
  

> [!TIP]
> Если вы не хотите использовать действие **переместить сообщение в папку нежелательной почты** , вы можете выбрать другое действие в политиках фильтрации содержимого в центре администрирования Exchange. Дополнительные сведения см. в статье [Configure your spam filter policies](configure-your-spam-filter-policies.md). Для получения дополнительных сведений об этих полях в заголовке сообщения просмотрите [заголовки сообщений по защите от нежелательной почты](anti-spam-message-headers.md).
> 
## <a name="see-also"></a>См. также

[Командлет New-TransportRule](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

