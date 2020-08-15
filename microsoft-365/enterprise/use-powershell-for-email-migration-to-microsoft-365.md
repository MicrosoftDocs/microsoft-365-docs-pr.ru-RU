---
title: Миграция электронной почты в Microsoft 365 с помощью PowerShell
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.date: 07/17/2020
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 795158e1-7dfc-4d9e-b805-373dd576c4e7
description: В этой статье рассказывается, как перенести электронную почту из существующей системы в Microsoft 365 с помощью PowerShell.
ms.openlocfilehash: afbed872c3cac483c63e8a2d537931220c3c349c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693558"
---
# <a name="use-powershell-for-email-migration-to-microsoft-365"></a><span data-ttu-id="62d5f-103">Миграция электронной почты в Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="62d5f-103">Use PowerShell for email migration to Microsoft 365</span></span>

<span data-ttu-id="62d5f-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="62d5f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="62d5f-105">Когда администраторы сначала настраивают Microsoft 365, многие из них переносят электронную почту из существующих систем.</span><span class="sxs-lookup"><span data-stu-id="62d5f-105">When administrators first set up Microsoft 365, many of them migrate email from existing systems.</span></span> <span data-ttu-id="62d5f-106">Это также можно сделать с помощью центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="62d5f-106">You can also do this by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="62d5f-107">Кроме того, для переноса электронной почты вы можете использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62d5f-107">You can also use Windows PowerShell to migrate email.</span></span>
  
<span data-ttu-id="62d5f-108">Используйте Windows PowerShell для переноса электронной почты в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="62d5f-108">Use Windows PowerShell to migrate email to Microsoft 365.</span></span> 
  
- [<span data-ttu-id="62d5f-109">Прямая миграция в Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="62d5f-109">Use PowerShell to perform a cutover migration to Microsoft 365</span></span>](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md)
    
- [<span data-ttu-id="62d5f-110">Миграция IMAP в Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="62d5f-110">Use PowerShell to perform an IMAP migration to Microsoft 365</span></span>](use-powershell-to-perform-an-imap-migration-to-microsoft-365.md)
    
- [<span data-ttu-id="62d5f-111">Поэтапная миграция в Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="62d5f-111">Use PowerShell to perform a staged migration to Microsoft 365</span></span>](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md)
    
## <a name="related-topics"></a><span data-ttu-id="62d5f-112">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="62d5f-112">Related topics</span></span>

[<span data-ttu-id="62d5f-113">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="62d5f-113">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="62d5f-114">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62d5f-114">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="62d5f-115">Управление SharePoint Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="62d5f-115">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
<span data-ttu-id="62d5f-116">[Использование Windows PowerShell для создания отчетов в Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md) 
 [Почему необходимо использовать Microsoft 365 PowerShell](why-you-need-to-use-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="62d5f-116">[Use Windows PowerShell to create reports in Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)
[Why you need to use Microsoft 365 PowerShell](why-you-need-to-use-microsoft-365-powershell.md)</span></span>
  
[<span data-ttu-id="62d5f-117">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="62d5f-117">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

