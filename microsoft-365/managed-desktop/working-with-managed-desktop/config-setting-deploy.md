---
title: Развертывание настраиваемых параметров на компьютере, управляемом Майкрософт
description: Развертывание и отслеживание настраиваемых изменений параметров в компьютере, управляемом Майкрософт.
keywords: Компьютер под управлением Майкрософт, Microsoft 365, служба, документация, развертывание, поэтапное развертывание, настраиваемые параметры
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
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="59172-104">Развертывание и отслеживание настраиваемых параметров — компьютеры, управляемые Майкрософт</span><span class="sxs-lookup"><span data-stu-id="59172-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="59172-105">После внесения изменений в категории параметров и стадии развертывания страница состояния развертывания позволяет начать развертывание параметров в группах.</span><span class="sxs-lookup"><span data-stu-id="59172-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="59172-106">На этой странице показана сводка по каждому настраиваемому параметру.</span><span class="sxs-lookup"><span data-stu-id="59172-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="59172-107">Открыв категорию параметров, можно развернуть параметры в группах и отслеживать ход развертывания.</span><span class="sxs-lookup"><span data-stu-id="59172-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="59172-108">Состояния развертывания</span><span class="sxs-lookup"><span data-stu-id="59172-108">Deployment statuses</span></span> 

<span data-ttu-id="59172-109">Это состояния, которые вы увидите для каждого развертывания.</span><span class="sxs-lookup"><span data-stu-id="59172-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="59172-110">Status</span><span class="sxs-lookup"><span data-stu-id="59172-110">Status</span></span>  | <span data-ttu-id="59172-111">Объяснение</span><span class="sxs-lookup"><span data-stu-id="59172-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="59172-112">Развертывание</span><span class="sxs-lookup"><span data-stu-id="59172-112">Deploy</span></span> | <span data-ttu-id="59172-113">Изменения ожидают развертывания в этой группе.</span><span class="sxs-lookup"><span data-stu-id="59172-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="59172-114">В процессе выполнения</span><span class="sxs-lookup"><span data-stu-id="59172-114">In progress</span></span> | <span data-ttu-id="59172-115">Изменение применяется к активным устройствам в этой группе.</span><span class="sxs-lookup"><span data-stu-id="59172-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="59172-116">Завершение</span><span class="sxs-lookup"><span data-stu-id="59172-116">Complete</span></span> | <span data-ttu-id="59172-117">Изменение выполнено на всех активных устройствах в этой группе.</span><span class="sxs-lookup"><span data-stu-id="59172-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="59172-118">Не выполнено</span><span class="sxs-lookup"><span data-stu-id="59172-118">Failed</span></span> | <span data-ttu-id="59172-119">Сбой изменения на 10 % активных устройств в группе, поэтому развертывание было остановлено.</span><span class="sxs-lookup"><span data-stu-id="59172-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="59172-120">Запрос в службу поддержки будет автоматически открыт с помощью операций microsoft Managed Desktop для устранения неполадок развертывания.</span><span class="sxs-lookup"><span data-stu-id="59172-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="59172-121">Reverted</span><span class="sxs-lookup"><span data-stu-id="59172-121">Reverted</span></span> | <span data-ttu-id="59172-122">Изменение было отменено до последнего изменения, которое было успешно развернуто во всех группах развертывания.</span><span class="sxs-lookup"><span data-stu-id="59172-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="59172-123">Развертывание изменений</span><span class="sxs-lookup"><span data-stu-id="59172-123">Deploy changes</span></span>

<span data-ttu-id="59172-124">В этих инструкциях мы откажемся от фонового рисунка рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="59172-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="59172-125">После поэтапного развертывания изменения развертываются со страницы состояния развертывания.</span><span class="sxs-lookup"><span data-stu-id="59172-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="59172-126">**Развертывание изменений**</span><span class="sxs-lookup"><span data-stu-id="59172-126">**To deploy changes**</span></span>

1. <span data-ttu-id="59172-127">Войдите в [Microsoft Endpoint Manager и](https://endpoint.microsoft.com/) перейдите в меню **"Устройства"**</span><span class="sxs-lookup"><span data-stu-id="59172-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="59172-128">Наберем раздел "Рабочий стол, управляемый Майкрософт", выберите **"Параметры".**</span><span class="sxs-lookup"><span data-stu-id="59172-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="59172-129">В **рабочей области** состояния развертывания выберите параметр, который требуется развернуть, а затем выберите поэтапное развертывание для развертывания.</span><span class="sxs-lookup"><span data-stu-id="59172-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="59172-130">Выберите  "Развернуть", чтобы развернуть изменение в одной из групп развертывания.</span><span class="sxs-lookup"><span data-stu-id="59172-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="59172-131">Оранжевый значок предупреждения указывает, что для развертывания доступна предыдущая группа, так как ее рекомендуется развертывать по порядку.</span><span class="sxs-lookup"><span data-stu-id="59172-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="59172-132">Рекомендуется развертывать развертывание в группах развертывания в таком порядке: Test, First, Fast, and then Broad.</span><span class="sxs-lookup"><span data-stu-id="59172-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="59172-133">После завершения изменений в каждой группе состояние меняется на **"Завершено".**</span><span class="sxs-lookup"><span data-stu-id="59172-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="59172-134">Отовращать развертывание</span><span class="sxs-lookup"><span data-stu-id="59172-134">Revert deployment</span></span>

<span data-ttu-id="59172-135">После развертывания изменения можно вернуться к статусу **развертывания.**</span><span class="sxs-lookup"><span data-stu-id="59172-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="59172-136">При отращении изменения, которое находится **в** процессе выполнения или **завершения,** текущее развертывание останавливается.</span><span class="sxs-lookup"><span data-stu-id="59172-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="59172-137">Этот параметр вернется к последней версии, развернутой для всех групп.</span><span class="sxs-lookup"><span data-stu-id="59172-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="59172-138">В качестве примера мы покажем, как отменить изменение с помощью фонового рисунка рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="59172-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="59172-139">**Как отменить изменение**</span><span class="sxs-lookup"><span data-stu-id="59172-139">**To revert a change**</span></span>
1. <span data-ttu-id="59172-140">Войдите в [Microsoft Endpoint Manager и](https://endpoint.microsoft.com/) перейдите в меню **"Устройства"**</span><span class="sxs-lookup"><span data-stu-id="59172-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="59172-141">Наберем раздел "Рабочий стол, управляемый Майкрософт", выберите **"Параметры".**</span><span class="sxs-lookup"><span data-stu-id="59172-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="59172-142">В **рабочей области состояния** развертывания выберите параметр, который требуется отовращать, а затем выберите поэтапное развертывание, для чего требуется вернуться.</span><span class="sxs-lookup"><span data-stu-id="59172-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="59172-143">Under **Need to revert this change?**, select **Revert deployment**.</span><span class="sxs-lookup"><span data-stu-id="59172-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="59172-144">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="59172-144">Additional resources</span></span>
- [<span data-ttu-id="59172-145">Обзор настраиваемых параметров</span><span class="sxs-lookup"><span data-stu-id="59172-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="59172-146">Справочник по настраиваемым параметрам</span><span class="sxs-lookup"><span data-stu-id="59172-146">Configurable settings reference</span></span>](config-setting-ref.md) 
