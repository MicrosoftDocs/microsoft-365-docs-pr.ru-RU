---
title: Развертывание настраиваемых параметров на наСтольном компьютере, управляемом Майкрософт
description: Развертывание и отслеживание настраиваемых изменений параметров на наСтольном компьютере, управляемом Майкрософт.
keywords: НаСтольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация, развертывание, поэтапное развертывание, настраиваемые параметры
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4662373b926d07558ecedd05c9dfcf472ceb6357
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278438"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="e33c3-104">Развертывание и отслеживание настраиваемых параметров — Рабочий стол, управляемый корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e33c3-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="e33c3-105">После внесения изменений в категории параметров и поэтапного развертывания на странице состояния развертывания можно приступить к развертыванию параметров в группах.</span><span class="sxs-lookup"><span data-stu-id="e33c3-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="e33c3-106">На этой странице приведены сводные сведения о настраиваемых параметрах.</span><span class="sxs-lookup"><span data-stu-id="e33c3-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="e33c3-107">Открыв категорию параметров, вы можете развернуть параметры для групп и отслеживать ход выполнения этих развертываний.</span><span class="sxs-lookup"><span data-stu-id="e33c3-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="e33c3-108">Состояния развертывания</span><span class="sxs-lookup"><span data-stu-id="e33c3-108">Deployment statuses</span></span> 

<span data-ttu-id="e33c3-109">Это статуес, которые будут отображаться для каждого развертывания.</span><span class="sxs-lookup"><span data-stu-id="e33c3-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="e33c3-110">Состояние</span><span class="sxs-lookup"><span data-stu-id="e33c3-110">Status</span></span>  | <span data-ttu-id="e33c3-111">Объяснение</span><span class="sxs-lookup"><span data-stu-id="e33c3-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="e33c3-112">Развертывание</span><span class="sxs-lookup"><span data-stu-id="e33c3-112">Deploy</span></span> | <span data-ttu-id="e33c3-113">Ваше изменение ожидает развертывания в этой группе.</span><span class="sxs-lookup"><span data-stu-id="e33c3-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="e33c3-114">Выполняется</span><span class="sxs-lookup"><span data-stu-id="e33c3-114">In progress</span></span> | <span data-ttu-id="e33c3-115">Изменение применяется к активным устройствам в этой группе.</span><span class="sxs-lookup"><span data-stu-id="e33c3-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="e33c3-116">Завершение</span><span class="sxs-lookup"><span data-stu-id="e33c3-116">Complete</span></span> | <span data-ttu-id="e33c3-117">Изменение завершено для всех активных устройств в этой группе.</span><span class="sxs-lookup"><span data-stu-id="e33c3-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="e33c3-118">Failed</span><span class="sxs-lookup"><span data-stu-id="e33c3-118">Failed</span></span> | <span data-ttu-id="e33c3-119">Изменение не удалось выполнить на 10 процентов активных устройств в группе, поэтому развертывание было остановлено.</span><span class="sxs-lookup"><span data-stu-id="e33c3-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="e33c3-120">Запрос В службу поддержки будет автоматически открыт с помощью управляемых операций на рабочем столе Майкрософт для устранения неполадок в развертывании.</span><span class="sxs-lookup"><span data-stu-id="e33c3-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="e33c3-121">Возвращаются</span><span class="sxs-lookup"><span data-stu-id="e33c3-121">Reverted</span></span> | <span data-ttu-id="e33c3-122">Изменено Последнее изменение, которое было успешно развернуто во всех группах развертывания.</span><span class="sxs-lookup"><span data-stu-id="e33c3-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="e33c3-123">Развертывание изменений</span><span class="sxs-lookup"><span data-stu-id="e33c3-123">Deploy changes</span></span>

<span data-ttu-id="e33c3-124">В этих инструкциях мы будем показывать фоновый рисунок рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="e33c3-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="e33c3-125">После поэтапного развертывания вы развертываете изменения на странице состояния развертывания.</span><span class="sxs-lookup"><span data-stu-id="e33c3-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="e33c3-126">**Развертывание изменений**</span><span class="sxs-lookup"><span data-stu-id="e33c3-126">**To deploy changes**</span></span>

1. <span data-ttu-id="e33c3-127">Вход на [портал администрирования рабочих столов с управляемЫми Майкрософт](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="e33c3-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="e33c3-128">В разделе **Параметры**выберите пункт **Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="e33c3-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="e33c3-129">В рабочей области **состояния развертывания** выберите параметр, который необходимо развернуть, а затем выберите поэтапное развертывание для развертывания.</span><span class="sxs-lookup"><span data-stu-id="e33c3-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="e33c3-130">Нажмите кнопку **развернуть** , чтобы развернуть изменения в одной из групп развертывания.</span><span class="sxs-lookup"><span data-stu-id="e33c3-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

![Общие сведения о состоянии развертывания настраиваемых параметров](images/deploy-cs-overview.png)

<span data-ttu-id="e33c3-132">Настольный компьютер, управляемый Майкрософт, рекомендует развертывать группы развертывания в следующем порядке: тестирование, первый, быстрый, а затем общий.</span><span class="sxs-lookup"><span data-stu-id="e33c3-132">Microsoft Managed Desktop recommends deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="e33c3-133">По завершении изменений в каждой группе состояние изменится на \*\*\*\*"завершено".</span><span class="sxs-lookup"><span data-stu-id="e33c3-133">When changes complete in each group, the status changes to **Complete**.</span></span>

![Развертывание настраиваемых параметров завершено](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="e33c3-135">Отмена развертывания</span><span class="sxs-lookup"><span data-stu-id="e33c3-135">Revert deployment</span></span>

<span data-ttu-id="e33c3-136">После развертывания изменения можно вернуться к **состоянию развертывания**.</span><span class="sxs-lookup"><span data-stu-id="e33c3-136">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="e33c3-137">При возвращении изменения, которое выполняется \*\*\*\* или завершено, текущее развертывание перестает быть **завершенным**.</span><span class="sxs-lookup"><span data-stu-id="e33c3-137">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="e33c3-138">Этот параметр вернется к последней версии, которая была развернута для всех групп.</span><span class="sxs-lookup"><span data-stu-id="e33c3-138">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="e33c3-139">Мы покажем, как вернуть изменения, используя фоновый рисунок рабочего стола в качестве примера.</span><span class="sxs-lookup"><span data-stu-id="e33c3-139">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="e33c3-140">**Отмена изменения**</span><span class="sxs-lookup"><span data-stu-id="e33c3-140">**To revert a change**</span></span>
1. <span data-ttu-id="e33c3-141">Вход на [портал администрирования рабочих столов с управляемЫми Майкрософт](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="e33c3-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="e33c3-142">В разделе **Параметры**выберите пункт **Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="e33c3-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="e33c3-143">В рабочей области **состояния развертывания** выберите параметр, который требуется восстановить, а затем выберите поэтапное развертывание для отмены.</span><span class="sxs-lookup"><span data-stu-id="e33c3-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="e33c3-144">В разделе **необходимо отменить это изменение**выберите **вернуть развертывание**.</span><span class="sxs-lookup"><span data-stu-id="e33c3-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![Возврат настраиваемых параметров развертывания](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="e33c3-146">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="e33c3-146">Additional resources</span></span>
- [<span data-ttu-id="e33c3-147">Общие сведения о настраиваемых параметрах</span><span class="sxs-lookup"><span data-stu-id="e33c3-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="e33c3-148">Справочные сведения о настраиваемых параметрах</span><span class="sxs-lookup"><span data-stu-id="e33c3-148">Configurable settings reference</span></span>](config-setting-ref.md) 
