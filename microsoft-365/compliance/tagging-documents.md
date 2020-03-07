---
title: Добавление тегов к документам в наборе для проверки
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 1c0eaed5d5971a55e4e9851bac3133bcd961eb36
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557699"
---
# <a name="tag-documents-in-a-review-set"></a><span data-ttu-id="f5289-102">Добавление тегов к документам в наборе для проверки</span><span class="sxs-lookup"><span data-stu-id="f5289-102">Tag documents in a review set</span></span>

<span data-ttu-id="f5289-103">Организация контента в наборе проверки важна для выполнения различных рабочих процессов в процессе обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="f5289-103">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="f5289-104">В частности, импорт позволяет:</span><span class="sxs-lookup"><span data-stu-id="f5289-104">This includes:</span></span>

- <span data-ttu-id="f5289-105">Отбор ненужного контента</span><span class="sxs-lookup"><span data-stu-id="f5289-105">Culling unnecessary content</span></span>

- <span data-ttu-id="f5289-106">Определение релевантного содержимого</span><span class="sxs-lookup"><span data-stu-id="f5289-106">Identifying relevant content</span></span>
 
- <span data-ttu-id="f5289-107">Определение контента, который должен быть проверен экспертом или юристом</span><span class="sxs-lookup"><span data-stu-id="f5289-107">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="f5289-108">Когда эксперты, юристы или другие пользователи просматривают контент в наборе рецензирования, их мнения, связанные с содержимым, могут быть захвачены с помощью тегов.</span><span class="sxs-lookup"><span data-stu-id="f5289-108">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="f5289-109">Например, если предполагалось исключать ненужное содержимое, пользователь может отмечать документы тегами, например "не отвечает".</span><span class="sxs-lookup"><span data-stu-id="f5289-109">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as “non-responsive”.</span></span> <span data-ttu-id="f5289-110">После рассмотрения и пометки контента можно создать поисковый набор для исключения любого содержимого, помеченного как "не отвечает", что исключает это содержимое из следующих действий в рабочем процессе обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="f5289-110">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as “non-responsive”, which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="f5289-111">Область тегов можно изменить для каждого случая, чтобы теги могли поддерживать рабочий процесс, предназначенный для рецензирования.</span><span class="sxs-lookup"><span data-stu-id="f5289-111">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="f5289-112">Типы тегов</span><span class="sxs-lookup"><span data-stu-id="f5289-112">Tag types</span></span>

<span data-ttu-id="f5289-113">Расширенное обнаружение электронных данных предоставляет два типа тегов:</span><span class="sxs-lookup"><span data-stu-id="f5289-113">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="f5289-114">**Один тег выбора** — запрещает пользователям выбирать один тег в группе.</span><span class="sxs-lookup"><span data-stu-id="f5289-114">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="f5289-115">Это может быть удобно, чтобы пользователи не могли выбирать конфликтующие теги, такие как "реагирующий" и "не отвечает".</span><span class="sxs-lookup"><span data-stu-id="f5289-115">This can be useful to ensure users don’t select conflicting tags such as “responsive” and “non-responsive”.</span></span> <span data-ttu-id="f5289-116">Они будут отображаться в виде переключателей.</span><span class="sxs-lookup"><span data-stu-id="f5289-116">These will appear as radio buttons.</span></span>

- <span data-ttu-id="f5289-117">**Несколько тегов выбора** — позволяет пользователям выбирать несколько тегов в группе.</span><span class="sxs-lookup"><span data-stu-id="f5289-117">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="f5289-118">Они будут отображаться в качестве флажков.</span><span class="sxs-lookup"><span data-stu-id="f5289-118">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="f5289-119">Структура тегов</span><span class="sxs-lookup"><span data-stu-id="f5289-119">Tag structure</span></span>

<span data-ttu-id="f5289-120">В дополнение к типам тегов, структура того, как теги организованы в палитре тегов, может использоваться для упрощения интуитивной маркировки документов.</span><span class="sxs-lookup"><span data-stu-id="f5289-120">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="f5289-121">Теги группируются по разделам.</span><span class="sxs-lookup"><span data-stu-id="f5289-121">Tags are grouped by sections.</span></span> <span data-ttu-id="f5289-122">Обзор Set Search поддерживает поиск по разделу "возможность поиска по тегам и тегу".</span><span class="sxs-lookup"><span data-stu-id="f5289-122">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="f5289-123">Это означает, что вы можете создать поисковый набор для получения документов, помеченных тегом в разделе.</span><span class="sxs-lookup"><span data-stu-id="f5289-123">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Разделы с тегами в панели тегов](../media/Tagtypes.png)

<span data-ttu-id="f5289-125">Теги можно упорядочить, дополнив их вложение в раздел.</span><span class="sxs-lookup"><span data-stu-id="f5289-125">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="f5289-126">Например, если предполагается определить и пометить привилегированный контент, можно использовать вложение, чтобы сделать так, чтобы пользователь мог пометить документ как "Привилегированный" и выбрать тип привилегий, проверив соответствующий вложенный тег.</span><span class="sxs-lookup"><span data-stu-id="f5289-126">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as “Privileged” and select the type of privilege by checking the appropriate nested tag.</span></span>

![Вложенные теги в разделе тегов](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="f5289-128">Применение тегов</span><span class="sxs-lookup"><span data-stu-id="f5289-128">Applying tags</span></span>

<span data-ttu-id="f5289-129">Существует несколько способов применения тега к контенту.</span><span class="sxs-lookup"><span data-stu-id="f5289-129">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="f5289-130">Добавление тегов для одного документа</span><span class="sxs-lookup"><span data-stu-id="f5289-130">Tagging a single document</span></span>

<span data-ttu-id="f5289-131">При просмотре документа в наборе рецензирования можно отобразить теги, которые может использовать проверка, щелкнув **панель маркировки**.</span><span class="sxs-lookup"><span data-stu-id="f5289-131">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![Щелкните панель тегов, чтобы отобразить панель тегов](../media/Singledoctag.png)

<span data-ttu-id="f5289-133">Это позволит применить теги к документу, отображаемому в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="f5289-133">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="f5289-134">Массовая маркировка</span><span class="sxs-lookup"><span data-stu-id="f5289-134">Bulk tagging</span></span>

<span data-ttu-id="f5289-135">Массовое расстановку тегов можно выполнить, выбрав несколько файлов в сетке результатов, а затем используя теги на **панели маркировки** , как при разметке отдельных документов.</span><span class="sxs-lookup"><span data-stu-id="f5289-135">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="f5289-136">Массовое снятие тегов можно выполнить, выбирая Теги дважды; При первом щелчке будет применен тег, а во втором выделенном фрагменте этот тег будет очищен для всех выбранных файлов.</span><span class="sxs-lookup"><span data-stu-id="f5289-136">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![Снимок экрана с автоматическим созданием описания сотового телефона](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="f5289-138">При массовом разметке на панели маркировки отображается количество файлов, помеченных для каждого тега в панели.</span><span class="sxs-lookup"><span data-stu-id="f5289-138">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="f5289-139">Добавление тегов в другие панели рецензирования</span><span class="sxs-lookup"><span data-stu-id="f5289-139">Tagging in other review panels</span></span>

<span data-ttu-id="f5289-140">При просмотре документов можно использовать другие панели рецензирования для просмотра других характеристик документов в таблице результатов.</span><span class="sxs-lookup"><span data-stu-id="f5289-140">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="f5289-141">Это включает проверку других связанных документов, почтовых потоков, ближайших дубликатов и хэш-дубликатов.</span><span class="sxs-lookup"><span data-stu-id="f5289-141">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="f5289-142">Например, если вы просматриваете связанные документы (с помощью панели рецензирования **семейства документов** ), вы можете значительно сократить время проверки путем массового разметки связанных документов.</span><span class="sxs-lookup"><span data-stu-id="f5289-142">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="f5289-143">Например, если сообщение электронной почты имеет несколько вложений и вы хотите обеспечить единообразное пометку всех семейств.</span><span class="sxs-lookup"><span data-stu-id="f5289-143">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="f5289-144">Например, вот как можно отобразить **панель расстановки тегов** при использовании панели "Обзор **семейства документов** ":</span><span class="sxs-lookup"><span data-stu-id="f5289-144">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="f5289-145">Откройте панель рецензирование для выбранного документа (например, при отображении списка связанных материалов в панели "Проверка **семейства документов** " щелкните элемент **теги документы** под панелью рецензирование семейства документов.</span><span class="sxs-lookup"><span data-stu-id="f5289-145">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="f5289-146">Панель тегирования отображается в виде всплывающего окна.</span><span class="sxs-lookup"><span data-stu-id="f5289-146">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="f5289-147">Выберите один или несколько тегов, которые необходимо применить к выбранному документу.</span><span class="sxs-lookup"><span data-stu-id="f5289-147">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="f5289-148">Чтобы отметить все документы, выберите все документы в области **семейство документов** , щелкните Теги **документы**, а затем выберите Теги, которые применяются ко всему семейству документов.</span><span class="sxs-lookup"><span data-stu-id="f5289-148">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![Снимок экрана с автоматически созданным описанием записи социальных медиа](../media/Relatedtag.png)
