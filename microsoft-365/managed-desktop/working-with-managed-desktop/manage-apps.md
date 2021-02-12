---
title: Управление приложениями на компьютерах, управляемых Майкрософт
description: Сведения об обновлении бизнес-приложений, развернутых на настольных устройствах, управляемых Майкрософт
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600686"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="a81da-104">Управление бизнес-приложениями на компьютерах, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a81da-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="a81da-105">Существует несколько способов управления обновлениями приложений для приложений, которые вы перенаправили на компьютеры, управляемые Майкрософт, и развернули их на своих устройствах, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a81da-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="a81da-106">Вы можете обновлять приложения на портале Microsoft Managed Desktop или Intune.</span><span class="sxs-lookup"><span data-stu-id="a81da-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="a81da-107">Обновление бизнес-приложений на компьютерах, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a81da-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="a81da-108">**Обновление бизнес-приложений на портале microsoft Managed Desktop**</span><span class="sxs-lookup"><span data-stu-id="a81da-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="a81da-109">Во sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="a81da-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="a81da-110">Under **Inventory**, select **Apps**.</span><span class="sxs-lookup"><span data-stu-id="a81da-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="a81da-111">Выберите приложение, которое вы хотите обновить, а затем выберите **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="a81da-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="a81da-112">В **области "Управление"** выберите **"Свойства".**</span><span class="sxs-lookup"><span data-stu-id="a81da-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="a81da-113">Щелкните **файл пакета приложения** и перейдите к отправке нового файла пакета приложения.</span><span class="sxs-lookup"><span data-stu-id="a81da-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="a81da-114">Выберите **файл пакета приложения.**</span><span class="sxs-lookup"><span data-stu-id="a81da-114">Select **App package file**.</span></span>
7. <span data-ttu-id="a81da-115">Выберите значок папки и перейдите к расположению обновленного файла приложения.</span><span class="sxs-lookup"><span data-stu-id="a81da-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="a81da-116">Выберите **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="a81da-116">Select **Open**.</span></span> <span data-ttu-id="a81da-117">Сведения о приложении обновляются с помощью сведений о пакете.</span><span class="sxs-lookup"><span data-stu-id="a81da-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="a81da-118">**Убедитесь, что версия приложения** отражает обновленный пакет приложения.</span><span class="sxs-lookup"><span data-stu-id="a81da-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="a81da-119">Обновленное приложение будет развернуто на устройствах пользователя.</span><span class="sxs-lookup"><span data-stu-id="a81da-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="a81da-120">Обновление бизнес-приложений в Intune</span><span class="sxs-lookup"><span data-stu-id="a81da-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="a81da-121">**Обновление бизнес-приложений в Intune**</span><span class="sxs-lookup"><span data-stu-id="a81da-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="a81da-122">Во sign in to [Azure portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="a81da-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="a81da-123">Выберите **"Все**  >  **службы Intune".**</span><span class="sxs-lookup"><span data-stu-id="a81da-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="a81da-124">Intune находится в разделе **"Мониторинг и управление".**</span><span class="sxs-lookup"><span data-stu-id="a81da-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="a81da-125">Выберите **клиентские приложения > приложения.**</span><span class="sxs-lookup"><span data-stu-id="a81da-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="a81da-126">Найдите и выберите свое приложение в списке приложений.</span><span class="sxs-lookup"><span data-stu-id="a81da-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="a81da-127">В blade **"Обзор"** выберите **"Свойства".**</span><span class="sxs-lookup"><span data-stu-id="a81da-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="a81da-128">Выберите **файл пакета приложения.**</span><span class="sxs-lookup"><span data-stu-id="a81da-128">Select **App package file**.</span></span>
7. <span data-ttu-id="a81da-129">Выберите значок папки и перейдите к расположению обновленного файла приложения.</span><span class="sxs-lookup"><span data-stu-id="a81da-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="a81da-130">Выберите **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="a81da-130">Select **Open**.</span></span> <span data-ttu-id="a81da-131">Сведения о приложении обновляются с помощью сведений о пакете.</span><span class="sxs-lookup"><span data-stu-id="a81da-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="a81da-132">**Убедитесь, что версия приложения** отражает обновленный пакет приложения.</span><span class="sxs-lookup"><span data-stu-id="a81da-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="a81da-133">Откат приложения до предыдущей версии</span><span class="sxs-lookup"><span data-stu-id="a81da-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="a81da-134">Если при развертывании новой версии приложения обнаружена ошибка, можно вернуться к предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="a81da-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="a81da-135">Процесс, описанный здесь, для приложений, тип которых указан как **бизнес-приложение Windows MSI** или **приложение для Windows (Win 32) —** предварительная версия</span><span class="sxs-lookup"><span data-stu-id="a81da-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="a81da-136">**Откат бизнес-приложения до предыдущей версии**</span><span class="sxs-lookup"><span data-stu-id="a81da-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="a81da-137">Во sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="a81da-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="a81da-138">Under **Inventory**, select **Apps**.</span><span class="sxs-lookup"><span data-stu-id="a81da-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="a81da-139">Выберите приложение, которое необходимо откатить, а затем выберите **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="a81da-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="a81da-140">В **области "Управление"** выберите **"Свойства".**</span><span class="sxs-lookup"><span data-stu-id="a81da-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="a81da-141">Для **бизнес-приложений Windows MSI** выберите сведения о приложении, а затем в версии приложения **"Игнорировать"** выберите **"Да".**</span><span class="sxs-lookup"><span data-stu-id="a81da-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="a81da-142">Для **приложения Для Windows (Win 32) —** предварительные версии приложений, выберите сведения о приложении, выберите правила **обнаружения,** а затем выберите **"Добавить".** </span><span class="sxs-lookup"><span data-stu-id="a81da-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="a81da-143">Если существует правило MSI, убедитесь, что для проверки версии продукта **MSI** установлено **"Нет".**</span><span class="sxs-lookup"><span data-stu-id="a81da-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="a81da-144">[Отправка предыдущей версии файла источника](../get-started/deploy-apps.md) приложения на портал администрирования управляемых компьютеров (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="a81da-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

