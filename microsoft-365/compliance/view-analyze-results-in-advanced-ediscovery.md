---
title: Просмотр результатов анализа в Advanced eDiscovery
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
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: В этой теме представлены результаты анализа в Advanced eDiscovery, включая определения отображаемой задачи.
ms.openlocfilehash: 64c91cb5929a7a74e53d653faff98d5792d3f131
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663263"
---
# <a name="view-analyze-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="8e977-103">Просмотр результатов анализа в Advanced eDiscovery (классическая)</span><span class="sxs-lookup"><span data-stu-id="8e977-103">View Analyze results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="8e977-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="8e977-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="8e977-106">В Advanced eDiscovery ход выполнения и результаты анализа можно просматривать на различных дисплеях, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="8e977-106">In Advanced eDiscovery, progress and results for the Analyze process can be viewed in a variety of displays as described below.</span></span>
  
## <a name="view-analyze-task-status"></a><span data-ttu-id="8e977-107">Просмотр состояния задачи "Анализ"</span><span class="sxs-lookup"><span data-stu-id="8e977-107">View Analyze task status</span></span>

<span data-ttu-id="8e977-108">В **состоянии \> задачи "Подготовка анализа \> \> результатов"** состояние отображается во время и после выполнения процесса анализа.</span><span class="sxs-lookup"><span data-stu-id="8e977-108">In **Prepare \> Analyze \> Results \> Task status**, the status is displayed during and after Analyze process execution.</span></span> 
  
![Состояние задачи анализа](../media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
<span data-ttu-id="8e977-110">Отображаемая задача может отличаться в зависимости от выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="8e977-110">The tasks displayed may vary depending on the options selected.</span></span> 
  
- <span data-ttu-id="8e977-111">**ND/ET: setup**: prepares for the run, for example, sets run and case parameters.</span><span class="sxs-lookup"><span data-stu-id="8e977-111">**ND/ET: setup**: Prepares for the run, for example, sets run and case parameters.</span></span>
    
- <span data-ttu-id="8e977-112">**ND/ET: вычисление ND**: обрабатывает практически дубликат анализа файлов.</span><span class="sxs-lookup"><span data-stu-id="8e977-112">**ND/ET: ND calculation**: Processes Near-duplicate analysis of files.</span></span>
    
- <span data-ttu-id="8e977-113">**ND/ET: вычисление ET**: выполняет анализ потока электронной почты для всего набора электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8e977-113">**ND/ET: ET calculation**: Performs Email Thread analysis on the entire email set.</span></span>
    
- <span data-ttu-id="8e977-114">**ND/ET: pivots and similarities**: Performs pivot and file similarity processing.</span><span class="sxs-lookup"><span data-stu-id="8e977-114">**ND/ET: pivots and similarities**: Performs pivot and file similarity processing.</span></span>
    
- <span data-ttu-id="8e977-115">**ND/ET: обновление метаданных:** завершение новых данных, собранных для файлов в базе данных.</span><span class="sxs-lookup"><span data-stu-id="8e977-115">**ND/ET: metadata update**: Finalizes the new data collected on the files in the database.</span></span>
    
- <span data-ttu-id="8e977-116">**Темы: вычисление тем**: выполняет анализ тем.</span><span class="sxs-lookup"><span data-stu-id="8e977-116">**Themes: themes calculation**: Runs themes analysis.</span></span> <span data-ttu-id="8e977-117">(Отображается, только если выбрано.)</span><span class="sxs-lookup"><span data-stu-id="8e977-117">(Displayed only if selected.)</span></span>
    
- <span data-ttu-id="8e977-118">**Состояние задачи:** эта строка отображается после завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="8e977-118">**Task status**: This line is displayed after task completion.</span></span> <span data-ttu-id="8e977-119">Во время выполнения задач отображается продолжительность выполнения.</span><span class="sxs-lookup"><span data-stu-id="8e977-119">While tasks are running, run duration is displayed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8e977-120">Результаты анализа практически дубликатов и потоков электронной почты (ND и ED) применяются к количеству обрабатываемых документов.</span><span class="sxs-lookup"><span data-stu-id="8e977-120">The Analyze results of Near-duplicates and Email Threads (ND and ED) applies to the number of documents to be processed.</span></span> <span data-ttu-id="8e977-121">Он не включает точные дублирующиеся файлы.</span><span class="sxs-lookup"><span data-stu-id="8e977-121">It does not include Exact duplicate files.</span></span> 
  
## <a name="view-near-duplicates-and-email-threads-status"></a><span data-ttu-id="8e977-122">Просмотр почти дубликатов и состояния потоков электронной почты</span><span class="sxs-lookup"><span data-stu-id="8e977-122">View Near-duplicates and Email Threads status</span></span>

<span data-ttu-id="8e977-123">В **результатах** целевой аудитории отображается количество документов, сообщений электронной почты, вложений и ошибок в целевой аудитории.</span><span class="sxs-lookup"><span data-stu-id="8e977-123">The **Target** population results display the number of documents, emails, attachments, and errors in the target population.</span></span> 
  
<span data-ttu-id="8e977-124">В **результатах** "Документы" отображается количество стеков, уникальных почти дубликатов и точные дублирующиеся файлы.</span><span class="sxs-lookup"><span data-stu-id="8e977-124">The **Documents** results display the number of pivots, unique near-duplicates, and exact duplicate files.</span></span> 
  
<span data-ttu-id="8e977-125">В **результатах "Сообщения** электронной почты" отображается число инклюзивных, включительно минус, уникальных инклюзивных копий, а также остальные сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8e977-125">The **Emails** results display the number of inclusive, inclusive minus, unique inclusive copies, and the rest of the email messages.</span></span> <span data-ttu-id="8e977-126">Различные типы результатов электронной почты:</span><span class="sxs-lookup"><span data-stu-id="8e977-126">The different types of email results are:</span></span> 
  
- <span data-ttu-id="8e977-127">Инклюзивное: инклюзивное сообщение электронной почты является завершающим узлом в потоке электронной почты и содержит всю предыдущую историю этого потока.</span><span class="sxs-lookup"><span data-stu-id="8e977-127">**Inclusive**: An inclusive email is the terminating node in an email thread and contains all the previous history of that thread.</span></span> <span data-ttu-id="8e977-128">В результате проверяющей может безопасно сосредоточиться на инклюзивном сообщении электронной почты без необходимости читать предыдущие сообщения в потоке.</span><span class="sxs-lookup"><span data-stu-id="8e977-128">As a result, the reviewer can safely focus on the inclusive email, without the need to read the previous messages in the thread.</span></span> 
    
- <span data-ttu-id="8e977-129">**Инклюзивное** минус: инклюзивное сообщение электронной почты обозначается как инклюзивное минус, если с родительскими инклюзивными сообщениями связано одно или несколько разных вложений.</span><span class="sxs-lookup"><span data-stu-id="8e977-129">**Inclusive minus**: An inclusive email is designated as inclusive minus if there are one or more different attachments associated with the parents of the inclusive message.</span></span> <span data-ttu-id="8e977-130">В этом контексте термин Parent используется для сообщений, расположенных вверх в потоке электронной почты или бесед, включенных в определенное инклюзивное сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8e977-130">In this context, the term Parent is used for messages located upwards on the email thread or conversations included in that specific inclusive email.</span></span> <span data-ttu-id="8e977-131">Проверяющей может использовать инклюзивный знак минус в качестве сигнала о том, что, хотя может не потребоваться просмотр контента инклюзивных родителей электронной почты, может быть полезно просмотреть вложения, связанные с родительскими путями инклюзивного пути.</span><span class="sxs-lookup"><span data-stu-id="8e977-131">A reviewer can use the inclusive minus indication as a signal that although it might not be necessary to review the content of the inclusive email parents, it may be useful to review the attachments associated with the inclusive path parents.</span></span> 
    
- <span data-ttu-id="8e977-132">**Инклюзивная** копия: инклюзивное сообщение электронной почты обозначается как инклюзивная копия, если это копия другого сообщения, помеченного как инклюзивная или включительно минус.</span><span class="sxs-lookup"><span data-stu-id="8e977-132">**Inclusive copy**: An inclusive email is designated as inclusive copy if it's the copy of another message marked as inclusive or inclusive minus.</span></span> <span data-ttu-id="8e977-133">Другими словами, это сообщение имеет ту же тему и текст, что и другое инклюзивное сообщение, и, таким образом, совместно находится в том же узле.</span><span class="sxs-lookup"><span data-stu-id="8e977-133">In other words, this message has the same subject and body as another inclusive message and, as such, co-resides in the same node.</span></span> <span data-ttu-id="8e977-134">Так как сообщения инклюзивной копии содержат одинаковое содержимое, их обычно можно пропустить в процессе проверки.</span><span class="sxs-lookup"><span data-stu-id="8e977-134">Because inclusive copy messages contain the same content, they can usually be skipped in the review process.</span></span> 
    
- <span data-ttu-id="8e977-135">**В остальном**: это означает, что электронная почта не содержит уникального содержимого и, следовательно, не подпадет под предыдущие три категории.</span><span class="sxs-lookup"><span data-stu-id="8e977-135">**The rest**: This indicates email that doesn't contain any unique content, and therefore doesn't fall into any of the previous three categories.</span></span> <span data-ttu-id="8e977-136">Эти сообщения электронной почты не требуют проверки.</span><span class="sxs-lookup"><span data-stu-id="8e977-136">These email messages don't need to be reviewed.</span></span> <span data-ttu-id="8e977-137">Если сообщение содержит вложение, которое не включено в более позднее инклюзивное сообщение электронной почты, может потребоваться проверка вложения.</span><span class="sxs-lookup"><span data-stu-id="8e977-137">If a message contains an attachment that isn't on a later inclusive email, then the attachment might need to be reviewed.</span></span> <span data-ttu-id="8e977-138">На это указывает наличие инклюзивного сообщения без электронной почты в потоке.</span><span class="sxs-lookup"><span data-stu-id="8e977-138">This is indicated by the existence of an inclusive minus email within the thread.</span></span>
    
<span data-ttu-id="8e977-139">В **результатах** "Вложения" отображается число вложений в соответствии с таким типом, как уникальные и дубликаты.</span><span class="sxs-lookup"><span data-stu-id="8e977-139">The **Attachments** results display the number of attachments, according to such type as unique and duplicates.</span></span> 
  
![Почти повторяющиеся результаты и цепочки сообщений](../media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a><span data-ttu-id="8e977-141">См. также</span><span class="sxs-lookup"><span data-stu-id="8e977-141">See also</span></span>

[<span data-ttu-id="8e977-142">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="8e977-142">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="8e977-143">Понимание сходства документов</span><span class="sxs-lookup"><span data-stu-id="8e977-143">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8e977-144">Настройка параметров анализа</span><span class="sxs-lookup"><span data-stu-id="8e977-144">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8e977-145">Настройка игнорирования текста</span><span class="sxs-lookup"><span data-stu-id="8e977-145">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8e977-146">Настройка дополнительных параметров анализа</span><span class="sxs-lookup"><span data-stu-id="8e977-146">Setting Analyze advanced settings</span></span>](view-analyze-results-in-advanced-ediscovery.md)

