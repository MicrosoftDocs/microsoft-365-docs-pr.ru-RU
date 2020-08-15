---
title: Отключение синхронизации каталогов для Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: В этой статье содержатся сведения об использовании PowerShell для отключения синхронизации службы каталогов для Microsoft 365.
ms.openlocfilehash: 0bd8591f91dcf20cb1061b3cd93f69511027bab1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692928"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Отключение синхронизации каталогов для Microsoft 365
Вы можете отключить синхронизацию службы каталогов с помощью PowerShell. Тем не менее, не рекомендуется отключать синхронизацию службы каталогов в качестве действия по устранению неполадок. Если вам нужна помощь с устранением проблем с синхронизацией службы каталогов, обратитесь к разделу [Устранение проблем с синхронизацией каталогов для статьи Microsoft 365](fix-problems-with-directory-synchronization.md) . 
  
При необходимости [свяжитесь со службой поддержки](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) для бизнес-продуктов.
  
## <a name="turn-off-directory-synchronization"></a>Отключение синхронизации каталогов  
Чтобы отключить синхронизацию службы каталогов, выполните указанные ниже действия.
  
1. Сначала установите необходимое программное обеспечение и подключитесь к вашей подписке на Microsoft 365. Для получения инструкций обратитесь [к разделу Подключение к модулю Microsoft Azure Active Directory для Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
2. Используйте [Set – мсолдирсинценаблед](https://go.microsoft.com/fwlink/p/?LinkId=821939) , чтобы отключить синхронизацию службы каталогов: 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>При использовании этой команды необходимо подождать 72 часов, прежде чем можно будет снова включить синхронизацию каталогов.
>
 
