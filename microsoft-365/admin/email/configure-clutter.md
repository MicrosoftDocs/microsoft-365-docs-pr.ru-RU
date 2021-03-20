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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Узнайте, как включить или отключить функцию Clutter для всех или определенных пользователей в организации с помощью Exchange PowerShell. '
ms.openlocfilehash: ac68893bc0aeea5ab214698c54524921e2b1921d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915906"
---
# <a name="configure-clutter-for-your-organization"></a>Настройка функции 'Несрочные' для организации

> [!TIP]
> [Сфокусированный почтовый ящик](../setup/configure-focused-inbox.md) заменит clutter. Дополнительные новости. [Обновление по сфокусированным почтовым ящикам и нашим планам по помехам](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Как администратору может потребоваться управлять функцией Clutter в Microsoft 365. Чтобы включить или отключить эту функцию для пользователей организации, используйте Exchange PowerShell. (Физические лица могут включить и отключить его с помощью этих инструкций: [Выключите или нагромождение в Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).
  
Сведения об [использовании PowerShell с Помощью PowerShell](/powershell/exchange/exchange-online-powershell) с Exchange Online и Подключение к Exchange Online [PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell) Необходимо иметь учетную запись, которая имеет хотя бы роль администратора службы Exchange и возможность подключения к Exchange Online с PowerShell. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Включение функции "Ненужные" с помощью Exchange PowerShell

Вы можете включить функцию "Ненужные" вручную для почтового ящика, выполнив командлет [Set-Clutter](/powershell/module/exchange/set-clutter). Вы также можете просматривать параметры функции "Ненужные" для почтовых ящиков в вашей организации с помощью командлета [Get-Clutter](/powershell/module/exchange/get-clutter). 
  
Включение функции "Ненужные" для одного пользователя (Allie Bellew)
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Отключение функции "Ненужные" с помощью Exchange PowerShell

Вы можете отключить функцию "Ненужные" вручную для почтового ящика, выполнив командлет [Set-Clutter](/powershell/module/exchange/set-clutter). Вы также можете просматривать параметры функции **Ненужные** для почтовых ящиков в вашей организации с помощью командлета [Get-Clutter](/powershell/module/exchange/get-clutter). 
  
Отключение функции "Ненужные" для одного пользователя (Allie Bellew)
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Если вы использовали PowerShell для массового создания пользователей, вам потребуется выполнить командлет [Set-Clutter](/powershell/module/exchange/set-clutter) для почтового ящика каждого пользователя. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>Отображение переключателя функции "Несрочные" для пользователей в Outlook в Интернете
<a name="bkmk_onoff"> </a>

В качестве администратора можно повторно включить clutter с помощью Exchange PowerShell. После этого функция "Сортировка почты" отключается, а функция "Несрочные" снова становится активной. 
  
 **Если вы используете Outlook в Интернете с подпиской Microsoft 365 Бизнес Премиум:**
  
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

[Использование функции "Несрочные" для сортировки сообщений с низким приоритетом в Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[Использование clutter для сортировки сообщений с низким приоритетом в OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[Отключение функции "Несрочные" в Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
