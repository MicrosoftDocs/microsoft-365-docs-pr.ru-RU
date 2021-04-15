---
title: Настройка антивируса Microsoft Defender с помощью диспетчера конфигурации и intune
description: Используйте Microsoft Endpoint Manager и Microsoft Intune для настройки av и защиты конечных точек Microsoft Defender
keywords: scep, intune, endpoint protection, configuration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/26/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 0ab8dde9ba725ec256762ebedce65fdcb22a5cdf
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765651"
---
# <a name="use-microsoft-endpoint-manager-and-microsoft-intune-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="ab914-104">Используйте Microsoft Endpoint Manager и Microsoft Intune для настройки и управления антивирусом Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ab914-104">Use Microsoft Endpoint Manager and Microsoft Intune to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ab914-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ab914-105">**Applies to:**</span></span>

- [<span data-ttu-id="ab914-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ab914-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ab914-107">Если вы использовали Microsoft Endpoint Manager или Microsoft Intune для управления конечными точками в сети, теперь вы можете использовать Microsoft Endpoint Manager для управления антивирусными проверками Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ab914-107">If you were using Microsoft Endpoint Manager or Microsoft Intune to manage the endpoints on your network, you can now use Microsoft Endpoint Manager to manage Microsoft Defender Antivirus scans.</span></span>

1. <span data-ttu-id="ab914-108">В центре администрирования microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) (), перейдите в **службу безопасности конечных точек.**</span><span class="sxs-lookup"><span data-stu-id="ab914-108">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Endpoint Security**.</span></span>

2. <span data-ttu-id="ab914-109">В **статье Управление** выберите **антивирус**.</span><span class="sxs-lookup"><span data-stu-id="ab914-109">Under **Manage**, choose **Antivirus**.</span></span>

3. <span data-ttu-id="ab914-110">Выберите антивирусную политику Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ab914-110">Select your Microsoft Defender Antivirus policy.</span></span> 

4. <span data-ttu-id="ab914-111">В **статье Управление** выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="ab914-111">Under **Manage**, choose **Properties**.</span></span>

5. <span data-ttu-id="ab914-112">Рядом с **настройками конфигурации** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="ab914-112">Next to **Configuration settings**, choose **Edit**.</span></span>

6. <span data-ttu-id="ab914-113">**Расширите раздел Scan** и просмотрите или отредактируйте параметры сканирования.</span><span class="sxs-lookup"><span data-stu-id="ab914-113">Expand the **Scan** section, and review or edit your scanning settings.</span></span>

7. <span data-ttu-id="ab914-114">Выберите **Обзор + сохранить**</span><span class="sxs-lookup"><span data-stu-id="ab914-114">Choose **Review + save**</span></span>

<span data-ttu-id="ab914-115">Нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="ab914-115">Need help?</span></span> <span data-ttu-id="ab914-116">См. [в этой записи Управление безопасностью конечных точек в Microsoft Intune.](/mem/intune/protect/endpoint-security)</span><span class="sxs-lookup"><span data-stu-id="ab914-116">See [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span></span>


## <a name="related-articles"></a><span data-ttu-id="ab914-117">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ab914-117">Related articles</span></span>

- [<span data-ttu-id="ab914-118">Справочные темы для средств управления и конфигурации</span><span class="sxs-lookup"><span data-stu-id="ab914-118">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ab914-119">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="ab914-119">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)