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
# <a name="get-started-with-app-control"></a><span data-ttu-id="38f91-103">Начало работы с элементом управления приложениями</span><span class="sxs-lookup"><span data-stu-id="38f91-103">Get started with app control</span></span>

<span data-ttu-id="38f91-104">Прежде чем включить управление приложениями в своей среде, обязательно просмотрите и поймете, как [управляемые Майкрософт](../service-description/app-control.md) компьютеры реализуют его, а также ваши роли и обязанности.</span><span class="sxs-lookup"><span data-stu-id="38f91-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="38f91-105">Компьютеры, управляемые Майкрософт, упрощают управление приложениями, принимая во внимание более сложные аспекты получения безопасной базовой политики.</span><span class="sxs-lookup"><span data-stu-id="38f91-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="38f91-106">ИТ-администраторам по-прежнему необходимо протестировать приложения в круге тестирования и просмотреть журналы на все предупреждения или ошибки.</span><span class="sxs-lookup"><span data-stu-id="38f91-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="38f91-107">Если приложению требуется исключение, вы можете подать запрос, или в зависимости от того, кто первым обнаружит его, может потребоваться операция microsoft Managed Desktop Operation.</span><span class="sxs-lookup"><span data-stu-id="38f91-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="38f91-108">Начальное развертывание приложений</span><span class="sxs-lookup"><span data-stu-id="38f91-108">Initial deployment of apps</span></span>

<span data-ttu-id="38f91-109">При первом развертывании приложений компьютеры, управляемые Майкрософт, должны оценить их текущее поведение.</span><span class="sxs-lookup"><span data-stu-id="38f91-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="38f91-110">Конкретные действия по включанию управления приложениями зависят от того, были ли устройства уже развернуты в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="38f91-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="38f91-111">Устройства еще не используются</span><span class="sxs-lookup"><span data-stu-id="38f91-111">Devices not yet in use</span></span>

<span data-ttu-id="38f91-112">Если у вас еще нет устройств, откройте билет службы с помощью операций microsoft Managed Desktop Operations с запросом на включение управления приложениями.</span><span class="sxs-lookup"><span data-stu-id="38f91-112">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="38f91-113">Операции постепенно развертывают политики в группах развертывания по следующему расписанию:</span><span class="sxs-lookup"><span data-stu-id="38f91-113">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="38f91-114">Группа развертывания</span><span class="sxs-lookup"><span data-stu-id="38f91-114">Deployment group</span></span>  |<span data-ttu-id="38f91-115">Тип политики</span><span class="sxs-lookup"><span data-stu-id="38f91-115">Policy type</span></span>  |<span data-ttu-id="38f91-116">Время</span><span class="sxs-lookup"><span data-stu-id="38f91-116">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="38f91-117">Тест</span><span class="sxs-lookup"><span data-stu-id="38f91-117">Test</span></span>     |  <span data-ttu-id="38f91-118">Аудит</span><span class="sxs-lookup"><span data-stu-id="38f91-118">Audit</span></span>       |  <span data-ttu-id="38f91-119">День 0</span><span class="sxs-lookup"><span data-stu-id="38f91-119">Day 0</span></span>       |
|<span data-ttu-id="38f91-120">Первый</span><span class="sxs-lookup"><span data-stu-id="38f91-120">First</span></span>     | <span data-ttu-id="38f91-121">Enforced</span><span class="sxs-lookup"><span data-stu-id="38f91-121">Enforced</span></span>        | <span data-ttu-id="38f91-122">День 1</span><span class="sxs-lookup"><span data-stu-id="38f91-122">Day 1</span></span>        |
|<span data-ttu-id="38f91-123">Быстро</span><span class="sxs-lookup"><span data-stu-id="38f91-123">Fast</span></span>     | <span data-ttu-id="38f91-124">Enforced</span><span class="sxs-lookup"><span data-stu-id="38f91-124">Enforced</span></span>        |  <span data-ttu-id="38f91-125">День 2</span><span class="sxs-lookup"><span data-stu-id="38f91-125">Day 2</span></span>       |
|<span data-ttu-id="38f91-126">Общие</span><span class="sxs-lookup"><span data-stu-id="38f91-126">Broad</span></span>     | <span data-ttu-id="38f91-127">Enforced</span><span class="sxs-lookup"><span data-stu-id="38f91-127">Enforced</span></span>        |  <span data-ttu-id="38f91-128">День 3</span><span class="sxs-lookup"><span data-stu-id="38f91-128">Day 3</span></span>       |

<span data-ttu-id="38f91-129">Вы всегда можете открыть другой запрос на обслуживание, чтобы приостановить или откатить часть этого развертывания в любое время во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="38f91-129">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="38f91-130">Устройства, которые уже используются</span><span class="sxs-lookup"><span data-stu-id="38f91-130">Devices already in use</span></span>

<span data-ttu-id="38f91-131">Если уже используется хотя бы одно настольное устройство, управляемое Майкрософт, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="38f91-131">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="38f91-132">Откройте билет службы с помощью операций microsoft Managed Desktop Operations с запросом на включение управления приложениями.</span><span class="sxs-lookup"><span data-stu-id="38f91-132">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="38f91-133">Операции будут развертывать политику [аудита](../service-description/app-control.md#audit-policy) на всех устройствах.</span><span class="sxs-lookup"><span data-stu-id="38f91-133">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="38f91-134">[Проверьте свои приложения,](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) чтобы проверить, будут ли они заблокированы.</span><span class="sxs-lookup"><span data-stu-id="38f91-134">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="38f91-135">Если приложение будет заблокировано, откройте запрос [подписи.](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)</span><span class="sxs-lookup"><span data-stu-id="38f91-135">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="38f91-136">Завершив тестирование (независимо от результатов), уведомите Operations, замещая ожидающие запросы подписав.</span><span class="sxs-lookup"><span data-stu-id="38f91-136">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="38f91-137">Операции постепенно развертывают политики в группах развертывания по следующему расписанию:</span><span class="sxs-lookup"><span data-stu-id="38f91-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="38f91-138">Группа развертывания</span><span class="sxs-lookup"><span data-stu-id="38f91-138">Deployment group</span></span>  |<span data-ttu-id="38f91-139">Тип политики</span><span class="sxs-lookup"><span data-stu-id="38f91-139">Policy type</span></span>  |<span data-ttu-id="38f91-140">Время</span><span class="sxs-lookup"><span data-stu-id="38f91-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="38f91-141">Тест</span><span class="sxs-lookup"><span data-stu-id="38f91-141">Test</span></span>     |  <span data-ttu-id="38f91-142">Аудит</span><span class="sxs-lookup"><span data-stu-id="38f91-142">Audit</span></span>       |  <span data-ttu-id="38f91-143">День 0</span><span class="sxs-lookup"><span data-stu-id="38f91-143">Day 0</span></span>       |
|<span data-ttu-id="38f91-144">Первый</span><span class="sxs-lookup"><span data-stu-id="38f91-144">First</span></span>     | <span data-ttu-id="38f91-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="38f91-145">Enforced</span></span>        | <span data-ttu-id="38f91-146">День 1</span><span class="sxs-lookup"><span data-stu-id="38f91-146">Day 1</span></span>        |
|<span data-ttu-id="38f91-147">Быстро</span><span class="sxs-lookup"><span data-stu-id="38f91-147">Fast</span></span>     | <span data-ttu-id="38f91-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="38f91-148">Enforced</span></span>        |  <span data-ttu-id="38f91-149">Приостановлено, выкат по запросу</span><span class="sxs-lookup"><span data-stu-id="38f91-149">Paused, rollout on request</span></span>       |
|<span data-ttu-id="38f91-150">Общие</span><span class="sxs-lookup"><span data-stu-id="38f91-150">Broad</span></span>     | <span data-ttu-id="38f91-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="38f91-151">Enforced</span></span>        |  <span data-ttu-id="38f91-152">Приостановлено, выкат по запросу</span><span class="sxs-lookup"><span data-stu-id="38f91-152">Paused, rollout on request</span></span>       |

<span data-ttu-id="38f91-153">Вы всегда можете открыть другой запрос на обслуживание, чтобы приостановить или откатить часть этого развертывания в любое время во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="38f91-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>



