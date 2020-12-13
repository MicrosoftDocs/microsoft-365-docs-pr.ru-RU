---
title: Настройка нагрузок для добавления импортируемых файлов в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: Перед выполнением обучения релевантности в Advanced eDiscovery просмотрите действия по добавлению импортируемых файлов к последней определенной загрузке или пакету файлов.
ms.openlocfilehash: 7cd244ba1ba516c2b7376b71e809b4c01ff5df8b
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663484"
---
# <a name="set-up-loads-to-add-imported-files-in-advanced-ediscovery-classic"></a><span data-ttu-id="cc47d-103">Настройка нагрузок для добавления импортируемых файлов в Advanced eDiscovery (классическая)</span><span class="sxs-lookup"><span data-stu-id="cc47d-103">Set up loads to add imported files in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="cc47d-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="cc47d-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="cc47d-106">В Advanced eDiscovery нагрузка — это новый пакет файлов, добавленный в дело.</span><span class="sxs-lookup"><span data-stu-id="cc47d-106">In Advanced eDiscovery, a load is a new batch of files added to a case.</span></span> <span data-ttu-id="cc47d-107">По умолчанию определяется одна нагрузка, в нее добавляются все импортируемые файлы.</span><span class="sxs-lookup"><span data-stu-id="cc47d-107">By default, one load is defined and all imported files are added to it.</span></span> <span data-ttu-id="cc47d-108">Перед выполнением обучения релевантности импортируемые файлы необходимо добавить в нагрузку.</span><span class="sxs-lookup"><span data-stu-id="cc47d-108">Before performing Relevance training, imported files must be added to the load.</span></span> 
  
<span data-ttu-id="cc47d-109">Рассмотрим следующие сценарии:</span><span class="sxs-lookup"><span data-stu-id="cc47d-109">Consider the following scenarios:</span></span>
  
- <span data-ttu-id="cc47d-110">Известно, что новые файлы похожи на предыдущие файлы, загруженные в базу данных дел, или предыдущая загрузка файлов была случайным набором из коллекции файлов.</span><span class="sxs-lookup"><span data-stu-id="cc47d-110">New files are known to be similar to the previous files loaded to the case database, or the previous load of files was a random set from the file collection.</span></span> <span data-ttu-id="cc47d-111">В этом случае добавьте импортируемые файлы в текущую загрузку файлов.</span><span class="sxs-lookup"><span data-stu-id="cc47d-111">In this instance, add the imported files to the current file load.</span></span>
    
- <span data-ttu-id="cc47d-112">Новые файлы отличаются от предыдущих (например, из другого источника) или вы не знаете, что они похожи или отличаются от предыдущих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="cc47d-112">New files are different from previous ones (for example, from a different source), or you have no prior knowledge that they're similar or different to the previous loads.</span></span> <span data-ttu-id="cc47d-113">В этом сценарии добавьте импортируемые файлы в новую загрузку файлов.</span><span class="sxs-lookup"><span data-stu-id="cc47d-113">In this scenario, add the imported files to a new file load.</span></span> <span data-ttu-id="cc47d-114">Advanced eDiscovery распознает этот сценарий как сценарий покатиной загрузки, вызывает дополнительный процесс, блокирует обучение релевантности и пакетные вычисления, пока не завершится перезапись, а новая нагрузка будет интегрирована и обучена.</span><span class="sxs-lookup"><span data-stu-id="cc47d-114">Advanced eDiscovery recognizes this as a Rolling loads scenario, invokes a Catch-up process, locks Relevance training and Batch calculations until Catch-up is completed, and the new load is integrated and trained.</span></span> 
    
## <a name="adding-imported-files-to-the-current-load"></a><span data-ttu-id="cc47d-115">Добавление импортируемых файлов в текущую нагрузку</span><span class="sxs-lookup"><span data-stu-id="cc47d-115">Adding imported files to the current load</span></span>

<span data-ttu-id="cc47d-116">Все импортируемые файлы необходимо добавить в нагрузку для обработки в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="cc47d-116">All imported files must be added to a load to be processed in Advanced eDiscovery.</span></span> <span data-ttu-id="cc47d-117">Импортируемые файлы добавляются к последней определенной нагрузке.</span><span class="sxs-lookup"><span data-stu-id="cc47d-117">Imported files are added to the last defined load.</span></span> <span data-ttu-id="cc47d-118">Если вы импортируете дополнительные файлы позже, они также должны быть добавлены в нагрузку.</span><span class="sxs-lookup"><span data-stu-id="cc47d-118">If you import additional files later, they also must be added to the load.</span></span>
  
1. <span data-ttu-id="cc47d-119">На **вкладке \> "Релевантность" выберите** **"Загрузки".**</span><span class="sxs-lookup"><span data-stu-id="cc47d-119">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
    ![Элемент "Операции загрузки" на вкладке "Настройка релевантности"](../media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. <span data-ttu-id="cc47d-121">**Включаем файлы:** выберите параметр для включаемого файла.</span><span class="sxs-lookup"><span data-stu-id="cc47d-121">**Include files**: Select an option for files to include.</span></span> <span data-ttu-id="cc47d-122">По умолчанию добавление файлов в текущую нагрузку основано на "Всех файлах".</span><span class="sxs-lookup"><span data-stu-id="cc47d-122">By default, adding files to the current load is based on the "All files" population.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="cc47d-123">Загрузка всех доступных кэшных файлов в релевантность.</span><span class="sxs-lookup"><span data-stu-id="cc47d-123">Load all available culled files into Relevance.</span></span> <span data-ttu-id="cc47d-124">Если вы планируете загрузить только часть доступных файлов, сначала обратитесь в службу поддержки, так как загрузка подмножество может отрицательно повлиять на обучение релевантности.</span><span class="sxs-lookup"><span data-stu-id="cc47d-124">If you plan to load only a subset of the available files, please first consult with Support, as loading subsets can adversely affect Relevance training.</span></span> 
  
3. <span data-ttu-id="cc47d-125">В **управлении загрузками** выберите нагрузку.</span><span class="sxs-lookup"><span data-stu-id="cc47d-125">In **Loads management**, select a load.</span></span>
    
4. <span data-ttu-id="cc47d-126">Нажмите **кнопку "Добавить файлы".**</span><span class="sxs-lookup"><span data-stu-id="cc47d-126">Click **Add files**.</span></span> <span data-ttu-id="cc47d-127">Файлы добавляются в загрузку, и отображается сообщение с подтверждением.</span><span class="sxs-lookup"><span data-stu-id="cc47d-127">The files are added to the load and a confirmation message is displayed.</span></span> 
    
5. <span data-ttu-id="cc47d-128">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cc47d-128">Click **OK**.</span></span>
    
<span data-ttu-id="cc47d-129">Теперь файлы можно обработать в релевантности Advanced eDiscovery для обучения файлам.</span><span class="sxs-lookup"><span data-stu-id="cc47d-129">The files can now be processed in Advanced eDiscovery Relevance for training the files.</span></span>
  
## <a name="editing-a-load-name-within-a-case"></a><span data-ttu-id="cc47d-130">Изменение имени загрузки в рамках дела</span><span class="sxs-lookup"><span data-stu-id="cc47d-130">Editing a load name within a case</span></span>

<span data-ttu-id="cc47d-131">При изменении имени загрузки рекомендуется использовать важное для дела имя.</span><span class="sxs-lookup"><span data-stu-id="cc47d-131">If changing the load name, it is recommended to use a name that is significant to the case.</span></span>
  
1. <span data-ttu-id="cc47d-132">На **вкладке \> "Релевантность" выберите** **"Загрузки".**</span><span class="sxs-lookup"><span data-stu-id="cc47d-132">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="cc47d-133">В **списке управления загрузками** выберите загрузку и щелкните значок **редактирования.**</span><span class="sxs-lookup"><span data-stu-id="cc47d-133">From the **Loads management** list, select a load and click the **Edit** icon.</span></span> <span data-ttu-id="cc47d-134">Отобразилось окно "Изменить загрузку".</span><span class="sxs-lookup"><span data-stu-id="cc47d-134">The Edit load window is displayed.</span></span> 
    
3. <span data-ttu-id="cc47d-135">Введите изменения и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="cc47d-135">Enter the changes, and then click **OK**.</span></span>
    
## <a name="adding-imported-files-to-a-new-load"></a><span data-ttu-id="cc47d-136">Добавление импортируемых файлов в новую нагрузку</span><span class="sxs-lookup"><span data-stu-id="cc47d-136">Adding imported files to a new load</span></span>

<span data-ttu-id="cc47d-137">После начала обучения релевантности или выполнения пакетного вычисления можно импортировать и обработать дополнительный набор файлов.</span><span class="sxs-lookup"><span data-stu-id="cc47d-137">After starting Relevance training or performing Batch calculation, you may want to import and process an additional set of files.</span></span> 
  
<span data-ttu-id="cc47d-138">Во время перебора можно создать, пометить и проанализировать набор дополнительных данных.</span><span class="sxs-lookup"><span data-stu-id="cc47d-138">During Catch-up, you can create, tag, and analyze the Catch-up set.</span></span> <span data-ttu-id="cc47d-139">Advanced eDiscovery сравнивает оценку релевантных и не релевантных файлов в новой нагрузке с предыдущими нагрузками.</span><span class="sxs-lookup"><span data-stu-id="cc47d-139">Advanced eDiscovery compares its assessment of Relevant and Non-Relevant files in the new load to those in previous loads.</span></span> <span data-ttu-id="cc47d-140">На основе результатов вам будет предложено принять дополнительные решения, если это необходимо, и Advanced eDiscovery предоставляет рекомендации на основе полученных сведений об релевантности.</span><span class="sxs-lookup"><span data-stu-id="cc47d-140">Based on the results, you are prompted to make Catch-up decisions, if necessary, and Advanced eDiscovery provides recommendations based on the accrued Relevance information.</span></span> 
  
<span data-ttu-id="cc47d-141">Функции подвижных загрузок и перезагрузок различаются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cc47d-141">Rolling Loads and Catch-up functionality varies as follows:</span></span> 
  
- <span data-ttu-id="cc47d-142">При импорте новой нагрузки файла после вычисления Batch Advanced eDiscovery определяет, в какой степени файлы попадают в одну из следующих категорий:</span><span class="sxs-lookup"><span data-stu-id="cc47d-142">When you import a new file load after Batch calculation, Advanced eDiscovery determines to what extent the files fall into one of the following categories:</span></span>
    
  - <span data-ttu-id="cc47d-143">Аналогичный (однородный): новый настраиваемый круг обучения релевантности не требуется, и знания, накопимые из предыдущей нагрузки, можно применять "как есть" к новой нагрузке.</span><span class="sxs-lookup"><span data-stu-id="cc47d-143">Similar (homogeneous): A new, custom round of Relevance training is not required and the knowledge accrued from the previous load can be applied "as is" to the new load.</span></span> 
    
  - <span data-ttu-id="cc47d-144">Отдельный (разнородный): требуется новый настраиваемый круг обучения релевантности, а знания, накопимые в результате предыдущей нагрузки, не могут применяться.</span><span class="sxs-lookup"><span data-stu-id="cc47d-144">Distinct (heterogeneous): A new, custom round of Relevance training is required, and the knowledge accrued from the previous load cannot be applied.</span></span> 
    
    <span data-ttu-id="cc47d-145">Эти термины относятся к уровню сходства файлов между нагрузками, а не внутри них.</span><span class="sxs-lookup"><span data-stu-id="cc47d-145">These terms refer to the level of similarity of files between loads and not within the loads.</span></span> 
    
- <span data-ttu-id="cc47d-146">При импорте новой нагрузки файла во время обучения релевантности (перед пакетным вычислением) вы можете продолжить обучение релевантности в объединенном наборе файлов.</span><span class="sxs-lookup"><span data-stu-id="cc47d-146">When importing a new file load during Relevance training (before Batch calculation), Catch-up enables you to continue Relevance training on the united file set.</span></span> <span data-ttu-id="cc47d-147">Advanced eDiscovery не оценивает, похожа ли новая нагрузка на предыдущую нагрузку или отличается от нее.</span><span class="sxs-lookup"><span data-stu-id="cc47d-147">Advanced eDiscovery does not estimate whether the new load is similar to or distinct from the previous load.</span></span> <span data-ttu-id="cc47d-148">Он просто собирает сведения о новой нагрузке и позволяет продолжить обучение релевантности для новых и предыдущих наборов файлов.</span><span class="sxs-lookup"><span data-stu-id="cc47d-148">It simply collects information about the new load and enables Relevance training to continue on the new and previous sets of files.</span></span> 
    
- <span data-ttu-id="cc47d-149">Если при обучении релевантности имеется несколько проблем, а также проблемы после пакетного вычисления, процесс перенаверки выполняется один раз для всех проблем, а результаты вычисляются и отображаются для каждой проблемы.</span><span class="sxs-lookup"><span data-stu-id="cc47d-149">When there are multiple issues in Relevance training as well as issues after Batch calculation, the Catch-up process is performed once for all issues, and the results are calculated and displayed for each issue.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cc47d-150">Размер примера catch-up может отличаться.</span><span class="sxs-lookup"><span data-stu-id="cc47d-150">The size of the Catch-up sample may vary.</span></span> <span data-ttu-id="cc47d-151">Он зависит от размера новой нагрузки относительно предыдущих нагрузок и от количества образцов, завершенных перед добавлением новой нагрузки.</span><span class="sxs-lookup"><span data-stu-id="cc47d-151">It depends on the size of the new load relative to the previous loads, and on the number of samples completed before adding the new load.</span></span> <span data-ttu-id="cc47d-152">В этом примере обычно используется набор из 200–2000 файлов из новой нагрузки.</span><span class="sxs-lookup"><span data-stu-id="cc47d-152">The Catch-up sample is typically a set of 200 to 2,000 files from the new load.</span></span> 
  
> [!TIP]
> <span data-ttu-id="cc47d-153">Дополнительные материалы останавливают любые другие задачи и требуют отдельного тега и проверки файлов.</span><span class="sxs-lookup"><span data-stu-id="cc47d-153">Catch-up stops any other tasks and requires individual file tagging and review.</span></span> <span data-ttu-id="cc47d-154">Таким образом, при добавлении новых файлов в большие пакеты можно снизить затраты.</span><span class="sxs-lookup"><span data-stu-id="cc47d-154">Therefore, you can reduce overhead when you add new files in large batches.</span></span> 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a><span data-ttu-id="cc47d-155">Добавление новой загрузки файла с помощью дополнительных и покатных нагрузок</span><span class="sxs-lookup"><span data-stu-id="cc47d-155">Adding a new file load using Catch-up and Rolling loads</span></span>

1. <span data-ttu-id="cc47d-156">На **вкладке \> "Релевантность" выберите** **"Загрузки".**</span><span class="sxs-lookup"><span data-stu-id="cc47d-156">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="cc47d-157">В **области управления загрузками** щелкните **+** значок, чтобы добавить нагрузку.</span><span class="sxs-lookup"><span data-stu-id="cc47d-157">Under **Loads management**, click the **+** icon to add a load.</span></span> <span data-ttu-id="cc47d-158">Отобразилось сообщение с подтверждением.</span><span class="sxs-lookup"><span data-stu-id="cc47d-158">A confirmation message is displayed.</span></span> 
    
3. <span data-ttu-id="cc47d-159">Чтобы продолжить, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="cc47d-159">Click **Yes** to continue.</span></span> <span data-ttu-id="cc47d-160">**Отобразилось** диалоговое окно "Добавление новой нагрузки".</span><span class="sxs-lookup"><span data-stu-id="cc47d-160">The **Add new load** dialog is displayed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="cc47d-161">Новую нагрузку можно добавить только в том случае, если были выполнены действия с предыдущей нагрузкой.</span><span class="sxs-lookup"><span data-stu-id="cc47d-161">You can only add a new load if actions were performed to the previous load.</span></span> 
  
4. <span data-ttu-id="cc47d-162">В **диалоговом окте "Добавление новой** нагрузки" введите сведения в имя загрузки и **описание,** а затем нажмите кнопку **"ОК".** </span><span class="sxs-lookup"><span data-stu-id="cc47d-162">In the **Add new load** dialog, type information in **Load name** and **Description** and then click **OK**.</span></span> <span data-ttu-id="cc47d-163">Advanced eDiscovery добавляет новую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="cc47d-163">Advanced eDiscovery adds a new load.</span></span>
    
5. <span data-ttu-id="cc47d-164">Чтобы импортировать новый файл загрузки, нажмите кнопку **"Добавить файлы".**</span><span class="sxs-lookup"><span data-stu-id="cc47d-164">To import the new load file, click **Add files**.</span></span> <span data-ttu-id="cc47d-165">Все новые файлы добавляются в эту нагрузку.</span><span class="sxs-lookup"><span data-stu-id="cc47d-165">All new files are added to this load.</span></span> <span data-ttu-id="cc47d-166">После того как Advanced eDiscovery импортирует файлы, оно распознает сценарий rolling loads и указывает на дополнительные данные в качестве следующего шага.</span><span class="sxs-lookup"><span data-stu-id="cc47d-166">After Advanced eDiscovery imports the files, it recognizes the Rolling loads scenario and indicates Catch-up as the next step.</span></span>
    
6. <span data-ttu-id="cc47d-167">Щелкните **"Catch-up"** в нижней части диалога, чтобы запустить сценарий.</span><span class="sxs-lookup"><span data-stu-id="cc47d-167">Click **Catch-up** at the bottom of the dialog to run the scenario.</span></span> 
    
    <span data-ttu-id="cc47d-168">Для всех проблем создается один набор catch-up, обычно содержащий от 200 до 2000 файлов из новой нагрузки, чтобы разрешить одновременное добавление тегов файлов.</span><span class="sxs-lookup"><span data-stu-id="cc47d-168">A single Catch-up set, typically containing 200 to 2,000 files from the new load, is created for all issues to allow concurrent file tagging.</span></span>
    
    <span data-ttu-id="cc47d-169">Предоставляются подробные сведения о том, похожи ли нагрузки или они отличаются, объединяются ли advanced eDiscovery автоматически или разбиваются нагрузки, а также сведения об обработке на следующем этапе.</span><span class="sxs-lookup"><span data-stu-id="cc47d-169">Details are provided about whether loads are similar or distinct, whether Advanced eDiscovery merged or split the loads automatically, and information regarding processing in the next step.</span></span>
    
    <span data-ttu-id="cc47d-170">После этого можно пометить файлы и выполнить операцию вычисления.</span><span class="sxs-lookup"><span data-stu-id="cc47d-170">You can then tag files and run a calculate operation.</span></span> <span data-ttu-id="cc47d-171">Теги позволяют релевантности определить, похожи ли нагрузки или отличаются, и позволяет продолжить работу над новым набором файлов.</span><span class="sxs-lookup"><span data-stu-id="cc47d-171">The tagging enables Relevance to determine if loads are similar or distinct and enables you to continue working on the new set of files.</span></span>
    
7. <span data-ttu-id="cc47d-172">После проверки набора catch-up просмотрите **отслеживание \>** релевантности для результатов.</span><span class="sxs-lookup"><span data-stu-id="cc47d-172">After the Catch-up set is reviewed, view **Relevance \> Track** for the Catch-up results.</span></span> 
    
1. <span data-ttu-id="cc47d-173">Если новая нагрузка на файл была добавлена во время обучения релевантности (то есть проблема еще не прошла пакетных **вычислений),** продолжение обучения — это следующий шаг независимо от результатов.</span><span class="sxs-lookup"><span data-stu-id="cc47d-173">If the new file load was added during Relevance training (meaning, the issue has not yet gone through Batch calculation), **Continue training** is the next step, regardless of the Catch-up results.</span></span> 
    
    <span data-ttu-id="cc47d-174">Новые и предыдущие нагрузки обрабатываются как одна нагрузка, а обучение релевантности продолжается в объединенном наборе.</span><span class="sxs-lookup"><span data-stu-id="cc47d-174">The new and previous loads are processed as one load and Relevance training continues on the united set.</span></span> <span data-ttu-id="cc47d-175">Теперь вы завершили эту процедуру и можете продолжить обучение релевантности.</span><span class="sxs-lookup"><span data-stu-id="cc47d-175">You are now finished with this procedure and can continue Relevance training.</span></span> 
    
2. <span data-ttu-id="cc47d-176">Если новая нагрузка была добавлена после вычисления пакета, переходите к следующим шагам.</span><span class="sxs-lookup"><span data-stu-id="cc47d-176">If the new load was added after Batch calculation, proceed to the following steps.</span></span>
    
8. <span data-ttu-id="cc47d-177">Для новых нагрузок, добавленных после пакетного вычисления, Advanced eDiscovery определяет, похожа ли новая нагрузка на предыдущие нагрузки или отличается от нее следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cc47d-177">For new loads added after Batch calculation, Advanced eDiscovery determines if the new load is similar to or distinct from previous loads, as follows:</span></span>
    
1. <span data-ttu-id="cc47d-178">Если было обнаружено, что нагрузки похожи: нет необходимости в дополнительном обучении релевантности.</span><span class="sxs-lookup"><span data-stu-id="cc47d-178">If loads were found to be similar: No additional Relevance training is necessary.</span></span> <span data-ttu-id="cc47d-179">The dashboard shows the recommended next step is to run \*\* Batch calculation \*\* again to calculate Relevance scores for the new load.</span><span class="sxs-lookup"><span data-stu-id="cc47d-179">The dashboard shows the recommended next step is to run \*\* Batch calculation \*\* again to calculate Relevance scores for the new load.</span></span> <span data-ttu-id="cc47d-180">Загрузки оказалось похожими, поэтому предыдущий анализ классификаторов можно выполнить в новых файлах.</span><span class="sxs-lookup"><span data-stu-id="cc47d-180">Loads were found to be similar, so the previous classifier analysis can be run on the new files.</span></span> 
    
2. <span data-ttu-id="cc47d-181">Если было обнаружено, что нагрузки отличаются: требуется дополнительный курс обучения релевантности, и следующим шагом является принятие более подробного решения.</span><span class="sxs-lookup"><span data-stu-id="cc47d-181">If loads were found to be distinct: More Relevance training is necessary and the next step is Catch-up decision.</span></span> <span data-ttu-id="cc47d-182">Выберите более тщательное решение следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cc47d-182">Select a Catch-up decision as follows:</span></span>
    
    <span data-ttu-id="cc47d-183">Если выбрать **"Объединить нагрузки",** Advanced eDiscovery объединяет предыдущие и новые нагрузки для обучающего набора.</span><span class="sxs-lookup"><span data-stu-id="cc47d-183">If you select **Merge loads**, Advanced eDiscovery merges previous and new loads for the training set.</span></span> <span data-ttu-id="cc47d-184">Хотя первая нагрузка прошла через пакетное вычисление, требуется больше обучения.</span><span class="sxs-lookup"><span data-stu-id="cc47d-184">Although the first load went through Batch calculation, more training is needed.</span></span> <span data-ttu-id="cc47d-185">Продолжайте обучение новым и предыдущим нагрузкам вместе.</span><span class="sxs-lookup"><span data-stu-id="cc47d-185">Continue training new and previous loads together.</span></span> <span data-ttu-id="cc47d-186">Затем пакетное вычисление будет запускаться снова, и предыдущие оценки пакетных вычислений должны быть проигнорированы.</span><span class="sxs-lookup"><span data-stu-id="cc47d-186">Batch calculation will then run again and the previous Batch calculation scores should be ignored.</span></span> <span data-ttu-id="cc47d-187">Выберите этот вариант, если можно пересчитать оценки релевантности для существующих нагрузок, например, если проверка существующих загрузок файлов не началась.</span><span class="sxs-lookup"><span data-stu-id="cc47d-187">Choose this selection when Relevance scores for existing loads can be recalculated, for example, when review of existing file loads has not started.</span></span>
    
    <span data-ttu-id="cc47d-188">Если выбрать разделение **нагрузок,** продолжайте обучение релевантности только при новой нагрузке.</span><span class="sxs-lookup"><span data-stu-id="cc47d-188">If you select **Split loads**, continue Relevance training only on the new load.</span></span> <span data-ttu-id="cc47d-189">В этом случае предыдущие оценки пакетных вычислений останутся прежними.</span><span class="sxs-lookup"><span data-stu-id="cc47d-189">In this instance, previous Batch calculation scores will remain as is.</span></span> <span data-ttu-id="cc47d-190">Выберите этот параметр, если существующие оценки релевантности для существующих нагрузок не могут быть пересчитаны, например, если проверка существующих нагрузок уже запущена.</span><span class="sxs-lookup"><span data-stu-id="cc47d-190">Choose this option when existing Relevance scores for existing loads cannot be recalculated, for example, if review of existing loads has already started.</span></span> <span data-ttu-id="cc47d-191">Оценки релевантности управляются отдельно от этой точки и не могут быть объединены.</span><span class="sxs-lookup"><span data-stu-id="cc47d-191">Relevance scores are managed separately from this point onward and cannot be merged.</span></span>
    
3. <span data-ttu-id="cc47d-192">Щелкните **"Продолжить обучение".**</span><span class="sxs-lookup"><span data-stu-id="cc47d-192">Click **Continue training**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cc47d-193">См. также</span><span class="sxs-lookup"><span data-stu-id="cc47d-193">See also</span></span>

[<span data-ttu-id="cc47d-194">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="cc47d-194">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="cc47d-195">Определение вопросов и назначение пользователей</span><span class="sxs-lookup"><span data-stu-id="cc47d-195">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="cc47d-196">Определение выделенных ключевых слов и дополнительных параметров</span><span class="sxs-lookup"><span data-stu-id="cc47d-196">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

