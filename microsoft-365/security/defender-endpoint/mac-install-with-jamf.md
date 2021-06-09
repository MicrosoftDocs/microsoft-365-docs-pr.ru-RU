---
title: Развертывание Microsoft Defender для конечной точки на macOS с помощью Jamf Pro
description: Развертывание Microsoft Defender для конечной точки на macOS с помощью Jamf Pro
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: b41c5ec827e110e0101c50ce7babeb6442096edb
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842894"
---
# <a name="deploying-microsoft-defender-for-endpoint-on-macos-with-jamf-pro"></a><span data-ttu-id="4612c-104">Развертывание Microsoft Defender для конечной точки на macOS с помощью Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="4612c-104">Deploying Microsoft Defender for Endpoint on macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4612c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4612c-105">**Applies to:**</span></span>
- [<span data-ttu-id="4612c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="4612c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4612c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4612c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="4612c-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="4612c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4612c-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="4612c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="4612c-110">Узнайте, как развернуть Microsoft Defender для конечной точки на macOS с помощью Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="4612c-110">Learn how to deploy Microsoft Defender for Endpoint on macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="4612c-111">Если вы используете macOS Catalina (10.15.4) или более новые версии macOS, см. новые профили конфигурации для [macOS Catalina](/microsoft-365/security/defender-endpoint/mac-sysext-policies)и более новые версии macOS .</span><span class="sxs-lookup"><span data-stu-id="4612c-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="4612c-112">Это многоступенчатый процесс.</span><span class="sxs-lookup"><span data-stu-id="4612c-112">This is a multi step process.</span></span> <span data-ttu-id="4612c-113">Необходимо выполнить все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4612c-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="4612c-114">Вход на портал Jamf</span><span class="sxs-lookup"><span data-stu-id="4612c-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="4612c-115">Настройка конечной точки Microsoft Defender для групп устройств macOS в Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="4612c-115">Setup the Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="4612c-116">Настройка конечной точки Microsoft Defender для политик macOS в Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="4612c-116">Setup the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="4612c-117">Регистрация защитника Microsoft для конечной точки на устройствах macOS в Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="4612c-117">Enroll the Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




