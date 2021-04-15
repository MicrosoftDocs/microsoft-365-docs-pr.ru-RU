---
title: Управление обнаружением тем в Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Узнайте, как администрирование обнаружения тем в разделе Microsoft Viva Topics.
ms.openlocfilehash: 53e304dc69ccf2ca6fe01d29f0997c539406b0fe
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768978"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a><span data-ttu-id="8f78d-103">Управление обнаружением тем в Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="8f78d-103">Manage topic discovery in Microsoft Viva Topics</span></span>

<span data-ttu-id="8f78d-104">Вы можете управлять настройками обнаружения тем в центре администрирования [Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="8f78d-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="8f78d-105">Для выполнения этих задач необходимо быть глобальным администратором или администратором SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8f78d-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="8f78d-106">Чтобы получить доступ к настройкам управления темами:</span><span class="sxs-lookup"><span data-stu-id="8f78d-106">To access topics management settings:</span></span>

1. <span data-ttu-id="8f78d-107">В центре администрирования Microsoft 365 щелкните **Параметры,** а затем **параметры Org.**</span><span class="sxs-lookup"><span data-stu-id="8f78d-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="8f78d-108">На **вкладке Services** щелкните **Раздел опытом**.</span><span class="sxs-lookup"><span data-stu-id="8f78d-108">On the **Services** tab, click **Topic experiences**.</span></span>

    ![Подключение людей к знаниям](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="8f78d-110">Выберите **вкладку "Открытие** темы". Сведения о каждом параметре см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="8f78d-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![параметры знаний и сетей](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="8f78d-112">Выберите источники темы SharePoint</span><span class="sxs-lookup"><span data-stu-id="8f78d-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="8f78d-113">Вы можете изменить сайты SharePoint в организации, которые будут обходиться по темам.</span><span class="sxs-lookup"><span data-stu-id="8f78d-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="8f78d-114">Если вы хотите включить или исключить определенный список сайтов, можно использовать следующий шаблон csv:</span><span class="sxs-lookup"><span data-stu-id="8f78d-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="8f78d-115">Если вы добавляете сайты с помощью выборщика сайтов, они добавляются в существующий список сайтов, чтобы включить или исключить.</span><span class="sxs-lookup"><span data-stu-id="8f78d-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="8f78d-116">Если вы загрузите файл CSV, он переопишет любой существующий список.</span><span class="sxs-lookup"><span data-stu-id="8f78d-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="8f78d-117">Если вы ранее включили или исключили определенные сайты, скачайте список в качестве файла CSV, внося изменения и загрузите новый список.</span><span class="sxs-lookup"><span data-stu-id="8f78d-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="8f78d-118">Выбор сайтов для обнаружения тем</span><span class="sxs-lookup"><span data-stu-id="8f78d-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="8f78d-119">На **вкладке Открытие Темы** в **разделе Выбор источников темы SharePoint** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="8f78d-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="8f78d-120">На странице **Выбор источников темы SharePoint** выберите, какие сайты SharePoint будут обходиться в качестве источников для ваших тем во время обнаружения.</span><span class="sxs-lookup"><span data-stu-id="8f78d-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="8f78d-121">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="8f78d-121">This includes:</span></span>
    - <span data-ttu-id="8f78d-122">**Все сайты.** Все сайты SharePoint в вашем клиенте.</span><span class="sxs-lookup"><span data-stu-id="8f78d-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="8f78d-123">Это захватывает текущие и будущие сайты.</span><span class="sxs-lookup"><span data-stu-id="8f78d-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="8f78d-124">**Все, кроме выбранных сайтов:** введите имена сайтов, которые необходимо исключить.</span><span class="sxs-lookup"><span data-stu-id="8f78d-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="8f78d-125">Вы также можете загрузить список сайтов, которые вы хотите отказаться от обнаружения.</span><span class="sxs-lookup"><span data-stu-id="8f78d-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="8f78d-126">Сайты, созданные в будущем, будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="8f78d-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="8f78d-127">**Только выбранные сайты:** введите имена сайтов, которые вы хотите включить.</span><span class="sxs-lookup"><span data-stu-id="8f78d-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="8f78d-128">Вы также можете загрузить список сайтов.</span><span class="sxs-lookup"><span data-stu-id="8f78d-128">You can also upload a list of sites.</span></span> <span data-ttu-id="8f78d-129">Сайты, созданные в будущем, не будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="8f78d-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="8f78d-130">**Нет сайтов.** Темы не будут автоматически генерируться или обновляться с помощью контента SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8f78d-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="8f78d-131">Существующие темы остаются в центре тем.</span><span class="sxs-lookup"><span data-stu-id="8f78d-131">Existing topics remain in the topic center.</span></span>

    ![Снимок экрана пользовательского интерфейса источников темы SharePoint](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="8f78d-133">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8f78d-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="8f78d-134">Исключение тем по имени</span><span class="sxs-lookup"><span data-stu-id="8f78d-134">Exclude topics by name</span></span>

<span data-ttu-id="8f78d-135">Вы можете исключить темы из обнаружения, загрузив список с помощью файла .csv.</span><span class="sxs-lookup"><span data-stu-id="8f78d-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="8f78d-136">Если ранее были исключены темы, вы можете скачать .csv, внести изменения и загрузить его снова.</span><span class="sxs-lookup"><span data-stu-id="8f78d-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="8f78d-137">На **вкладке Открытие Темы,** в разделе **Исключить темы,** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="8f78d-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="8f78d-138">Нажмите **Кнопку Исключить темы по имени**.</span><span class="sxs-lookup"><span data-stu-id="8f78d-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="8f78d-139">Если вам нужно создать список, скачайте шаблон csv и добавьте разделы, которые необходимо исключить (см. раздел Работа с *шаблоном CSV* ниже).</span><span class="sxs-lookup"><span data-stu-id="8f78d-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="8f78d-140">Когда файл будет готов, нажмите **кнопку Обзор** и загрузите файл.</span><span class="sxs-lookup"><span data-stu-id="8f78d-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="8f78d-141">Если есть существующий список, вы можете скачать .csv, содержащий список.</span><span class="sxs-lookup"><span data-stu-id="8f78d-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="8f78d-142">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8f78d-142">Click **Save**.</span></span>

    ![Снимок экрана об исключении тем пользовательского интерфейса](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="8f78d-144">Работа с шаблоном .csv</span><span class="sxs-lookup"><span data-stu-id="8f78d-144">Working with the .csv template</span></span>

<span data-ttu-id="8f78d-145">Вы можете скопировать шаблон csv ниже:</span><span class="sxs-lookup"><span data-stu-id="8f78d-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="8f78d-146">В шаблоне CSV введите следующую информацию о темах, которые необходимо исключить:</span><span class="sxs-lookup"><span data-stu-id="8f78d-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="8f78d-147">**Имя.** Введите имя темы, которая вы хотите исключить.</span><span class="sxs-lookup"><span data-stu-id="8f78d-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="8f78d-148">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="8f78d-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="8f78d-149">Точное совпадение. Можно исключить точное имя или аббревиатура (например, *Contoso* или *ATL).*</span><span class="sxs-lookup"><span data-stu-id="8f78d-149">Exact match: You can exclude the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="8f78d-150">Частичное совпадение. Вы можете исключить все темы, в них есть определенное слово.</span><span class="sxs-lookup"><span data-stu-id="8f78d-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="8f78d-151">Например, *дуга* исключает все темы со *словом* дуга в нем, такие как круг *дуги,* сварка плазменной дуги или *дуга обучения.* Обратите внимание, что не исключены темы, в которые текст включен как часть слова, например *Архитектура.*</span><span class="sxs-lookup"><span data-stu-id="8f78d-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="8f78d-152">**Означает (необязательно).** Если вы хотите исключить аббревиатура, введите слова, которые обозначает аббревиатура.</span><span class="sxs-lookup"><span data-stu-id="8f78d-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="8f78d-153">**MatchType-Exact/Partial**. Введите, было ли вписано имя *точным* или *частичным типом* совпадения.</span><span class="sxs-lookup"><span data-stu-id="8f78d-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![Исключение тем в шаблоне CSV](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="8f78d-155">См. также</span><span class="sxs-lookup"><span data-stu-id="8f78d-155">See also</span></span>

[<span data-ttu-id="8f78d-156">Управление обзором тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8f78d-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="8f78d-157">Управление разрешениями тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8f78d-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="8f78d-158">Изменение имени центра темы в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8f78d-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
