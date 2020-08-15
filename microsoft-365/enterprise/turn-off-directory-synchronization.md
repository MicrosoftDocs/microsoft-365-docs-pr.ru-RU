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
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="0a3f0-103">Отключение синхронизации каталогов для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0a3f0-103">Turn off directory synchronization for Microsoft 365</span></span>
<span data-ttu-id="0a3f0-104">Вы можете отключить синхронизацию службы каталогов с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0a3f0-104">You can use PowerShell to turn off directory synchronization.</span></span> <span data-ttu-id="0a3f0-105">Тем не менее, не рекомендуется отключать синхронизацию службы каталогов в качестве действия по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="0a3f0-105">However, it is not recommended that you turn off directory synchronization as a troubleshooting step.</span></span> <span data-ttu-id="0a3f0-106">Если вам нужна помощь с устранением проблем с синхронизацией службы каталогов, обратитесь к разделу [Устранение проблем с синхронизацией каталогов для статьи Microsoft 365](fix-problems-with-directory-synchronization.md) .</span><span class="sxs-lookup"><span data-stu-id="0a3f0-106">If you need assistance with troubleshooting directory synchronization, see the [Fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) article.</span></span> 
  
<span data-ttu-id="0a3f0-107">При необходимости [свяжитесь со службой поддержки](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) для бизнес-продуктов.</span><span class="sxs-lookup"><span data-stu-id="0a3f0-107">[Contact support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) for business products if needed.</span></span>
  
## <a name="turn-off-directory-synchronization"></a><span data-ttu-id="0a3f0-108">Отключение синхронизации каталогов</span><span class="sxs-lookup"><span data-stu-id="0a3f0-108">Turn off directory synchronization</span></span>  
<span data-ttu-id="0a3f0-109">Чтобы отключить синхронизацию службы каталогов, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0a3f0-109">To turn off Directory synchronization:</span></span>
  
1. <span data-ttu-id="0a3f0-110">Сначала установите необходимое программное обеспечение и подключитесь к вашей подписке на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0a3f0-110">First, install the required software and connect to your Microsoft 365 subscription.</span></span> <span data-ttu-id="0a3f0-111">Для получения инструкций обратитесь [к разделу Подключение к модулю Microsoft Azure Active Directory для Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0a3f0-111">For instructions, see [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
2. <span data-ttu-id="0a3f0-112">Используйте [Set – мсолдирсинценаблед](https://go.microsoft.com/fwlink/p/?LinkId=821939) , чтобы отключить синхронизацию службы каталогов:</span><span class="sxs-lookup"><span data-stu-id="0a3f0-112">Use [Set-MsolDirSyncEnabled](https://go.microsoft.com/fwlink/p/?LinkId=821939) to disable directory synchronization:</span></span> 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
><span data-ttu-id="0a3f0-113">При использовании этой команды необходимо подождать 72 часов, прежде чем можно будет снова включить синхронизацию каталогов.</span><span class="sxs-lookup"><span data-stu-id="0a3f0-113">If you use this command, you must wait 72 hours before you can turn directory synchronization back on.</span></span>
>
 
