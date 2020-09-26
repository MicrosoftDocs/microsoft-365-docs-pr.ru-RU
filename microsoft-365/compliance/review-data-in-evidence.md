---
title: Просмотр данных в свидетельстве
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Узнайте о методах для проверки данных в свидетельствах, таких как просмотр в машинных, текстовых или практических собственных форматах.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9335b95cc57add69660b707577829caef1ad8183
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285385"
---
# <a name="review-the-data-in-evidence"></a><span data-ttu-id="23f61-103">Просмотр данных в свидетельстве</span><span class="sxs-lookup"><span data-stu-id="23f61-103">Review the data in evidence</span></span>

<span data-ttu-id="23f61-104">Данные в наборе свидетельств во время расследования данных — это моментальный снимок результатов поиска, которые вы собрали и добавляете в набор свидетельств.</span><span class="sxs-lookup"><span data-stu-id="23f61-104">The data in an evidence set in a data investigation is a snapshot of the search results that you collected and added to the evidence set.</span></span> <span data-ttu-id="23f61-105">Когда вы добавляете результаты поиска в свидетельство, процесс запускается для извлечения файлов, метаданных и текста из элементов, возвращенных при поиске.</span><span class="sxs-lookup"><span data-stu-id="23f61-105">When you add search results to evidence, a process is triggered to extract files, metadata, and text from the items returned by the search.</span></span> <span data-ttu-id="23f61-106">Затем средство расследования данных (Предварительная версия) создает новый индекс (процесс с *расширенной индексацией*) всех данных и добавляет к набору свидетельств на вкладке **свидетельство** .</span><span class="sxs-lookup"><span data-stu-id="23f61-106">Then the Data Investigations (preview) tool then builds a new index (by a process called *Advanced indexing*) of all the data and adds to an evidence set on the **Evidence** tab.</span></span> 

<span data-ttu-id="23f61-107">При расследовании с учетом времени это позволяет быстро включить среду, удалив фактические или нежелательные данные, расположенные в исходном источнике данных, в то же время, что позволяет исследовать повторно созданные доказательства в среде карантина, в этом случае данные копируются в набор свидетельства.</span><span class="sxs-lookup"><span data-stu-id="23f61-107">For time-sensitive investigations, this allows you to quickly contain the environment by deleting the actual spilled or malicious data located in the at original data source, while at the same time allowing you to investigate the re-created evidence in a quarantined environment, which in this case is the data copied to the evidence set).</span></span> <span data-ttu-id="23f61-108">После того как свидетельство будет собрано и Добавлено в набор свидетельств, можно просмотреть отдельные документы в собственном формате, в текстовом формате или в близком формате, который можно использовать для аннотирования и исправления документов.</span><span class="sxs-lookup"><span data-stu-id="23f61-108">After the evidence is collected and added to the evidence set, you can review individual documents in their native format, text format, or a near-native format that you can use to annotate and redact documents.</span></span> <span data-ttu-id="23f61-109">Кроме того, вы можете выполнять запросы для сужения набора данных по диапазону времени, типам файлов, владельцам данных и многим другим свойствам и условиям поиска.</span><span class="sxs-lookup"><span data-stu-id="23f61-109">Additionally, you can run queries to narrow the data set by time range, file types, data owners, and many other properties and search conditions.</span></span> <span data-ttu-id="23f61-110">Например, с помощью условий "Автор", "отправитель" или "получатель" можно быстро определить людей, участвующих в инциденте, а также предоставить доступ к данным из вашей организации к внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="23f61-110">For example, by using the Author, Sender, or Recipient conditions, you can quickly identify the people are involved in the incident and if any data from your organization has been shared with external users.</span></span> <span data-ttu-id="23f61-111">Дополнительные сведения о поиске в наборе свидетельств можно найти [в статье запрос данных в доказательстве](evidence-query.md).</span><span class="sxs-lookup"><span data-stu-id="23f61-111">For more information about searching through data in an evidence set, see [Query the data in evidence](evidence-query.md).</span></span>

<span data-ttu-id="23f61-112">Чтобы сгруппировать документы и получить дополнительную помощь по проверке, выберите набор свидетельств на вкладке **свидетельство** , а затем нажмите кнопку **Управление доказательством**.</span><span class="sxs-lookup"><span data-stu-id="23f61-112">To group documents and get more assistance for your review, select an evidence set on the **Evidence** tab, and then click **Manage evidence**.</span></span> <span data-ttu-id="23f61-113">В плитке **аналитика** щелкните **перестроить аналитику для всего набора**.</span><span class="sxs-lookup"><span data-stu-id="23f61-113">In the **Analytics** tile, click **Rebuild analytics for the whole set**.</span></span> <span data-ttu-id="23f61-114">При этом будет выполняться Расширенная аналитика, например поиск повторяющихся данных, почтовые потоки и анализ темы.</span><span class="sxs-lookup"><span data-stu-id="23f61-114">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="23f61-115">После этого вы увидите общие темы данных, а также упорядочивайте документы по потокам электронной почты, рядом с дубликатами, а также точные дубликаты, которые помогут провести расследование.</span><span class="sxs-lookup"><span data-stu-id="23f61-115">Afterwards, you can see the general themes of the data and also organize documents by email threads, near duplicates, and exact duplicates to help your investigation.</span></span> <span data-ttu-id="23f61-116">Дополнительные сведения см. [в статье Run Analytics для более быстрого исследования](run-analytics-to-investigate-faster.md).</span><span class="sxs-lookup"><span data-stu-id="23f61-116">For more information, see [Run analytics to investigate faster](run-analytics-to-investigate-faster.md).</span></span>

## <a name="view-documents-in-evidence"></a><span data-ttu-id="23f61-117">Просмотр документов в свидетельстве</span><span class="sxs-lookup"><span data-stu-id="23f61-117">View documents in evidence</span></span>

<span data-ttu-id="23f61-118">Средство расследования данных (Preview) позволяет отображать содержимое в нескольких различных средствах просмотра, при этом у каждого средства просмотра есть своя цель.</span><span class="sxs-lookup"><span data-stu-id="23f61-118">The Data Investigations (preview) tool allows you to display content in several different viewers, with each viewer having a different purpose.</span></span> <span data-ttu-id="23f61-119">Эти средства просмотра:</span><span class="sxs-lookup"><span data-stu-id="23f61-119">These viewers are:</span></span>

- <span data-ttu-id="23f61-120">Метаданные файла</span><span class="sxs-lookup"><span data-stu-id="23f61-120">File metadata</span></span>
- <span data-ttu-id="23f61-121">Собственное представление</span><span class="sxs-lookup"><span data-stu-id="23f61-121">Native view</span></span>
- <span data-ttu-id="23f61-122">Представление текста</span><span class="sxs-lookup"><span data-stu-id="23f61-122">Text view</span></span>
- <span data-ttu-id="23f61-123">Представление "Примечания"</span><span class="sxs-lookup"><span data-stu-id="23f61-123">Annotate view</span></span>

<span data-ttu-id="23f61-124">Чтобы получить доступ к любому из этих средств просмотра, просто выберите документ в наборе свидетельств.</span><span class="sxs-lookup"><span data-stu-id="23f61-124">To access any of these viewers, just select a document in an evidence set.</span></span>

## <a name="file-metadata"></a><span data-ttu-id="23f61-125">Метаданные файла</span><span class="sxs-lookup"><span data-stu-id="23f61-125">File metadata</span></span>

<span data-ttu-id="23f61-126">В этом представлении отображаются различные свойства метаданных, связанные с выбранным документом.</span><span class="sxs-lookup"><span data-stu-id="23f61-126">This view displays various metadata properties associated with the selected document.</span></span> <span data-ttu-id="23f61-127">Чтобы включить или отключить это представление, щелкните **метаданные файла**.</span><span class="sxs-lookup"><span data-stu-id="23f61-127">You can toggle this view on and off by clicking **File metadata**.</span></span> <span data-ttu-id="23f61-128">При просмотре документа можно просматривать метаданные файла и по-прежнему изменять их между различными средствами просмотра.</span><span class="sxs-lookup"><span data-stu-id="23f61-128">When reviewing a document, you can view the file metadata and still change between the different viewers.</span></span>

<span data-ttu-id="23f61-129">Ниже приведен пример метаданных файла для документа.</span><span class="sxs-lookup"><span data-stu-id="23f61-129">Here's an example of the file metadata for a document.</span></span> <span data-ttu-id="23f61-130">Дополнительные сведения о полях метаданных приведены [в статье Document Data расследования (Предварительная версия)](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="23f61-130">For more information about the metadata fields, see [Document metadata fields in Data Investigations (preview)](document-metadata-fields.md).</span></span>

![Панель метаданных файлов](../media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="23f61-132">Собственное представление</span><span class="sxs-lookup"><span data-stu-id="23f61-132">Native view</span></span>

<span data-ttu-id="23f61-133">В собственном средстве просмотра отображается наиболее точное представление документа в собственном формате.</span><span class="sxs-lookup"><span data-stu-id="23f61-133">The Native viewer displays the most accurate view of a document in its native format.</span></span> <span data-ttu-id="23f61-134">Собственное представление поддерживается для сотен типов файлов и предназначено для отображения документов в собственном интерфейсе труест.</span><span class="sxs-lookup"><span data-stu-id="23f61-134">Native view is supported for hundreds of file types and is meant to display documents in the truest native experience possible.</span></span> <span data-ttu-id="23f61-135">Для файлов Microsoft Office в собственном средстве просмотра используется веб-версия приложений Office.</span><span class="sxs-lookup"><span data-stu-id="23f61-135">For Microsoft Office files, the Native viewer uses the web version of Office apps.</span></span> <span data-ttu-id="23f61-136">Это позволяет просматривать содержимое, например комментарии в различных документах Office, формулах и скрытых строках и столбцах в Excel, а также представление заметок в PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="23f61-136">This allows you to view content such as comments in different Office documents, formulas and hidden rows/columns in Excel, and the Notes view in PowerPoint.</span></span>

![<span data-ttu-id="23f61-137">Собственное представление</span><span class="sxs-lookup"><span data-stu-id="23f61-137">Native view</span></span>
](../media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="23f61-138">Представление текста</span><span class="sxs-lookup"><span data-stu-id="23f61-138">Text view</span></span>

<span data-ttu-id="23f61-139">Средство просмотра текста предоставляет представление извлеченного текста файла.</span><span class="sxs-lookup"><span data-stu-id="23f61-139">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="23f61-140">Он игнорирует все внедренные изображения и форматирование, но это представление полезно, если вы пытаетесь быстро просмотреть и изучить содержимое документа.</span><span class="sxs-lookup"><span data-stu-id="23f61-140">It ignores any embedded images and formatting, but this view is useful if you're trying to quickly review and understand the content in a document.</span></span> <span data-ttu-id="23f61-141">Кроме того, в текстовое представление включены следующие функции:</span><span class="sxs-lookup"><span data-stu-id="23f61-141">Text view also includes these features:</span></span>

  - <span data-ttu-id="23f61-142">Счетчик линий, упрощающий ссылки на определенные части документа.</span><span class="sxs-lookup"><span data-stu-id="23f61-142">A line counter, which makes it easier to reference specific portions of a document.</span></span>

  - <span data-ttu-id="23f61-143">Выделение совпадений поиска, выделяющий термины в документе, а также на полосу прокрутки</span><span class="sxs-lookup"><span data-stu-id="23f61-143">Search hit highlighting that highlight terms in the document as well as on the scrollbar</span></span>

  - <span data-ttu-id="23f61-144">Представление diff предоставляет представление сравнения, которое выделяет текстовые различия при просмотре документов с помощью панели **близких дубликатов** .</span><span class="sxs-lookup"><span data-stu-id="23f61-144">A diff view provides a comparison view that highlights the text differences when viewing documents using the **Near duplicates** panel.</span></span>

<span data-ttu-id="23f61-145">**Пример счетчика линии и выделение совпадений поиска в тексте и полоса прокрутки**</span><span class="sxs-lookup"><span data-stu-id="23f61-145">**Example of line counter and search hit highlighting in text and scrollbar**</span></span>

![<span data-ttu-id="23f61-146">Представление текста</span><span class="sxs-lookup"><span data-stu-id="23f61-146">Text view</span></span>
](../media/Reviewimage4.png)

<span data-ttu-id="23f61-147">**Пример представления diff**</span><span class="sxs-lookup"><span data-stu-id="23f61-147">**Example of the diff view**</span></span>

![<span data-ttu-id="23f61-148">Представление diff</span><span class="sxs-lookup"><span data-stu-id="23f61-148">Diff view</span></span>
](../media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="23f61-149">Представление "Примечания"</span><span class="sxs-lookup"><span data-stu-id="23f61-149">Annotate view</span></span>

<span data-ttu-id="23f61-150">Представление "Примечания" содержит функции, позволяющие применить разметку к документу во время рецензирования. к ним относятся следующие средства:</span><span class="sxs-lookup"><span data-stu-id="23f61-150">The Annotate view provides features that allow you to apply markup on a document during the review process; this  includes these tools:</span></span>

  - <span data-ttu-id="23f61-151">**Исправления областей** — вы можете нарисовать непрозрачное поле в документе, которое скрывает конфиденциальное содержимое.</span><span class="sxs-lookup"><span data-stu-id="23f61-151">**Area redactions** – You can draw an opaque box on the document that hides sensitive content.</span></span>

  - <span data-ttu-id="23f61-152">**Карандаш** — вы можете свободно рисовать в документе, чтобы привлечь внимание к определенным частям содержимого.</span><span class="sxs-lookup"><span data-stu-id="23f61-152">**Pencil** – You can free-hand draw on a document to bring attention to certain portions of the content</span></span>

  - <span data-ttu-id="23f61-153">**Выбор заметок** — вы можете выбирать и удалять примечания в документе.</span><span class="sxs-lookup"><span data-stu-id="23f61-153">**Select annotations** - You can select and delete annotations in a document.</span></span>

  - <span data-ttu-id="23f61-154">**Переключать заметку прозрачность** — можно переключать прозрачность заметок (между непрозрачным и полупрозрачным), чтобы можно было просматривать содержимое, находящихся за заметкой.</span><span class="sxs-lookup"><span data-stu-id="23f61-154">**Toggle annotation transparency** – You can toggle the transparency of annotations (between opaque and semi-transparent) so you can view the content behind the annotation.</span></span> <span data-ttu-id="23f61-155">Это включает в себя переключение прозрачности аннотаций и исправлений карандаша.</span><span class="sxs-lookup"><span data-stu-id="23f61-155">This includes toggling the transparency of pencil annotations and redactions.</span></span>

<span data-ttu-id="23f61-156">Кроме того, в представлении примечаний предусмотрены следующие функции навигации:</span><span class="sxs-lookup"><span data-stu-id="23f61-156">The Annotate view also provides the following navigation functionality:</span></span>

  - <span data-ttu-id="23f61-157">**Предыдущая страница**, **Следующая страница**и **перейдите к** элементам управления навигацией по страницам, чтобы использовать их для многостраничных документов.</span><span class="sxs-lookup"><span data-stu-id="23f61-157">**Previous page**, **Next page**, and **Go to page** - Navigation controls to use for multi-page documents.</span></span>

  - <span data-ttu-id="23f61-158">**Zoom (увеличить** ) — увеличивает или уменьшает размер документов в представлении "Примечания".</span><span class="sxs-lookup"><span data-stu-id="23f61-158">**Zoom** – Increases or decreases the size of documents in Annotate view.</span></span>

  - <span data-ttu-id="23f61-159">**Поворот** — поворот документов по часовой стрелке.</span><span class="sxs-lookup"><span data-stu-id="23f61-159">**Rotate** – Rotate documents clockwise.</span></span>

  - <span data-ttu-id="23f61-160">**Поиск** — Поиск ключевых слов в документе, а затем используйте предыдущий и следующий элементы управления для просмотра совпадений (выделено) в документе.</span><span class="sxs-lookup"><span data-stu-id="23f61-160">**Search** – Search for keywords in a document, and then use Previous and Next controls to view the hits (which are highlighted) within the document.</span></span>

<span data-ttu-id="23f61-161">**Пример представления примечаний**</span><span class="sxs-lookup"><span data-stu-id="23f61-161">**Example of Annotate view**</span></span>

![Представление "Примечания"](../media/Reviewimage1.png)

> [!NOTE]
> <span data-ttu-id="23f61-163">Примечания применяются к копии документа, добавленного в набор свидетельств.</span><span class="sxs-lookup"><span data-stu-id="23f61-163">Annotations are applied to a copy of the document that was added to the evidence set.</span></span> <span data-ttu-id="23f61-164">Исходные документы в службе Live не заметок.</span><span class="sxs-lookup"><span data-stu-id="23f61-164">The original documents in the live service aren't annotated.</span></span>
