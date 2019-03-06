---
title: Развертывание настраиваемых параметров на наСтольном компьютере, управляемом Майкрософт
description: Развертывание и отслеживание настраиваемых изменений параметров на наСтольном компьютере, управляемом Майкрософт.
keywords: НаСтольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация, развертывание, поэтапное развертывание, настраиваемые параметры
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 62a17c95f5dc6b11f446a27684c507d7aaa95b7b
ms.sourcegitcommit: 8d2e6bcc257a665f53ee914c7f0e1dfb9d31a9e0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "30414175"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="b3788-104">Развертывание и отслеживание настраиваемых параметров — Рабочий стол, управляемый корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b3788-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="b3788-105">После внесения изменений в категории параметров и поэтапного развертывания можно развернуть и отслеживать ход развертывания по состоянию развертывания.</span><span class="sxs-lookup"><span data-stu-id="b3788-105">After you make changes to your setting categories and stage a deployment, you can deploy and track progress for the deployment on Deployment status.</span></span> <span data-ttu-id="b3788-106">На этой странице приведены сводные сведения о настраиваемых параметрах.</span><span class="sxs-lookup"><span data-stu-id="b3788-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="b3788-107">Откройте категорию параметров, чтобы просмотреть каждое развертывание и их сведения, чтобы развернуть изменения.</span><span class="sxs-lookup"><span data-stu-id="b3788-107">Open a setting category to see each deployment and their details, to deploy the changes.</span></span> 

## <a name="deployment-statuses"></a><span data-ttu-id="b3788-108">Состояния развертывания</span><span class="sxs-lookup"><span data-stu-id="b3788-108">Deployment statuses</span></span> 

<span data-ttu-id="b3788-109">Это статуес, которые будут отображаться для каждого развертывания.</span><span class="sxs-lookup"><span data-stu-id="b3788-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="b3788-110">Status</span><span class="sxs-lookup"><span data-stu-id="b3788-110">Status</span></span>  | <span data-ttu-id="b3788-111">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b3788-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="b3788-112">Развертывание</span><span class="sxs-lookup"><span data-stu-id="b3788-112">Deploy</span></span> | <span data-ttu-id="b3788-113">Ваше изменение ожидает развертывания в этом кольце.</span><span class="sxs-lookup"><span data-stu-id="b3788-113">Your change is waiting to be deployed to this ring.</span></span>
<span data-ttu-id="b3788-114">Выполняется</span><span class="sxs-lookup"><span data-stu-id="b3788-114">In progress</span></span> | <span data-ttu-id="b3788-115">Изменение применяется к активным устройствам в этом кольце.</span><span class="sxs-lookup"><span data-stu-id="b3788-115">The change is being applied to active devices in this ring.</span></span> 
<span data-ttu-id="b3788-116">Завершение</span><span class="sxs-lookup"><span data-stu-id="b3788-116">Complete</span></span> | <span data-ttu-id="b3788-117">Изменение завершено на всех активных устройствах в этом круге.</span><span class="sxs-lookup"><span data-stu-id="b3788-117">The change completed on all active devices in this ring.</span></span> 
<span data-ttu-id="b3788-118">Failed</span><span class="sxs-lookup"><span data-stu-id="b3788-118">Failed</span></span> | <span data-ttu-id="b3788-119">Изменение не удалось выполнить на 10 процентов активных устройств в кольце, поэтому развертывание было остановлено.</span><span class="sxs-lookup"><span data-stu-id="b3788-119">The change failed on a 10 percent of active devices in the ring, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="b3788-120">Запрос В службу поддержки будет автоматически открыт с помощью управляемых операций на рабочем столе Майкрософт для устранения неполадок в развертывании.</span><span class="sxs-lookup"><span data-stu-id="b3788-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="b3788-121">Возвращаются</span><span class="sxs-lookup"><span data-stu-id="b3788-121">Reverted</span></span> | <span data-ttu-id="b3788-122">Изменено Последнее изменение, которое было успешно развернуто во всех кольцах развертывания.</span><span class="sxs-lookup"><span data-stu-id="b3788-122">The change was reverted to the last change that was successfully deployed to all deployment rings.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="b3788-123">Развертывание изменений</span><span class="sxs-lookup"><span data-stu-id="b3788-123">Deploy changes</span></span>

<span data-ttu-id="b3788-124">В этих инструкциях мы будем показывать фоновый рисунок рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="b3788-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="b3788-125">После поэтапного развертывания вы развертываете изменения из состояния развертывания.</span><span class="sxs-lookup"><span data-stu-id="b3788-125">After you’ve staged a deployment, you deploy changes from Deployment status.</span></span> 

<span data-ttu-id="b3788-126">**Развертывание изменений**</span><span class="sxs-lookup"><span data-stu-id="b3788-126">**To deploy changes**</span></span>

1. <span data-ttu-id="b3788-127">Вход на [портал администрирования рабочих столов с управляемЫми Майкрософт](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="b3788-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="b3788-128">В разделе **Параметры**выберите пункт **Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="b3788-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="b3788-129">В рабочей области **состояния развертывания** выберите параметр, который необходимо развернуть, а затем выберите поэтапное развертывание для развертывания.</span><span class="sxs-lookup"><span data-stu-id="b3788-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="b3788-130">Нажмите кнопку **развернуть** , чтобы развернуть изменения в одном из звонков развертывания.</span><span class="sxs-lookup"><span data-stu-id="b3788-130">Select **Deploy** to deploy the change to one of the deployment rings.</span></span>

![Общие сведения о состоянии развертывания настраиваемых параметров](images/deploy-cs-overview.png)

<span data-ttu-id="b3788-132">НаСтольные компьютеры, управляемые корпорацией Майкрософт, рекомендуют развертывать на кольцах в следующем порядке: Test, First, Fast, а затем в широком смысле.</span><span class="sxs-lookup"><span data-stu-id="b3788-132">Microsoft Managed Desktop recommends deploying to deployment rings in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="b3788-133">По завершении изменений каждого кольца состояние изменится на " **завершено**".</span><span class="sxs-lookup"><span data-stu-id="b3788-133">When changes complete in each ring, the status changes to **Complete**.</span></span>

![Развертывание настраиваемых параметров завершено](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="b3788-135">Отмена развертывания</span><span class="sxs-lookup"><span data-stu-id="b3788-135">Revert deployment</span></span>

<span data-ttu-id="b3788-136">В этих инструкциях мы будем показывать фоновый рисунок рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="b3788-136">We’ll show Desktop background picture in these instructions.</span></span> 

<span data-ttu-id="b3788-137">После развертывания изменения можно вернуться к **состоянию развертывания**.</span><span class="sxs-lookup"><span data-stu-id="b3788-137">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="b3788-138">При возвращении изменения, которое выполняется \*\*\*\* или завершено, текущее развертывание перестает быть **завершенным**.</span><span class="sxs-lookup"><span data-stu-id="b3788-138">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="b3788-139">Этот параметр вернется к последней версии, которая была развернута для всех звонков.</span><span class="sxs-lookup"><span data-stu-id="b3788-139">The setting will revert to the last version that was deployed to all rings.</span></span> 

<span data-ttu-id="b3788-140">**Отмена изменения**</span><span class="sxs-lookup"><span data-stu-id="b3788-140">**To revert a change**</span></span>
1. <span data-ttu-id="b3788-141">Вход на [портал администрирования рабочих столов с управляемЫми Майкрософт](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="b3788-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="b3788-142">В разделе **Параметры**выберите пункт **Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="b3788-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="b3788-143">В рабочей области **состояния развертывания** выберите параметр, который требуется восстановить, а затем выберите поэтапное развертывание для отмены.</span><span class="sxs-lookup"><span data-stu-id="b3788-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="b3788-144">В разделе **необходимо отменить это изменение**выберите **вернуть развертывание**.</span><span class="sxs-lookup"><span data-stu-id="b3788-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![Возврат настраиваемых параметров развертывания](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="b3788-146">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="b3788-146">Additional resources</span></span>
- [<span data-ttu-id="b3788-147">Общие сведения о настраиваемых параметрах</span><span class="sxs-lookup"><span data-stu-id="b3788-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="b3788-148">Справочные сведения о настраиваемых параметрах</span><span class="sxs-lookup"><span data-stu-id="b3788-148">Configurable settings reference</span></span>](config-setting-ref.md) 