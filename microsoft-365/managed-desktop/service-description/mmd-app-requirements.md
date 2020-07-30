---
title: Требования к классическому приложению, управляемому корпорацией Майкрософт
description: ''
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 94d51d7b28922a05c892eb4ffc14aee813a9069c
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522029"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="e3592-103">Требования к классическому приложению, управляемому корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e3592-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="e3592-104">Для настольных компьютеров Майкрософт необходимо управлять устройствами, используя конкретный подход к обеспечению производительности, надежности и возможности обслуживания устройств.</span><span class="sxs-lookup"><span data-stu-id="e3592-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span> <span data-ttu-id="e3592-105">Если вы уверены, что подход, выполняемый корпорацией Майкрософт для настольных компьютеров, для указанных ниже областей не будет работать, вы можете запросить [исключение в плане обслуживания](customizing.md).</span><span class="sxs-lookup"><span data-stu-id="e3592-105">If you’re sure that the approach taken by Microsoft Managed Desktop for the areas below will not work for you, you can request an [exception to the service plan](customizing.md).</span></span>


|<span data-ttu-id="e3592-106">Область управления</span><span class="sxs-lookup"><span data-stu-id="e3592-106">Management area</span></span>  |<span data-ttu-id="e3592-107">Подход к рабочему столу с управляемыми Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e3592-107">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="e3592-108">Настройка устройств или Управление политиками</span><span class="sxs-lookup"><span data-stu-id="e3592-108">Device configuration or policy management</span></span>     |  <span data-ttu-id="e3592-109">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e3592-109">Microsoft Intune</span></span>       |
|<span data-ttu-id="e3592-110">Управление приложениями</span><span class="sxs-lookup"><span data-stu-id="e3592-110">Application management</span></span>     | <span data-ttu-id="e3592-111">Microsoft Intune и корпоративный портал</span><span class="sxs-lookup"><span data-stu-id="e3592-111">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="e3592-112">Развертывание драйвера</span><span class="sxs-lookup"><span data-stu-id="e3592-112">Driver deployment</span></span>     |  <span data-ttu-id="e3592-113">Драйверы, включенные в устройство, обновление Windows или Intune</span><span class="sxs-lookup"><span data-stu-id="e3592-113">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="e3592-114">Безопасность устройств</span><span class="sxs-lookup"><span data-stu-id="e3592-114">Device security</span></span>     | <span data-ttu-id="e3592-115">См. раздел [безопасность устройства](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="e3592-115">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="e3592-116">Управление идентификацией и доступом</span><span class="sxs-lookup"><span data-stu-id="e3592-116">Identity and access management</span></span>     | <span data-ttu-id="e3592-117">Просмотр [удостоверений и управления доступом](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="e3592-117">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="e3592-118">Безопасность сети</span><span class="sxs-lookup"><span data-stu-id="e3592-118">Network security</span></span>     | <span data-ttu-id="e3592-119">Просмотр [безопасности сети](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="e3592-119">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="e3592-120">Безопасность информации</span><span class="sxs-lookup"><span data-stu-id="e3592-120">Information security</span></span>     |  <span data-ttu-id="e3592-121">Просмотр [сведений о безопасности](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="e3592-121">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="e3592-122">Восстановление данных</span><span class="sxs-lookup"><span data-stu-id="e3592-122">Data recovery</span></span>     | <span data-ttu-id="e3592-123">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e3592-123">OneDrive for Business</span></span>        |
|<span data-ttu-id="e3592-124">Производительность ядра</span><span class="sxs-lookup"><span data-stu-id="e3592-124">Core productivity</span></span>     | <span data-ttu-id="e3592-125">Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e3592-125">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="e3592-126">Браузер</span><span class="sxs-lookup"><span data-stu-id="e3592-126">Browser</span></span>     | <span data-ttu-id="e3592-127">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e3592-127">Microsoft Edge</span></span>        |




<span data-ttu-id="e3592-128">На рабочем столе Майкрософт может отслеживаться другое программное обеспечение, работающее на управляемых устройствах.</span><span class="sxs-lookup"><span data-stu-id="e3592-128">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="e3592-129">Если отрицательно влияет на безопасность, производительность и надежность системы, может потребоваться запросить исключение в плане обслуживания.</span><span class="sxs-lookup"><span data-stu-id="e3592-129">If it negatively impacts system security, performance, or reliability, you might be required to request an exception to the service plan.</span></span>


