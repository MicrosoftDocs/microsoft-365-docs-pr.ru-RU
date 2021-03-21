---
title: Используйте постные всплывающие окантовки для уменьшения памяти, используемой при чтении сообщений почты
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
description: В этой статье содержатся сведения об использовании постных всплывающих сообщений для повышения производительности скачивания сообщений в Outlook в Интернете.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925260"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Используйте постные всплывающие окантовки для уменьшения памяти, используемой при чтении сообщений почты

В этой статье содержатся сведения о повышении производительности скачивания сообщений в Outlook в Интернете. Эта статья является частью [сетевого планирования и настройки производительности для проекта Office 365.](./network-planning-and-performance.md)
  
В качестве глобального администратора Office 365 вы можете настроить Outlook в Интернете для доставки постных всплывающих сообщений _—_ меньшей и менее объемной памяти версий определенных сообщений электронной почты в Microsoft Edge или Internet Explorer. Когда нежирные всплывающие компоненты настраиваются для Outlook в Интернете, отрисовка на стороне сервера загружается, что оптимизирует производительность.
  
> [!NOTE]
> По данным на март 2018 г., постные всплывающие сообщения недоступны для сообщений, которые указывают ограничения прав на использование, такие как управление правами на информацию (IRM).
  
Эти функции будут продолжать работать в главном окне, но недоступны в постных всплывающих окнах:
  
- Надстройки Outlook
  
- Присутствие Skype для бизнеса
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Настройка постных всплывающих всплывающих данных для всех пользователей в организации Office 365
  
1. [Подключение к Exchange Online с помощью удаленной powerShell](/powershell/exchange/connect-to-exchange-online-powershell).
  
2. Выполните [набор-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) с параметром LeanPopoutEnabled следующим образом:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  Например, чтобы включить нежирные всплывающие окантовки для всех пользователей в организации:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  Отключение постных всплывающих отключений для всех пользователей в организации:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```