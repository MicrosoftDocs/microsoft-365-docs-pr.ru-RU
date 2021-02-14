---
title: CSV-файл со списком устройств
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Узнайте, как сделать CSV-файл для AutoPilot в Microsoft 365 для бизнеса.
ms.openlocfilehash: 030fb96e9e60c792fb685af57d34eacd6670645a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399366"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="dec06-103">CSV-файл со списком устройств</span><span class="sxs-lookup"><span data-stu-id="dec06-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="dec06-104">Формат CSV-файла со списком устройств</span><span class="sxs-lookup"><span data-stu-id="dec06-104">Device list .csv file format</span></span>

<span data-ttu-id="dec06-105">Чтобы управлять устройствами и развертывать их с помощью Windows Autopilot, вам необходим CSV-файл со специальными сведениями о них.</span><span class="sxs-lookup"><span data-stu-id="dec06-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="dec06-106">Заголовки столбцов в файле со списком устройств должны следовать в таком порядке:</span><span class="sxs-lookup"><span data-stu-id="dec06-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="dec06-107">Столбец A: Device Serial Number (Серийный номер устройства)</span><span class="sxs-lookup"><span data-stu-id="dec06-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="dec06-108">Столбец B: оставьте пустым</span><span class="sxs-lookup"><span data-stu-id="dec06-108">Column B: leave blank</span></span>

- <span data-ttu-id="dec06-109">Столбец C: Hardware Hash (Хэш оборудования)</span><span class="sxs-lookup"><span data-stu-id="dec06-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="dec06-110">Эту информацию можно получить у поставщика оборудования или с помощью [сценария PowerShell с именем Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), который создаст CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="dec06-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="dec06-p101">Когда вы добавляете устройства, их также необходимо добавить в профиль. Профиль используется для применения профилей развертывания AutoPilot к устройству или группе устройств.</span><span class="sxs-lookup"><span data-stu-id="dec06-p101">When you add devices, you also need to add them to a Profile. A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="dec06-113">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="dec06-113">Related articles</span></span>

[<span data-ttu-id="dec06-114">Документация и ресурсы по Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="dec06-114">Microsoft 365 for business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="dec06-115">Начало работы с Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="dec06-115">Get started with Microsoft 365 for business</span></span>](https://docs.microsoft.com/microsoft-365/business/microsoft-365-business-overview)
  
[<span data-ttu-id="dec06-116">Управление Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="dec06-116">Manage Microsoft 365 for business</span></span>](https://docs.microsoft.com/microsoft-365/business/manage)
  
