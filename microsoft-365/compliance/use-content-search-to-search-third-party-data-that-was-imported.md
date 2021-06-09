---
title: Использование поиска контента для поиска импортируемых сторонних данных
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: С помощью средства поиска содержимого для поиска элементов, импортируемых в почтовые ящики в Microsoft 365 из сторонних источников данных, создав запросы.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24ca63cf78b85f7b8b5181d5babd16058b641128
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324575"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="a9908-103">Использование поиска контента для поиска сторонних данных, импортируемых пользовательским соединитетелем партнеров</span><span class="sxs-lookup"><span data-stu-id="a9908-103">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="a9908-104">Вы можете [](content-search.md) использовать средство поиска содержимого в Центре & обеспечения соответствия требованиям для поиска элементов, импортируемых в почтовые ящики Microsoft 365 из сторонних источников данных.</span><span class="sxs-lookup"><span data-stu-id="a9908-104">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="a9908-105">Можно создать запрос для поиска всех импортируемых сторонних элементов данных или создать запрос для поиска определенных сторонних элементов данных.</span><span class="sxs-lookup"><span data-stu-id="a9908-105">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="a9908-106">Кроме того, можно также создать политику хранения на основе запросов или удержание электронных данных на основе запросов для сохранения сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="a9908-106">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="a9908-107">Дополнительные сведения о работе с партнером по импорту сторонних данных и списке типов сторонних данных, которые можно импортировать в Microsoft 365, см. в статью Работа с партнером по архивам [сторонних](work-with-partner-to-archive-third-party-data.md)данных в Office 365 .</span><span class="sxs-lookup"><span data-stu-id="a9908-107">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9908-108">Руководство в этой статье применяется только к сторонним данным, импортируемым пользовательским соединитетелем партнеров.</span><span class="sxs-lookup"><span data-stu-id="a9908-108">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="a9908-109">Эта статья не применяется к сторонним данным, импортируемым с помощью сторонних соединители данных [в](archiving-third-party-data.md#third-party-data-connectors) центре соответствия требованиям Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a9908-109">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="a9908-110">Создание запроса для поиска всех сторонних данных</span><span class="sxs-lookup"><span data-stu-id="a9908-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="a9908-111">Для поиска (или удержания) любых сторонних данных, импортируемых в Office 365, можно использовать пару свойств сообщения в поле ключевого слова для поиска контента или при создании удержания на основе `kind:externaldata` запросов.</span><span class="sxs-lookup"><span data-stu-id="a9908-111">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="a9908-112">Например, для поиска элементов, импортируемых из любого источника сторонних данных и содержащих слово "contoso" в свойстве Subject импортируемого элемента, можно использовать следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="a9908-112">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="a9908-113">В предыдущем примере запроса ключевого слова содержится свойство субъекта.</span><span class="sxs-lookup"><span data-stu-id="a9908-113">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="a9908-114">Список других свойств сторонних элементов данных, которые могут включаться в запрос ключевого слова, см. в разделе "Дополнительные сведения" в разделе Работа с партнером для архива сторонних данных в [Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span><span class="sxs-lookup"><span data-stu-id="a9908-114">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="a9908-115">При создании запросов для поиска и хранения сторонних данных можно также использовать условия, чтобы сузить результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="a9908-115">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="a9908-116">Дополнительные сведения о создании запросов поиска контента см. в статье [Keyword queries and search conditions for Content Search.](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="a9908-116">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="a9908-117">Создание запроса для поиска определенных типов сторонних данных</span><span class="sxs-lookup"><span data-stu-id="a9908-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="a9908-118">Вместо поиска всех типов сторонних данных можно создавать запросы, которые ищут только для конкретного типа сторонних данных, используя следующее свойство *сообщения:* пара значений в поле ключевого слова для поиска контента:</span><span class="sxs-lookup"><span data-stu-id="a9908-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property: value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="a9908-119">Например, для поиска данных Facebook, которые содержат слово "contoso" в свойстве Subject, используется следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="a9908-119">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="a9908-120">В следующей таблице перечислены типы сторонних данных, которые можно искать, и значение, которое необходимо использовать для свойства сообщения для конкретного поиска для этого типа  `itemclass:` сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="a9908-120">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="a9908-121">Синтаксис запроса не является чувствительным к делу.</span><span class="sxs-lookup"><span data-stu-id="a9908-121">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="a9908-122">**Тип сторонних данных**</span><span class="sxs-lookup"><span data-stu-id="a9908-122">**Third-party data type**</span></span>|<span data-ttu-id="a9908-123">**Значение для  `itemclass:` свойства**</span><span class="sxs-lookup"><span data-stu-id="a9908-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a9908-124">AIM</span><span class="sxs-lookup"><span data-stu-id="a9908-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="a9908-125">American Idol;</span><span class="sxs-lookup"><span data-stu-id="a9908-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="a9908-126">AOL с клиентом Pivot;</span><span class="sxs-lookup"><span data-stu-id="a9908-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="a9908-127">Apple Juice;</span><span class="sxs-lookup"><span data-stu-id="a9908-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="a9908-128">Ares</span><span class="sxs-lookup"><span data-stu-id="a9908-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="a9908-129">Axs Encrypted;</span><span class="sxs-lookup"><span data-stu-id="a9908-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="a9908-130">Axs Exchange;</span><span class="sxs-lookup"><span data-stu-id="a9908-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="a9908-131">Axs Local Archive;</span><span class="sxs-lookup"><span data-stu-id="a9908-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="a9908-132">Axs Placeholder</span><span class="sxs-lookup"><span data-stu-id="a9908-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="a9908-133">Axs Signed;</span><span class="sxs-lookup"><span data-stu-id="a9908-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="a9908-134">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="a9908-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="a9908-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="a9908-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="a9908-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="a9908-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="a9908-137">Blackberry</span><span class="sxs-lookup"><span data-stu-id="a9908-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="a9908-138">Журналы вызовов BlackBerry</span><span class="sxs-lookup"><span data-stu-id="a9908-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="a9908-139">Посыльный ежевики</span><span class="sxs-lookup"><span data-stu-id="a9908-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="a9908-140">ПИН-код BlackBerry</span><span class="sxs-lookup"><span data-stu-id="a9908-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="a9908-141">BlackBerry SMS</span><span class="sxs-lookup"><span data-stu-id="a9908-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="a9908-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="a9908-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="a9908-143">Сообщение Bloomberg</span><span class="sxs-lookup"><span data-stu-id="a9908-143">Bloomberg Message</span></span>  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|<span data-ttu-id="a9908-144">Обмен сообщениями Bloomberg</span><span class="sxs-lookup"><span data-stu-id="a9908-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="a9908-145">Box</span><span class="sxs-lookup"><span data-stu-id="a9908-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="a9908-146">Сервер присутствия Cisco IM &amp;</span><span class="sxs-lookup"><span data-stu-id="a9908-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="a9908-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="a9908-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="a9908-148">CipherCloud для Salesforce Chatter;</span><span class="sxs-lookup"><span data-stu-id="a9908-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="a9908-149">Direct Connect;</span><span class="sxs-lookup"><span data-stu-id="a9908-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="a9908-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="a9908-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="a9908-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="a9908-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="a9908-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="a9908-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="a9908-153">Flickr</span><span class="sxs-lookup"><span data-stu-id="a9908-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="a9908-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="a9908-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="a9908-155">Google+</span><span class="sxs-lookup"><span data-stu-id="a9908-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="a9908-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="a9908-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="a9908-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="a9908-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="a9908-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="a9908-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="a9908-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="a9908-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="a9908-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="a9908-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="a9908-161">Подключения IBM</span><span class="sxs-lookup"><span data-stu-id="a9908-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="a9908-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="a9908-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="a9908-163">ICE Chat</span><span class="sxs-lookup"><span data-stu-id="a9908-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|<span data-ttu-id="a9908-164">Indii Messenger;</span><span class="sxs-lookup"><span data-stu-id="a9908-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="a9908-165">Instagram</span><span class="sxs-lookup"><span data-stu-id="a9908-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="a9908-166">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="a9908-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="a9908-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="a9908-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="a9908-168">IRC</span><span class="sxs-lookup"><span data-stu-id="a9908-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="a9908-169">Jive</span><span class="sxs-lookup"><span data-stu-id="a9908-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="a9908-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="a9908-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="a9908-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="a9908-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="a9908-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="a9908-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="a9908-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="a9908-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="a9908-174">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="a9908-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="a9908-175">Согласование умов</span><span class="sxs-lookup"><span data-stu-id="a9908-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="a9908-176">Mobile Guard;</span><span class="sxs-lookup"><span data-stu-id="a9908-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="a9908-177">MSN</span><span class="sxs-lookup"><span data-stu-id="a9908-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="a9908-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="a9908-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="a9908-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="a9908-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="a9908-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="a9908-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="a9908-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="a9908-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="a9908-182">Pivot</span><span class="sxs-lookup"><span data-stu-id="a9908-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="a9908-183">QQ</span><span class="sxs-lookup"><span data-stu-id="a9908-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="a9908-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="a9908-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="a9908-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="a9908-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="a9908-186">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a9908-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="a9908-187">Slack Enterprise Grid;</span><span class="sxs-lookup"><span data-stu-id="a9908-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="a9908-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="a9908-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="a9908-189">Squawker</span><span class="sxs-lookup"><span data-stu-id="a9908-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="a9908-190">Symphony</span><span class="sxs-lookup"><span data-stu-id="a9908-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="a9908-191">Thomson Reuters.</span><span class="sxs-lookup"><span data-stu-id="a9908-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="a9908-192">Thomson Reuters Eikon Messenger.</span><span class="sxs-lookup"><span data-stu-id="a9908-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="a9908-193">Tor</span><span class="sxs-lookup"><span data-stu-id="a9908-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="a9908-194">TTT</span><span class="sxs-lookup"><span data-stu-id="a9908-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="a9908-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="a9908-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="a9908-196">UBS Chat;</span><span class="sxs-lookup"><span data-stu-id="a9908-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="a9908-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="a9908-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="a9908-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="a9908-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="a9908-199">Winny</span><span class="sxs-lookup"><span data-stu-id="a9908-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="a9908-200">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="a9908-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="a9908-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="a9908-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="a9908-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="a9908-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="a9908-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="a9908-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
