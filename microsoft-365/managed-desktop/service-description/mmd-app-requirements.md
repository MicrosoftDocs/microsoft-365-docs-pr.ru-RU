---
title: Требования к классическим приложениям, управляемым Майкрософт
description: ''
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 322a46ce48cce4d080e51f482178462934d5c8f2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659718"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="20b61-103">Требования к классическим приложениям, управляемым Майкрософт</span><span class="sxs-lookup"><span data-stu-id="20b61-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="20b61-104">Компьютеры, управляемые Майкрософт, требуют, чтобы мы управляли устройствами с помощью определенного подхода, чтобы гарантировать производительность, надежность и работоспособность устройств.</span><span class="sxs-lookup"><span data-stu-id="20b61-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span>


|<span data-ttu-id="20b61-105">Область управления</span><span class="sxs-lookup"><span data-stu-id="20b61-105">Management area</span></span>  |<span data-ttu-id="20b61-106">Подход к компьютеру, управляемому Майкрософт</span><span class="sxs-lookup"><span data-stu-id="20b61-106">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="20b61-107">Конфигурация устройства или управление политиками</span><span class="sxs-lookup"><span data-stu-id="20b61-107">Device configuration or policy management</span></span>     |  <span data-ttu-id="20b61-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="20b61-108">Microsoft Intune</span></span>       |
|<span data-ttu-id="20b61-109">Управление приложениями</span><span class="sxs-lookup"><span data-stu-id="20b61-109">Application management</span></span>     | <span data-ttu-id="20b61-110">Microsoft Intune и портал компании</span><span class="sxs-lookup"><span data-stu-id="20b61-110">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="20b61-111">Развертывание драйверов</span><span class="sxs-lookup"><span data-stu-id="20b61-111">Driver deployment</span></span>     |  <span data-ttu-id="20b61-112">Драйверы, включенные в устройство, Windows Update или Intune</span><span class="sxs-lookup"><span data-stu-id="20b61-112">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="20b61-113">Безопасность устройств</span><span class="sxs-lookup"><span data-stu-id="20b61-113">Device security</span></span>     | <span data-ttu-id="20b61-114">См. ["Безопасность устройств"](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="20b61-114">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="20b61-115">Управление идентификацией и доступом</span><span class="sxs-lookup"><span data-stu-id="20b61-115">Identity and access management</span></span>     | <span data-ttu-id="20b61-116">См. ["Управление удостоверением и доступом"](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="20b61-116">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="20b61-117">Безопасность сети</span><span class="sxs-lookup"><span data-stu-id="20b61-117">Network security</span></span>     | <span data-ttu-id="20b61-118">См. ["Безопасность сети"](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="20b61-118">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="20b61-119">Информационная безопасность</span><span class="sxs-lookup"><span data-stu-id="20b61-119">Information security</span></span>     |  <span data-ttu-id="20b61-120">См. ["Информационная безопасность"](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="20b61-120">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="20b61-121">Восстановление данных</span><span class="sxs-lookup"><span data-stu-id="20b61-121">Data recovery</span></span>     | <span data-ttu-id="20b61-122">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="20b61-122">OneDrive for Business</span></span>        |
|<span data-ttu-id="20b61-123">Основная производительность</span><span class="sxs-lookup"><span data-stu-id="20b61-123">Core productivity</span></span>     | <span data-ttu-id="20b61-124">Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="20b61-124">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="20b61-125">Браузер</span><span class="sxs-lookup"><span data-stu-id="20b61-125">Browser</span></span>     | <span data-ttu-id="20b61-126">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="20b61-126">Microsoft Edge</span></span>        |




<span data-ttu-id="20b61-127">Компьютеры, управляемые Майкрософт, могут отслеживать другое программное обеспечение, запущенное на управляемых устройствах.</span><span class="sxs-lookup"><span data-stu-id="20b61-127">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="20b61-128">Если это отрицательно сказывается на управлении устройствами, безопасности, производительности или надежности устройств, может потребоваться запросить исключение из [плана обслуживания.](customizing.md)</span><span class="sxs-lookup"><span data-stu-id="20b61-128">If it negatively impacts device management, device security, performance, or reliability, you might be required to request an [exception to the service plan](customizing.md).</span></span>
