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
description: Узнайте, как администрировать обнаружение тем в Microsoft Viva Topics.
ms.openlocfilehash: 36b64433726479dc2a46c809ae9504c6f12f4ab8
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107769"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a><span data-ttu-id="9c4cd-103">Управление обнаружением тем в Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="9c4cd-103">Manage topic discovery in Microsoft Viva Topics</span></span>

<span data-ttu-id="9c4cd-104">Вы можете управлять настройками обнаружения тем в Центре администрирования [Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="9c4cd-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="9c4cd-105">Для выполнения этих задач необходимо быть глобальным администратором или администратором SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="9c4cd-106">Чтобы получить доступ к настройкам управления разделами:</span><span class="sxs-lookup"><span data-stu-id="9c4cd-106">To access topics management settings:</span></span>

1. <span data-ttu-id="9c4cd-107">В Центре администрирования Microsoft 365 выберите **"Параметры"** и **"Параметры организации".**</span><span class="sxs-lookup"><span data-stu-id="9c4cd-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="9c4cd-108">На **вкладке "Службы"** щелкните **"Раздел".**</span><span class="sxs-lookup"><span data-stu-id="9c4cd-108">On the **Services** tab, click **Topic experiences**.</span></span>

    ![Подключение людей к знаниям](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="9c4cd-110">Выберите **вкладку "Обнаружение** темы". Сведения о каждом параметре см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="9c4cd-112">Выбор источников тем SharePoint</span><span class="sxs-lookup"><span data-stu-id="9c4cd-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="9c4cd-113">Вы можете изменить сайты SharePoint в организации, которые будут обходиться по темам.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="9c4cd-114">Если вы хотите включить или исключить определенный список сайтов, можно использовать следующий шаблон CSV:</span><span class="sxs-lookup"><span data-stu-id="9c4cd-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="9c4cd-115">При добавлении сайтов с помощью этого веб-сайта они добавляются в существующий список сайтов, которые необходимо включить или исключить.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="9c4cd-116">При отправке CSV-файла он переоценит любой существующий список.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="9c4cd-117">Если вы ранее включали или исключали определенные сайты, вы загружаете список в CSV-файл, внося изменения и загружая новый список.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="9c4cd-118">Выбор сайтов для обнаружения тем</span><span class="sxs-lookup"><span data-stu-id="9c4cd-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="9c4cd-119">На **вкладке "Обнаружение тем" в** разделе "Выбор источников **темы SharePoint"** выберите "Изменить". </span><span class="sxs-lookup"><span data-stu-id="9c4cd-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="9c4cd-120">На странице **"Выбор источников тем SharePoint"** выберите, какие сайты SharePoint будут обходиться в качестве источников для разделов во время обнаружения.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="9c4cd-121">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="9c4cd-121">This includes:</span></span>
    - <span data-ttu-id="9c4cd-122">**Все сайты**: все сайты SharePoint в клиенте.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="9c4cd-123">В этом случае будут фиксироваться текущие и будущие сайты.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="9c4cd-124">**Все, кроме выбранных сайтов:** введите имена сайтов, которые нужно исключить.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="9c4cd-125">Вы также можете отправить список сайтов, от обнаружения на которые нужно отказаться.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="9c4cd-126">Сайты, созданные в будущем, будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="9c4cd-127">**Только выбранные сайты:** введите имена сайтов, которые нужно включить.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="9c4cd-128">Вы также можете отправить список сайтов.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-128">You can also upload a list of sites.</span></span> <span data-ttu-id="9c4cd-129">Сайты, созданные в будущем, не будут включены в качестве источников для обнаружения тем.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="9c4cd-130">**Нет сайтов:** разделы не будут автоматически созданы или обновлены с контентом SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="9c4cd-131">Существующие темы остаются в центре тем.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-131">Existing topics remain in the topic center.</span></span>

    ![Снимок экрана: пользовательский интерфейс источников тем SharePoint](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="9c4cd-133">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="9c4cd-134">Исключение разделов по имени</span><span class="sxs-lookup"><span data-stu-id="9c4cd-134">Exclude topics by name</span></span>

<span data-ttu-id="9c4cd-135">Вы можете исключить темы из обнаружения, загрузив список с помощью CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="9c4cd-136">Если вы ранее исключили разделы, вы можете скачать CSV-файл, внести изменения и отправить его еще раз.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="9c4cd-137">На **вкладке "Обнаружение тем" в** разделе **"Исключить"** выберите **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="9c4cd-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="9c4cd-138">Щелкните **"Исключить разделы по имени".**</span><span class="sxs-lookup"><span data-stu-id="9c4cd-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="9c4cd-139">Если необходимо создать список, скачайте шаблон CSV и добавьте разделы, которые нужно исключить (см. раздел "Работа с шаблоном *CSV" ниже).*</span><span class="sxs-lookup"><span data-stu-id="9c4cd-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="9c4cd-140">Когда файл будет готов, нажмите **кнопку "Обзор"** и загрузите файл.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="9c4cd-141">Если существует существующий список, вы можете скачать CSV-файл, содержащий этот список.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="9c4cd-142">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-142">Click **Save**.</span></span>

    ![Снимок экрана: пользовательский интерфейс исключаемой темы](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="9c4cd-144">Работа с шаблоном CSV</span><span class="sxs-lookup"><span data-stu-id="9c4cd-144">Working with the .csv template</span></span>

<span data-ttu-id="9c4cd-145">Шаблон CSV можно скопировать ниже:</span><span class="sxs-lookup"><span data-stu-id="9c4cd-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="9c4cd-146">В шаблоне CSV введите следующие сведения о темах, которые необходимо исключить:</span><span class="sxs-lookup"><span data-stu-id="9c4cd-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="9c4cd-147">**Name**: Type the name of the topic you want to exclude.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="9c4cd-148">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="9c4cd-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="9c4cd-149">Точное совпадение: можно включить точное имя или аббревиатуру (например, *Contoso* или *ATL).*</span><span class="sxs-lookup"><span data-stu-id="9c4cd-149">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="9c4cd-150">Частичное совпадение: можно исключить все темы, в них есть определенное слово.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="9c4cd-151">Например,  arc исключит все темы со словом *arc* в нем, такие как "Arc *circle",* *"Arc arc welding"* или *"Training arc".* Обратите внимание, что он не будет исключать темы, в которых текст включается как часть слова, например *"Архитектура".*</span><span class="sxs-lookup"><span data-stu-id="9c4cd-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="9c4cd-152">**Означает (необязательно).** Если вы хотите исключить аббревиатуру, введите слова, за которые стоит аббревиатура.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="9c4cd-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span><span class="sxs-lookup"><span data-stu-id="9c4cd-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![Исключение разделов в шаблоне CSV](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="9c4cd-155">См. также</span><span class="sxs-lookup"><span data-stu-id="9c4cd-155">See also</span></span>

[<span data-ttu-id="9c4cd-156">Управление видимостью тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9c4cd-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="9c4cd-157">Управление разрешениями тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9c4cd-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="9c4cd-158">Изменение имени центра тем в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9c4cd-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
