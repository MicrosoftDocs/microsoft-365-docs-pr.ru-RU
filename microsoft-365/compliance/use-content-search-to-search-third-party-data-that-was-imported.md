---
title: Поиск импортируемых сторонних данных с помощью поиска контента
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
description: Используйте средство eDiscovery поиска контента для поиска элементов, импортируемых в почтовые ящики в Microsoft 365 из стороного источника данных, создавая запросы.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24ca63cf78b85f7b8b5181d5babd16058b641128
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324575"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="a58da-103">Использование поиска контента для поиска сторонних данных, импортируемых пользовательским партнерским соединитетелем</span><span class="sxs-lookup"><span data-stu-id="a58da-103">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="a58da-104">Вы можете использовать средство [eDiscovery](content-search.md) поиска контента в Центре безопасности & соответствия требованиям для поиска элементов, импортируемых в почтовые ящики в Microsoft 365 из стороного источника данных.</span><span class="sxs-lookup"><span data-stu-id="a58da-104">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="a58da-105">Можно создать запрос для поиска всех импортируемых элементов сторонних данных или создать запрос для поиска определенных элементов сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="a58da-105">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="a58da-106">Кроме того, вы можете создать политику хранения на основе запроса или удержание на основе электронных данных на основе запросов, чтобы сохранить сторонние данные.</span><span class="sxs-lookup"><span data-stu-id="a58da-106">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="a58da-107">Дополнительные сведения о работе с партнером по импорту сторонних данных и список типов сторонних данных, которые можно импортировать в Microsoft 365, см. в совместной работе с партнером по архивам сторонних данных [в Office 365.](work-with-partner-to-archive-third-party-data.md)</span><span class="sxs-lookup"><span data-stu-id="a58da-107">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a58da-108">Инструкции в этой статье применимы только к сторонним данным, импортируемым пользовательским партнерским соединитетелем.</span><span class="sxs-lookup"><span data-stu-id="a58da-108">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="a58da-109">Эта статья не относится к сторонним данным, импортируемым с помощью сторонних соединители данных [в](archiving-third-party-data.md#third-party-data-connectors) Центре соответствия требованиям Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a58da-109">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="a58da-110">Создание запроса для поиска всех сторонних данных</span><span class="sxs-lookup"><span data-stu-id="a58da-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="a58da-111">Чтобы искать (или удерживать) любые сторонние данные, импортируемые в Office 365, можно использовать пару "свойство-значение" сообщения в поле ключевых слов для поиска контента или при создании удержания на основе  `kind:externaldata` запроса.</span><span class="sxs-lookup"><span data-stu-id="a58da-111">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="a58da-112">Например, чтобы найти элементы, импортируемые из любого стороненного источника данных и содержащие слово "contoso" в свойстве Subject импортируемого элемента, следует использовать следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="a58da-112">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="a58da-113">В предыдущем примере запроса ключевого слова содержится свойство subject.</span><span class="sxs-lookup"><span data-stu-id="a58da-113">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="a58da-114">Список других свойств сторонних элементов данных, которые могут быть включены в запрос по ключевому слову, см. в разделе "Дополнительные сведения" статьи "Работа с партнером по архивам сторонних данных в [Office 365".](work-with-partner-to-archive-third-party-data.md#more-information)</span><span class="sxs-lookup"><span data-stu-id="a58da-114">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="a58da-115">При создании запросов для поиска и хранения сторонних данных можно также использовать условия для сужение результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="a58da-115">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="a58da-116">Дополнительные сведения о создании запросов на поиск контента см. в статье "Запросы по ключевым словам и условия поиска [контента".](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="a58da-116">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="a58da-117">Создание запроса для поиска определенных типов сторонних данных</span><span class="sxs-lookup"><span data-stu-id="a58da-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="a58da-118">Вместо поиска по всем типам сторонних данных можно создавать запросы, которые ищут только определенные типы сторонних данных, используя следующее свойство *сообщения:* пару значений в поле ключевых слов для поиска контента:</span><span class="sxs-lookup"><span data-stu-id="a58da-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property: value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="a58da-119">Например, чтобы найти данные Facebook, которые содержат слово "contoso" в свойстве Subject, используйте следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="a58da-119">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="a58da-120">В следующей таблице перечислены типы сторонних данных, которые можно искать, и значение свойства сообщения для специального поиска таких  `itemclass:` данных.</span><span class="sxs-lookup"><span data-stu-id="a58da-120">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="a58da-121">Синтаксис запроса не чувствителен к делу.</span><span class="sxs-lookup"><span data-stu-id="a58da-121">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="a58da-122">**Тип данных сторонних пользователей**</span><span class="sxs-lookup"><span data-stu-id="a58da-122">**Third-party data type**</span></span>|<span data-ttu-id="a58da-123">**Значение  `itemclass:` свойства**</span><span class="sxs-lookup"><span data-stu-id="a58da-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a58da-124">AIM</span><span class="sxs-lookup"><span data-stu-id="a58da-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="a58da-125">American Idol;</span><span class="sxs-lookup"><span data-stu-id="a58da-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="a58da-126">AOL с клиентом Pivot;</span><span class="sxs-lookup"><span data-stu-id="a58da-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="a58da-127">Apple Juice;</span><span class="sxs-lookup"><span data-stu-id="a58da-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="a58da-128">Ares</span><span class="sxs-lookup"><span data-stu-id="a58da-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="a58da-129">Axs Encrypted;</span><span class="sxs-lookup"><span data-stu-id="a58da-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="a58da-130">Axs Exchange;</span><span class="sxs-lookup"><span data-stu-id="a58da-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="a58da-131">Axs Local Archive;</span><span class="sxs-lookup"><span data-stu-id="a58da-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="a58da-132">Axs Placeholder</span><span class="sxs-lookup"><span data-stu-id="a58da-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="a58da-133">Axs Signed;</span><span class="sxs-lookup"><span data-stu-id="a58da-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="a58da-134">Севизово</span><span class="sxs-lookup"><span data-stu-id="a58da-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="a58da-135">Захарий</span><span class="sxs-lookup"><span data-stu-id="a58da-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="a58da-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="a58da-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="a58da-137">Blackberry</span><span class="sxs-lookup"><span data-stu-id="a58da-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="a58da-138">Журналы вызовов BlackBerry</span><span class="sxs-lookup"><span data-stu-id="a58da-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="a58da-139">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="a58da-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="a58da-140">PIN-код BlackBerry</span><span class="sxs-lookup"><span data-stu-id="a58da-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="a58da-141">BlackBerry SMS</span><span class="sxs-lookup"><span data-stu-id="a58da-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="a58da-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="a58da-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="a58da-143">Сообщение Bloomberg</span><span class="sxs-lookup"><span data-stu-id="a58da-143">Bloomberg Message</span></span>  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|<span data-ttu-id="a58da-144">Сообщения Bloomberg</span><span class="sxs-lookup"><span data-stu-id="a58da-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="a58da-145">Box</span><span class="sxs-lookup"><span data-stu-id="a58da-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="a58da-146">Cisco IM &amp; Presence Server</span><span class="sxs-lookup"><span data-stu-id="a58da-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="a58da-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="a58da-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="a58da-148">CipherCloud для Salesforce Chatter;</span><span class="sxs-lookup"><span data-stu-id="a58da-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="a58da-149">Direct Connect;</span><span class="sxs-lookup"><span data-stu-id="a58da-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="a58da-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="a58da-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="a58da-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="a58da-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="a58da-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="a58da-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="a58da-153">Flickr</span><span class="sxs-lookup"><span data-stu-id="a58da-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="a58da-154">Гнунелла</span><span class="sxs-lookup"><span data-stu-id="a58da-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="a58da-155">Google+</span><span class="sxs-lookup"><span data-stu-id="a58da-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="a58da-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="a58da-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="a58da-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="a58da-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="a58da-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="a58da-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="a58da-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="a58da-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="a58da-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="a58da-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="a58da-161">IBM Connections</span><span class="sxs-lookup"><span data-stu-id="a58da-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="a58da-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="a58da-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="a58da-163">ICE Chat</span><span class="sxs-lookup"><span data-stu-id="a58da-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|<span data-ttu-id="a58da-164">Indii Messenger;</span><span class="sxs-lookup"><span data-stu-id="a58da-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="a58da-165">Много</span><span class="sxs-lookup"><span data-stu-id="a58da-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="a58da-166">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="a58da-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="a58da-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="a58da-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="a58da-168">IRC</span><span class="sxs-lookup"><span data-stu-id="a58da-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="a58da-169">Jive</span><span class="sxs-lookup"><span data-stu-id="a58da-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="a58da-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="a58da-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="a58da-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="a58da-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="a58da-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="a58da-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="a58da-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="a58da-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="a58da-174">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="a58da-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="a58da-175">Выравнивание по виду</span><span class="sxs-lookup"><span data-stu-id="a58da-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="a58da-176">Mobile Guard;</span><span class="sxs-lookup"><span data-stu-id="a58da-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="a58da-177">MSN</span><span class="sxs-lookup"><span data-stu-id="a58da-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="a58da-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="a58da-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="a58da-179">THENetwork</span><span class="sxs-lookup"><span data-stu-id="a58da-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="a58da-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="a58da-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="a58da-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="a58da-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="a58da-182">Pivot</span><span class="sxs-lookup"><span data-stu-id="a58da-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="a58da-183">QQ</span><span class="sxs-lookup"><span data-stu-id="a58da-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="a58da-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="a58da-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="a58da-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="a58da-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="a58da-186">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a58da-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="a58da-187">Slack Enterprise Grid;</span><span class="sxs-lookup"><span data-stu-id="a58da-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="a58da-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="a58da-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="a58da-189">Squawker</span><span class="sxs-lookup"><span data-stu-id="a58da-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="a58da-190">Symphony</span><span class="sxs-lookup"><span data-stu-id="a58da-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="a58da-191">Thomson Reuters.</span><span class="sxs-lookup"><span data-stu-id="a58da-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="a58da-192">Thomson Reuters Eikon Messenger.</span><span class="sxs-lookup"><span data-stu-id="a58da-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="a58da-193">Tor</span><span class="sxs-lookup"><span data-stu-id="a58da-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="a58da-194">TTT</span><span class="sxs-lookup"><span data-stu-id="a58da-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="a58da-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="a58da-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="a58da-196">UBS Chat;</span><span class="sxs-lookup"><span data-stu-id="a58da-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="a58da-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="a58da-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="a58da-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="a58da-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="a58da-199">Winny</span><span class="sxs-lookup"><span data-stu-id="a58da-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="a58da-200">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="a58da-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="a58da-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="a58da-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="a58da-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="a58da-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="a58da-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="a58da-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
