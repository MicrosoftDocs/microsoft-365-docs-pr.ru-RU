---
title: Отключение доступа к Sway с помощью PowerShell для Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: 7221a4c9-ae03-4598-81fe-a655c02f40ab
description: Узнайте, где скачать ManageSway.ps1 PowerShell, который позволяет отключить доступ к Sway в организации Microsoft 365.
ms.openlocfilehash: bec96c6232eee88355997f56e49f1f99b8cc2fbd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693176"
---
# <a name="disable-access-to-sway-with-powershell-for-microsoft-365"></a><span data-ttu-id="dd332-103">Отключение доступа к Sway с помощью PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dd332-103">Disable access to Sway with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="dd332-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="dd332-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="dd332-105">Сценарий ManageSway.ps1 PowerShell позволяет просматривать и отключать службы в организации Microsoft 365, включая Sway.</span><span class="sxs-lookup"><span data-stu-id="dd332-105">The ManageSway.ps1 PowerShell script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="dd332-106">Данный сценарий позволяет автоматизировать процедуры, описанные в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="dd332-106">This script automates the procedures that are described in the following topics:</span></span>
  
- [<span data-ttu-id="dd332-107">Просмотр лицензий и служб с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd332-107">View licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="dd332-108">Отключение доступа к службам с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd332-108">Disable access to services with PowerShell</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
    
<span data-ttu-id="dd332-109">Необходимо загрузить два файла, связанные со сценарием:</span><span class="sxs-lookup"><span data-stu-id="dd332-109">You need to download the two files that are associated with the script:</span></span>
  
- <span data-ttu-id="dd332-110">Сценарий ManageSway.ps1: [https://go.microsoft.com/fwlink/p/?LinkId=785070](https://go.microsoft.com/fwlink/p/?LinkId=785070)</span><span class="sxs-lookup"><span data-stu-id="dd332-110">The ManageSway.ps1 script at [https://go.microsoft.com/fwlink/p/?LinkId=785070](https://go.microsoft.com/fwlink/p/?LinkId=785070)</span></span>
    
- <span data-ttu-id="dd332-111">Файл справки для сценария: [https://go.microsoft.com/fwlink/p/?LinkId=785072](https://go.microsoft.com/fwlink/p/?LinkId=785072)</span><span class="sxs-lookup"><span data-stu-id="dd332-111">The help file for the script at [https://go.microsoft.com/fwlink/p/?LinkId=785072](https://go.microsoft.com/fwlink/p/?LinkId=785072)</span></span>
    

