---
title: Поиск и маркировка
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: В Advanced eDiscovery модуль поиска и тегирования позволяет искать, просматривать и упорядочивать документы в своем случае. В настоящее время этот модуль находится в бета-версии.
ms.openlocfilehash: 012154e117e0d2b800f0e1077d43f2e1c1d10b0e
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557809"
---
# <a name="search-and-tagging"></a><span data-ttu-id="a7ff1-104">Поиск и маркировка</span><span class="sxs-lookup"><span data-stu-id="a7ff1-104">Search and Tagging</span></span>

<span data-ttu-id="a7ff1-105">В Advanced eDiscovery модуль поиска и тегирования позволяет искать, просматривать и упорядочивать документы в своем случае.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-105">In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case.</span></span> <span data-ttu-id="a7ff1-106">В настоящее время этот модуль находится в бета-версии.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-106">Currently, this module is in beta.</span></span> <span data-ttu-id="a7ff1-107">Краткий пример поиска и маркировки можно найти в статье [Управление данными с помощью расширенного видео eDiscovery](https://www.youtube.com/watch?v=VaPYL3DHP6I) .</span><span class="sxs-lookup"><span data-stu-id="a7ff1-107">For a brief demonstration of searching and tagging, see the [Manage your data with Advanced eDiscovery](https://www.youtube.com/watch?v=VaPYL3DHP6I) video.</span></span>

> [!NOTE]
> <span data-ttu-id="a7ff1-p103">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="a7ff1-p103">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="search-the-documents-in-your-case"></a><span data-ttu-id="a7ff1-110">Поиск в документах в своем случае</span><span class="sxs-lookup"><span data-stu-id="a7ff1-110">Search the documents in your case</span></span>

<span data-ttu-id="a7ff1-111">После обработки документов в расширенном случае обнаружения электронных данных (и при необходимости запуска модуля анализа или релевантности) можно использовать поиск и маркировку для поиска документов, а затем упорядочивать их, применяя теги, зависящие от регистра (также называемые метками).</span><span class="sxs-lookup"><span data-stu-id="a7ff1-111">After you have processed documents in an Advanced eDiscovery case (and optionally run the Analyze or Relevance module), you can use the Search and Tagging to search documents and then organize them by applying case-specific tags (also called labels).</span></span> <span data-ttu-id="a7ff1-112">Вы можете определить поисковый запрос с помощью предоставленных карточек условий или с помощью KQL языка запросов в карточке ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-112">You can define a search query using the provided condition cards or by using a KQL-like query language in the Keywords condition card.</span></span> <span data-ttu-id="a7ff1-113">Поддерживается общий синтаксис KQL, например, AND, OR, NOT и NEAR (n), а также замыкающий символ подстановочного знака (\*).</span><span class="sxs-lookup"><span data-stu-id="a7ff1-113">Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (\*).</span></span> 

<span data-ttu-id="a7ff1-114">В следующей таблице перечислены свойства, которые можно искать с помощью запроса ключевого слова KQL.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-114">The following table lists the properties that you can search for using a KQL keyword query.</span></span> <span data-ttu-id="a7ff1-115">Кроме того, вы можете использовать карточку условия в средстве расширенного поиска eDiscovery для добавления условия (для выбранных свойств) в поисковый запрос.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-115">Alternatively, you can use a condition card for in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span>

|<span data-ttu-id="a7ff1-116">**Свойство**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-116">**Property**</span></span>|<span data-ttu-id="a7ff1-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a7ff1-118">**каселабел**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-118">**caselabel**</span></span> <br/> | <span data-ttu-id="a7ff1-119">Имя тега, созданного/примененного при разметке документа.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-119">The name of the tag created/applied when a document is tagged.</span></span> <br/> |
|<span data-ttu-id="a7ff1-120">**Хранитель**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-120">**custodian**</span></span> <br/> | <span data-ttu-id="a7ff1-121">Хранитель, связанный с документом; подлежит ограничениям.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-121">The custodian associated with a document; subject to limitations.</span></span> <br/> |
|<span data-ttu-id="a7ff1-122">**дата**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-122">**date**</span></span> <br/> | <span data-ttu-id="a7ff1-123">Дата отправки для электронной почты; Дата изменения документов сайта.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-123">Sent date for email; the modified date for site documents.</span></span> <br/> |
|<span data-ttu-id="a7ff1-124">**ИД**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-124">**fileid**</span></span> <br/> | <span data-ttu-id="a7ff1-125">Идентификатор файла в случае.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-125">The File ID within the case.</span></span> <br/> |
|<span data-ttu-id="a7ff1-126">**filetype**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-126">**filetype**</span></span> <br/> | <span data-ttu-id="a7ff1-127">Собственное расширение файла.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-127">The native file extension.</span></span> <br/> |
|<span data-ttu-id="a7ff1-128">**филекласс**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-128">**fileclass**</span></span> <br/> | <span data-ttu-id="a7ff1-129">Электронная почта, документ или вложение.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-129">Email, document, or attachment.</span></span> <br/> |
|<span data-ttu-id="a7ff1-130">**сендераусор**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-130">**senderauthor**</span></span> <br/> | <span data-ttu-id="a7ff1-131">Отправитель сообщения электронной почты; Автор документов сайта.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-131">The sender for email; the author for site documents.</span></span> <br/> |
|<span data-ttu-id="a7ff1-132">**size**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-132">**size**</span></span> <br/> | <span data-ttu-id="a7ff1-133">Размер файла в КИЛОБАЙТах.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-133">The size of the file in KB.</span></span> <br/> |
|<span data-ttu-id="a7ff1-134">**субжекттитле**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-134">**subjecttitle**</span></span> <br/> | <span data-ttu-id="a7ff1-135">Тема сообщения электронной почты; название документов сайта.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-135">The subject for email; the title for site documents.</span></span> <br/> |
|<span data-ttu-id="a7ff1-136">**bcc**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-136">**bcc**</span></span> <br/> | <span data-ttu-id="a7ff1-137">Поле "Скрытая копия" сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-137">The Bcc field of an email.</span></span> <br/> |
|<span data-ttu-id="a7ff1-138">**cc**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-138">**cc**</span></span> <br/> | <span data-ttu-id="a7ff1-139">Поле "копия" сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-139">The Cc field of an email.</span></span> <br/> |
|<span data-ttu-id="a7ff1-140">**participants**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-140">**participants**</span></span> <br/> | <span data-ttu-id="a7ff1-141">Адрес электронной почты всех участников в цепочке электронной почты, в том числе отсутствующие ссылки.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-141">The email address of all participants in an email thread, including for missing links.</span></span> <br/> |
|<span data-ttu-id="a7ff1-142">**received**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-142">**received**</span></span> <br/> | <span data-ttu-id="a7ff1-143">Дата получения электронного сообщения.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-143">The date an email was received.</span></span> <br/> |
|<span data-ttu-id="a7ff1-144">**recipients**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-144">**recipients**</span></span> <br/> | <span data-ttu-id="a7ff1-145">Получатели сообщения электронной почты, включаемые в поля "Кому", "копия" или "Скрытая копия".</span><span class="sxs-lookup"><span data-stu-id="a7ff1-145">Recipients of an email, included on the To, Cc, or Bcc fields.</span></span> <br/> |
|<span data-ttu-id="a7ff1-146">**sender**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-146">**sender**</span></span> <br/> | <span data-ttu-id="a7ff1-147">Отправитель сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-147">The sender of an email.</span></span> <br/> |
|<span data-ttu-id="a7ff1-148">**ластмодифиеддате**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-148">**lastmodifieddate**</span></span> <br/> | <span data-ttu-id="a7ff1-149">Дата последнего изменения документа сайта.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-149">The last modified date of a site document.</span></span> <br/> |
|<span data-ttu-id="a7ff1-150">**sent**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-150">**sent**</span></span> <br/> | <span data-ttu-id="a7ff1-151">Дата отправки сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-151">The sent date of an email.</span></span> <br/> |
|<span data-ttu-id="a7ff1-152">**to**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-152">**to**</span></span> <br/> | <span data-ttu-id="a7ff1-153">Получатель, указанный в поле "Кому" сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-153">The recipient listed in the To field of an email.</span></span> <br/> |
|<span data-ttu-id="a7ff1-154">**Редактирование**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-154">**author**</span></span> <br/> | <span data-ttu-id="a7ff1-155">Автор документа сайта.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-155">The author of a site document.</span></span> <br/> |
|<span data-ttu-id="a7ff1-156">**заголовок**</span><span class="sxs-lookup"><span data-stu-id="a7ff1-156">**title**</span></span> <br/> | <span data-ttu-id="a7ff1-157">Название документа сайта.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-157">The title of a site document.</span></span> <br/> |
|<span data-ttu-id="a7ff1-158">**доминантсеме**\*</span><span class="sxs-lookup"><span data-stu-id="a7ff1-158">**dominanttheme**\*</span></span> <br/> | <span data-ttu-id="a7ff1-159">Тема элемента.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-159">The dominant theme of an item.</span></span> <br/> |
|<span data-ttu-id="a7ff1-160">**семеслист**\*</span><span class="sxs-lookup"><span data-stu-id="a7ff1-160">**themeslist**\*</span></span> <br/> | <span data-ttu-id="a7ff1-161">Темы, связанные с элементом.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-161">Themes that are associated with an item.</span></span> <br/> |
|<span data-ttu-id="a7ff1-162">**readpercentile_ [иссуенум]**\*\*</span><span class="sxs-lookup"><span data-stu-id="a7ff1-162">**readpercentile_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="a7ff1-163">Засчитанный процентиль элемента для вопроса, определяемого [иссуенум].</span><span class="sxs-lookup"><span data-stu-id="a7ff1-163">The read percentile of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="a7ff1-164">**relevancescore_ [иссуенум]**\*\*</span><span class="sxs-lookup"><span data-stu-id="a7ff1-164">**relevancescore_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="a7ff1-165">Показатель релевантности элемента для вопроса, определенного с помощью [иссуенум].</span><span class="sxs-lookup"><span data-stu-id="a7ff1-165">The relevance score of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="a7ff1-166">**relevancetag_ [TagName]**\*\*</span><span class="sxs-lookup"><span data-stu-id="a7ff1-166">**relevancetag_[tagname]**\*\*</span></span> <br/> | <span data-ttu-id="a7ff1-167">Если элемент был помечен вручную для релевантности, тег определяется [TagName].</span><span class="sxs-lookup"><span data-stu-id="a7ff1-167">If an item has been manually tagged for relevance, the tag defined by  [tagname].</span></span> <br/> |
|||

<span data-ttu-id="a7ff1-168">\*Доступно только в том случае, если запущен модуль Themes.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-168">\* Only available if the Themes module has been run.</span></span>

<span data-ttu-id="a7ff1-169">\*\*Доступно, только если запущен модуль релевантности.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-169">\*\* Only available if the Relevance module has been run.</span></span>

<span data-ttu-id="a7ff1-170">Кроме того, вы можете использовать карточку условия в средстве расширенного поиска eDiscovery, чтобы добавить условие (для выбранных свойств) в поисковый запрос.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-170">Alternatively, you can use a condition card in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span> <span data-ttu-id="a7ff1-171">На следующем снимке экрана показаны условия, которые можно добавить в запрос.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-171">The following screenshot shows the conditions that can be added to a query.</span></span> <span data-ttu-id="a7ff1-172">Столбец **Group** указывает, применяется ли свойство к электронной почте, документам сайта или обоим (указывается *общим*значением).</span><span class="sxs-lookup"><span data-stu-id="a7ff1-172">The **Group** column indicates whether the property applies to email, site documents, or both (indicated by the value *Common*).</span></span> <span data-ttu-id="a7ff1-173">Этот столбец также определяет доступные для поиска свойства, доступные после запуска модуля релевантности.</span><span class="sxs-lookup"><span data-stu-id="a7ff1-173">This column also identifies the searchable properties that are available after you run the Relevance module.</span></span>

![Условия поиска в расширенном средстве поиска eDiscovery](../media/AeDSearchConditions.png)

<span data-ttu-id="a7ff1-175">Дополнительные сведения о свойствах, включаемых в поиск, можно найти в разделе [запросы и условия поиска по ключевым словам](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="a7ff1-175">For more information about searchable properties, see [Keyword queries and search conditions](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a7ff1-176">См. также</span><span class="sxs-lookup"><span data-stu-id="a7ff1-176">See also</span></span>

[<span data-ttu-id="a7ff1-177">Расширенное обнаружение электронных данных (классический)</span><span class="sxs-lookup"><span data-stu-id="a7ff1-177">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="a7ff1-178">Понимание оценки релевантности</span><span class="sxs-lookup"><span data-stu-id="a7ff1-178">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a7ff1-179">Маркировка и оценка</span><span class="sxs-lookup"><span data-stu-id="a7ff1-179">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a7ff1-180">Расстановка тегов и релевантности</span><span class="sxs-lookup"><span data-stu-id="a7ff1-180">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a7ff1-181">Анализ релевантности отслеживания</span><span class="sxs-lookup"><span data-stu-id="a7ff1-181">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a7ff1-182">Выбор на основе результатов</span><span class="sxs-lookup"><span data-stu-id="a7ff1-182">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a7ff1-183">Анализ релевантности тестирования</span><span class="sxs-lookup"><span data-stu-id="a7ff1-183">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

