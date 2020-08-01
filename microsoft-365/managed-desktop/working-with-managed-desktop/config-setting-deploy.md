---
title: Развертывание настраиваемых параметров на настольном компьютере, управляемом Майкрософт
description: Развертывание и отслеживание настраиваемых изменений параметров на настольном компьютере, управляемом Майкрософт.
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация, развертывание, поэтапное развертывание, настраиваемые параметры
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b731422e6d981b12ea576ed26b841e7c679266ae
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530263"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="b699e-104">Развертывание и отслеживание настраиваемых параметров — Рабочий стол, управляемый корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b699e-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="b699e-105">После внесения изменений в категории параметров и поэтапного развертывания на странице состояния развертывания можно приступить к развертыванию параметров в группах.</span><span class="sxs-lookup"><span data-stu-id="b699e-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="b699e-106">На этой странице приведены сводные сведения о настраиваемых параметрах.</span><span class="sxs-lookup"><span data-stu-id="b699e-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="b699e-107">Открыв категорию параметров, вы можете развернуть параметры для групп и отслеживать ход выполнения этих развертываний.</span><span class="sxs-lookup"><span data-stu-id="b699e-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="b699e-108">Состояния развертывания</span><span class="sxs-lookup"><span data-stu-id="b699e-108">Deployment statuses</span></span> 

<span data-ttu-id="b699e-109">Ниже приведены состояния, которые будут отображаться для каждого развертывания.</span><span class="sxs-lookup"><span data-stu-id="b699e-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="b699e-110">Status</span><span class="sxs-lookup"><span data-stu-id="b699e-110">Status</span></span>  | <span data-ttu-id="b699e-111">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b699e-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="b699e-112">Развертывание</span><span class="sxs-lookup"><span data-stu-id="b699e-112">Deploy</span></span> | <span data-ttu-id="b699e-113">Ваше изменение ожидает развертывания в этой группе.</span><span class="sxs-lookup"><span data-stu-id="b699e-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="b699e-114">Выполняется</span><span class="sxs-lookup"><span data-stu-id="b699e-114">In progress</span></span> | <span data-ttu-id="b699e-115">Изменение применяется к активным устройствам в этой группе.</span><span class="sxs-lookup"><span data-stu-id="b699e-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="b699e-116">Завершение</span><span class="sxs-lookup"><span data-stu-id="b699e-116">Complete</span></span> | <span data-ttu-id="b699e-117">Изменение завершено для всех активных устройств в этой группе.</span><span class="sxs-lookup"><span data-stu-id="b699e-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="b699e-118">Не выполнено</span><span class="sxs-lookup"><span data-stu-id="b699e-118">Failed</span></span> | <span data-ttu-id="b699e-119">Изменение не удалось выполнить на 10 процентов активных устройств в группе, поэтому развертывание было остановлено.</span><span class="sxs-lookup"><span data-stu-id="b699e-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="b699e-120">Запрос в службу поддержки будет автоматически открыт с помощью управляемых операций на рабочем столе Майкрософт для устранения неполадок в развертывании.</span><span class="sxs-lookup"><span data-stu-id="b699e-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="b699e-121">Возвращаются</span><span class="sxs-lookup"><span data-stu-id="b699e-121">Reverted</span></span> | <span data-ttu-id="b699e-122">Изменено Последнее изменение, которое было успешно развернуто во всех группах развертывания.</span><span class="sxs-lookup"><span data-stu-id="b699e-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="b699e-123">Развертывание изменений</span><span class="sxs-lookup"><span data-stu-id="b699e-123">Deploy changes</span></span>

<span data-ttu-id="b699e-124">В этих инструкциях мы будем показывать фоновый рисунок рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="b699e-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="b699e-125">После поэтапного развертывания вы развертываете изменения на странице состояния развертывания.</span><span class="sxs-lookup"><span data-stu-id="b699e-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="b699e-126">**Развертывание изменений**</span><span class="sxs-lookup"><span data-stu-id="b699e-126">**To deploy changes**</span></span>

1. <span data-ttu-id="b699e-127">Вход на [портал администрирования рабочих столов с управляемыми Майкрософт](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="b699e-127">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="b699e-128">В разделе **Параметры**выберите пункт **Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="b699e-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="b699e-129">В рабочей области **состояния развертывания** выберите параметр, который необходимо развернуть, а затем выберите поэтапное развертывание для развертывания.</span><span class="sxs-lookup"><span data-stu-id="b699e-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="b699e-130">Нажмите кнопку **развернуть** , чтобы развернуть изменения в одной из групп развертывания.</span><span class="sxs-lookup"><span data-stu-id="b699e-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="b699e-131">Оранжевый значок предупреждения указывает, что существует доступ к предыдущей группе, так как ее рекомендуется развертывать по порядку.</span><span class="sxs-lookup"><span data-stu-id="b699e-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<span data-ttu-id="b699e-132">![Рабочая область состояния развертывания.</span><span class="sxs-lookup"><span data-stu-id="b699e-132">![Deployment status workspace.</span></span> <span data-ttu-id="b699e-133">Область надежных сайтов справа.</span><span class="sxs-lookup"><span data-stu-id="b699e-133">Trusted sites pane on the right.</span></span> <span data-ttu-id="b699e-134">В разделе группы развертывания три столбца: группы развертывания, устройства и состояние.</span><span class="sxs-lookup"><span data-stu-id="b699e-134">In the Deployment groups section are three columns: deployment groups, devices, and status.</span></span> <span data-ttu-id="b699e-135">В столбце Состояние выделено значение "развернуть".](../../media/1deployedit.png)</span><span class="sxs-lookup"><span data-stu-id="b699e-135">In the status column, "deploy" is highlighted.](../../media/1deployedit.png)</span></span>
<span data-ttu-id="b699e-136">Мы рекомендуем развертывать в группах развертывания в следующем порядке: Test, First, Fast, а затем широком.</span><span class="sxs-lookup"><span data-stu-id="b699e-136">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="b699e-137">По завершении изменений в каждой группе состояние изменится на " **завершено**".</span><span class="sxs-lookup"><span data-stu-id="b699e-137">When changes complete in each group, the status changes to **Complete**.</span></span>

![Рабочая область состояния развертывания со столбцами даты обновления, версии, проверки, первой, быстрой и широкой.](../../media/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="b699e-140">Отмена развертывания</span><span class="sxs-lookup"><span data-stu-id="b699e-140">Revert deployment</span></span>

<span data-ttu-id="b699e-141">После развертывания изменения можно вернуться к **состоянию развертывания**.</span><span class="sxs-lookup"><span data-stu-id="b699e-141">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="b699e-142">При возвращении изменения, которое выполняется **или** завершено, текущее развертывание перестает быть **завершенным**.</span><span class="sxs-lookup"><span data-stu-id="b699e-142">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="b699e-143">Этот параметр вернется к последней версии, которая была развернута для всех групп.</span><span class="sxs-lookup"><span data-stu-id="b699e-143">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="b699e-144">Мы покажем, как вернуть изменения, используя фоновый рисунок рабочего стола в качестве примера.</span><span class="sxs-lookup"><span data-stu-id="b699e-144">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="b699e-145">**Отмена изменения**</span><span class="sxs-lookup"><span data-stu-id="b699e-145">**To revert a change**</span></span>
1. <span data-ttu-id="b699e-146">Вход на [портал администрирования рабочих столов с управляемыми Майкрософт](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="b699e-146">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="b699e-147">В разделе **Параметры**выберите пункт **Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="b699e-147">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="b699e-148">В рабочей области **состояния развертывания** выберите параметр, который требуется восстановить, а затем выберите поэтапное развертывание для отмены.</span><span class="sxs-lookup"><span data-stu-id="b699e-148">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="b699e-149">В разделе **требуется отменить это изменение**нажмите кнопку **вернуть развертывание**.</span><span class="sxs-lookup"><span data-stu-id="b699e-149">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

![Рабочая область состояния развертывания.](../../media/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="b699e-153">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="b699e-153">Additional resources</span></span>
- [<span data-ttu-id="b699e-154">Общие сведения о настраиваемых параметрах</span><span class="sxs-lookup"><span data-stu-id="b699e-154">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="b699e-155">Справочник по настраиваемым параметрам</span><span class="sxs-lookup"><span data-stu-id="b699e-155">Configurable settings reference</span></span>](config-setting-ref.md) 
