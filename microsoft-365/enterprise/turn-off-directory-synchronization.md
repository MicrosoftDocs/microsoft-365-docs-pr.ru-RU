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
description: В этой статье сведения об использовании PowerShell для отключения синхронизации каталогов для Microsoft 365.
ms.openlocfilehash: 036130b70382e28ad9d8cb10786ad5e266375c20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909314"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Отключение синхронизации каталогов для Microsoft 365
Чтобы отключить синхронизацию каталогов, можно использовать PowerShell. Однако не рекомендуется отключить синхронизацию каталогов в качестве шага по устранению неполадок. Если вам нужна помощь в устранении неполадок в синхронизации каталогов, см. в статье Исправление проблем с синхронизацией каталогов для [статьи Microsoft 365.](fix-problems-with-directory-synchronization.md) 
  
[При необходимости обратитесь](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) в службу поддержки бизнес-продуктов.
  
## <a name="turn-off-directory-synchronization"></a>Отключение синхронизации службы каталогов  
Чтобы отключить синхронизацию каталогов:
  
1. Сначала установите необходимое программное обеспечение и подключите его к подписке Microsoft 365. Инструкции см. в [ссылке Connect с модулем Microsoft Azure Active Directory для](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)Windows PowerShell.
    
2. Чтобы отключить синхронизацию каталогов, используйте [Set-MsolDirSyncEnabled:](/previous-versions/azure/dn194097(v=azure.100)) 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>Если вы используете эту команду, необходимо подождать 72 часа, прежде чем вы сможете включить синхронизацию каталогов.
>
