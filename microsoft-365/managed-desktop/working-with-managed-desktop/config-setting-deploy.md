---
title: Развертывание настраиваемых параметров на настольном компьютере, управляемом Майкрософт
description: Развертывание и отслеживание настраиваемых изменений параметров на настольном компьютере, управляемом Майкрософт.
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация, развертывание, поэтапное развертывание, настраиваемые параметры
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5b6a2756514e94cb4f96141d6e7c9f6f2a6dd7ff
ms.sourcegitcommit: a4657a499967751d4c2dfc6cd1904258ab8be193
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "37040815"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="fd438-104">Развертывание и отслеживание настраиваемых параметров — Рабочий стол, управляемый корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fd438-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="fd438-105">После внесения изменений в категории параметров и поэтапного развертывания на странице состояния развертывания можно приступить к развертыванию параметров в группах.</span><span class="sxs-lookup"><span data-stu-id="fd438-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="fd438-106">На этой странице приведены сводные сведения о настраиваемых параметрах.</span><span class="sxs-lookup"><span data-stu-id="fd438-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="fd438-107">Открыв категорию параметров, вы можете развернуть параметры для групп и отслеживать ход выполнения этих развертываний.</span><span class="sxs-lookup"><span data-stu-id="fd438-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="fd438-108">Состояния развертывания</span><span class="sxs-lookup"><span data-stu-id="fd438-108">Deployment statuses</span></span> 

<span data-ttu-id="fd438-109">Ниже приведены состояния, которые будут отображаться для каждого развертывания.</span><span class="sxs-lookup"><span data-stu-id="fd438-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="fd438-110">Status</span><span class="sxs-lookup"><span data-stu-id="fd438-110">Status</span></span>  | <span data-ttu-id="fd438-111">Объяснение</span><span class="sxs-lookup"><span data-stu-id="fd438-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="fd438-112">Развертывание</span><span class="sxs-lookup"><span data-stu-id="fd438-112">Deploy</span></span> | <span data-ttu-id="fd438-113">Ваше изменение ожидает развертывания в этой группе.</span><span class="sxs-lookup"><span data-stu-id="fd438-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="fd438-114">Выполняется</span><span class="sxs-lookup"><span data-stu-id="fd438-114">In progress</span></span> | <span data-ttu-id="fd438-115">Изменение применяется к активным устройствам в этой группе.</span><span class="sxs-lookup"><span data-stu-id="fd438-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="fd438-116">Завершение</span><span class="sxs-lookup"><span data-stu-id="fd438-116">Complete</span></span> | <span data-ttu-id="fd438-117">Изменение завершено для всех активных устройств в этой группе.</span><span class="sxs-lookup"><span data-stu-id="fd438-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="fd438-118">Failed</span><span class="sxs-lookup"><span data-stu-id="fd438-118">Failed</span></span> | <span data-ttu-id="fd438-119">Изменение не удалось выполнить на 10 процентов активных устройств в группе, поэтому развертывание было остановлено.</span><span class="sxs-lookup"><span data-stu-id="fd438-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="fd438-120">Запрос в службу поддержки будет автоматически открыт с помощью управляемых операций на рабочем столе Майкрософт для устранения неполадок в развертывании.</span><span class="sxs-lookup"><span data-stu-id="fd438-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="fd438-121">Возвращаются</span><span class="sxs-lookup"><span data-stu-id="fd438-121">Reverted</span></span> | <span data-ttu-id="fd438-122">Изменено Последнее изменение, которое было успешно развернуто во всех группах развертывания.</span><span class="sxs-lookup"><span data-stu-id="fd438-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="fd438-123">Развертывание изменений</span><span class="sxs-lookup"><span data-stu-id="fd438-123">Deploy changes</span></span>

<span data-ttu-id="fd438-124">В этих инструкциях мы будем показывать фоновый рисунок рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="fd438-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="fd438-125">После поэтапного развертывания вы развертываете изменения на странице состояния развертывания.</span><span class="sxs-lookup"><span data-stu-id="fd438-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="fd438-126">**Развертывание изменений**</span><span class="sxs-lookup"><span data-stu-id="fd438-126">**To deploy changes**</span></span>

1. <span data-ttu-id="fd438-127">Вход на [портал администрирования рабочих столов с управляемыми Майкрософт](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="fd438-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="fd438-128">В разделе **Параметры**выберите пункт **Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="fd438-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="fd438-129">В рабочей области **состояния развертывания** выберите параметр, который необходимо развернуть, а затем выберите поэтапное развертывание для развертывания.</span><span class="sxs-lookup"><span data-stu-id="fd438-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="fd438-130">Нажмите кнопку **развернуть** , чтобы развернуть изменения в одной из групп развертывания.</span><span class="sxs-lookup"><span data-stu-id="fd438-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

<span data-ttu-id="fd438-131">![Обзор настраиваемых параметров. Обзор](images/1deployedit.png) состояния развертывания управляемого рабочего стола Майкрософт рекомендация развертывания в группах развертывания в следующем порядке: тестирование, первый, быстрый, а затем общий.</span><span class="sxs-lookup"><span data-stu-id="fd438-131">![Configurable settings deployment status overview](images/1deployedit.png) Microsoft Managed Desktop recommends deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="fd438-132">По завершении изменений в каждой группе состояние изменится на " **завершено**".</span><span class="sxs-lookup"><span data-stu-id="fd438-132">When changes complete in each group, the status changes to **Complete**.</span></span>

![Развертывание настраиваемых параметров завершено](images/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="fd438-134">Отмена развертывания</span><span class="sxs-lookup"><span data-stu-id="fd438-134">Revert deployment</span></span>

<span data-ttu-id="fd438-135">После развертывания изменения можно вернуться к **состоянию развертывания**.</span><span class="sxs-lookup"><span data-stu-id="fd438-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="fd438-136">При возвращении изменения, которое выполняется **или** завершено, текущее развертывание перестает быть **завершенным**.</span><span class="sxs-lookup"><span data-stu-id="fd438-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="fd438-137">Этот параметр вернется к последней версии, которая была развернута для всех групп.</span><span class="sxs-lookup"><span data-stu-id="fd438-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="fd438-138">Мы покажем, как вернуть изменения, используя фоновый рисунок рабочего стола в качестве примера.</span><span class="sxs-lookup"><span data-stu-id="fd438-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="fd438-139">**Отмена изменения**</span><span class="sxs-lookup"><span data-stu-id="fd438-139">**To revert a change**</span></span>
1. <span data-ttu-id="fd438-140">Вход на [портал администрирования рабочих столов с управляемыми Майкрософт](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="fd438-140">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="fd438-141">В разделе **Параметры**выберите пункт **Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="fd438-141">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="fd438-142">В рабочей области **состояния развертывания** выберите параметр, который требуется восстановить, а затем выберите поэтапное развертывание для отмены.</span><span class="sxs-lookup"><span data-stu-id="fd438-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="fd438-143">В разделе **необходимо отменить это изменение**выберите **вернуть развертывание**.</span><span class="sxs-lookup"><span data-stu-id="fd438-143">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![Возврат настраиваемых параметров развертывания](images/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="fd438-145">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="fd438-145">Additional resources</span></span>
- [<span data-ttu-id="fd438-146">Общие сведения о настраиваемых параметрах</span><span class="sxs-lookup"><span data-stu-id="fd438-146">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="fd438-147">Справочные сведения о настраиваемых параметрах</span><span class="sxs-lookup"><span data-stu-id="fd438-147">Configurable settings reference</span></span>](config-setting-ref.md) 
