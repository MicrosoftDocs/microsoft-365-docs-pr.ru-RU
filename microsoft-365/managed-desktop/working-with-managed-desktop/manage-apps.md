---
title: Управление приложениями в компьютеры, управляемые Майкрософт
description: Сведения об обновлении бизнес-приложений, развернутых на компьютеры, управляемые Майкрософт устройствах
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: b016d8458b4b4cc9f6b684d3b8a3c0a1e1322fef
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925411"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="e0db5-104">Управление бизнес-приложениями на компьютерах, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e0db5-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="e0db5-105">Существует несколько способов управления обновлениями приложений для приложений, которые вы компьютеры, управляемые Майкрософт и развернуты на компьютеры, управляемые Майкрософт устройствах.</span><span class="sxs-lookup"><span data-stu-id="e0db5-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="e0db5-106">Обновления приложений можно сделать на компьютеры, управляемые Майкрософт портале или Intune.</span><span class="sxs-lookup"><span data-stu-id="e0db5-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="e0db5-107">Обновление бизнес-приложений в компьютеры, управляемые Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e0db5-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="e0db5-108">**Обновление бизнес-приложений на компьютеры, управляемые Майкрософт портале**</span><span class="sxs-lookup"><span data-stu-id="e0db5-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="e0db5-109">Во входе [на компьютеры, управляемые Майкрософт администратора](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="e0db5-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="e0db5-110">В **рамках инвентаризации** выберите **Приложения**.</span><span class="sxs-lookup"><span data-stu-id="e0db5-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="e0db5-111">Выберите приложение, которое необходимо обновить, а затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e0db5-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="e0db5-112">В **статье Управление** выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="e0db5-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="e0db5-113">Щелкните **файл пакета приложения,** а затем просмотрите, чтобы загрузить новый файл пакета приложений.</span><span class="sxs-lookup"><span data-stu-id="e0db5-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="e0db5-114">Выберите **файл пакета приложений**.</span><span class="sxs-lookup"><span data-stu-id="e0db5-114">Select **App package file**.</span></span>
7. <span data-ttu-id="e0db5-115">Выберите значок папки и просмотрите расположение обновленного файла приложения.</span><span class="sxs-lookup"><span data-stu-id="e0db5-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="e0db5-116">Выберите **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="e0db5-116">Select **Open**.</span></span> <span data-ttu-id="e0db5-117">Сведения о приложении обновляются с помощью данных пакета.</span><span class="sxs-lookup"><span data-stu-id="e0db5-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="e0db5-118">Убедитесь, **что версия Приложения** отражает обновленный пакет приложений.</span><span class="sxs-lookup"><span data-stu-id="e0db5-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="e0db5-119">Обновленное приложение будет развернуто на устройствах пользователя.</span><span class="sxs-lookup"><span data-stu-id="e0db5-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="e0db5-120">Обновление бизнес-приложений в Intune</span><span class="sxs-lookup"><span data-stu-id="e0db5-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="e0db5-121">**Обновление бизнес-приложений в Intune**</span><span class="sxs-lookup"><span data-stu-id="e0db5-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="e0db5-122">Во входе на [портал Azure.](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="e0db5-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="e0db5-123">Выберите **Все**  >  **службы Intune**.</span><span class="sxs-lookup"><span data-stu-id="e0db5-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="e0db5-124">Intune находится в разделе **Мониторинг + Управление.**</span><span class="sxs-lookup"><span data-stu-id="e0db5-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="e0db5-125">Выберите **клиентские приложения > приложения**.</span><span class="sxs-lookup"><span data-stu-id="e0db5-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="e0db5-126">Поиск и выбор приложения в списке приложений.</span><span class="sxs-lookup"><span data-stu-id="e0db5-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="e0db5-127">В **лезвии Обзор** выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e0db5-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="e0db5-128">Выберите **файл пакета приложений**.</span><span class="sxs-lookup"><span data-stu-id="e0db5-128">Select **App package file**.</span></span>
7. <span data-ttu-id="e0db5-129">Выберите значок папки и просмотрите расположение обновленного файла приложения.</span><span class="sxs-lookup"><span data-stu-id="e0db5-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="e0db5-130">Выберите **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="e0db5-130">Select **Open**.</span></span> <span data-ttu-id="e0db5-131">Сведения о приложении обновляются с помощью данных пакета.</span><span class="sxs-lookup"><span data-stu-id="e0db5-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="e0db5-132">Убедитесь, **что версия Приложения** отражает обновленный пакет приложений.</span><span class="sxs-lookup"><span data-stu-id="e0db5-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="e0db5-133">Откат приложения в предыдущую версию</span><span class="sxs-lookup"><span data-stu-id="e0db5-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="e0db5-134">Если при развертывании новой версии приложения обнаружена ошибка, можно вернуться к предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="e0db5-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="e0db5-135">Процесс, описанный здесь, для приложений, в которых тип указан как Windows MSI линейки **бизнес-приложения** или **Windows приложения (Win 32) - предварительный просмотр**</span><span class="sxs-lookup"><span data-stu-id="e0db5-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="e0db5-136">**Откат бизнес-приложения в предыдущую версию**</span><span class="sxs-lookup"><span data-stu-id="e0db5-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="e0db5-137">Во входе [на компьютеры, управляемые Майкрософт администратора](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="e0db5-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="e0db5-138">В **рамках инвентаризации** выберите **Приложения**.</span><span class="sxs-lookup"><span data-stu-id="e0db5-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="e0db5-139">Выберите приложение, необходимое для отката, а затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e0db5-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="e0db5-140">В **статье Управление** выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="e0db5-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="e0db5-141">Для Windows приложения-приложения для линейки **бизнес-приложений MSI** выберите сведения о приложении, а затем в версии Ignore **app** выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="e0db5-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="e0db5-142">Для **Windows (Win 32) —** предварительные приложения, выберите сведения о приложении, выберите правила обнаружения, а затем выберите **Добавить**.  </span><span class="sxs-lookup"><span data-stu-id="e0db5-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="e0db5-143">Если существует правило MSI, убедитесь, что проверка версии продукта **MSI** установлена на **no**.</span><span class="sxs-lookup"><span data-stu-id="e0db5-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="e0db5-144">[Upload предыдущей версии](../get-started/deploy-apps.md) файла источника приложения на компьютеры, управляемые Майкрософт администратора.</span><span class="sxs-lookup"><span data-stu-id="e0db5-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

