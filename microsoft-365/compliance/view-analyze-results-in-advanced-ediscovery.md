---
title: Просмотр результатов анализа в Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
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
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: 'Сведения о том, как просматривать результаты анализа в Office 365 Advanced eDiscovery, включая определения отображаемых параметров задачи.  '
ms.openlocfilehash: 9e06770135afd62a39115c9365a698df4493bd72
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597256"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="917d3-103">Просмотр результатов анализа в Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="917d3-103">View Analyze results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="917d3-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="917d3-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="917d3-106">Во время расширенного обнаружения электронных данных результаты и результаты для процесса анализа можно просматривать в различных экранах, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="917d3-106">In Advanced eDiscovery, progress and results for the Analyze process can be viewed in a variety of displays as described below.</span></span>
  
## <a name="view-analyze-task-status"></a><span data-ttu-id="917d3-107">Просмотр состояния задачи анализа</span><span class="sxs-lookup"><span data-stu-id="917d3-107">View Analyze task status</span></span>

<span data-ttu-id="917d3-108">**Состояние задачи \> подготовить \> анализ \> результатов**позволяет отобразить состояние, которое отображается во время и после анализа выполнения процесса.</span><span class="sxs-lookup"><span data-stu-id="917d3-108">In **Prepare \> Analyze \> Results \> Task status**, the status is displayed during and after Analyze process execution.</span></span> 
  
![Состояние задачи анализа](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
<span data-ttu-id="917d3-110">Отображаемые задачи могут различаться в зависимости от выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="917d3-110">The tasks displayed may vary depending on the options selected.</span></span> 
  
- <span data-ttu-id="917d3-111">**ND/ET: Программа установки**: подготовка к запуску, например, задает параметры Run и Case.</span><span class="sxs-lookup"><span data-stu-id="917d3-111">**ND/ET: setup**: Prepares for the run, for example, sets run and case parameters.</span></span>
    
- <span data-ttu-id="917d3-112">**ND/ET: ND**: обрабатывает анализ файлов практических копий.</span><span class="sxs-lookup"><span data-stu-id="917d3-112">**ND/ET: ND calculation**: Processes Near-duplicate analysis of files.</span></span>
    
- <span data-ttu-id="917d3-113">**ND/ET: расчет et**: выполняет анализ цепочки электронных сообщений для всего набора электронной почты.</span><span class="sxs-lookup"><span data-stu-id="917d3-113">**ND/ET: ET calculation**: Performs Email Thread analysis on the entire email set.</span></span>
    
- <span data-ttu-id="917d3-114">**ND/ET: сводки и сходства**: выполняет сведение и обработку подобия файла.</span><span class="sxs-lookup"><span data-stu-id="917d3-114">**ND/ET: pivots and similarities**: Performs pivot and file similarity processing.</span></span>
    
- <span data-ttu-id="917d3-115">**ND/ET: Metadata Update**: завершает новые данные, собранные для файлов в базе данных.</span><span class="sxs-lookup"><span data-stu-id="917d3-115">**ND/ET: metadata update**: Finalizes the new data collected on the files in the database.</span></span>
    
- <span data-ttu-id="917d3-116">**Темы: вычисление тем**: выполнение анализа тем.</span><span class="sxs-lookup"><span data-stu-id="917d3-116">**Themes: themes calculation**: Runs themes analysis.</span></span> <span data-ttu-id="917d3-117">(Отображается, только если выбрано.)</span><span class="sxs-lookup"><span data-stu-id="917d3-117">(Displayed only if selected.)</span></span>
    
- <span data-ttu-id="917d3-118">**Состояние задачи**: Эта строка отображается после завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="917d3-118">**Task status**: This line is displayed after task completion.</span></span> <span data-ttu-id="917d3-119">Во время выполнения задач отображается длительность выполнения.</span><span class="sxs-lookup"><span data-stu-id="917d3-119">While tasks are running, run duration is displayed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="917d3-120">Результаты анализа результатов практических дубликатов и почтовых потоков (ND и ED) применяются к количеству обрабатываемых документов.</span><span class="sxs-lookup"><span data-stu-id="917d3-120">The Analyze results of Near-duplicates and Email Threads (ND and ED) applies to the number of documents to be processed.</span></span> <span data-ttu-id="917d3-121">В него не включены точные повторяющиеся файлы.</span><span class="sxs-lookup"><span data-stu-id="917d3-121">It does not include Exact duplicate files.</span></span> 
  
## <a name="view-near-duplicates-and-email-threads-status"></a><span data-ttu-id="917d3-122">Просмотр состояния почти повторяющихся и почтовых потоков</span><span class="sxs-lookup"><span data-stu-id="917d3-122">View Near-duplicates and Email Threads status</span></span>

<span data-ttu-id="917d3-123">В результатах **целевого** заполнения отображается количество документов, сообщений электронной почты, вложений и ошибок в целевом заполнении.</span><span class="sxs-lookup"><span data-stu-id="917d3-123">The **Target** population results display the number of documents, emails, attachments, and errors in the target population.</span></span> 
  
<span data-ttu-id="917d3-124">В результатах **документов** отображается количество сводных таблиц, уникальных посторонних и повторяющихся файлов.</span><span class="sxs-lookup"><span data-stu-id="917d3-124">The **Documents** results display the number of pivots, unique near-duplicates, and exact duplicate files.</span></span> 
  
<span data-ttu-id="917d3-125">В результатах **электронной почты** отображается количество включительно включительно, уникальные Инклюзивные копии и остальные сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="917d3-125">The **Emails** results display the number of inclusive, inclusive minus, unique inclusive copies, and the rest of the email messages.</span></span> <span data-ttu-id="917d3-126">Ниже приведены различные типы результатов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="917d3-126">The different types of email results are:</span></span> 
  
- <span data-ttu-id="917d3-127">**Включительно**: включающая электронная почта — узел завершения в цепочке электронной почты и содержит все предыдущие истории этого потока.</span><span class="sxs-lookup"><span data-stu-id="917d3-127">**Inclusive**: An inclusive email is the terminating node in an email thread and contains all the previous history of that thread.</span></span> <span data-ttu-id="917d3-128">В результате проверяющий может безопасно сосредоточиться на инклюзивной электронной почте без необходимости чтения предыдущих сообщений в потоке.</span><span class="sxs-lookup"><span data-stu-id="917d3-128">As a result, the reviewer can safely focus on the inclusive email, without the need to read the previous messages in the thread.</span></span> 
    
- <span data-ttu-id="917d3-129">**Включительно**: инклюзивная электронная почта обозначается как инклюзивное минус, если существует одно или несколько вложений, связанных с родителями инклюзивного сообщения.</span><span class="sxs-lookup"><span data-stu-id="917d3-129">**Inclusive minus**: An inclusive email is designated as inclusive minus if there are one or more different attachments associated with the parents of the inclusive message.</span></span> <span data-ttu-id="917d3-130">В этом контексте термин родитель используется для сообщений, расположенных выше в цепочке сообщений электронной почты или беседах, включенных в конкретную электронную почту.</span><span class="sxs-lookup"><span data-stu-id="917d3-130">In this context, the term Parent is used for messages located upwards on the email thread or conversations included in that specific inclusive email.</span></span> <span data-ttu-id="917d3-131">Проверяющий может использовать индикатор инклюзивного минуса в качестве сигнала, хотя это может быть необязательно для просмотра контента инклюзивных родителей электронной почты, может быть полезен Просмотр вложений, связанных с родителями невключающих путей.</span><span class="sxs-lookup"><span data-stu-id="917d3-131">A reviewer can use the inclusive minus indication as a signal that although it might not be necessary to review the content of the inclusive email parents, it may be useful to review the attachments associated with the inclusive path parents.</span></span> 
    
- <span data-ttu-id="917d3-132">**Инклюзивная копия**: включающая электронная почта считается инклюзивной копией, если она является копией другого сообщения, помеченной как включающая или инклюзивная минус.</span><span class="sxs-lookup"><span data-stu-id="917d3-132">**Inclusive copy**: An inclusive email is designated as inclusive copy if it's the copy of another message marked as inclusive or inclusive minus.</span></span> <span data-ttu-id="917d3-133">Другими словами, это сообщение имеет те же тема и основной текст, что и другое сообщение, и, как и, в том же узле.</span><span class="sxs-lookup"><span data-stu-id="917d3-133">In other words, this message has the same subject and body as another inclusive message and, as such, co-resides in the same node.</span></span> <span data-ttu-id="917d3-134">Так как Инклюзивные сообщения копии содержат одинаковое содержимое, они обычно могут пропускаться в процессе проверки.</span><span class="sxs-lookup"><span data-stu-id="917d3-134">Because inclusive copy messages contain the same content, they can usually be skipped in the review process.</span></span> 
    
- <span data-ttu-id="917d3-135">**REST**: это указывает на то, что сообщение электронной почты не содержит уникального содержимого и поэтому не попадает ни на какие три категории.</span><span class="sxs-lookup"><span data-stu-id="917d3-135">**The rest**: This indicates email that doesn't contain any unique content, and therefore doesn't fall into any of the previous three categories.</span></span> <span data-ttu-id="917d3-136">Эти сообщения электронной почты не требуется проверять.</span><span class="sxs-lookup"><span data-stu-id="917d3-136">These email messages don't need to be reviewed.</span></span> <span data-ttu-id="917d3-137">Если сообщение содержит вложение, которое не находится в более поздней инклюзивной электронной почте, то, возможно, необходимо проверить вложение.</span><span class="sxs-lookup"><span data-stu-id="917d3-137">If a message contains an attachment that isn't on a later inclusive email, then the attachment might need to be reviewed.</span></span> <span data-ttu-id="917d3-138">Это определяется тем, что в потоке существует инклюзивная почта минуса.</span><span class="sxs-lookup"><span data-stu-id="917d3-138">This is indicated by the existence of an inclusive minus email within the thread.</span></span>
    
<span data-ttu-id="917d3-139">Результаты **вложений** отображают количество вложений, в соответствии с такими типами, как уникальные и повторяющиеся.</span><span class="sxs-lookup"><span data-stu-id="917d3-139">The **Attachments** results display the number of attachments, according to such type as unique and duplicates.</span></span> 
  
![Почти повторяющиеся результаты и цепочки сообщений](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a><span data-ttu-id="917d3-141">См. также</span><span class="sxs-lookup"><span data-stu-id="917d3-141">See also</span></span>

[<span data-ttu-id="917d3-142">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="917d3-142">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="917d3-143">Сведения о сходстве документов</span><span class="sxs-lookup"><span data-stu-id="917d3-143">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="917d3-144">Настройка параметров анализа</span><span class="sxs-lookup"><span data-stu-id="917d3-144">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="917d3-145">Настройка игнорируемого текста</span><span class="sxs-lookup"><span data-stu-id="917d3-145">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="917d3-146">Настройка дополнительных параметров анализа</span><span class="sxs-lookup"><span data-stu-id="917d3-146">Setting Analyze advanced settings</span></span>](view-analyze-results-in-advanced-ediscovery.md)

