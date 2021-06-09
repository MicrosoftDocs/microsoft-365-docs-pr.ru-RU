---
title: Отключите синхронизацию каталогов для Microsoft 365
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
ms.openlocfilehash: 26f8729078ea06657ced565db780b57c7e537aa4
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445712"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="0af32-103">Отключите синхронизацию каталогов для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0af32-103">Turn off directory synchronization for Microsoft 365</span></span>
<span data-ttu-id="0af32-104">С помощью PowerShell можно отключить синхронизацию каталогов и преобразовать синхронизированных пользователей в облачные.</span><span class="sxs-lookup"><span data-stu-id="0af32-104">You can use PowerShell to turn off directory synchronization and convert your synchronized users to cloud-only.</span></span> <span data-ttu-id="0af32-105">Однако не рекомендуется отключить синхронизацию каталогов в качестве шага по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="0af32-105">However, it is not recommended that you turn off directory synchronization as a troubleshooting step.</span></span> <span data-ttu-id="0af32-106">Если вам нужна помощь в устранении неполадок в синхронизации каталогов, см. в статье Исправление проблем с [синхронизацией](fix-problems-with-directory-synchronization.md) каталогов для Microsoft 365 статьи.</span><span class="sxs-lookup"><span data-stu-id="0af32-106">If you need assistance with troubleshooting directory synchronization, see the [Fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) article.</span></span> 
  
<span data-ttu-id="0af32-107">[При необходимости обратитесь](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) в службу поддержки бизнес-продуктов.</span><span class="sxs-lookup"><span data-stu-id="0af32-107">[Contact support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) for business products if needed.</span></span>
  
## <a name="turn-off-directory-synchronization"></a><span data-ttu-id="0af32-108">Отключение синхронизации службы каталогов</span><span class="sxs-lookup"><span data-stu-id="0af32-108">Turn off directory synchronization</span></span>  
<span data-ttu-id="0af32-109">Чтобы отключить синхронизацию каталогов:</span><span class="sxs-lookup"><span data-stu-id="0af32-109">To turn off Directory synchronization:</span></span>
  
1. <span data-ttu-id="0af32-110">Сначала установите необходимое программное обеспечение и подключите его к Microsoft 365 подписке.</span><span class="sxs-lookup"><span data-stu-id="0af32-110">First, install the required software and connect to your Microsoft 365 subscription.</span></span> <span data-ttu-id="0af32-111">Инструкции см. [в Подключение с модулем Microsoft Azure Active Directory для Windows PowerShell.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="0af32-111">For instructions, see [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
2. <span data-ttu-id="0af32-112">Чтобы отключить синхронизацию каталогов, используйте [Set-MsolDirSyncEnabled:](/previous-versions/azure/dn194097(v=azure.100))</span><span class="sxs-lookup"><span data-stu-id="0af32-112">Use [Set-MsolDirSyncEnabled](/previous-versions/azure/dn194097(v=azure.100)) to disable directory synchronization:</span></span> 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
><span data-ttu-id="0af32-113">Если вы используете эту команду, необходимо подождать 72 часа, прежде чем вы сможете включить синхронизацию каталогов.</span><span class="sxs-lookup"><span data-stu-id="0af32-113">If you use this command, you must wait 72 hours before you can turn directory synchronization back on.</span></span>
>
