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
description: В этой статье содержатся сведения об использовании постных всплывающих сообщений для повышения производительности скачивания сообщений Outlook в Интернете.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925260"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Используйте постные всплывающие окантовки для уменьшения памяти, используемой при чтении сообщений почты

В этой статье содержатся сведения о повышении производительности скачивания сообщений Outlook в Интернете. Эта статья является частью [сетевого планирования и](./network-planning-and-performance.md) настройки производительности для Office 365 проекта.
  
В качестве Office 365 глобального администратора можно настроить Outlook в Интернете для доставки постных всплывающих сообщений _,_ меньшей и менее интенсивной памяти некоторых сообщений электронной почты в Microsoft Edge или Internet Explorer. При настройке нежирных всплывающих Outlook в Интернете загружаются отрисовки серверных компонентов, которые оптимизируют производительность.
  
> [!NOTE]
> По данным на март 2018 г., постные всплывающие сообщения недоступны для сообщений, которые указывают ограничения прав на использование, такие как управление правами на информацию (IRM).
  
Эти функции будут продолжать работать в главном окне, но недоступны в постных всплывающих окнах:
  
- Надстройки Outlook
  
- Skype для бизнеса присутствия
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Настройка постных всплывающих окантовок для всех пользователей в Office 365 организации
  
1. [Подключение использовать Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
  
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