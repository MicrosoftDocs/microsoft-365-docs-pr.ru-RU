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
ms.openlocfilehash: 645c3657bdd1540ac95b68460b4dff6d25627c2c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185934"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="dd033-104">Устранение неполадок с лицензиями для Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="dd033-104">Troubleshoot license issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="dd033-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="dd033-105">**Applies to:**</span></span>

- [<span data-ttu-id="dd033-106">Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="dd033-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="dd033-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="dd033-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dd033-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dd033-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="dd033-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="dd033-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dd033-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="dd033-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="dd033-111">При проверке microsoft [Defender для конечной](microsoft-defender-endpoint-mac.md) точки для Mac и [ручного](mac-install-manually.md) тестирования развертывания или проверки концепции (PoC) вы можете получить следующую ошибку:</span><span class="sxs-lookup"><span data-stu-id="dd033-111">While you are going through [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Изображение ошибки лицензии](images/no-license-found.png)

<span data-ttu-id="dd033-113">**Сообщение:**</span><span class="sxs-lookup"><span data-stu-id="dd033-113">**Message:**</span></span> 

<span data-ttu-id="dd033-114">Лицензия не найдена</span><span class="sxs-lookup"><span data-stu-id="dd033-114">No license found</span></span>

<span data-ttu-id="dd033-115">Похоже, у вашей организации нет лицензии на подписку microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="dd033-115">Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="dd033-116">Обратитесь к системному администратору.</span><span class="sxs-lookup"><span data-stu-id="dd033-116">Contact your administrator for help.</span></span>

<span data-ttu-id="dd033-117">**Причина:**</span><span class="sxs-lookup"><span data-stu-id="dd033-117">**Cause:**</span></span> 

<span data-ttu-id="dd033-118">Вы развернули и/или установили Microsoft Defender для конечной точки для пакета macOS ("Пакет установки загрузки"), но, возможно, вы запустите сценарий конфигурации ("Скачайте пакет onboarding").</span><span class="sxs-lookup"><span data-stu-id="dd033-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="dd033-119">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="dd033-119">**Solution:**</span></span>

<span data-ttu-id="dd033-120">Следуйте инструкциям MicrosoftDefenderATPOnboardingMacOs.py, задокументированным здесь: [конфигурация клиента](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="dd033-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

