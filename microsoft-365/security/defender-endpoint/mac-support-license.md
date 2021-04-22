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
ms.openlocfilehash: e8084fab434246a5c9f12af40872ade66e6fa163
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934265"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="6229b-104">Устранение неполадок с лицензиями для Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="6229b-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6229b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6229b-105">**Applies to:**</span></span>

- [<span data-ttu-id="6229b-106">Microsoft Defender для конечной точки в macOS</span><span class="sxs-lookup"><span data-stu-id="6229b-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="6229b-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6229b-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6229b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6229b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6229b-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="6229b-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6229b-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="6229b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="6229b-111">Во время проверки развертывания [macOS](microsoft-defender-endpoint-mac.md) и [](mac-install-manually.md) ручного развертывания в Microsoft Defender для конечной точки или проверки концепции (PoC) вы можете получить следующую ошибку:</span><span class="sxs-lookup"><span data-stu-id="6229b-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Изображение ошибки лицензии](images/no-license-found.png)

<span data-ttu-id="6229b-113&quot;>**Сообщение:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;6229b-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;6229b-114&quot;>Лицензия не найдена</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;6229b-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;6229b-115&quot;>Похоже, у вашей организации нет лицензии на подписку microsoft 365 Enterprise.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;6229b-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;6229b-116&quot;>Обратитесь к системному администратору.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;6229b-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;6229b-117&quot;>**Причина:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;6229b-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;6229b-118&quot;>Вы развернули и/или установили microsoft Defender для конечной точки на пакете macOS (&quot;Пакет установки загрузки"), но, возможно, вы запустите сценарий конфигурации ("Скачайте пакет onboarding").</span><span class="sxs-lookup"><span data-stu-id="6229b-118">You deployed and/or installed the Microsoft Defender for Endpoint on macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="6229b-119">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="6229b-119">**Solution:**</span></span>

<span data-ttu-id="6229b-120">Следуйте инструкциям MicrosoftDefenderATPOnboardingMacOs.py, задокументированным здесь: [конфигурация клиента](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="6229b-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

