---
title: Использование служебных программ Advanced eDiscovery
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
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: Сведения о службах Advanced eDiscovery, в том числе журнале дела, очистке данных, ошибках процесса, изменении релевантности и анализе прозрачности.
ms.openlocfilehash: 745b81609d73ec88525c3348cc4d582c7d5d7b30
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663298"
---
# <a name="use-advanced-ediscovery-classic-utilities"></a><span data-ttu-id="306cb-103">Использование служебных программ Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="306cb-103">Use Advanced eDiscovery (classic) utilities</span></span>

> [!NOTE]
> <span data-ttu-id="306cb-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="306cb-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="306cb-106">Жки, которые отображаются и доступны в Advanced eDiscovery, зависят от контекста и ролей пользователей.</span><span class="sxs-lookup"><span data-stu-id="306cb-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="306cb-107">Журнал дела</span><span class="sxs-lookup"><span data-stu-id="306cb-107">Case log</span></span>

<span data-ttu-id="306cb-108">В журнале дел приводится подробный список действий по обработке приложений, которые можно использовать для отслеживания, устранения неполадок, а также для устранения ошибок и предупреждений.</span><span class="sxs-lookup"><span data-stu-id="306cb-108">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings.</span></span> <span data-ttu-id="306cb-109">Журнал может быть создан и сохранен локально на хост-сервере или отправлен непосредственно на адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="306cb-109">The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="306cb-110">Файл журнала также можно скачать на компьютер клиента.</span><span class="sxs-lookup"><span data-stu-id="306cb-110">The log file can also be downloaded to the client's computer.</span></span> <span data-ttu-id="306cb-111">Параметр загрузки клиента может быть включен или отключен в соответствии с конфигурацией и ролью пользователя.</span><span class="sxs-lookup"><span data-stu-id="306cb-111">The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="306cb-112">В панели меню щелкните **значок Cogwheel.**</span><span class="sxs-lookup"><span data-stu-id="306cb-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="306cb-113">На **вкладке "Параметры" и \> "Utilities Utilities"** выберите **"Настройка журнала \> дела".**</span><span class="sxs-lookup"><span data-stu-id="306cb-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="306cb-114">Выберите уровень **журнала** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="306cb-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="306cb-115">**Стандарт:** включает базовые данные журнала.</span><span class="sxs-lookup"><span data-stu-id="306cb-115">**Standard**: Includes the basic log data.</span></span> <span data-ttu-id="306cb-116">Этот параметр обычно необходим для мониторинга и должен использоваться, если не рекомендуется иное.</span><span class="sxs-lookup"><span data-stu-id="306cb-116">This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="306cb-117">**Минимальное:** используется для очень больших случаев и возвращает только последние данные.</span><span class="sxs-lookup"><span data-stu-id="306cb-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="306cb-118">Нажмите **кнопку "Выполнить журнал дела"**.</span><span class="sxs-lookup"><span data-stu-id="306cb-118">Click **Run Case log**.</span></span> <span data-ttu-id="306cb-119">Создается журнал и отображается путь.</span><span class="sxs-lookup"><span data-stu-id="306cb-119">The log is generated and path is displayed.</span></span> <span data-ttu-id="306cb-120">Сведения о ходе выполнения текущей и последней задачи отображаются в области состояния задачи.</span><span class="sxs-lookup"><span data-stu-id="306cb-120">The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="306cb-121">Очистка данных</span><span class="sxs-lookup"><span data-stu-id="306cb-121">Clear data</span></span>

<span data-ttu-id="306cb-122">Если необходимо удалить или повторно инициализировать данные дела, необходимо инициализировать экземпляр базы данных.</span><span class="sxs-lookup"><span data-stu-id="306cb-122">If it is necessary to delete or reinitialize case data, the database instance must be initialized.</span></span> <span data-ttu-id="306cb-123">Программа очистки данных удаляет все указанные записи из базы данных дел, текстовых файлов, папки дел и собранных результатов.</span><span class="sxs-lookup"><span data-stu-id="306cb-123">The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results.</span></span> <span data-ttu-id="306cb-124">Эту функцию может выполнять только администратор.</span><span class="sxs-lookup"><span data-stu-id="306cb-124">The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="306cb-125">Это действие не является обратимым и очищает все теги релевантности и анализ, выполняемые экспертом.</span><span class="sxs-lookup"><span data-stu-id="306cb-125">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert.</span></span> <span data-ttu-id="306cb-126">При необходимости сохраните резервную копию данных.</span><span class="sxs-lookup"><span data-stu-id="306cb-126">Save a backup of data, if necessary.</span></span> <span data-ttu-id="306cb-127">Используйте этот параметр с крайней осторожностью.</span><span class="sxs-lookup"><span data-stu-id="306cb-127">Use this option with extreme care.</span></span> <span data-ttu-id="306cb-128">Удаление файлов с тегами и ранжирований может повлиять на результаты релевантности.</span><span class="sxs-lookup"><span data-stu-id="306cb-128">Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="306cb-129">В панели меню щелкните **значок Cogwheel.**</span><span class="sxs-lookup"><span data-stu-id="306cb-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="306cb-130">На **вкладке "Параметры" и \> "Utilities Utilities"** выберите **"Очистить настройку \> данных".**</span><span class="sxs-lookup"><span data-stu-id="306cb-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="306cb-131">Выберите параметр для инициализации данных:</span><span class="sxs-lookup"><span data-stu-id="306cb-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="306cb-132">**Релевантность**: удаляет всю работу, сделанную в релевантности, включая определение нагрузок и связь файлов с загрузками.</span><span class="sxs-lookup"><span data-stu-id="306cb-132">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads.</span></span> <span data-ttu-id="306cb-133">Он удаляет все примеры и теги.</span><span class="sxs-lookup"><span data-stu-id="306cb-133">It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="306cb-134">**Практически дубликаты** и потоки электронной почты: удаляет все данные анализа почти дубликатов и потоки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="306cb-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="306cb-135">**Темы:** удаляет данные, связанные с темами.</span><span class="sxs-lookup"><span data-stu-id="306cb-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="306cb-136">**История экспорта:** удаляет сведения об истории пакетов экспорта.</span><span class="sxs-lookup"><span data-stu-id="306cb-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="306cb-137">Щелкните **"Очистить данные".**</span><span class="sxs-lookup"><span data-stu-id="306cb-137">Click **Clear data**.</span></span> <span data-ttu-id="306cb-138">Данные дела очищены.</span><span class="sxs-lookup"><span data-stu-id="306cb-138">The case data is cleared.</span></span> <span data-ttu-id="306cb-139">Сведения о ходе выполнения текущей и последней задачи отображаются в области **состояния** задачи.</span><span class="sxs-lookup"><span data-stu-id="306cb-139">The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="306cb-140">Изменение релевантности</span><span class="sxs-lookup"><span data-stu-id="306cb-140">Modify Relevance</span></span>

<span data-ttu-id="306cb-141">В этом разделе описывается, как пропустить или откатить пример релевантности.</span><span class="sxs-lookup"><span data-stu-id="306cb-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="306cb-142">В панели меню щелкните **значок Cogwheel.**</span><span class="sxs-lookup"><span data-stu-id="306cb-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="306cb-143">На **вкладке "Параметры" и \> "Utilities Utilities" (Параметры и utilities Utilities)** выберите **"Изменить релевантность".**</span><span class="sxs-lookup"><span data-stu-id="306cb-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="306cb-144">Выберите один из вариантов:</span><span class="sxs-lookup"><span data-stu-id="306cb-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="306cb-145">**Пропустить текущий пример для** текущего пользователя: он помечает как **Skip** все неотмечаемые файлы в примере открытого дела пользователя, запустив сканю.</span><span class="sxs-lookup"><span data-stu-id="306cb-145">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility.</span></span> <span data-ttu-id="306cb-146">Обработка релевантности не будет выполняться для файлов, помеченных как **Skip.**</span><span class="sxs-lookup"><span data-stu-id="306cb-146">Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="306cb-147">**Пропустить текущий пример — все** открытые образцы: будет отмечаться как **Skip**, все ненавязченные файлы во всех открытых примерах для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="306cb-147">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users.</span></span> <span data-ttu-id="306cb-148">Этот параметр не рекомендуется, если пользователи в настоящее время помечали примеры тегов.</span><span class="sxs-lookup"><span data-stu-id="306cb-148">This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="306cb-149">**Откат последнего примера:** последний завершенный пример обучения релевантности будет откатен независимо от того, до или после процесса "Расчет".</span><span class="sxs-lookup"><span data-stu-id="306cb-149">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process.</span></span> <span data-ttu-id="306cb-150">Откат примера не допускается.</span><span class="sxs-lookup"><span data-stu-id="306cb-150">Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="306cb-151">Нажмите **кнопку** "Выполнить", чтобы выполнить.</span><span class="sxs-lookup"><span data-stu-id="306cb-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="306cb-152">Анализ прозрачности</span><span class="sxs-lookup"><span data-stu-id="306cb-152">Transparency analysis</span></span>

<span data-ttu-id="306cb-153">С помощью этой с помощью анализа прозрачности можно получить подробное представление файлов и назначенной им оценки релевантности.</span><span class="sxs-lookup"><span data-stu-id="306cb-153">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score.</span></span> <span data-ttu-id="306cb-154">Отчет можно использовать в качестве проверки на санацию или для сравнения релевантности файла, определенного рецензентом, по сравнению с релевантностью, назначенной Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="306cb-154">The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="306cb-155">Помимо оценки релевантности Advanced eDiscovery вычисляет и назначает вес ключевых слов, учитывая контекст ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="306cb-155">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context.</span></span> <span data-ttu-id="306cb-156">Одному и том же слову в файле могут быть назначены разные веса в зависимости от контекста и расположения.</span><span class="sxs-lookup"><span data-stu-id="306cb-156">The same word in a file can be assigned different weights, depending on context and location.</span></span> <span data-ttu-id="306cb-157">Каждое ключевое слово помечается с использованием увеличивающегося масштаба интенсивности цвета в диапазоне от желтого до темно-оранжевого и различных оттенков серого.</span><span class="sxs-lookup"><span data-stu-id="306cb-157">Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray.</span></span> <span data-ttu-id="306cb-158">Цветовое кодирование используется для визуального обозначения относительного положительного или отрицательного влияния слова на оценку релевантности.</span><span class="sxs-lookup"><span data-stu-id="306cb-158">Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="306cb-159">В сценарии с несколькими вопросами для каждой проблемы может быть создан отчет анализа прозрачности.</span><span class="sxs-lookup"><span data-stu-id="306cb-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="306cb-160">В панели меню щелкните **значок Cogwheel.**</span><span class="sxs-lookup"><span data-stu-id="306cb-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="306cb-161">На **вкладке "Параметры и \> utilities Utilities"** выберите **"Настройка анализа \> прозрачности".**</span><span class="sxs-lookup"><span data-stu-id="306cb-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="306cb-162">In \*\* File ID \*\*, enter the file ID of the file to process.</span><span class="sxs-lookup"><span data-stu-id="306cb-162">In \*\* File ID \*\*, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="306cb-163">В **списке проблем** выберите проблему.</span><span class="sxs-lookup"><span data-stu-id="306cb-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="306cb-164">Щелкните **анализ прозрачности.**</span><span class="sxs-lookup"><span data-stu-id="306cb-164">Click **Transparency analysis**.</span></span> <span data-ttu-id="306cb-165">По завершении отобразится отчет анализа прозрачности для файла, в котором показано, как помеченные цвета ключевых слов соотносятся с общей оценкой релевантности.</span><span class="sxs-lookup"><span data-stu-id="306cb-165">Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="306cb-166">См. также</span><span class="sxs-lookup"><span data-stu-id="306cb-166">See also</span></span>

[<span data-ttu-id="306cb-167">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="306cb-167">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="306cb-168">Определение параметров дела и клиента</span><span class="sxs-lookup"><span data-stu-id="306cb-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)

