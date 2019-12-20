---
title: Подготовка данных для Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: 'Узнайте, как использовать центр обеспечения безопасности &amp; Microsoft 365 для подготовки данных Office 365 для анализа с помощью Office 365 Advanced eDiscovery. '
ms.openlocfilehash: 0429c957035068074a571c97cf430b27f9ad5904
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40803826"
---
# <a name="prepare-data-for-office-365-advanced-ediscovery"></a><span data-ttu-id="8cd37-103">Подготовка данных для Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8cd37-103">Prepare data for Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="8cd37-104">В этом разделе описывается, как загружать результаты поиска контента в случае с дополнительным обнаружением электронных данных.</span><span class="sxs-lookup"><span data-stu-id="8cd37-104">This topic describes how to load the results of a Content Search in to a case in Advanced eDiscovery.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8cd37-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="8cd37-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="step-1-prepare-office-365-data-for-advanced-ediscovery"></a><span data-ttu-id="8cd37-107">Шаг 1: подготовка данных Office 365 для расширенного обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="8cd37-107">Step 1: Prepare Office 365 data for Advanced eDiscovery</span></span>

<span data-ttu-id="8cd37-108">Для анализа данных с помощью расширенного обнаружения электронных данных можно использовать результаты поиска контента, который вы используете в &amp; центре безопасности Майкрософт 365 (на странице " **Поиск контента** " в центре безопасности &amp; соответствия требованиям Microsoft 365), или при поиске, связанном с вариантом обнаружения электронных данных, на странице **Обнаружение электронных** данных &amp; в центре безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="8cd37-108">To analyze data with Advanced eDiscovery, you can use the results of a Content Search that you run in the Microsoft 365 Security &amp; Compliance Center (listed on the **Content search** page in the Microsoft 365 Security &amp; Compliance Center) or a search associated with an eDiscovery case (listed on the **eDiscovery** page in the Security &amp; Compliance Center).</span></span> 
  
<span data-ttu-id="8cd37-109">Подробное описание действий по подготовке результатов поиска для анализа в Advanced eDiscovery приведено в статье [Подготовка результатов поиска для Office 365 Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="8cd37-109">For the detailed steps on preparing search results for analysis in Advanced eDiscovery, see [Prepare search results for Office 365 Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8cd37-110">Если у вас есть данные за пределами Office 365 и хотите импортировать их в Office 365, чтобы вы могли подготовить и проанализировать их в Advanced eDiscovery, ознакомьтесь со статьей [Обзор импорта PST-файлов в office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) и [архивации сторонних данных в Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918).</span><span class="sxs-lookup"><span data-stu-id="8cd37-110">If you have data outside of Office 365 and want to import it to Office 365 so that you can prepare and analyze it in Advanced eDiscovery, a see [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) and [Archiving third-party data in Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918).</span></span> 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a><span data-ttu-id="8cd37-111">Шаг 2: Загрузка данных результатов поиска в дело с дополнительным обнаружением электронных данных</span><span class="sxs-lookup"><span data-stu-id="8cd37-111">Step 2: Load search result data in to a case in Advanced eDiscovery</span></span>

<span data-ttu-id="8cd37-112">После подготовки результатов поиска в центре безопасности &amp; и соответствия требованиям для анализа следующий шаг — загрузка результатов поиска в случае Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="8cd37-112">After you prepare the search results in the Security &amp; Compliance Center for analysis, the next step is to load the search results in to a case in Advanced eDiscovery.</span></span> <span data-ttu-id="8cd37-113">Более подробную информацию можно найти в разделе [Run the process Module](run-the-process-module-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="8cd37-113">For more detailed information, see [Run the Process module](run-the-process-module-in-advanced-ediscovery.md).</span></span>
  
1. <span data-ttu-id="8cd37-114">Перейдите по ссылке [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="8cd37-114">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="8cd37-115">Войдите в Office 365 с помощью своей рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="8cd37-115">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="8cd37-116">Чтобы отобразился список дел в организации, в Центре безопасности и соответствия требованиям выберите **Поиск и исследование** \> **Обнаружение электронных данных**.</span><span class="sxs-lookup"><span data-stu-id="8cd37-116">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
4. <span data-ttu-id="8cd37-117">Нажмите кнопку **Открыть** рядом с тем случае, в которое вы хотите загрузить данные в разделе Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="8cd37-117">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
5. <span data-ttu-id="8cd37-118">На странице **Главная** для этого дела выберите **Advanced eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="8cd37-118">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span> 
    
    ![Нажмите кнопку переключения, чтобы открыть Расширенное обнаружение электронных данных, чтобы открыть дело в Advanced eDiscovery](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="8cd37-120">Отображается панель **подключения к расширенному** индикатору выполнения обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="8cd37-120">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="8cd37-121">При подключении к расширенному обнаружению электронных данных список контейнеров отображается на странице Настройка для этого случая.</span><span class="sxs-lookup"><span data-stu-id="8cd37-121">When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![В Advanced eDiscovery отображается обращение](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="8cd37-123">Эти контейнеры представляют результаты поиска, подготовленные для анализа в ходе расширенного обнаружения электронных данных на этапе 1.</span><span class="sxs-lookup"><span data-stu-id="8cd37-123">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1.</span></span> <span data-ttu-id="8cd37-124">Обратите внимание, что имя контейнера имеет то же имя, что и поиск контента, в случае в центре &amp; соответствия требованиям безопасности.</span><span class="sxs-lookup"><span data-stu-id="8cd37-124">Note that the name of the container has the same name as the Content Search in the case in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="8cd37-125">Контейнеры в списке подготовлены.</span><span class="sxs-lookup"><span data-stu-id="8cd37-125">The containers in the list are the ones that you prepared.</span></span> <span data-ttu-id="8cd37-126">Если для расширенного обнаружения электронных данных были подготовлены другие пользовательские результаты поиска, соответствующие контейнеры не будут включены в список.</span><span class="sxs-lookup"><span data-stu-id="8cd37-126">If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
6. <span data-ttu-id="8cd37-127">Чтобы загрузить данные результатов поиска из контейнера в дело с дополнительным обнаружением электронных данных, выберите контейнер и нажмите кнопку **обработать**.</span><span class="sxs-lookup"><span data-stu-id="8cd37-127">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
<span data-ttu-id="8cd37-128">После добавления результатов поиска из центра безопасности &amp; и соответствия требованиям в Advanced eDiscovery, следующим шагом является использование средств расширенного обнаружения электронных данных для анализа и отбора данных, релевантных для случая.</span><span class="sxs-lookup"><span data-stu-id="8cd37-128">After the search results from the Security &amp; Compliance Center are added to the case in Advanced eDiscovery, the next step is to use the tools in Advanced eDiscovery to analyze and cull the data that's relevant to the case.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8cd37-129">См. также</span><span class="sxs-lookup"><span data-stu-id="8cd37-129">See also</span></span>

[<span data-ttu-id="8cd37-130">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8cd37-130">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="8cd37-131">Настройка пользователей и обращений</span><span class="sxs-lookup"><span data-stu-id="8cd37-131">Set up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8cd37-132">Анализ данных дела</span><span class="sxs-lookup"><span data-stu-id="8cd37-132">Analyzing case data</span></span>](analyze-case-data-with-advanced-ediscovery.md)
  
[<span data-ttu-id="8cd37-133">Управление установкой релевантности</span><span class="sxs-lookup"><span data-stu-id="8cd37-133">Managing Relevance setup</span></span>](manage-relevance-setup-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8cd37-134">Использование модуля релевантности</span><span class="sxs-lookup"><span data-stu-id="8cd37-134">Using the Relevance module</span></span>](use-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8cd37-135">Экспорт данных дела</span><span class="sxs-lookup"><span data-stu-id="8cd37-135">Exporting case data</span></span>](export-case-data-in-advanced-ediscovery.md)

