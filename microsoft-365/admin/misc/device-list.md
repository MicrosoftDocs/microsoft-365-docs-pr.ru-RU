---
title: CSV-файл со списком устройств
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
ms.openlocfilehash: 13d7fbffd8d6fbe1af0dde55a4e98688060d9da8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579222"
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

[Microsoft 365 для бизнес-документации и ресурсов](../../business/index.yml)
  
[Начало работы с Microsoft 365 для бизнеса](../../business/microsoft-365-business-overview.md)
  
[Управление Microsoft 365 для бизнеса](../../business/manage.md)
