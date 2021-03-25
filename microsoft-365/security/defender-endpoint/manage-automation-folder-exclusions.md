---
title: Управление исключениями из папки автоматизации
description: Добавьте исключения из папки автоматизации для управления файлами, исключенными из автоматического расследования.
keywords: управление, автоматизация, исключение, блок, чистая, вредоносная
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 37a251acd3b7631cffffaf2eb76bf0f2b4954ee6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185841"
---
# <a name="manage-automation-folder-exclusions"></a><span data-ttu-id="75f51-104">Управление исключениями из папки автоматизации</span><span class="sxs-lookup"><span data-stu-id="75f51-104">Manage automation folder exclusions</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="75f51-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="75f51-105">**Applies to:**</span></span>
- [<span data-ttu-id="75f51-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="75f51-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="75f51-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75f51-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="75f51-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="75f51-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="75f51-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="75f51-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

<span data-ttu-id="75f51-110">Исключения из папки автоматизации позволяют указать папки, которые будет пропускать автоматическое расследование.</span><span class="sxs-lookup"><span data-stu-id="75f51-110">Automation folder exclusions allow you to specify folders that the Automated investigation will skip.</span></span> 

<span data-ttu-id="75f51-111">Вы можете управлять следующими атрибутами в папке, которую необходимо пропустить:</span><span class="sxs-lookup"><span data-stu-id="75f51-111">You can control the following attributes about the folder that you'd like to be skipped:</span></span>
- <span data-ttu-id="75f51-112">Folders</span><span class="sxs-lookup"><span data-stu-id="75f51-112">Folders</span></span> 
- <span data-ttu-id="75f51-113">Расширения файлов</span><span class="sxs-lookup"><span data-stu-id="75f51-113">Extensions of the files</span></span>
- <span data-ttu-id="75f51-114">Имена файлов</span><span class="sxs-lookup"><span data-stu-id="75f51-114">File names</span></span>


<span data-ttu-id="75f51-115">**Folders**</span><span class="sxs-lookup"><span data-stu-id="75f51-115">**Folders**</span></span><br>
<span data-ttu-id="75f51-116">Вы можете указать папку и ее подмостки, которые необходимо пропустить.</span><span class="sxs-lookup"><span data-stu-id="75f51-116">You can specify a folder and its subfolders to be skipped.</span></span> 


>[!NOTE]
><span data-ttu-id="75f51-117">В настоящее время использование wild cards в качестве способа исключения файлов в каталоге еще не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="75f51-117">At this time, use of wild cards as a way to exclude files under a directory is not yet supported.</span></span> 


<span data-ttu-id="75f51-118">**Расширения**</span><span class="sxs-lookup"><span data-stu-id="75f51-118">**Extensions**</span></span><br>
<span data-ttu-id="75f51-119">Можно указать расширения, которые необходимо исключить в определенном каталоге.</span><span class="sxs-lookup"><span data-stu-id="75f51-119">You can specify the extensions to exclude in a specific directory.</span></span> <span data-ttu-id="75f51-120">Расширения — это способ предотвратить использование злоумышленником исключенной папки для сокрытия эксплойта.</span><span class="sxs-lookup"><span data-stu-id="75f51-120">The extensions are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="75f51-121">Расширения явно определяют, какие файлы игнорировать.</span><span class="sxs-lookup"><span data-stu-id="75f51-121">The extensions explicitly define which files to ignore.</span></span> 

<span data-ttu-id="75f51-122">**Имена файлов**</span><span class="sxs-lookup"><span data-stu-id="75f51-122">**File names**</span></span><br>
<span data-ttu-id="75f51-123">Вы можете указать имена файлов, которые необходимо исключить в определенном каталоге.</span><span class="sxs-lookup"><span data-stu-id="75f51-123">You can specify the file names that you want to be excluded in a specific directory.</span></span> <span data-ttu-id="75f51-124">Имена — это способ предотвратить использование злоумышленником исключенной папки для сокрытия эксплойта.</span><span class="sxs-lookup"><span data-stu-id="75f51-124">The names are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="75f51-125">Имена явно определяют, какие файлы игнорировать.</span><span class="sxs-lookup"><span data-stu-id="75f51-125">The names explicitly define which files to ignore.</span></span> 



## <a name="add-an-automation-folder-exclusion"></a><span data-ttu-id="75f51-126">Добавление исключения папки автоматизации</span><span class="sxs-lookup"><span data-stu-id="75f51-126">Add an automation folder exclusion</span></span>
1. <span data-ttu-id="75f51-127">В области навигации выберите **исключения из папки "Автоматизация**  >  **параметров".**</span><span class="sxs-lookup"><span data-stu-id="75f51-127">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  

2. <span data-ttu-id="75f51-128">Щелкните **исключение из новой папки**.</span><span class="sxs-lookup"><span data-stu-id="75f51-128">Click **New folder exclusion**.</span></span>  

3. <span data-ttu-id="75f51-129">Введите сведения о папке:</span><span class="sxs-lookup"><span data-stu-id="75f51-129">Enter the folder details:</span></span>

    - <span data-ttu-id="75f51-130">Folder</span><span class="sxs-lookup"><span data-stu-id="75f51-130">Folder</span></span>
    - <span data-ttu-id="75f51-131">Расширения</span><span class="sxs-lookup"><span data-stu-id="75f51-131">Extensions</span></span>
    - <span data-ttu-id="75f51-132">Имена файлов</span><span class="sxs-lookup"><span data-stu-id="75f51-132">File names</span></span>
    - <span data-ttu-id="75f51-133">Описание</span><span class="sxs-lookup"><span data-stu-id="75f51-133">Description</span></span>
    

4. <span data-ttu-id="75f51-134">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="75f51-134">Click **Save**.</span></span>

>[!NOTE]
> <span data-ttu-id="75f51-135">Команды Live Response для сбора или изучения исключенных файлов сбой с ошибкой: "Файл исключен".</span><span class="sxs-lookup"><span data-stu-id="75f51-135">Live Response commands to collect or examine excluded files will fail with error: "File is excluded".</span></span> <span data-ttu-id="75f51-136">Кроме того, автоматические исследования будут игнорировать исключенные элементы.</span><span class="sxs-lookup"><span data-stu-id="75f51-136">In addition, automated investigations will ignore the excluded items.</span></span>

## <a name="edit-an-automation-folder-exclusion"></a><span data-ttu-id="75f51-137">Изменение исключения папки автоматизации</span><span class="sxs-lookup"><span data-stu-id="75f51-137">Edit an automation folder exclusion</span></span> 
1. <span data-ttu-id="75f51-138">В области навигации выберите **исключения из папки "Автоматизация**  >  **параметров".**</span><span class="sxs-lookup"><span data-stu-id="75f51-138">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span> 

2. <span data-ttu-id="75f51-139">Нажмите **кнопку Изменить** исключение папки.</span><span class="sxs-lookup"><span data-stu-id="75f51-139">Click **Edit** on the folder exclusion.</span></span>  

3. <span data-ttu-id="75f51-140">Обновите сведения о правиле и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="75f51-140">Update the details of the rule and click **Save**.</span></span>

## <a name="remove-an-automation-folder-exclusion"></a><span data-ttu-id="75f51-141">Удаление исключения папки автоматизации</span><span class="sxs-lookup"><span data-stu-id="75f51-141">Remove an automation folder exclusion</span></span> 
1. <span data-ttu-id="75f51-142">В области навигации выберите **исключения из папки "Автоматизация**  >  **параметров".**</span><span class="sxs-lookup"><span data-stu-id="75f51-142">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  
2. <span data-ttu-id="75f51-143">Нажмите **кнопку Удалить исключение**.</span><span class="sxs-lookup"><span data-stu-id="75f51-143">Click **Remove exclusion**.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="75f51-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="75f51-144">Related topics</span></span>
- [<span data-ttu-id="75f51-145">Управление списками автоматизации, разрешенными и заблокированными</span><span class="sxs-lookup"><span data-stu-id="75f51-145">Manage automation allowed/blocked lists</span></span>](manage-indicators.md)
- [<span data-ttu-id="75f51-146">Управление загрузкой файлов автоматизации</span><span class="sxs-lookup"><span data-stu-id="75f51-146">Manage automation file uploads</span></span>](manage-automation-file-uploads.md)
