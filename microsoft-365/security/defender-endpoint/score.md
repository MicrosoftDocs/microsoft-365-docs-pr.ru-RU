---
title: Методы и свойства оценки
description: Извлекает оценку экспозиции организации, оценку безопасности устройства и оценку экспозиции по группе устройств
keywords: apis, graph api, supported apis, score, exposure score, device secure score, exposure score by device group
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 89012dce4aa5b74d09f071b23f7709b4bd0bf03c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771434"
---
# <a name="score-resource-type"></a><span data-ttu-id="3f866-104">Тип ресурса Score</span><span class="sxs-lookup"><span data-stu-id="3f866-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3f866-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3f866-105">**Applies to:**</span></span>
- [<span data-ttu-id="3f866-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3f866-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3f866-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3f866-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3f866-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="3f866-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3f866-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="3f866-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="3f866-110">Методы</span><span class="sxs-lookup"><span data-stu-id="3f866-110">Methods</span></span>

<span data-ttu-id="3f866-111">Метод</span><span class="sxs-lookup"><span data-stu-id="3f866-111">Method</span></span> |<span data-ttu-id="3f866-112">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="3f866-112">Return Type</span></span> |<span data-ttu-id="3f866-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3f866-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="3f866-114">Получить показатель уязвимости</span><span class="sxs-lookup"><span data-stu-id="3f866-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="3f866-115">Показатель</span><span class="sxs-lookup"><span data-stu-id="3f866-115">Score</span></span>](score.md) | <span data-ttu-id="3f866-116">Получите оценку экспозиции организации.</span><span class="sxs-lookup"><span data-stu-id="3f866-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="3f866-117">Получить оценку безопасности устройства</span><span class="sxs-lookup"><span data-stu-id="3f866-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="3f866-118">Показатель</span><span class="sxs-lookup"><span data-stu-id="3f866-118">Score</span></span>](score.md) | <span data-ttu-id="3f866-119">Получите безопасную оценку для устройства организации.</span><span class="sxs-lookup"><span data-stu-id="3f866-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="3f866-120">Оценка экспозиции списка по группе устройств</span><span class="sxs-lookup"><span data-stu-id="3f866-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="3f866-121">Показатель</span><span class="sxs-lookup"><span data-stu-id="3f866-121">Score</span></span>](score.md) | <span data-ttu-id="3f866-122">Список баллов по группе устройств.</span><span class="sxs-lookup"><span data-stu-id="3f866-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="3f866-123">Свойства</span><span class="sxs-lookup"><span data-stu-id="3f866-123">Properties</span></span>

<span data-ttu-id="3f866-124">Свойство</span><span class="sxs-lookup"><span data-stu-id="3f866-124">Property</span></span> |  <span data-ttu-id="3f866-125">Тип</span><span class="sxs-lookup"><span data-stu-id="3f866-125">Type</span></span>    |   <span data-ttu-id="3f866-126">Описание</span><span class="sxs-lookup"><span data-stu-id="3f866-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="3f866-127">Оценка</span><span class="sxs-lookup"><span data-stu-id="3f866-127">Score</span></span> | <span data-ttu-id="3f866-128">Двойное с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="3f866-128">Double</span></span> | <span data-ttu-id="3f866-129">Текущий балл.</span><span class="sxs-lookup"><span data-stu-id="3f866-129">The current score.</span></span>
<span data-ttu-id="3f866-130">Time</span><span class="sxs-lookup"><span data-stu-id="3f866-130">Time</span></span> | <span data-ttu-id="3f866-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="3f866-131">DateTime</span></span> | <span data-ttu-id="3f866-132">Дата и время, в течение которых был сделан вызов для этого API.</span><span class="sxs-lookup"><span data-stu-id="3f866-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="3f866-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="3f866-133">RbacGroupName</span></span> | <span data-ttu-id="3f866-134">String</span><span class="sxs-lookup"><span data-stu-id="3f866-134">String</span></span> | <span data-ttu-id="3f866-135">Имя группы устройств.</span><span class="sxs-lookup"><span data-stu-id="3f866-135">The device group name.</span></span>
