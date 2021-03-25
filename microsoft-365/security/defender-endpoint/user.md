---
title: Тип ресурса пользователя
description: Извлечение последних оповещений Microsoft Defender для конечных точек, связанных с пользователями.
keywords: apis, graph api, supported apis, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e3b2a567a953883d1d0ecd062159bfee4135dc85
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51197961"
---
# <a name="user-resource-type"></a><span data-ttu-id="9bba1-104">Тип ресурса user</span><span class="sxs-lookup"><span data-stu-id="9bba1-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9bba1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9bba1-105">**Applies to:**</span></span>
- [<span data-ttu-id="9bba1-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9bba1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="9bba1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bba1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9bba1-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="9bba1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9bba1-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="9bba1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="9bba1-110">Метод</span><span class="sxs-lookup"><span data-stu-id="9bba1-110">Method</span></span>|<span data-ttu-id="9bba1-111">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="9bba1-111">Return Type</span></span> |<span data-ttu-id="9bba1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9bba1-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="9bba1-113">Списки оповещений, связанных с пользователем</span><span class="sxs-lookup"><span data-stu-id="9bba1-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="9bba1-114">Коллекция [alert](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="9bba1-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="9bba1-115">Список всех оповещений, связанных с [пользователем.](user.md)</span><span class="sxs-lookup"><span data-stu-id="9bba1-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="9bba1-116">Список устройств, связанных с пользователем</span><span class="sxs-lookup"><span data-stu-id="9bba1-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="9bba1-117">[коллекция](machine.md) машин</span><span class="sxs-lookup"><span data-stu-id="9bba1-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="9bba1-118">Список всех устройств, которые были зарегистрированы [пользователем.](user.md)</span><span class="sxs-lookup"><span data-stu-id="9bba1-118">List all the devices that were logged on by a [user](user.md).</span></span>
