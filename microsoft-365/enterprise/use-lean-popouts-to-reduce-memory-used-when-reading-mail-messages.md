---
title: Использование экономичных всплывающих окон для уменьшения объема памяти, используемой при чтении почтовых сообщений
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: В этой статье содержатся сведения об использовании экономичных всплывающих окон для улучшения скорости загрузки сообщений в Outlook в Интернете.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693446"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Использование экономичных всплывающих окон для уменьшения объема памяти, используемой при чтении почтовых сообщений

В этой статье содержатся сведения о том, как улучшить производительность загрузки сообщений в Outlook в Интернете. Эта статья является частью [планирования сети и настройки производительности для проекта Office 365](https://aka.ms/tune) .
  
Как глобальный администратор Office 365 вы можете настроить Outlook в Интернете, чтобы обеспечить _экономичное всплывающих окон_, меньшее количество сообщений электронной почты в Microsoft EDGE или Internet Explorer. Когда экономичный всплывающих окон настраивается для Outlook в Интернете, загружаются серверные компоненты, которые оптимизируют производительность.
  
> [!NOTE]
> За март 2018, экономичный всплывающих окон недоступен для сообщений, в которых указаны ограничения прав на использование, например, управления правами на доступ к данным (IRM).
  
Эти функции продолжат работу в главном окне, но недоступны в экономичных всплывающих окон:
  
- Надстройки Outlook
  
- Присутствие в Skype для бизнеса
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Настройка экономичного всплывающих окон для всех пользователей в организации Office 365
  
1. [Подключитесь к Exchange Online с помощью удаленной оболочки PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).
  
2. Выполните командлет [Set – OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) с параметром леанпопаутенаблед следующим образом:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  Например, чтобы включить экономичный всплывающих окон для всех пользователей в Организации:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  Чтобы отключить экономичный всплывающих окон для всех пользователей в Организации:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
