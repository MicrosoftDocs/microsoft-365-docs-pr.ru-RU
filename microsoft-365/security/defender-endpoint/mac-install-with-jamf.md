---
title: Развертывание ATP Защитника Майкрософт для macOS с помощью Jamf Pro
description: Развертывание ATP Защитника Майкрософт для macOS с помощью Jamf Pro
keywords: Microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 56f5e860bd2a9dd47ce16379b5e1ca1a263d62d0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187413"
---
# <a name="deploying-microsoft-defender-for-endpoint-for-macos-with-jamf-pro"></a><span data-ttu-id="cdc96-104">Развертывание Microsoft Defender для конечной точки для macOS с помощью Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="cdc96-104">Deploying Microsoft Defender for Endpoint for macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cdc96-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="cdc96-105">**Applies to:**</span></span>
- [<span data-ttu-id="cdc96-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="cdc96-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cdc96-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cdc96-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="cdc96-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="cdc96-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cdc96-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="cdc96-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="cdc96-110">Узнайте, как развернуть Microsoft Defender для конечной точки для macOS с помощью Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="cdc96-110">Learn how to deploy Microsoft Defender for Endpoint for macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="cdc96-111">Если вы используете macOS Catalina (10.15.4) или более новые версии macOS, см. новые профили конфигурации для [macOS Catalina](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies)и более новые версии macOS .</span><span class="sxs-lookup"><span data-stu-id="cdc96-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="cdc96-112">Это многоступенчатый процесс.</span><span class="sxs-lookup"><span data-stu-id="cdc96-112">This is a multi step process.</span></span> <span data-ttu-id="cdc96-113">Необходимо выполнить все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cdc96-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="cdc96-114">Вход на портал Jamf</span><span class="sxs-lookup"><span data-stu-id="cdc96-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="cdc96-115">Настройка microsoft Defender для конечной точки для групп устройств macOS в Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="cdc96-115">Setup the Microsoft Defender for Endpoint for macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="cdc96-116">Настройка защитника Майкрософт для конечной точки для политик macOS в Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="cdc96-116">Setup the Microsoft Defender for Endpoint for macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="cdc96-117">Регистрация microsoft Defender для конечной точки для macOS-устройств в Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="cdc96-117">Enroll the Microsoft Defender for Endpoint for macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




