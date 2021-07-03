---
title: Развертывание настраиваемых параметров в компьютеры, управляемые Майкрософт
description: Развертывание и отслеживание настраиваемых параметров в компьютеры, управляемые Майкрософт.
keywords: компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация, развертывание, поэтапное развертывание, настраиваемые параметры
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: aad4995f9c329b0fd8fcbcc8b1d13379453c2a76
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287805"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="34d9f-104">Развертывание и отслеживание настраиваемых параметров — компьютеры, управляемые Майкрософт</span><span class="sxs-lookup"><span data-stu-id="34d9f-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="34d9f-105">После внесения изменений в категории параметров и этапа развертывания страница состояния развертывания позволяет приступить к развертыванию параметров в группах.</span><span class="sxs-lookup"><span data-stu-id="34d9f-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="34d9f-106">На этой странице показан сводка каждого настраиваемого параметра.</span><span class="sxs-lookup"><span data-stu-id="34d9f-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="34d9f-107">Открыв категорию параметров, можно развернуть параметры для групп и отслеживать ход этих развертывание.</span><span class="sxs-lookup"><span data-stu-id="34d9f-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="34d9f-108">Состояния развертывания</span><span class="sxs-lookup"><span data-stu-id="34d9f-108">Deployment statuses</span></span>

<span data-ttu-id="34d9f-109">Это состояния, которые вы увидите для каждого развертывания.</span><span class="sxs-lookup"><span data-stu-id="34d9f-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="34d9f-110">Status</span><span class="sxs-lookup"><span data-stu-id="34d9f-110">Status</span></span> | <span data-ttu-id="34d9f-111">Объяснение</span><span class="sxs-lookup"><span data-stu-id="34d9f-111">Explanation</span></span>
--- | ---
<span data-ttu-id="34d9f-112">Развертывание</span><span class="sxs-lookup"><span data-stu-id="34d9f-112">Deploy</span></span> | <span data-ttu-id="34d9f-113">Изменения ожидают развертывания в этой группе.</span><span class="sxs-lookup"><span data-stu-id="34d9f-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="34d9f-114">В процессе выполнения</span><span class="sxs-lookup"><span data-stu-id="34d9f-114">In progress</span></span> | <span data-ttu-id="34d9f-115">Это изменение применяется к активным устройствам в этой группе.</span><span class="sxs-lookup"><span data-stu-id="34d9f-115">The change is being applied to active devices in this group.</span></span>
<span data-ttu-id="34d9f-116">Полностью</span><span class="sxs-lookup"><span data-stu-id="34d9f-116">Complete</span></span> | <span data-ttu-id="34d9f-117">Изменение выполнено на всех активных устройствах в этой группе.</span><span class="sxs-lookup"><span data-stu-id="34d9f-117">The change completed on all active devices in this group.</span></span>
<span data-ttu-id="34d9f-118">Не выполнено</span><span class="sxs-lookup"><span data-stu-id="34d9f-118">Failed</span></span> | <span data-ttu-id="34d9f-119">Изменение не удалось на 10% активных устройств в группе, поэтому развертывание было остановлено.</span><span class="sxs-lookup"><span data-stu-id="34d9f-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="34d9f-120">Запрос на поддержку будет автоматически открыт с помощью компьютеры, управляемые Майкрософт для устранения неполадок развертывания.</span><span class="sxs-lookup"><span data-stu-id="34d9f-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span>
<span data-ttu-id="34d9f-121">Reverted</span><span class="sxs-lookup"><span data-stu-id="34d9f-121">Reverted</span></span> | <span data-ttu-id="34d9f-122">Изменение было отменено до последнего изменения, успешно развернутого во всех группах развертывания.</span><span class="sxs-lookup"><span data-stu-id="34d9f-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="34d9f-123">Развертывание изменений</span><span class="sxs-lookup"><span data-stu-id="34d9f-123">Deploy changes</span></span>

<span data-ttu-id="34d9f-124">В этих инструкциях мы покажем фоновое изображение рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="34d9f-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="34d9f-125">После развертывания необходимо развернуть изменения со страницы состояния развертывания.</span><span class="sxs-lookup"><span data-stu-id="34d9f-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span>

<span data-ttu-id="34d9f-126">**Развертывание изменений**</span><span class="sxs-lookup"><span data-stu-id="34d9f-126">**To deploy changes**</span></span>

1. <span data-ttu-id="34d9f-127">Войдите в [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) и перейдите в меню **Devices**</span><span class="sxs-lookup"><span data-stu-id="34d9f-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="34d9f-128">Посмотрите раздел компьютеры, управляемые Майкрософт, выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="34d9f-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="34d9f-129">В **рабочей области состояния** развертывания выберите параметр, который необходимо развернуть, а затем выберите поэтапное развертывание для развертывания.</span><span class="sxs-lookup"><span data-stu-id="34d9f-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="34d9f-130">Выберите **Развертывание,** чтобы развернуть изменение в одной из групп развертывания.</span><span class="sxs-lookup"><span data-stu-id="34d9f-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE]
> <span data-ttu-id="34d9f-131">Оранжевый значок предостережения указывает на то, что для развертывания доступна предыдущая группа, которая рекомендуется развертывать в порядке.</span><span class="sxs-lookup"><span data-stu-id="34d9f-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="34d9f-132">Рекомендуется развертывать группы развертывания в этом порядке: Test, First, Fast и Broad.</span><span class="sxs-lookup"><span data-stu-id="34d9f-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="34d9f-133">Когда изменения завершались в каждой группе, состояние изменяется в **Complete**.</span><span class="sxs-lookup"><span data-stu-id="34d9f-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="34d9f-134">Повторное развертывание</span><span class="sxs-lookup"><span data-stu-id="34d9f-134">Revert deployment</span></span>

<span data-ttu-id="34d9f-135">После развертывания изменения можно вернуться из состояния **Развертывания.**</span><span class="sxs-lookup"><span data-stu-id="34d9f-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="34d9f-136">При повторном изменении, которое находится в **процессе или** **завершении,** текущее развертывание прекращается.</span><span class="sxs-lookup"><span data-stu-id="34d9f-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="34d9f-137">Параметр вернется к последней версии, развернутой во всех группах.</span><span class="sxs-lookup"><span data-stu-id="34d9f-137">The setting will revert to the last version that was deployed to all groups.</span></span>

<span data-ttu-id="34d9f-138">В качестве примера покажем действия по повторному измене с помощью фоновой картинки desktop.</span><span class="sxs-lookup"><span data-stu-id="34d9f-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="34d9f-139">**Чтобы отменить изменение**</span><span class="sxs-lookup"><span data-stu-id="34d9f-139">**To revert a change**</span></span>

1. <span data-ttu-id="34d9f-140">Войдите в [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) и перейдите в меню **Devices**</span><span class="sxs-lookup"><span data-stu-id="34d9f-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="34d9f-141">Посмотрите раздел компьютеры, управляемые Майкрософт, выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="34d9f-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="34d9f-142">В **рабочей области состояния** развертывания выберите параметр, который необходимо вернуться, а затем выберите поэтапное развертывание для повторного развертывания.</span><span class="sxs-lookup"><span data-stu-id="34d9f-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="34d9f-143">В **статье Need to revert this change?,** select **Revert deployment**.</span><span class="sxs-lookup"><span data-stu-id="34d9f-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="34d9f-144">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="34d9f-144">Additional resources</span></span>

- [<span data-ttu-id="34d9f-145">Обзор настраиваемых параметров</span><span class="sxs-lookup"><span data-stu-id="34d9f-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="34d9f-146">Справочник по настраиваемым параметрам</span><span class="sxs-lookup"><span data-stu-id="34d9f-146">Configurable settings reference</span></span>](config-setting-ref.md) 
