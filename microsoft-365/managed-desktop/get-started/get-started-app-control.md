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
# <a name="get-started-with-app-control"></a><span data-ttu-id="b703e-103">Начало работы с элементом управления приложениями</span><span class="sxs-lookup"><span data-stu-id="b703e-103">Get started with app control</span></span>

<span data-ttu-id="b703e-104">Перед включением управления приложениями в среде обязательно ознакомьтесь со [сведениями о том, как на рабочем столе, управляемом Майкрософт, реализуется его](../service-description/app-control.md) роли и обязанности.</span><span class="sxs-lookup"><span data-stu-id="b703e-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="b703e-105">Рабочий стол, управляемый корпорацией Майкрософт, упрощает управление приложениями, преднимая более сложные аспекты получения безопасной базовой политики.</span><span class="sxs-lookup"><span data-stu-id="b703e-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="b703e-106">ИТ-администраторы должны по-прежнему протестировать приложения в тестовом кольце и просмотреть журналы на наличие предупреждений и ошибок.</span><span class="sxs-lookup"><span data-stu-id="b703e-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="b703e-107">Если приложению требуется исключение, можно заархивировать запрос или операцию рабочего стола, управляемую Майкрософт, в зависимости от того, кто обнаруживает его.</span><span class="sxs-lookup"><span data-stu-id="b703e-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="b703e-108">Начальное развертывание приложений</span><span class="sxs-lookup"><span data-stu-id="b703e-108">Initial deployment of apps</span></span>

<span data-ttu-id="b703e-109">При первом развертывании приложений компьютер, управляемый Майкрософт, должен оценить их текущее поведение.</span><span class="sxs-lookup"><span data-stu-id="b703e-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="b703e-110">Действия, необходимые для включения управления приложениями, зависят от того, были ли уже развернуты устройства в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="b703e-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="b703e-111">Устройства еще не используются</span><span class="sxs-lookup"><span data-stu-id="b703e-111">Devices not yet in use</span></span>

<span data-ttu-id="b703e-112">Если вы еще не используете устройства, откройте билет службы с управляемыми рабочими операциями, выполняемыми корпорацией Майкрософт, который запрашивает включение управления приложением.</span><span class="sxs-lookup"><span data-stu-id="b703e-112">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="b703e-113">Операции будут последовательно развертывать политики в группах развертывания, следующих за этим расписанием:</span><span class="sxs-lookup"><span data-stu-id="b703e-113">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="b703e-114">Группа развертывания</span><span class="sxs-lookup"><span data-stu-id="b703e-114">Deployment group</span></span>  |<span data-ttu-id="b703e-115">Тип политики</span><span class="sxs-lookup"><span data-stu-id="b703e-115">Policy type</span></span>  |<span data-ttu-id="b703e-116">Время</span><span class="sxs-lookup"><span data-stu-id="b703e-116">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b703e-117">Тест</span><span class="sxs-lookup"><span data-stu-id="b703e-117">Test</span></span>     |  <span data-ttu-id="b703e-118">Аудит</span><span class="sxs-lookup"><span data-stu-id="b703e-118">Audit</span></span>       |  <span data-ttu-id="b703e-119">День 0</span><span class="sxs-lookup"><span data-stu-id="b703e-119">Day 0</span></span>       |
|<span data-ttu-id="b703e-120">Первый</span><span class="sxs-lookup"><span data-stu-id="b703e-120">First</span></span>     | <span data-ttu-id="b703e-121">Enforced</span><span class="sxs-lookup"><span data-stu-id="b703e-121">Enforced</span></span>        | <span data-ttu-id="b703e-122">День 1</span><span class="sxs-lookup"><span data-stu-id="b703e-122">Day 1</span></span>        |
|<span data-ttu-id="b703e-123">Быстро</span><span class="sxs-lookup"><span data-stu-id="b703e-123">Fast</span></span>     | <span data-ttu-id="b703e-124">Enforced</span><span class="sxs-lookup"><span data-stu-id="b703e-124">Enforced</span></span>        |  <span data-ttu-id="b703e-125">День 2</span><span class="sxs-lookup"><span data-stu-id="b703e-125">Day 2</span></span>       |
|<span data-ttu-id="b703e-126">Общие</span><span class="sxs-lookup"><span data-stu-id="b703e-126">Broad</span></span>     | <span data-ttu-id="b703e-127">Enforced</span><span class="sxs-lookup"><span data-stu-id="b703e-127">Enforced</span></span>        |  <span data-ttu-id="b703e-128">День 3</span><span class="sxs-lookup"><span data-stu-id="b703e-128">Day 3</span></span>       |

<span data-ttu-id="b703e-129">Вы всегда можете открыть другой запрос на обслуживание, чтобы приостановить или откатить часть этого развертывания в любой момент во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="b703e-129">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="b703e-130">Устройства уже используются</span><span class="sxs-lookup"><span data-stu-id="b703e-130">Devices already in use</span></span>

<span data-ttu-id="b703e-131">Если у вас уже есть хотя бы одно устройство для настольных компьютеров под управлением Майкрософт, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b703e-131">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="b703e-132">Откройте билет службы с управляемыми рабочими столами Майкрософт, запрашивающие Управление приложениями.</span><span class="sxs-lookup"><span data-stu-id="b703e-132">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="b703e-133">Операции будут разворачивать [политику аудита](../service-description/app-control.md#audit-policy) для всех устройств.</span><span class="sxs-lookup"><span data-stu-id="b703e-133">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="b703e-134">[Протестируйте приложения](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) , чтобы убедиться, что они заблокированы.</span><span class="sxs-lookup"><span data-stu-id="b703e-134">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="b703e-135">Если приложение будет заблокировано, откройте [запрос подписавшего](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span><span class="sxs-lookup"><span data-stu-id="b703e-135">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="b703e-136">Завершив тестирование (результаты), уведомите операции, заметив все ожидающие запросы подписавшего.</span><span class="sxs-lookup"><span data-stu-id="b703e-136">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="b703e-137">Операции будут последовательно развертывать политики в группах развертывания, следующих за этим расписанием:</span><span class="sxs-lookup"><span data-stu-id="b703e-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="b703e-138">Группа развертывания</span><span class="sxs-lookup"><span data-stu-id="b703e-138">Deployment group</span></span>  |<span data-ttu-id="b703e-139">Тип политики</span><span class="sxs-lookup"><span data-stu-id="b703e-139">Policy type</span></span>  |<span data-ttu-id="b703e-140">Время</span><span class="sxs-lookup"><span data-stu-id="b703e-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b703e-141">Тест</span><span class="sxs-lookup"><span data-stu-id="b703e-141">Test</span></span>     |  <span data-ttu-id="b703e-142">Аудит</span><span class="sxs-lookup"><span data-stu-id="b703e-142">Audit</span></span>       |  <span data-ttu-id="b703e-143">День 0</span><span class="sxs-lookup"><span data-stu-id="b703e-143">Day 0</span></span>       |
|<span data-ttu-id="b703e-144">Первый</span><span class="sxs-lookup"><span data-stu-id="b703e-144">First</span></span>     | <span data-ttu-id="b703e-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="b703e-145">Enforced</span></span>        | <span data-ttu-id="b703e-146">День 1</span><span class="sxs-lookup"><span data-stu-id="b703e-146">Day 1</span></span>        |
|<span data-ttu-id="b703e-147">Быстро</span><span class="sxs-lookup"><span data-stu-id="b703e-147">Fast</span></span>     | <span data-ttu-id="b703e-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="b703e-148">Enforced</span></span>        |  <span data-ttu-id="b703e-149">Приостановлено, развертывание по запросу</span><span class="sxs-lookup"><span data-stu-id="b703e-149">Paused, rollout on request</span></span>       |
|<span data-ttu-id="b703e-150">Общие</span><span class="sxs-lookup"><span data-stu-id="b703e-150">Broad</span></span>     | <span data-ttu-id="b703e-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="b703e-151">Enforced</span></span>        |  <span data-ttu-id="b703e-152">Приостановлено, развертывание по запросу</span><span class="sxs-lookup"><span data-stu-id="b703e-152">Paused, rollout on request</span></span>       |

<span data-ttu-id="b703e-153">Вы всегда можете открыть другой запрос на обслуживание, чтобы приостановить или откатить часть этого развертывания в любой момент во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="b703e-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>



