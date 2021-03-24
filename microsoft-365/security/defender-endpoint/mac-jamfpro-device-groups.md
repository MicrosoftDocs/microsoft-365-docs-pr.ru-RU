---
title: Настройка групп устройств в Jamf Pro
description: Узнайте, как настроить группы устройств в Jamf Pro для ATP Microsoft Defender для macOS
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
ms.openlocfilehash: 3e330f135e391214ffe25289d58c2d0de3257be0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070318"
---
# <a name="set-up-microsoft-defender-for-endpoint-for-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="63ee5-104">Настройка Microsoft Defender для конечной точки для групп устройств macOS в Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="63ee5-104">Set up Microsoft Defender for Endpoint for macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="63ee5-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="63ee5-105">**Applies to:**</span></span>
- [<span data-ttu-id="63ee5-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="63ee5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="63ee5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63ee5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="63ee5-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="63ee5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="63ee5-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="63ee5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="63ee5-110">Настройка групп устройств, аналогичных организационным группам групповой политики, коллекции устройств Microsoft Endpoint Configuration Manager и группам устройств Intune.</span><span class="sxs-lookup"><span data-stu-id="63ee5-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="63ee5-111">Перейдите к **статическим компьютерным группам.**</span><span class="sxs-lookup"><span data-stu-id="63ee5-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="63ee5-112">Выберите **New**.</span><span class="sxs-lookup"><span data-stu-id="63ee5-112">Select **New**.</span></span> 

    ![Изображение Jamf Pro1](images/jamf-pro-static-group.png)

3. <span data-ttu-id="63ee5-114">Укай имя дисплея и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="63ee5-114">Provide a display name and select **Save**.</span></span>

    ![Изображение Jamf Pro2](images/jamfpro-machine-group.png)

4. <span data-ttu-id="63ee5-116">Теперь вы увидите компьютерную группу **Contoso** в статических **компьютерных группах.**</span><span class="sxs-lookup"><span data-stu-id="63ee5-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Изображение Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="63ee5-118">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="63ee5-118">Next step</span></span>
- [<span data-ttu-id="63ee5-119">Настройка Microsoft Defender для конечной точки для политик macOS в Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="63ee5-119">Set up Microsoft Defender for Endpoint for macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
