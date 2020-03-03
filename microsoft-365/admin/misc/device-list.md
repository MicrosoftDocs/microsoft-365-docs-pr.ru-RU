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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Сведения о том, как создать CSV-файл для Аутопилоного Tin Microsoft 365 Business.
ms.openlocfilehash: 56d8fb234a1b526192468309c93c638694b92c6e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361360"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="74079-103">CSV-файл со списком устройств</span><span class="sxs-lookup"><span data-stu-id="74079-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="74079-104">Формат CSV-файла со списком устройств</span><span class="sxs-lookup"><span data-stu-id="74079-104">Device list .csv file format</span></span>

<span data-ttu-id="74079-105">Чтобы управлять устройствами и развертывать их с помощью Windows Autopilot, вам необходим CSV-файл со специальными сведениями о них.</span><span class="sxs-lookup"><span data-stu-id="74079-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="74079-106">Заголовки столбцов в файле со списком устройств должны следовать в таком порядке:</span><span class="sxs-lookup"><span data-stu-id="74079-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="74079-107">Столбец A: Device Serial Number (Серийный номер устройства)</span><span class="sxs-lookup"><span data-stu-id="74079-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="74079-108">Столбец B: оставьте пустым</span><span class="sxs-lookup"><span data-stu-id="74079-108">Column B: leave blank</span></span>

- <span data-ttu-id="74079-109">Столбец C: Hardware Hash (Хэш оборудования)</span><span class="sxs-lookup"><span data-stu-id="74079-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="74079-110">Эту информацию можно получить у поставщика оборудования или с помощью [сценария PowerShell с именем Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), который создаст CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="74079-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="74079-p101">Когда вы добавляете устройства, их также необходимо добавить в профиль. Профиль используется для применения профилей развертывания AutoPilot к устройству или группе устройств.</span><span class="sxs-lookup"><span data-stu-id="74079-p101">When you add devices, you also need to add them to a Profile. A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="74079-113">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="74079-113">Related articles</span></span>

[<span data-ttu-id="74079-114">Документы и ресурсы по Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="74079-114">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="74079-115">Начало работы с Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="74079-115">Get started with Microsoft 365 Business</span></span>](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[<span data-ttu-id="74079-116">Управление Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="74079-116">Manage Microsoft 365 Business</span></span>](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  
