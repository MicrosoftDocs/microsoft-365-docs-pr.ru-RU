---
title: Настройка групп устройств в Jamf Pro
description: Узнайте, как настроить группы устройств в Jamf Pro для Microsoft Defender для конечной точки для macOS
keywords: устройство, группа, microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 80dcb4ff73edd5e95603b15e097232a43dc0e05e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861615"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>Настройка Microsoft Defender для конечной точки в группах устройств macOS в Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Настройка групп устройств, аналогичных организационным группам групповой политики, коллекции устройств Microsoft Endpoint Configuration Manager и группам устройств Intune.

1. Перейдите к **статическим компьютерным группам.**

2. Выберите **New**. 

    ![Изображение Jamf Pro1](images/jamf-pro-static-group.png)

3. Укай имя дисплея и выберите **Сохранить**.

    ![Изображение Jamf Pro2](images/jamfpro-machine-group.png)

4. Теперь вы увидите компьютерную группу **Contoso** в статических **компьютерных группах.**

    ![Изображение Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a>Следующий шаг
- [Настройка Microsoft Defender для конечной точки для политик macOS в Jamf Pro](mac-jamfpro-policies.md)
