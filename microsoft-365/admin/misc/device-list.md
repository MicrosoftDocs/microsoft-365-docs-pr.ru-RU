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
description: Узнайте, как сделать CSV-файл для autoPilot в Microsoft 365 для бизнеса.
ms.openlocfilehash: 78a9012bac054329bdb87b02757f49f30dd44f65
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914742"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="5f5ec-103">CSV-файл со списком устройств</span><span class="sxs-lookup"><span data-stu-id="5f5ec-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="5f5ec-104">Формат CSV-файла со списком устройств</span><span class="sxs-lookup"><span data-stu-id="5f5ec-104">Device list .csv file format</span></span>

<span data-ttu-id="5f5ec-105">Чтобы управлять устройствами и развертывать их с помощью Windows Autopilot, вам необходим CSV-файл со специальными сведениями о них.</span><span class="sxs-lookup"><span data-stu-id="5f5ec-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="5f5ec-106">Заголовки столбцов в файле со списком устройств должны следовать в таком порядке:</span><span class="sxs-lookup"><span data-stu-id="5f5ec-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="5f5ec-107">Столбец A: Device Serial Number (Серийный номер устройства)</span><span class="sxs-lookup"><span data-stu-id="5f5ec-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="5f5ec-108">Столбец B: оставьте пустым</span><span class="sxs-lookup"><span data-stu-id="5f5ec-108">Column B: leave blank</span></span>

- <span data-ttu-id="5f5ec-109">Столбец C: Hardware Hash (Хэш оборудования)</span><span class="sxs-lookup"><span data-stu-id="5f5ec-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="5f5ec-110">Эту информацию можно получить у поставщика оборудования или с помощью [сценария PowerShell с именем Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), который создаст CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="5f5ec-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="5f5ec-p101">Когда вы добавляете устройства, их также необходимо добавить в профиль. Профиль используется для применения профилей развертывания AutoPilot к устройству или группе устройств.</span><span class="sxs-lookup"><span data-stu-id="5f5ec-p101">When you add devices, you also need to add them to a Profile. A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="5f5ec-113">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5f5ec-113">Related articles</span></span>

[<span data-ttu-id="5f5ec-114">Microsoft 365 для бизнес-документации и ресурсов</span><span class="sxs-lookup"><span data-stu-id="5f5ec-114">Microsoft 365 for business documentation and resources</span></span>](../../business/index.yml)
  
[<span data-ttu-id="5f5ec-115">Начало работы с Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5f5ec-115">Get started with Microsoft 365 for business</span></span>](../../business/microsoft-365-business-overview.md)
  
[<span data-ttu-id="5f5ec-116">Управление Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5f5ec-116">Manage Microsoft 365 for business</span></span>](../../business/manage.md)
