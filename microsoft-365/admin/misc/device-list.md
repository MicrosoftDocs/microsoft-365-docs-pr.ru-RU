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
description: Сведения о том, как создать CSV-файл для автопилота в Microsoft 365 для бизнеса.
ms.openlocfilehash: 030fb96e9e60c792fb685af57d34eacd6670645a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399366"
---
# <a name="device-list-csv-file"></a>CSV-файл со списком устройств

## <a name="device-list-csv-file-format"></a>Формат CSV-файла со списком устройств

Чтобы управлять устройствами и развертывать их с помощью Windows Autopilot, вам необходим CSV-файл со специальными сведениями о них.
  
Заголовки столбцов в файле со списком устройств должны следовать в таком порядке:
  
- Столбец A: Device Serial Number (Серийный номер устройства)

- Столбец B: оставьте пустым

- Столбец C: Hardware Hash (Хэш оборудования)

Эту информацию можно получить у поставщика оборудования или с помощью [сценария PowerShell с именем Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), который создаст CSV-файл. 

Когда вы добавляете устройства, их также необходимо добавить в профиль. Профиль используется для применения профилей развертывания AutoPilot к устройству или группе устройств.
  
## <a name="related-articles"></a>Статьи по теме

[Документация и ресурсы Microsoft 365 для бизнеса](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Начало работы с Microsoft 365 для бизнеса](https://docs.microsoft.com/microsoft-365/business/microsoft-365-business-overview)
  
[Управление Microsoft 365 для бизнеса](https://docs.microsoft.com/microsoft-365/business/manage)
  
