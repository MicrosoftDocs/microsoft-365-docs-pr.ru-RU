---
title: Настройка функции 'Несрочные' для организации
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Сведения о том, как включить или отключить функцию "несрочные" для всех или определенных пользователей в Организации с помощью Exchange PowerShell. '
ms.openlocfilehash: 65aa614095ecbebaad3d7eb38af1e74166ce20ac
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255287"
---
# <a name="configure-clutter-for-your-organization"></a>Настройка функции 'Несрочные' для организации

> [!TIP]
> [Сортировка папки "Входящие"](../setup/configure-focused-inbox.md) предполагает замену несрочных сообщений. Дополнительные сведения: [обновление в статье Сортировка почты и планов для несрочных сообщений](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Администратору может потребоваться управлять функцией "несрочные" в Office 365. Чтобы включить или отключить эту функцию для пользователей организации, используйте Exchange PowerShell. (Пользователи могут включать и отключать эту функцию, следуя инструкциям в статье [Отключение и включение функции "Несрочные" в Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).) 
  
Ознакомьтесь с [использованием PowerShell с Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) и [подключитесь к Exchange Online PowerShell, чтобы](https://go.microsoft.com/fwlink/?LinkID=722415) узнать больше об использовании Exchange PowerShell. Необходимо иметь учетную запись, которая имеет по крайней мере роль администратора службы Exchange и возможность подключения к Exchange Online с помощью PowerShell. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Включение функции "Ненужные" с помощью Exchange PowerShell

Вы можете включить функцию "Ненужные" вручную для почтового ящика, выполнив командлет [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446). Вы также можете просматривать параметры функции "Ненужные" для почтовых ящиков в вашей организации с помощью командлета [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759). 
  
Включение функции "Ненужные" для одного пользователя (Allie Bellew)
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Отключение функции "Ненужные" с помощью Exchange PowerShell

Вы можете отключить функцию "Ненужные" вручную для почтового ящика, выполнив командлет [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446). Вы также можете просматривать параметры функции **Ненужные** для почтовых ящиков в вашей организации с помощью командлета [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759). 
  
Отключение функции "Ненужные" для одного пользователя (Allie Bellew)
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Если вы использовали PowerShell для массового создания пользователей, вам потребуется выполнить командлет [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) для почтового ящика каждого пользователя. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>Отображение переключателя функции "Несрочные" для пользователей в Outlook в Интернете
<a name="bkmk_onoff"> </a>

Как администратор, вы можете повторно включить функцию "несрочные" с помощью Exchange PowerShell. После этого функция "Сортировка почты" отключается, а функция "Несрочные" снова становится активной. 
  
 **При использовании Outlook в Интернете с подпиской на Office 365 для бизнеса:**
  
- если у пользователя включена функция "Несрочные": 
    
  - отображаются параметры функции "Несрочные";
    
- если у пользователя включена функция "Сортировка почты": 
    
  - параметры функции "Несрочные" не отображаются;
    
- если отключены обе функции ("Несрочные" и "Сортировка почты"): 
    
  - в параметрах почты пользователя отображаются параметры функций "Несрочные" и "Сортировка почты".
    
 **При использовании Outlook.com:**
  
- если у пользователя включена функция "Несрочные": 
    
  - отображаются параметры функции "Несрочные";
    
- если у пользователя включена функция "Сортировка почты": 
    
  - параметры функции "Несрочные" не отображаются;
    
- если отключены обе функции ("Несрочные" и "Сортировка почты"): 
    
  - в параметрах почты пользователя отображаются параметры функций "Несрочные" и "Сортировка почты";
    
- если пользователь включил функцию "Сортировка почты" раньше:
    
  - параметры функции "Несрочные" никогда не будут отображаться;
    
    в противном случае: 
    
  - параметры функции "Несрочные" отображаются.
    
## <a name="related-articles"></a>Статьи по теме
<a name="bkmk_onoff"> </a>

[Использование функции "Несрочные" для сортировки сообщений с низким приоритетом в Outlook](https://support.office.com/article/7755ebf5-4585-469b-b1ab-8b12425c6b6b.aspx)
    
[Использование функции "несрочные" для сортировки сообщений с небольшим приоритетом в OWA](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[Отключение функции "Несрочные" в Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

