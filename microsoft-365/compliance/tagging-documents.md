---
title: Добавление тегов к документам в наборе для проверки
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
ms.assetid: ''
description: Добавление тегов к документам в наборе для проверки помогает удалить ненужный контент и определить релевантный контент в случае Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285285"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="9ff6e-103">Пометка документов в наборе для проверки в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="9ff6e-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="9ff6e-104">Организация контента в наборе для проверки важна для выполнения различных процессов в процессе eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="9ff6e-105">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="9ff6e-105">This includes:</span></span>

- <span data-ttu-id="9ff6e-106">Отсчитывание ненужного содержимого</span><span class="sxs-lookup"><span data-stu-id="9ff6e-106">Culling unnecessary content</span></span>

- <span data-ttu-id="9ff6e-107">Определение релевантной информации</span><span class="sxs-lookup"><span data-stu-id="9ff6e-107">Identifying relevant content</span></span>
 
- <span data-ttu-id="9ff6e-108">Определение контента, который должен просмотреть эксперт или адвокат</span><span class="sxs-lookup"><span data-stu-id="9ff6e-108">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="9ff6e-109">Когда эксперты, адвокаты или другие пользователи просматривают содержимое в наборе для проверки, их мнение, связанное с содержимым, можно фиксировать с помощью тегов.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="9ff6e-110">Например, если целью является отоимствовать ненужное содержимое, пользователь может пометить документы тегом, например "не отвечать".</span><span class="sxs-lookup"><span data-stu-id="9ff6e-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="9ff6e-111">После проверки и маркировки контента можно создать поиск в наборе для проверки, чтобы исключить любой контент, помеченный как "неотвечивая", что исключает этот контент из следующих действий рабочего процесса eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive", which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="9ff6e-112">Панель тегов можно настроить для каждого случая, чтобы теги могли поддерживать рабочий процесс проверки.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-112">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="9ff6e-113">Типы тегов</span><span class="sxs-lookup"><span data-stu-id="9ff6e-113">Tag types</span></span>

<span data-ttu-id="9ff6e-114">Advanced eDiscovery предоставляет два типа тегов:</span><span class="sxs-lookup"><span data-stu-id="9ff6e-114">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="9ff6e-115">**Теги единого выбора—** ограничивает пользователей выбором одного тега в группе.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-115">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="9ff6e-116">Это может быть полезно, чтобы пользователи не выбирали конфликтующие теги, такие как "отзывчивый" и "не реагирующий".</span><span class="sxs-lookup"><span data-stu-id="9ff6e-116">This can be useful to ensure users don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="9ff6e-117">Они будут отображаться в качестве кнопок.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-117">These will appear as radio buttons.</span></span>

- <span data-ttu-id="9ff6e-118">**Несколько тегов выбора** — разрешить пользователям выбирать несколько тегов в группе.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-118">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="9ff6e-119">Они будут отображаться в качестве контрольных тона.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-119">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="9ff6e-120">Структура тегов</span><span class="sxs-lookup"><span data-stu-id="9ff6e-120">Tag structure</span></span>

<span data-ttu-id="9ff6e-121">Помимо типов тегов, структуру организации тегов в области тегов можно использовать, чтобы сделать документы тегов более интуитивно понятными.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-121">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="9ff6e-122">Теги сгруппировали по разделам.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-122">Tags are grouped by sections.</span></span> <span data-ttu-id="9ff6e-123">Поиск в наборе для проверки поддерживает возможность поиска по тегам и разделам тегов.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-123">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="9ff6e-124">Это означает, что вы можете создать поиск в наборе для проверки, чтобы получить документы, помеченные любым тегом в разделе.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-124">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Разделы тегов на панели тегов](../media/Tagtypes.png)

<span data-ttu-id="9ff6e-126">Теги могут быть более уорганизованы путем их вложения в раздел.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-126">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="9ff6e-127">Например, если целью является идентификация и пометка привилегированного содержимого, можно использовать вложенные данные, чтобы понять, что пользователь может пометить документ как "Привилегированный" и выбрать тип привилегий, проверив соответствующий вложенный тег.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-127">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![Вложенные теги в разделе тегов](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="9ff6e-129">Применение тегов</span><span class="sxs-lookup"><span data-stu-id="9ff6e-129">Applying tags</span></span>

<span data-ttu-id="9ff6e-130">Существует несколько способов применения тега к содержимому.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-130">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="9ff6e-131">Добавление тегов к одному документу</span><span class="sxs-lookup"><span data-stu-id="9ff6e-131">Tagging a single document</span></span>

<span data-ttu-id="9ff6e-132">При просмотре документа в наборе для проверки можно отобразить теги, которые может использовать проверка, щелкнув панель **тегов.**</span><span class="sxs-lookup"><span data-stu-id="9ff6e-132">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![Щелкните панель тегов, чтобы отобразить панель тегов](../media/Singledoctag.png)

<span data-ttu-id="9ff6e-134">Это позволит применять теги к документу, отображаемму в представлении.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-134">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="9ff6e-135">Массовое добавление тегов</span><span class="sxs-lookup"><span data-stu-id="9ff6e-135">Bulk tagging</span></span>

<span data-ttu-id="9ff6e-136">Массовое добавление тегов можно сделать путем выбора нескольких файлов в сетке результатов, а затем с помощью тегов на панели тегов аналогично пометке отдельных документов. </span><span class="sxs-lookup"><span data-stu-id="9ff6e-136">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="9ff6e-137">Массовое разметку можно сделать, выбрав теги дважды; При первом щелчке тег будет применяться, а второй выбор обеспечит очистку тега для всех выбранных файлов.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-137">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![Снимок экрана с автоматически созданным описанием мобильного телефона](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="9ff6e-139">При массовом присвоении тегов на панели тегов отображается количество файлов, помеченных для каждого тега на панели.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-139">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="9ff6e-140">Добавление тегов на других панелях проверки</span><span class="sxs-lookup"><span data-stu-id="9ff6e-140">Tagging in other review panels</span></span>

<span data-ttu-id="9ff6e-141">При просмотре документов можно использовать другие панели проверки для просмотра других характеристик документов в сетке результатов.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-141">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="9ff6e-142">Это включает просмотр других связанных документов, потоков электронной почты, почти дубликатов и дубликатов hash.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-142">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="9ff6e-143">Например, при просмотре связанных документов (с помощью  панели проверки семейства документов) можно значительно сократить время проверки путем массовой маркировки связанных документов.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-143">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="9ff6e-144">Например, если в сообщении электронной почты есть несколько вложений и вы хотите убедиться, что все семейство помечено согласованно.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-144">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="9ff6e-145">Например, вот как отобразить панель **тегов** при использовании панели проверки семейства документов: </span><span class="sxs-lookup"><span data-stu-id="9ff6e-145">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="9ff6e-146">Открыв панель проверки для выбранного документа (например, отображая список  связанного контента  на панели проверки семейства документов, щелкните "Пометить документы" в панели проверки семейства документов.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-146">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="9ff6e-147">Панель тегов отображается как всплывающее окно.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-147">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="9ff6e-148">Выберите один или несколько тегов, чтобы применить выбранный документ.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-148">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="9ff6e-149">Чтобы пометить все документы,  выберите все документы на панели семейства документов, щелкните "Тег документов" и выберите теги, которые будут применяться для всего семейства документов.</span><span class="sxs-lookup"><span data-stu-id="9ff6e-149">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![Автоматически создан снимок экрана с описанием публикации в социальных сетях](../media/Relatedtag.png)
