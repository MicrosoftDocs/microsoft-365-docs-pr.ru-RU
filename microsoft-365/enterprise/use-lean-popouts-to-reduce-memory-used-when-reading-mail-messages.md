---
title: Используйте нежирные всплывающие окни, чтобы уменьшить объем памяти, используемый при чтении сообщений электронной почты
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
description: В этой статье содержатся сведения об использовании нежирных всплывающих сообщений для повышения производительности скачивания сообщений в Outlook в Интернете.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693446"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Используйте нежирные всплывающие окни, чтобы уменьшить объем памяти, используемый при чтении сообщений электронной почты

В этой статье содержатся сведения о повышении производительности скачивания сообщений в Outlook в Интернете. Эта статья входит в состав проекта "Планирование сети и [настройка производительности для Office 365".](https://aka.ms/tune)
  
Как глобальный администратор Office 365 вы можете настроить Outlook в Интернете для доставки небольших, менее объемных в памяти версий определенных сообщений электронной почты в Microsoft Edge или Internet Explorer. При настройке нестрогого всплывающих элементов для Outlook в Интернете загружаются серверные компоненты, оптимизируемые производительностью.
  
> [!NOTE]
> С марта 2018 г. для сообщений с ограничениями прав на использование, таких как управление правами на доступ к данным (IRM), недоступны ненамеренные всплывающие сообщения.
  
Эти функции продолжат работать в главном окне, но недоступны в нежирных всплывающих окнах:
  
- Надстройки Outlook
  
- Присутствие в Skype для бизнеса
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Настройка нестрогого всплывающих всплывающих папок для всех пользователей в организации Office 365
  
1. [Подключение к Exchange Online с помощью удаленной powerShell.](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx )
  
2. Запустите [cmdlet Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) с параметром LeanPopoutEnabled следующим образом:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  Например, чтобы включить нежирные всплывающие окни для всех пользователей в организации:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  Чтобы отключить нежирные всплывающие окни для всех пользователей в организации:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
