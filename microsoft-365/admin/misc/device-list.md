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
description: Сведения о том, как создать CSV-файл для автопилота в Microsoft 365 для бизнеса.
ms.openlocfilehash: c83862675db1372aa2cef27c727c04577b4cf5a3
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44064655"
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
  
