---
title: Устранение неполадок с лицензиями для Microsoft Defender для конечной точки на Mac
description: Устранение неполадок с лицензиями в Microsoft Defender для конечной точки на Mac.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mac, performance
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
ms.openlocfilehash: 1f8428c2995eec2dece290049eda67a3683b4c1e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244984"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="680c6-104">Устранение неполадок с лицензиями для Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="680c6-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="680c6-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="680c6-105">**Applies to:**</span></span>

- [<span data-ttu-id="680c6-106">Microsoft Defender для конечной точки в macOS</span><span class="sxs-lookup"><span data-stu-id="680c6-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="680c6-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="680c6-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="680c6-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="680c6-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="680c6-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="680c6-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="680c6-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="680c6-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="680c6-111">Во время проверки развертывания [macOS](microsoft-defender-endpoint-mac.md) и [](mac-install-manually.md) ручного развертывания в Microsoft Defender для конечной точки или проверки концепции (PoC) вы можете получить следующую ошибку:</span><span class="sxs-lookup"><span data-stu-id="680c6-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Изображение ошибки лицензии](images/no-license-found.png)

<span data-ttu-id="680c6-113&quot;>**Сообщение:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;680c6-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;680c6-114&quot;>Лицензия не найдена</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;680c6-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;680c6-115&quot;>Похоже, что у организации нет лицензии на Microsoft 365 корпоративный подписки.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;680c6-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;680c6-116&quot;>Обратитесь к системному администратору.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;680c6-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;680c6-117&quot;>**Причина:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;680c6-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;680c6-118&quot;>Вы развернули и/или установили Microsoft Defender для конечной точки для пакета macOS (&quot;Пакет установки загрузки"), но, возможно, вы запустите сценарий конфигурации ("Скачайте пакет onboarding"), либо не назначите пользователю лицензию.</span><span class="sxs-lookup"><span data-stu-id="680c6-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package"), but you might have run the configuration script ("Download onboarding package"), or you have not assigned a license to the user.</span></span>

<span data-ttu-id="680c6-119">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="680c6-119">**Solution:**</span></span>

<span data-ttu-id="680c6-120">Следуйте инструкциям MicrosoftDefenderATPOnboardingMacOs.py, задокументированным здесь: [конфигурация клиента](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="680c6-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>
