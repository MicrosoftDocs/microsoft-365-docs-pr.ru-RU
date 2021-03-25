---
title: Аппаратная изоляция (Windows 10)
ms.reviewer: ''
description: Узнайте, как аппаратная изоляция в Windows 10 помогает бороться с вредоносными программами.
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: 82841ccdb2a6ad09f43d0bf8d12cb54fe44d6dfe
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186909"
---
# <a name="hardware-based-isolation-in-windows-10"></a><span data-ttu-id="05adb-103">Аппаратная изоляция в Windows 10</span><span class="sxs-lookup"><span data-stu-id="05adb-103">Hardware-based isolation in Windows 10</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="05adb-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="05adb-104">**Applies to:**</span></span>
- [<span data-ttu-id="05adb-105">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="05adb-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="05adb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="05adb-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="05adb-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="05adb-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="05adb-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="05adb-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="05adb-109">Аппаратная изоляция помогает защитить целостность системы в Windows 10 и интегрирована с Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="05adb-109">Hardware-based isolation helps protect system integrity in Windows 10 and is integrated with Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="05adb-110">Возможность</span><span class="sxs-lookup"><span data-stu-id="05adb-110">Feature</span></span> | <span data-ttu-id="05adb-111">Описание</span><span class="sxs-lookup"><span data-stu-id="05adb-111">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="05adb-112">Application Guard в Защитнике Windows</span><span class="sxs-lookup"><span data-stu-id="05adb-112">Windows Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | <span data-ttu-id="05adb-113">Application Guard защищает устройство от расширенных атак, сохраняя производительность.</span><span class="sxs-lookup"><span data-stu-id="05adb-113">Application Guard protects your device from advanced attacks while keeping you productive.</span></span> <span data-ttu-id="05adb-114">С помощью уникального аппаратного подхода к изоляции цель состоит в том, чтобы изолировать ненадеженные веб-сайты и документы PDF в легком контейнере, отделенном от операционной системы с помощью родного гипервизора Windows.</span><span class="sxs-lookup"><span data-stu-id="05adb-114">Using a unique hardware-based isolation approach, the goal is to isolate untrusted websites and PDF documents inside a lightweight container that is separated from the operating system via the native Windows Hypervisor.</span></span> <span data-ttu-id="05adb-115">Если ненастоячивый сайт или pdf-документ окажется вредоносным, он по-прежнему остается в защищенном контейнере Application Guard, сохраняя защиту настольного компьютера и злоумышленника от корпоративных данных.</span><span class="sxs-lookup"><span data-stu-id="05adb-115">If an untrusted site or PDF document turns out to be malicious, it still remains contained within Application Guard’s secure container, keeping the desktop PC protected and the attacker away from your enterprise data.</span></span> |
| [<span data-ttu-id="05adb-116">Защитник Windows System Guard</span><span class="sxs-lookup"><span data-stu-id="05adb-116">Windows Defender System Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | <span data-ttu-id="05adb-117">System Guard защищает и поддерживает целостность системы при запуске и после ее запуска, а также проверяет целостность системы с помощью проверки.</span><span class="sxs-lookup"><span data-stu-id="05adb-117">System Guard protects and maintains the integrity of the system as it starts and after it's running, and validates system integrity by using attestation.</span></span>  |

