---
title: Развертывание настраиваемых параметров на настольном компьютере, управляемом Майкрософт
description: Развертывание и отслеживание настраиваемых изменений параметров на настольном компьютере, управляемом Майкрософт.
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация, развертывание, поэтапное развертывание, настраиваемые параметры
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7e3827dc12c04d2c7952f9321a70714691c5ed47
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012304"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="e5820-104">Развертывание и отслеживание настраиваемых параметров — Рабочий стол, управляемый корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e5820-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="e5820-105">После внесения изменений в категории параметров и поэтапного развертывания на странице состояния развертывания можно приступить к развертыванию параметров в группах.</span><span class="sxs-lookup"><span data-stu-id="e5820-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="e5820-106">На этой странице приведены сводные сведения о настраиваемых параметрах.</span><span class="sxs-lookup"><span data-stu-id="e5820-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="e5820-107">Открыв категорию параметров, вы можете развернуть параметры для групп и отслеживать ход выполнения этих развертываний.</span><span class="sxs-lookup"><span data-stu-id="e5820-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="e5820-108">Состояния развертывания</span><span class="sxs-lookup"><span data-stu-id="e5820-108">Deployment statuses</span></span> 

<span data-ttu-id="e5820-109">Ниже приведены состояния, которые будут отображаться для каждого развертывания.</span><span class="sxs-lookup"><span data-stu-id="e5820-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="e5820-110">Status</span><span class="sxs-lookup"><span data-stu-id="e5820-110">Status</span></span>  | <span data-ttu-id="e5820-111">Объяснение</span><span class="sxs-lookup"><span data-stu-id="e5820-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="e5820-112">Развертывание</span><span class="sxs-lookup"><span data-stu-id="e5820-112">Deploy</span></span> | <span data-ttu-id="e5820-113">Ваше изменение ожидает развертывания в этой группе.</span><span class="sxs-lookup"><span data-stu-id="e5820-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="e5820-114">Выполняется</span><span class="sxs-lookup"><span data-stu-id="e5820-114">In progress</span></span> | <span data-ttu-id="e5820-115">Изменение применяется к активным устройствам в этой группе.</span><span class="sxs-lookup"><span data-stu-id="e5820-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="e5820-116">Завершение</span><span class="sxs-lookup"><span data-stu-id="e5820-116">Complete</span></span> | <span data-ttu-id="e5820-117">Изменение завершено для всех активных устройств в этой группе.</span><span class="sxs-lookup"><span data-stu-id="e5820-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="e5820-118">Сбой</span><span class="sxs-lookup"><span data-stu-id="e5820-118">Failed</span></span> | <span data-ttu-id="e5820-119">Изменение не удалось выполнить на 10 процентов активных устройств в группе, поэтому развертывание было остановлено.</span><span class="sxs-lookup"><span data-stu-id="e5820-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="e5820-120">Запрос в службу поддержки будет автоматически открыт с помощью управляемых операций на рабочем столе Майкрософт для устранения неполадок в развертывании.</span><span class="sxs-lookup"><span data-stu-id="e5820-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="e5820-121">Возвращаются</span><span class="sxs-lookup"><span data-stu-id="e5820-121">Reverted</span></span> | <span data-ttu-id="e5820-122">Изменено Последнее изменение, которое было успешно развернуто во всех группах развертывания.</span><span class="sxs-lookup"><span data-stu-id="e5820-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="e5820-123">Развертывание изменений</span><span class="sxs-lookup"><span data-stu-id="e5820-123">Deploy changes</span></span>

<span data-ttu-id="e5820-124">В этих инструкциях мы будем показывать фоновый рисунок рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="e5820-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="e5820-125">После поэтапного развертывания вы развертываете изменения на странице состояния развертывания.</span><span class="sxs-lookup"><span data-stu-id="e5820-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="e5820-126">**Развертывание изменений**</span><span class="sxs-lookup"><span data-stu-id="e5820-126">**To deploy changes**</span></span>

1. <span data-ttu-id="e5820-127">Вход на [портал администрирования рабочих столов с управляемыми Майкрософт](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="e5820-127">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="e5820-128">В разделе **Параметры**выберите пункт **Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="e5820-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="e5820-129">В рабочей области **состояния развертывания** выберите параметр, который необходимо развернуть, а затем выберите поэтапное развертывание для развертывания.</span><span class="sxs-lookup"><span data-stu-id="e5820-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="e5820-130">Нажмите кнопку **развернуть** , чтобы развернуть изменения в одной из групп развертывания.</span><span class="sxs-lookup"><span data-stu-id="e5820-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

<span data-ttu-id="e5820-131">![Обзор настраиваемых параметров. Обзор](images/1deployedit.png) состояния развертывания управляемого рабочего стола Майкрософт рекомендация развертывания в группах развертывания в следующем порядке: тестирование, первый, быстрый, а затем общий.</span><span class="sxs-lookup"><span data-stu-id="e5820-131">![Configurable settings deployment status overview](images/1deployedit.png) Microsoft Managed Desktop recommends deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="e5820-132">По завершении изменений в каждой группе состояние изменится на " **завершено**".</span><span class="sxs-lookup"><span data-stu-id="e5820-132">When changes complete in each group, the status changes to **Complete**.</span></span>

![Развертывание настраиваемых параметров завершено](images/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="e5820-134">Отмена развертывания</span><span class="sxs-lookup"><span data-stu-id="e5820-134">Revert deployment</span></span>

<span data-ttu-id="e5820-135">После развертывания изменения можно вернуться к **состоянию развертывания**.</span><span class="sxs-lookup"><span data-stu-id="e5820-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="e5820-136">При возвращении изменения, которое выполняется **или** завершено, текущее развертывание перестает быть **завершенным**.</span><span class="sxs-lookup"><span data-stu-id="e5820-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="e5820-137">Этот параметр вернется к последней версии, которая была развернута для всех групп.</span><span class="sxs-lookup"><span data-stu-id="e5820-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="e5820-138">Мы покажем, как вернуть изменения, используя фоновый рисунок рабочего стола в качестве примера.</span><span class="sxs-lookup"><span data-stu-id="e5820-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="e5820-139">**Отмена изменения**</span><span class="sxs-lookup"><span data-stu-id="e5820-139">**To revert a change**</span></span>
1. <span data-ttu-id="e5820-140">Вход на [портал администрирования рабочих столов с управляемыми Майкрософт](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="e5820-140">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="e5820-141">В разделе **Параметры**выберите пункт **Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="e5820-141">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="e5820-142">В рабочей области **состояния развертывания** выберите параметр, который требуется восстановить, а затем выберите поэтапное развертывание для отмены.</span><span class="sxs-lookup"><span data-stu-id="e5820-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="e5820-143">В разделе **необходимо отменить это изменение**выберите **вернуть развертывание**.</span><span class="sxs-lookup"><span data-stu-id="e5820-143">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![Возврат настраиваемых параметров развертывания](images/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="e5820-145">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="e5820-145">Additional resources</span></span>
- [<span data-ttu-id="e5820-146">Общие сведения о настраиваемых параметрах</span><span class="sxs-lookup"><span data-stu-id="e5820-146">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="e5820-147">Справочник по настраиваемым параметрам</span><span class="sxs-lookup"><span data-stu-id="e5820-147">Configurable settings reference</span></span>](config-setting-ref.md) 
