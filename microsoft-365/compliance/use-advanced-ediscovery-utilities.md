---
title: Использование расширенных средств обнаружения электронных данных в Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: 'Сведения о служебных программах в Office 365 Advanced eDiscovery, включая журнал обращений, очистку данных, ошибки процессов, изменение релевантности и анализ прозрачности.  '
ms.openlocfilehash: df769ddddd37284da50bc715444f2bf928307706
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090657"
---
# <a name="use-office-365-advanced-ediscovery-utilities"></a><span data-ttu-id="f7284-103">Использование расширенных средств обнаружения электронных данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="f7284-103">Use Office 365 Advanced eDiscovery utilities</span></span>

> [!NOTE]
> <span data-ttu-id="f7284-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="f7284-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="f7284-106">Служебные программы, которые отображаются и доступны в Advanced eDiscovery, зависят от контекста и ролей пользователей.</span><span class="sxs-lookup"><span data-stu-id="f7284-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="f7284-107">Журнал обращений</span><span class="sxs-lookup"><span data-stu-id="f7284-107">Case log</span></span>

<span data-ttu-id="f7284-108">Журнал обращений содержит подробный список действий по обработке приложений, которые можно использовать для отслеживания, устранения неполадок и устранения ошибок и предупреждений.</span><span class="sxs-lookup"><span data-stu-id="f7284-108">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings.</span></span> <span data-ttu-id="f7284-109">Журнал может создаваться и храниться локально на узле или сервере или напрямую по адресу электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f7284-109">The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="f7284-110">Файл журнала также можно загрузить на компьютер клиента.</span><span class="sxs-lookup"><span data-stu-id="f7284-110">The log file can also be downloaded to the client's computer.</span></span> <span data-ttu-id="f7284-111">Функцию загрузки клиента можно включить или отключить в соответствии с конфигурацией и ролью пользователя.</span><span class="sxs-lookup"><span data-stu-id="f7284-111">The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="f7284-112">В строке меню щелкните значок **шестеренки** .</span><span class="sxs-lookup"><span data-stu-id="f7284-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="f7284-113">На вкладке **Служебные программы \> "Параметры и служебные** программы" выберите пункт **Настройка \> журнала обращений**.</span><span class="sxs-lookup"><span data-stu-id="f7284-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="f7284-114">Выберите **уровень ведения журнала** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f7284-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="f7284-115">**Standard**: включает основные данные журнала.</span><span class="sxs-lookup"><span data-stu-id="f7284-115">**Standard**: Includes the basic log data.</span></span> <span data-ttu-id="f7284-116">Этот параметр обычно необходим для мониторинга и должен использоваться, если не рекомендуется иное.</span><span class="sxs-lookup"><span data-stu-id="f7284-116">This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="f7284-117">**Минимум**: используется для очень больших случаев и возвращает только последние данные.</span><span class="sxs-lookup"><span data-stu-id="f7284-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="f7284-118">Щелкните пункт **Запуск журнала обращений**.</span><span class="sxs-lookup"><span data-stu-id="f7284-118">Click **Run Case log**.</span></span> <span data-ttu-id="f7284-119">Создается журнал и отображается путь.</span><span class="sxs-lookup"><span data-stu-id="f7284-119">The log is generated and path is displayed.</span></span> <span data-ttu-id="f7284-120">Сведения о ходе выполнения задачи для текущей и последней задачи отображаются в области состояния задачи.</span><span class="sxs-lookup"><span data-stu-id="f7284-120">The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="f7284-121">Очистка данных</span><span class="sxs-lookup"><span data-stu-id="f7284-121">Clear data</span></span>

<span data-ttu-id="f7284-122">Если необходимо удалить или повторно инициализировать данные Case, необходимо инициализировать экземпляр базы данных.</span><span class="sxs-lookup"><span data-stu-id="f7284-122">If it is necessary to delete or reinitialize case data, the database instance must be initialized.</span></span> <span data-ttu-id="f7284-123">Служебная программа очистки данных удаляет все указанные записи из базы данных, текстовых файлов, папки обращений и накопленных результатов.</span><span class="sxs-lookup"><span data-stu-id="f7284-123">The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results.</span></span> <span data-ttu-id="f7284-124">Эта функция может выполняться только администратором.</span><span class="sxs-lookup"><span data-stu-id="f7284-124">The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f7284-125">Это действие не является обратимым и будет очищать все разметку и анализ релевантности, выполняемые экспертом.</span><span class="sxs-lookup"><span data-stu-id="f7284-125">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert.</span></span> <span data-ttu-id="f7284-126">При необходимости сохраните резервную копию данных.</span><span class="sxs-lookup"><span data-stu-id="f7284-126">Save a backup of data, if necessary.</span></span> <span data-ttu-id="f7284-127">Используйте этот параметр с особой осторожностью.</span><span class="sxs-lookup"><span data-stu-id="f7284-127">Use this option with extreme care.</span></span> <span data-ttu-id="f7284-128">Удаление помеченных и ранжированных файлов может повлиять на результаты релевантности.</span><span class="sxs-lookup"><span data-stu-id="f7284-128">Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="f7284-129">В строке меню щелкните значок **шестеренки** .</span><span class="sxs-lookup"><span data-stu-id="f7284-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="f7284-130">На вкладке " **Параметры и \> служебные программы** " выберите пункт \*\*очистить настройку данных \> \*\*.</span><span class="sxs-lookup"><span data-stu-id="f7284-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="f7284-131">Выберите параметр для инициализации сведений:</span><span class="sxs-lookup"><span data-stu-id="f7284-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="f7284-132">**Релевантность**: удаляет все действия, выполняемые по релевантности, в том числе определение нагрузок и связей файлов для загрузки.</span><span class="sxs-lookup"><span data-stu-id="f7284-132">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads.</span></span> <span data-ttu-id="f7284-133">Он удаляет все примеры и разметки.</span><span class="sxs-lookup"><span data-stu-id="f7284-133">It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="f7284-134">**Почти повторяющиеся и почтовые потоки**: удаляет все данные анализа практических дубликатов и почтовых потоков.</span><span class="sxs-lookup"><span data-stu-id="f7284-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="f7284-135">**Темы**: удаляются связанные с темами данные.</span><span class="sxs-lookup"><span data-stu-id="f7284-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="f7284-136">**Export History**: удаляет историю сведений о пакетах экспорта.</span><span class="sxs-lookup"><span data-stu-id="f7284-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="f7284-137">Нажмите кнопку **Очистить данные**.</span><span class="sxs-lookup"><span data-stu-id="f7284-137">Click **Clear data**.</span></span> <span data-ttu-id="f7284-138">Данные Case очищаются.</span><span class="sxs-lookup"><span data-stu-id="f7284-138">The case data is cleared.</span></span> <span data-ttu-id="f7284-139">Сведения о ходе выполнения задачи для текущей и последней задачи отображаются в области **состояния задачи** .</span><span class="sxs-lookup"><span data-stu-id="f7284-139">The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="f7284-140">Изменение релевантности</span><span class="sxs-lookup"><span data-stu-id="f7284-140">Modify Relevance</span></span>

<span data-ttu-id="f7284-141">В этом разделе описывается, как пропустить или откатить пример релевантности.</span><span class="sxs-lookup"><span data-stu-id="f7284-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="f7284-142">В строке меню щелкните значок **шестеренки** .</span><span class="sxs-lookup"><span data-stu-id="f7284-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="f7284-143">На вкладке **Служебные программы \> параметры и служебные** программы выберите **изменить релевантность**.</span><span class="sxs-lookup"><span data-stu-id="f7284-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="f7284-144">Выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f7284-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="f7284-145">**Пропуск текущего примера — для текущего пользователя**: Этот тег будет помечен как **пропуск**всех файлов без тегов в образце Open Case пользователя, запустившего эту программу.</span><span class="sxs-lookup"><span data-stu-id="f7284-145">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility.</span></span> <span data-ttu-id="f7284-146">Обработка релевантности не будет выполняться для файлов с пометкой " **пропустить**".</span><span class="sxs-lookup"><span data-stu-id="f7284-146">Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="f7284-147">**Пропуск текущего примера — все открытые примеры**: Этот тег будет помечен как **пропуск**всех файлов без тегов во всех открытых примерах для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="f7284-147">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users.</span></span> <span data-ttu-id="f7284-148">Этот параметр не рекомендуется использовать, если пользователи в данный момент являются примерами тегов.</span><span class="sxs-lookup"><span data-stu-id="f7284-148">This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="f7284-149">**Предыдущий пример**: последний выполненный образец учебного захода будет откатить, независимо от того, находится ли он перед или после "вычисления".</span><span class="sxs-lookup"><span data-stu-id="f7284-149">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process.</span></span> <span data-ttu-id="f7284-150">Откат образца не разрешен.</span><span class="sxs-lookup"><span data-stu-id="f7284-150">Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="f7284-151">Нажмите кнопку **выполнить** для запуска.</span><span class="sxs-lookup"><span data-stu-id="f7284-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="f7284-152">Анализ прозрачности</span><span class="sxs-lookup"><span data-stu-id="f7284-152">Transparency analysis</span></span>

<span data-ttu-id="f7284-153">Средство анализа прозрачности позволяет получить подробные сведения о файлах и их назначенном показателе релевантности.</span><span class="sxs-lookup"><span data-stu-id="f7284-153">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score.</span></span> <span data-ttu-id="f7284-154">Этот отчет можно использовать в качестве проверки санити или для сравнения релевантности файла, определенного человеком, в сравнении с отношением, назначенному расширенному обнаружению электронных данных.</span><span class="sxs-lookup"><span data-stu-id="f7284-154">The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="f7284-155">В дополнение к оценкам релевантности, Расширенное обнаружение электронных данных вычисляет и назначает ключевое слово веса, которое учитывает контекст ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="f7284-155">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context.</span></span> <span data-ttu-id="f7284-156">Одному и тому же слову в файле можно присвоить различные веса в зависимости от контекста и местоположения.</span><span class="sxs-lookup"><span data-stu-id="f7284-156">The same word in a file can be assigned different weights, depending on context and location.</span></span> <span data-ttu-id="f7284-157">Каждое ключевое слово помечается с использованием увеличенного масштаба цвета в диапазоне от желтого до темно-оранжевого и различные оттенки серого.</span><span class="sxs-lookup"><span data-stu-id="f7284-157">Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray.</span></span> <span data-ttu-id="f7284-158">Цветовая кодировка используется для визуального обозначения относительного положительного или отрицательного вклада слова в показатель релевантности.</span><span class="sxs-lookup"><span data-stu-id="f7284-158">Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="f7284-159">В сценарии с несколькими проблемами для каждой из них можно создать отчет по анализу прозрачности.</span><span class="sxs-lookup"><span data-stu-id="f7284-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="f7284-160">В строке меню щелкните значок **шестеренки** .</span><span class="sxs-lookup"><span data-stu-id="f7284-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="f7284-161">На вкладке **Служебные программы \> параметры и служебные** программы выберите **Настройка \> анализа прозрачности**.</span><span class="sxs-lookup"><span data-stu-id="f7284-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="f7284-162">В поле \* \* ID файла \* \* введите идентификатор файла, который требуется обработать.</span><span class="sxs-lookup"><span data-stu-id="f7284-162">In \*\* File ID \*\*, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="f7284-163">В списке **неполадок** выберите соответствующую ошибку.</span><span class="sxs-lookup"><span data-stu-id="f7284-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="f7284-164">Щелкните **анализ прозрачности**.</span><span class="sxs-lookup"><span data-stu-id="f7284-164">Click **Transparency analysis**.</span></span> <span data-ttu-id="f7284-165">После завершения отображается отчет по анализу прозрачности для файла, который показывает, как отмеченные цвета ключевых слов соответствуют общему показателю релевантности.</span><span class="sxs-lookup"><span data-stu-id="f7284-165">Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f7284-166">См. также</span><span class="sxs-lookup"><span data-stu-id="f7284-166">See also</span></span>

[<span data-ttu-id="f7284-167">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f7284-167">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="f7284-168">Определение параметров дел и клиента</span><span class="sxs-lookup"><span data-stu-id="f7284-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)

