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
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104538"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="37816-104">Развертывание и отслеживание настраиваемых параметров — Рабочий стол, управляемый корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="37816-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="37816-105">После внесения изменений в категории параметров и поэтапного развертывания на странице состояния развертывания можно приступить к развертыванию параметров в группах.</span><span class="sxs-lookup"><span data-stu-id="37816-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="37816-106">На этой странице приведены сводные сведения о настраиваемых параметрах.</span><span class="sxs-lookup"><span data-stu-id="37816-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="37816-107">Открыв категорию параметров, вы можете развернуть параметры для групп и отслеживать ход выполнения этих развертываний.</span><span class="sxs-lookup"><span data-stu-id="37816-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="37816-108">Состояния развертывания</span><span class="sxs-lookup"><span data-stu-id="37816-108">Deployment statuses</span></span> 

<span data-ttu-id="37816-109">Ниже приведены состояния, которые будут отображаться для каждого развертывания.</span><span class="sxs-lookup"><span data-stu-id="37816-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="37816-110">Статус</span><span class="sxs-lookup"><span data-stu-id="37816-110">Status</span></span>  | <span data-ttu-id="37816-111">Объяснение</span><span class="sxs-lookup"><span data-stu-id="37816-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="37816-112">Развертывание</span><span class="sxs-lookup"><span data-stu-id="37816-112">Deploy</span></span> | <span data-ttu-id="37816-113">Ваше изменение ожидает развертывания в этой группе.</span><span class="sxs-lookup"><span data-stu-id="37816-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="37816-114">Выполняется</span><span class="sxs-lookup"><span data-stu-id="37816-114">In progress</span></span> | <span data-ttu-id="37816-115">Изменение применяется к активным устройствам в этой группе.</span><span class="sxs-lookup"><span data-stu-id="37816-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="37816-116">Завершение</span><span class="sxs-lookup"><span data-stu-id="37816-116">Complete</span></span> | <span data-ttu-id="37816-117">Изменение завершено для всех активных устройств в этой группе.</span><span class="sxs-lookup"><span data-stu-id="37816-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="37816-118">Не выполнено</span><span class="sxs-lookup"><span data-stu-id="37816-118">Failed</span></span> | <span data-ttu-id="37816-119">Изменение не удалось выполнить на 10 процентов активных устройств в группе, поэтому развертывание было остановлено.</span><span class="sxs-lookup"><span data-stu-id="37816-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="37816-120">Запрос в службу поддержки будет автоматически открыт с помощью управляемых операций на рабочем столе Майкрософт для устранения неполадок в развертывании.</span><span class="sxs-lookup"><span data-stu-id="37816-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="37816-121">Возвращаются</span><span class="sxs-lookup"><span data-stu-id="37816-121">Reverted</span></span> | <span data-ttu-id="37816-122">Изменено Последнее изменение, которое было успешно развернуто во всех группах развертывания.</span><span class="sxs-lookup"><span data-stu-id="37816-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="37816-123">Развертывание изменений</span><span class="sxs-lookup"><span data-stu-id="37816-123">Deploy changes</span></span>

<span data-ttu-id="37816-124">В этих инструкциях мы будем показывать фоновый рисунок рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="37816-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="37816-125">После поэтапного развертывания вы развертываете изменения на странице состояния развертывания.</span><span class="sxs-lookup"><span data-stu-id="37816-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="37816-126">**Развертывание изменений**</span><span class="sxs-lookup"><span data-stu-id="37816-126">**To deploy changes**</span></span>

1. <span data-ttu-id="37816-127">Вход в [Диспетчер конечных точек Майкрософт](https://endpoint.microsoft.com/) и переход в меню " **устройства** "</span><span class="sxs-lookup"><span data-stu-id="37816-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="37816-128">Найдите раздел Рабочий стол, управляемый Майкрософт, выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="37816-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="37816-129">В рабочей области **состояния развертывания** выберите параметр, который необходимо развернуть, а затем выберите поэтапное развертывание для развертывания.</span><span class="sxs-lookup"><span data-stu-id="37816-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="37816-130">Нажмите кнопку **развернуть** , чтобы развернуть изменения в одной из групп развертывания.</span><span class="sxs-lookup"><span data-stu-id="37816-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="37816-131">Оранжевый значок предупреждения указывает, что существует доступ к предыдущей группе, так как ее рекомендуется развертывать по порядку.</span><span class="sxs-lookup"><span data-stu-id="37816-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="37816-132">Мы рекомендуем развертывать в группах развертывания в следующем порядке: Test, First, Fast, а затем широком.</span><span class="sxs-lookup"><span data-stu-id="37816-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="37816-133">По завершении изменений в каждой группе состояние изменится на " **завершено**".</span><span class="sxs-lookup"><span data-stu-id="37816-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="37816-134">Отмена развертывания</span><span class="sxs-lookup"><span data-stu-id="37816-134">Revert deployment</span></span>

<span data-ttu-id="37816-135">После развертывания изменения можно вернуться к **состоянию развертывания**.</span><span class="sxs-lookup"><span data-stu-id="37816-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="37816-136">При возвращении изменения, которое выполняется **или** завершено, текущее развертывание перестает быть **завершенным**.</span><span class="sxs-lookup"><span data-stu-id="37816-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="37816-137">Этот параметр вернется к последней версии, которая была развернута для всех групп.</span><span class="sxs-lookup"><span data-stu-id="37816-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="37816-138">Мы покажем, как вернуть изменения, используя фоновый рисунок рабочего стола в качестве примера.</span><span class="sxs-lookup"><span data-stu-id="37816-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="37816-139">**Отмена изменения**</span><span class="sxs-lookup"><span data-stu-id="37816-139">**To revert a change**</span></span>
1. <span data-ttu-id="37816-140">Вход в [Диспетчер конечных точек Майкрософт](https://endpoint.microsoft.com/) и переход в меню " **устройства** "</span><span class="sxs-lookup"><span data-stu-id="37816-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="37816-141">Найдите раздел Рабочий стол, управляемый Майкрософт, выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="37816-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="37816-142">В рабочей области **состояния развертывания** выберите параметр, который требуется восстановить, а затем выберите поэтапное развертывание для отмены.</span><span class="sxs-lookup"><span data-stu-id="37816-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="37816-143">В разделе **требуется отменить это изменение**нажмите кнопку **вернуть развертывание**.</span><span class="sxs-lookup"><span data-stu-id="37816-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="37816-144">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="37816-144">Additional resources</span></span>
- [<span data-ttu-id="37816-145">Общие сведения о настраиваемых параметрах</span><span class="sxs-lookup"><span data-stu-id="37816-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="37816-146">Справочник по настраиваемым параметрам</span><span class="sxs-lookup"><span data-stu-id="37816-146">Configurable settings reference</span></span>](config-setting-ref.md) 
