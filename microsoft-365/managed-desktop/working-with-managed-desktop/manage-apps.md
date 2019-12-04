---
title: Управление приложениями на настольном компьютере, управляемом Майкрософт
description: Сведения об обновлении бизнес-приложений, развернутых на настольных компьютерах, управляемых Майкрософт
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7aca4713aae189e39133e08a1fbcad6fd75e6a70
ms.sourcegitcommit: 8fda7852b2a5baa92b8a365865b014ea6d100bbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "39813859"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="87981-104">Управление бизнес-приложениями на настольных компьютерах, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="87981-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="87981-105">Существует несколько способов управления обновлениями приложений для приложений, которые вы настроили на настольные компьютеры, управляемые корпорацией Майкрософт и развернутые на настольных устройствах, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="87981-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="87981-106">Вы можете вносить обновления для приложений на портале для настольных ПК, управляемом Майкрософт, или Intune.</span><span class="sxs-lookup"><span data-stu-id="87981-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="87981-107">Обновление бизнес-приложений на настольных компьютерах, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="87981-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="87981-108">**Обновление бизнес-приложений на настольных порталах, управляемых Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="87981-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="87981-109">Войдите на [портал администрирования рабочих столов с управляемыми правами Майкрософт](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="87981-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="87981-110">В разделе **запасы**выберите **приложения**.</span><span class="sxs-lookup"><span data-stu-id="87981-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="87981-111">Выберите приложение, которое вы хотите обновить, и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="87981-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="87981-112">В разделе **Управление**выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="87981-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="87981-113">Щелкните **файл пакета приложения**, а затем Обзор, чтобы отправить новый файл пакета приложения.</span><span class="sxs-lookup"><span data-stu-id="87981-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="87981-114">Выберите **файл пакета приложения**.</span><span class="sxs-lookup"><span data-stu-id="87981-114">Select **App package file**.</span></span>
7. <span data-ttu-id="87981-115">Выберите значок папки и перейдите к расположению обновленного файла приложения.</span><span class="sxs-lookup"><span data-stu-id="87981-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="87981-116">Нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="87981-116">Select **Open**.</span></span> <span data-ttu-id="87981-117">Сведения о приложении обновляются с использованием сведений о пакете.</span><span class="sxs-lookup"><span data-stu-id="87981-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="87981-118">Убедитесь, что **версия приложения** отражает обновленный пакет приложения.</span><span class="sxs-lookup"><span data-stu-id="87981-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="87981-119">Обновленное приложение будет развернуто на устройствах пользователя.</span><span class="sxs-lookup"><span data-stu-id="87981-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="87981-120">Обновление бизнес-приложений в Intune</span><span class="sxs-lookup"><span data-stu-id="87981-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="87981-121">**Обновление бизнес-приложений в Intune**</span><span class="sxs-lookup"><span data-stu-id="87981-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="87981-122">Войдите на [портал Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="87981-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="87981-123">Выберите **все службы** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="87981-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="87981-124">Intune находится в разделе **мониторинг и управление** .</span><span class="sxs-lookup"><span data-stu-id="87981-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="87981-125">Выберите **клиентские приложения > приложения**.</span><span class="sxs-lookup"><span data-stu-id="87981-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="87981-126">Найдите и выберите свое приложение в списке приложений.</span><span class="sxs-lookup"><span data-stu-id="87981-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="87981-127">В колонке **Обзор** выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="87981-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="87981-128">Выберите **файл пакета приложения**.</span><span class="sxs-lookup"><span data-stu-id="87981-128">Select **App package file**.</span></span>
7. <span data-ttu-id="87981-129">Выберите значок папки и перейдите к расположению обновленного файла приложения.</span><span class="sxs-lookup"><span data-stu-id="87981-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="87981-130">Нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="87981-130">Select **Open**.</span></span> <span data-ttu-id="87981-131">Сведения о приложении обновляются с использованием сведений о пакете.</span><span class="sxs-lookup"><span data-stu-id="87981-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="87981-132">Убедитесь, что **версия приложения** отражает обновленный пакет приложения.</span><span class="sxs-lookup"><span data-stu-id="87981-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="87981-133">Откат приложения к предыдущей версии</span><span class="sxs-lookup"><span data-stu-id="87981-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="87981-134">Если при развертывании новой версии приложения обнаружена ошибка, можно вернуться к предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="87981-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="87981-135">Процесс, описанный здесь, предназначен для приложений, где тип указан как **бизнес-приложение Windows MSI** или **приложение windows (Win 32)-Preview**</span><span class="sxs-lookup"><span data-stu-id="87981-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="87981-136">**Откат бизнес-приложения до предыдущей версии**</span><span class="sxs-lookup"><span data-stu-id="87981-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="87981-137">Войдите на [портал администрирования рабочих столов с управляемыми правами Майкрософт](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="87981-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="87981-138">В разделе **запасы**выберите **приложения**.</span><span class="sxs-lookup"><span data-stu-id="87981-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="87981-139">Выберите приложение, которое необходимо откатить, и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="87981-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="87981-140">В разделе **Управление**выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="87981-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="87981-141">Для приложений **Windows MSI для бизнес-** приложений выберите **сведения о приложении**, а затем в разделе **игнорировать версию приложения**выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="87981-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="87981-142">Для приложения **Windows (Win 32) — предварительный просмотр** приложений выберите **сведения о приложении**, выберите **правила обнаружения**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="87981-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="87981-143">Если имеется правило MSI, убедитесь, что для **проверки версии MSI** -файла установлено значение **нет**.</span><span class="sxs-lookup"><span data-stu-id="87981-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="87981-144">[Отправьте предыдущую версию исходного файла приложения](../get-started/deploy-apps.md) на портал администрирования настольных компьютеров Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="87981-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

