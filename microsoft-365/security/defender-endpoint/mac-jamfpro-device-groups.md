---
title: Настройка групп устройств в Jamf Pro
description: Узнайте, как настроить группы устройств в Jamf Pro для Microsoft Defender для конечной точки на macOS
keywords: устройство, группа, microsoft, defender, Microsoft Defender для endpoint, mac, установка, развертывание, деинсталлация, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 772b67ec84ae9614c9322763c140a60e7884644d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933809"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="8711f-104">Настройка Microsoft Defender для конечной точки в группах устройств macOS в Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="8711f-104">Set up Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8711f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8711f-105">**Applies to:**</span></span>
- [<span data-ttu-id="8711f-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8711f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8711f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8711f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8711f-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="8711f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8711f-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="8711f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="8711f-110">Настройка групп устройств, аналогичных организационным группам групповой политики, коллекции устройств Microsoft Endpoint Configuration Manager и группам устройств Intune.</span><span class="sxs-lookup"><span data-stu-id="8711f-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="8711f-111">Перейдите к **статическим компьютерным группам.**</span><span class="sxs-lookup"><span data-stu-id="8711f-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="8711f-112">Выберите **New**.</span><span class="sxs-lookup"><span data-stu-id="8711f-112">Select **New**.</span></span> 

    ![Изображение Jamf Pro1](images/jamf-pro-static-group.png)

3. <span data-ttu-id="8711f-114">Укай имя дисплея и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8711f-114">Provide a display name and select **Save**.</span></span>

    ![Изображение Jamf Pro2](images/jamfpro-machine-group.png)

4. <span data-ttu-id="8711f-116">Теперь вы увидите компьютерную группу **Contoso** в статических **компьютерных группах.**</span><span class="sxs-lookup"><span data-stu-id="8711f-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Изображение Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="8711f-118">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="8711f-118">Next step</span></span>
- [<span data-ttu-id="8711f-119">Настройка Microsoft Defender для конечной точки для политик macOS в Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="8711f-119">Set up Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
