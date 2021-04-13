---
title: Устранение неполадок с лицензиями для ATP Microsoft Defender для Mac
description: Устранение неполадок в лицензии Microsoft Defender ATP для Mac.
keywords: Microsoft, defender, atp, mac, performance
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
ms.openlocfilehash: 69dd85394837bb7f37e7d277110c8a5dbf7b6506
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689117"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="974bf-104">Устранение неполадок с лицензиями для Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="974bf-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="974bf-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="974bf-105">**Applies to:**</span></span>

- [<span data-ttu-id="974bf-106">Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="974bf-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="974bf-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="974bf-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="974bf-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="974bf-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="974bf-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="974bf-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="974bf-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="974bf-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="974bf-111">Во время проверки развертывания [macOS](microsoft-defender-endpoint-mac.md) и [](mac-install-manually.md) ручного развертывания в Microsoft Defender для конечной точки или проверки концепции (PoC) вы можете получить следующую ошибку:</span><span class="sxs-lookup"><span data-stu-id="974bf-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Изображение ошибки лицензии](images/no-license-found.png)

<span data-ttu-id="974bf-113&quot;>**Сообщение:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;974bf-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;974bf-114&quot;>Лицензия не найдена</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;974bf-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;974bf-115&quot;>Похоже, у вашей организации нет лицензии на подписку microsoft 365 Enterprise.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;974bf-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;974bf-116&quot;>Обратитесь к системному администратору.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;974bf-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;974bf-117&quot;>**Причина:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;974bf-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;974bf-118&quot;>Вы развернули и/или установили microsoft Defender для конечной точки на пакете macOS (&quot;Пакет установки загрузки"), но, возможно, вы запустите сценарий конфигурации ("Скачайте пакет onboarding").</span><span class="sxs-lookup"><span data-stu-id="974bf-118">You deployed and/or installed the Microsoft Defender for Endpoint on macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="974bf-119">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="974bf-119">**Solution:**</span></span>

<span data-ttu-id="974bf-120">Следуйте инструкциям MicrosoftDefenderATPOnboardingMacOs.py, задокументированным здесь: [конфигурация клиента](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="974bf-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

