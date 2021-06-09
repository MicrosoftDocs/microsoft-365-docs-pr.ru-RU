---
title: Настройка антивирусная программа в Microsoft Defender с помощью Microsoft Endpoint Manager
description: Используйте Microsoft Endpoint Manager Microsoft Intune и Microsoft Intune Microsoft Defender AV и Endpoint Protection
keywords: scep, intune, endpoint protection, configuration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683755"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="a802e-104">Используйте Microsoft Endpoint Manager для настройки и управления антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a802e-104">Use Microsoft Endpoint Manager to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a802e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a802e-105">**Applies to:**</span></span>

- [<span data-ttu-id="a802e-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a802e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a802e-107">Вы можете использовать [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) для настройки антивирусная программа в Microsoft Defender сканирования.</span><span class="sxs-lookup"><span data-stu-id="a802e-107">You can use [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to configure Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="a802e-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) и [Диспетчер конфигурации](/mem/configmgr/core/understand/introduction) теперь являются частью Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="a802e-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and [Configuration Manager](/mem/configmgr/core/understand/introduction) are now part of Endpoint Manager.</span></span>  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a><span data-ttu-id="a802e-109">Настройка антивирусная программа в Microsoft Defender в Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="a802e-109">Configure Microsoft Defender Antivirus scans in Endpoint Manager</span></span>

1. <span data-ttu-id="a802e-110">Перейдите в центр Microsoft Endpoint Manager администратора [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войдите.</span><span class="sxs-lookup"><span data-stu-id="a802e-110">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), and sign in.</span></span>

2. <span data-ttu-id="a802e-111">Перейдите к **безопасности конечных точек**.</span><span class="sxs-lookup"><span data-stu-id="a802e-111">Navigate to **Endpoint Security**.</span></span>

3. <span data-ttu-id="a802e-112">В **статье Управление** выберите **антивирус**.</span><span class="sxs-lookup"><span data-stu-id="a802e-112">Under **Manage**, choose **Antivirus**.</span></span>

4. <span data-ttu-id="a802e-113">Выберите антивирусная программа в Microsoft Defender политику.</span><span class="sxs-lookup"><span data-stu-id="a802e-113">Select your Microsoft Defender Antivirus policy.</span></span> 

5. <span data-ttu-id="a802e-114">В разделе **Управление** выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a802e-114">Under **Manage**, choose **Properties**.</span></span>

6. <span data-ttu-id="a802e-115">Рядом с **Параметры конфигурации** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a802e-115">Next to **Configuration settings**, choose **Edit**.</span></span>

7. <span data-ttu-id="a802e-116">**Расширите раздел Scan** и просмотрите или отредактируйте параметры сканирования.</span><span class="sxs-lookup"><span data-stu-id="a802e-116">Expand the **Scan** section, and review or edit your scanning settings.</span></span>

8. <span data-ttu-id="a802e-117">Выберите **Обзор + сохранить**</span><span class="sxs-lookup"><span data-stu-id="a802e-117">Choose **Review + save**</span></span>


> [!TIP]
> <span data-ttu-id="a802e-118">Нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="a802e-118">Need help?</span></span> <span data-ttu-id="a802e-119">См. [в Microsoft Intune Управление безопасностью конечных точек.](/mem/intune/protect/endpoint-security)</span><span class="sxs-lookup"><span data-stu-id="a802e-119">See [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span></span>


## <a name="related-articles"></a><span data-ttu-id="a802e-120">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="a802e-120">Related articles</span></span>

- [<span data-ttu-id="a802e-121">Справочные статьи для средств управления и конфигурации</span><span class="sxs-lookup"><span data-stu-id="a802e-121">Reference articles for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a802e-122">Антивирусная программа в Microsoft Defender (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="a802e-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)