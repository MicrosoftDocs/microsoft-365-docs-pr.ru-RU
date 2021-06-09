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
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a><span data-ttu-id="ae2be-103">Управление обнаружением тем в Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="ae2be-103">Manage topic discovery in Microsoft Viva Topics</span></span>

<span data-ttu-id="ae2be-104">Вы можете управлять настройками обнаружения тем в [центре Microsoft 365 администрирования.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ae2be-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="ae2be-105">Вы должны быть глобальным администратором или администратором SharePoint для выполнения этих задач.</span><span class="sxs-lookup"><span data-stu-id="ae2be-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="ae2be-106">Чтобы получить доступ к настройкам управления темами:</span><span class="sxs-lookup"><span data-stu-id="ae2be-106">To access topics management settings:</span></span>

1. <span data-ttu-id="ae2be-107">В центре администрирования Microsoft 365 нажмите **кнопку Параметры,** а затем **параметры Org**.</span><span class="sxs-lookup"><span data-stu-id="ae2be-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="ae2be-108">На **вкладке Services** щелкните **Раздел опытом**.</span><span class="sxs-lookup"><span data-stu-id="ae2be-108">On the **Services** tab, click **Topic experiences**.</span></span>

    ![Подключение к знаниям](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="ae2be-110">Выберите **вкладку "Открытие** темы". Сведения о каждом параметре см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="ae2be-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![параметры знаний и сетей](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="ae2be-112">Выберите SharePoint темы</span><span class="sxs-lookup"><span data-stu-id="ae2be-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="ae2be-113">Вы можете изменить SharePoint сайтов в организации, которые будут обхода для тем.</span><span class="sxs-lookup"><span data-stu-id="ae2be-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="ae2be-114">Если вы хотите включить или исключить определенный список сайтов, можно использовать следующий шаблон .csv:</span><span class="sxs-lookup"><span data-stu-id="ae2be-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="ae2be-115">При добавлении сайтов с помощью средства их выбора они добавляются в существующий список сайтов, которые необходимо включить или исключить.</span><span class="sxs-lookup"><span data-stu-id="ae2be-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="ae2be-116">При передаче файла .csv он переписывает любой существующий список.</span><span class="sxs-lookup"><span data-stu-id="ae2be-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="ae2be-117">Если вы ранее включили или исключили определенные сайты, вы скачиваете список в качестве .csv, внося изменения и загрузите новый список.</span><span class="sxs-lookup"><span data-stu-id="ae2be-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="ae2be-118">Выбор сайтов для обнаружения тем</span><span class="sxs-lookup"><span data-stu-id="ae2be-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="ae2be-119">На вкладке **Обнаружение тем** в разделе **Выбор источников тем SharePoint** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="ae2be-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="ae2be-120">На странице **Выберите SharePoint** темы выберите, какие SharePoint будут обхода в качестве источников для ваших тем во время обнаружения.</span><span class="sxs-lookup"><span data-stu-id="ae2be-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="ae2be-121">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="ae2be-121">This includes:</span></span>
    - <span data-ttu-id="ae2be-122">**Все сайты:** все SharePoint в клиенте.</span><span class="sxs-lookup"><span data-stu-id="ae2be-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="ae2be-123">Это захватывает текущие и будущие сайты.</span><span class="sxs-lookup"><span data-stu-id="ae2be-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="ae2be-124">**Все, кроме выбранных сайтов:** введите имена сайтов, которые необходимо исключить.</span><span class="sxs-lookup"><span data-stu-id="ae2be-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="ae2be-125">Вы также можете загрузить список сайтов, которые вы хотите отказаться от обнаружения.</span><span class="sxs-lookup"><span data-stu-id="ae2be-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="ae2be-126">Сайты, созданные в будущем, будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="ae2be-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="ae2be-127">**Только выбранные сайты:** введите имена сайтов, которые вы хотите включить.</span><span class="sxs-lookup"><span data-stu-id="ae2be-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="ae2be-128">Вы также можете загрузить список сайтов.</span><span class="sxs-lookup"><span data-stu-id="ae2be-128">You can also upload a list of sites.</span></span> <span data-ttu-id="ae2be-129">Сайты, созданные в будущем, не будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="ae2be-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="ae2be-130">**Нет сайтов.** Темы не будут автоматически генерируться или обновляться с помощью SharePoint контента.</span><span class="sxs-lookup"><span data-stu-id="ae2be-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="ae2be-131">Существующие темы остаются в центре тем.</span><span class="sxs-lookup"><span data-stu-id="ae2be-131">Existing topics remain in the topic center.</span></span>

    ![Скриншот пользовательского интерфейса SharePoint источников темы](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="ae2be-133">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ae2be-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="ae2be-134">Исключить темы по имени</span><span class="sxs-lookup"><span data-stu-id="ae2be-134">Exclude topics by name</span></span>

<span data-ttu-id="ae2be-135">Можно исключить темы из обнаружения, загрузив список с помощью файла .csv.</span><span class="sxs-lookup"><span data-stu-id="ae2be-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="ae2be-136">Если темы уже были исключены ранее, можно скачать файл .csv, внести изменения и передать его еще раз.</span><span class="sxs-lookup"><span data-stu-id="ae2be-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="ae2be-137">На вкладке **Обнаружение тем** в разделе **Исключить темы** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="ae2be-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="ae2be-138">Нажмите **Кнопку Исключить темы по имени**.</span><span class="sxs-lookup"><span data-stu-id="ae2be-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="ae2be-139">Если необходимо создать список, скачайте шаблон .csv и добавьте разделы, которые вы хотите исключить (см. раздел Работа с шаблоном *.csv* ниже).</span><span class="sxs-lookup"><span data-stu-id="ae2be-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="ae2be-140">Когда файл будет готов, нажмите **кнопку Обзор** и загрузите файл.</span><span class="sxs-lookup"><span data-stu-id="ae2be-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="ae2be-141">Если есть существующий список, вы можете скачать .csv, содержащий список.</span><span class="sxs-lookup"><span data-stu-id="ae2be-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="ae2be-142">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ae2be-142">Click **Save**.</span></span>

    ![Снимок экрана об исключении тем пользовательского интерфейса](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="ae2be-144">Работа с шаблоном .csv</span><span class="sxs-lookup"><span data-stu-id="ae2be-144">Working with the .csv template</span></span>

<span data-ttu-id="ae2be-145">Вы можете скопировать шаблон csv ниже:</span><span class="sxs-lookup"><span data-stu-id="ae2be-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="ae2be-146">В шаблоне CSV введите следующие сведения о темах, которые хотите исключить:</span><span class="sxs-lookup"><span data-stu-id="ae2be-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="ae2be-147">**Имя**: введите имя темы, которую хотите исключить.</span><span class="sxs-lookup"><span data-stu-id="ae2be-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="ae2be-148">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="ae2be-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="ae2be-149">Точное совпадение. Можно исключить точное имя или аббревиатура (например, *Contoso* или *ATL).*</span><span class="sxs-lookup"><span data-stu-id="ae2be-149">Exact match: You can exclude the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="ae2be-150">Частичное совпадение. Вы можете исключить все темы, в них есть определенное слово.</span><span class="sxs-lookup"><span data-stu-id="ae2be-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="ae2be-151">Например, *дуга* исключает все темы со *словом* дуга в нем, такие как круг *дуги,* сварка плазменной дуги или *дуга обучения.* Обратите внимание, что не исключены темы, в которые текст включен как часть слова, например *Архитектура.*</span><span class="sxs-lookup"><span data-stu-id="ae2be-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="ae2be-152">**Означает (необязательно).** Если вы хотите исключить аббревиатура, введите слова, которые обозначает аббревиатура.</span><span class="sxs-lookup"><span data-stu-id="ae2be-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="ae2be-153">**MatchType-Exact/Partial**. Введите, было ли вписано имя *точным* или *частичным типом* совпадения.</span><span class="sxs-lookup"><span data-stu-id="ae2be-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![Исключение тем в шаблоне CSV](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="ae2be-155">См. также</span><span class="sxs-lookup"><span data-stu-id="ae2be-155">See also</span></span>

[<span data-ttu-id="ae2be-156">Управление обзором тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ae2be-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="ae2be-157">Управление разрешениями тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ae2be-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="ae2be-158">Измените имя центра темы в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ae2be-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
