---
title: Отключение синхронизации службы каталогов для Microsoft 365
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
description: В этой статье вы найдете сведения об использовании PowerShell для отключения синхронизации службы каталогов для Microsoft 365.
ms.openlocfilehash: 0bd8591f91dcf20cb1061b3cd93f69511027bab1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692928"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Отключение синхронизации службы каталогов для Microsoft 365
Вы можете отключить синхронизацию каталогов с помощью PowerShell. Однако не рекомендуется отключать синхронизацию каталогов в качестве шага устранения неполадок. Если вам нужна помощь в устранении неполадок синхронизации службы каталогов, см. статью "Устранение проблем с синхронизацией службы каталогов [для Microsoft 365".](fix-problems-with-directory-synchronization.md) 
  
[При необходимости обратитесь](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) в службу поддержки бизнес-продуктов.
  
## <a name="turn-off-directory-synchronization"></a>Отключение синхронизации службы каталогов  
Отключение синхронизации каталогов:
  
1. Сначала установите необходимое программное обеспечение и подключите его к подписке на Microsoft 365. Инструкции см. в подключении с помощью модуля [Microsoft Azure Active Directory для Windows PowerShell.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
    
2. Чтобы отключить синхронизацию каталогов, используйте [set-MsolDirSyncEnabled:](https://go.microsoft.com/fwlink/p/?LinkId=821939) 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>При использовании этой команды необходимо подождать 72 часа, прежде чем можно будет снова включить синхронизацию каталогов.
>
 
