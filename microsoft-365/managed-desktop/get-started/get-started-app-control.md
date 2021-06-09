---
title: Начало работы с элементом управления приложениями
description: ''
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430463"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="44c43-103">Начало работы с элементом управления приложениями</span><span class="sxs-lookup"><span data-stu-id="44c43-103">Get started with app control</span></span>

<span data-ttu-id="44c43-104">Прежде чем включить управление приложениями в среде, обязательно просмотрите и [поймете,](../service-description/app-control.md) компьютеры, управляемые Майкрософт реализует его, а также роли и обязанности.</span><span class="sxs-lookup"><span data-stu-id="44c43-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="44c43-105">компьютеры, управляемые Майкрософт упрощает управление приложениями, заботясь о более сложных аспектах получения безопасной базовой политики.</span><span class="sxs-lookup"><span data-stu-id="44c43-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="44c43-106">ИТ-администраторы по-прежнему должны протестировать приложения на кольце Тестирования и просмотреть журналы на любые предупреждения или ошибки.</span><span class="sxs-lookup"><span data-stu-id="44c43-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="44c43-107">Если приложение нуждается в освобождении, вы можете подать запрос, или компьютеры, управляемые Майкрософт операция может, в зависимости от того, кто обнаруживает его в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="44c43-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="44c43-108">Начальное развертывание приложений</span><span class="sxs-lookup"><span data-stu-id="44c43-108">Initial deployment of apps</span></span>

<span data-ttu-id="44c43-109">При первом развертывании приложений компьютеры, управляемые Майкрософт оценить их текущее поведение.</span><span class="sxs-lookup"><span data-stu-id="44c43-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="44c43-110">Точные действия для включения управления приложениями зависят от того, были ли устройства уже развернуты в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="44c43-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="44c43-111">Устройства, которые еще не используются</span><span class="sxs-lookup"><span data-stu-id="44c43-111">Devices not yet in use</span></span>

<span data-ttu-id="44c43-112">Если у вас еще нет устройств, откройте билет на службу с компьютеры, управляемые Майкрософт операций с просьбой включить управление приложениями.</span><span class="sxs-lookup"><span data-stu-id="44c43-112">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="44c43-113">Операции будут постепенно развертывать политики в группах развертывания по следующему расписанию:</span><span class="sxs-lookup"><span data-stu-id="44c43-113">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="44c43-114">Группа развертывания</span><span class="sxs-lookup"><span data-stu-id="44c43-114">Deployment group</span></span>  |<span data-ttu-id="44c43-115">Тип политики</span><span class="sxs-lookup"><span data-stu-id="44c43-115">Policy type</span></span>  |<span data-ttu-id="44c43-116">Время</span><span class="sxs-lookup"><span data-stu-id="44c43-116">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="44c43-117">Тест</span><span class="sxs-lookup"><span data-stu-id="44c43-117">Test</span></span>     |  <span data-ttu-id="44c43-118">Аудит</span><span class="sxs-lookup"><span data-stu-id="44c43-118">Audit</span></span>       |  <span data-ttu-id="44c43-119">День 0</span><span class="sxs-lookup"><span data-stu-id="44c43-119">Day 0</span></span>       |
|<span data-ttu-id="44c43-120">Первый</span><span class="sxs-lookup"><span data-stu-id="44c43-120">First</span></span>     | <span data-ttu-id="44c43-121">Enforced</span><span class="sxs-lookup"><span data-stu-id="44c43-121">Enforced</span></span>        | <span data-ttu-id="44c43-122">День 1</span><span class="sxs-lookup"><span data-stu-id="44c43-122">Day 1</span></span>        |
|<span data-ttu-id="44c43-123">Быстро</span><span class="sxs-lookup"><span data-stu-id="44c43-123">Fast</span></span>     | <span data-ttu-id="44c43-124">Enforced</span><span class="sxs-lookup"><span data-stu-id="44c43-124">Enforced</span></span>        |  <span data-ttu-id="44c43-125">День 2</span><span class="sxs-lookup"><span data-stu-id="44c43-125">Day 2</span></span>       |
|<span data-ttu-id="44c43-126">Общие</span><span class="sxs-lookup"><span data-stu-id="44c43-126">Broad</span></span>     | <span data-ttu-id="44c43-127">Enforced</span><span class="sxs-lookup"><span data-stu-id="44c43-127">Enforced</span></span>        |  <span data-ttu-id="44c43-128">День 3</span><span class="sxs-lookup"><span data-stu-id="44c43-128">Day 3</span></span>       |

<span data-ttu-id="44c43-129">Вы всегда можете открыть другой запрос службы для приостановки или отката части этого развертывания в любое время во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="44c43-129">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="44c43-130">Устройства, которые уже используются</span><span class="sxs-lookup"><span data-stu-id="44c43-130">Devices already in use</span></span>

<span data-ttu-id="44c43-131">Если уже используется по крайней мере компьютеры, управляемые Майкрософт устройство, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="44c43-131">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="44c43-132">Откройте билет на службу с компьютеры, управляемые Майкрософт операций с запросом включить управление приложениями.</span><span class="sxs-lookup"><span data-stu-id="44c43-132">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="44c43-133">Операции будут развертывать политику [аудита на](../service-description/app-control.md#audit-policy) всех устройствах.</span><span class="sxs-lookup"><span data-stu-id="44c43-133">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="44c43-134">[Проверьте, будут](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) ли какие-либо приложения заблокированы.</span><span class="sxs-lookup"><span data-stu-id="44c43-134">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="44c43-135">Если приложение будет заблокировано, откройте запрос [подписавщика.](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)</span><span class="sxs-lookup"><span data-stu-id="44c43-135">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="44c43-136">После завершения тестирования (независимо от результатов) сообщите об операциях, замещая все ожидающие запросы подписав.</span><span class="sxs-lookup"><span data-stu-id="44c43-136">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="44c43-137">Операции будут постепенно развертывать политики в группах развертывания по следующему расписанию:</span><span class="sxs-lookup"><span data-stu-id="44c43-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="44c43-138">Группа развертывания</span><span class="sxs-lookup"><span data-stu-id="44c43-138">Deployment group</span></span>  |<span data-ttu-id="44c43-139">Тип политики</span><span class="sxs-lookup"><span data-stu-id="44c43-139">Policy type</span></span>  |<span data-ttu-id="44c43-140">Время</span><span class="sxs-lookup"><span data-stu-id="44c43-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="44c43-141">Тест</span><span class="sxs-lookup"><span data-stu-id="44c43-141">Test</span></span>     |  <span data-ttu-id="44c43-142">Аудит</span><span class="sxs-lookup"><span data-stu-id="44c43-142">Audit</span></span>       |  <span data-ttu-id="44c43-143">День 0</span><span class="sxs-lookup"><span data-stu-id="44c43-143">Day 0</span></span>       |
|<span data-ttu-id="44c43-144">Первый</span><span class="sxs-lookup"><span data-stu-id="44c43-144">First</span></span>     | <span data-ttu-id="44c43-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="44c43-145">Enforced</span></span>        | <span data-ttu-id="44c43-146">День 1</span><span class="sxs-lookup"><span data-stu-id="44c43-146">Day 1</span></span>        |
|<span data-ttu-id="44c43-147">Быстро</span><span class="sxs-lookup"><span data-stu-id="44c43-147">Fast</span></span>     | <span data-ttu-id="44c43-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="44c43-148">Enforced</span></span>        |  <span data-ttu-id="44c43-149">Приостановлено, выкат по запросу</span><span class="sxs-lookup"><span data-stu-id="44c43-149">Paused, rollout on request</span></span>       |
|<span data-ttu-id="44c43-150">Общие</span><span class="sxs-lookup"><span data-stu-id="44c43-150">Broad</span></span>     | <span data-ttu-id="44c43-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="44c43-151">Enforced</span></span>        |  <span data-ttu-id="44c43-152">Приостановлено, выкат по запросу</span><span class="sxs-lookup"><span data-stu-id="44c43-152">Paused, rollout on request</span></span>       |

<span data-ttu-id="44c43-153">Вы всегда можете открыть другой запрос службы для приостановки или отката части этого развертывания в любое время во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="44c43-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>



