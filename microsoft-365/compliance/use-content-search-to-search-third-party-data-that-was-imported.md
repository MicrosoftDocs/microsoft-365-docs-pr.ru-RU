---
title: Поиск данных, импортированных сторонними производителями, с помощью поиска контента
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
description: Воспользуйтесь средством поиска обнаружения электронных данных поиска контента для поиска элементов, импортированных в почтовые ящики в Microsoft 365, из стороннего источника данных. Можно создать запрос для поиска всех импортированных элементов или создать запрос для поиска определенных типов данных третьих сторон. В этой статье перечислены значения, которые можно использовать в запросе с ключевыми словами для поиска в сторонних типах данных, которые можно импортировать в Microsoft 365.
ms.openlocfilehash: c494f4bbb13919f9a980f227093d291c148e9afe
ms.sourcegitcommit: 86705d15231c987be2fcf5a295b9b6239fc46077
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2020
ms.locfileid: "44566673"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="b6155-105">Использование поиска контента для поиска данных сторонних поставщиков, импортированных с помощью настраиваемого соединителя партнера</span><span class="sxs-lookup"><span data-stu-id="b6155-105">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="b6155-106">[Средство обнаружения электронных данных поиска контента](content-search.md) можно использовать в центре безопасности & соответствия требованиям для поиска элементов, импортированных в почтовые ящики в Microsoft 365, из стороннего источника данных.</span><span class="sxs-lookup"><span data-stu-id="b6155-106">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="b6155-107">Вы можете создать запрос для поиска всех импортированных элементов сторонних данных или создать запрос для поиска определенных элементов данных стороннего производителя.</span><span class="sxs-lookup"><span data-stu-id="b6155-107">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="b6155-108">Кроме того, вы также можете создать политику хранения на основе запросов или удержание обнаружения электронных данных на основе запросов для сохранения сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="b6155-108">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="b6155-109">Для получения дополнительных сведений о работе с партнером по импорту сторонних данных и списка типов данных сторонних производителей, которые можно импортировать в Microsoft 365, ознакомьтесь со статьей [Работа с партнером для архивации сторонних данных в Office 365](work-with-partner-to-archive-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="b6155-109">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6155-110">Рекомендации, приведенные в этой статье, применимы только к сторонним данным, которые были импортированы с помощью пользовательского соединителя партнера.</span><span class="sxs-lookup"><span data-stu-id="b6155-110">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="b6155-111">Эта статья не относится к сторонним данным, которые импортируются с помощью [сторонних соединителей данных](archiving-third-party-data.md#third-party-data-connectors) в центре соответствия требованиям корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b6155-111">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="b6155-112">Создание запроса для поиска всех сторонних данных</span><span class="sxs-lookup"><span data-stu-id="b6155-112">Creating a query to search all third-party data</span></span>

<span data-ttu-id="b6155-113">Чтобы выполнить поиск (или поместиться на удержании) любого типа сторонних данных, импортированных в Office 365, можно использовать параметр `kind:externaldata` Message-value в поле ключевое слово для поиска контента или при создании удержания на основе запроса.</span><span class="sxs-lookup"><span data-stu-id="b6155-113">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="b6155-114">Например, чтобы найти элементы, импортированные из стороннего источника данных и содержащие слово "contoso" в свойстве subject импортированного элемента, используйте следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="b6155-114">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="b6155-115">Пример запроса к предыдущему ключевому слову включает свойство Subject.</span><span class="sxs-lookup"><span data-stu-id="b6155-115">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="b6155-116">Список других свойств сторонних элементов данных, которые могут быть включены в запрос ключевых слов, приведен в разделе "Дополнительные сведения" в разделе " [Работа с партнером для архивации сторонних данных в Office 365](work-with-partner-to-archive-third-party-data.md#more-information)".</span><span class="sxs-lookup"><span data-stu-id="b6155-116">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="b6155-117">При создании запросов для поиска и хранения сторонних данных можно также использовать условия для сужения результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="b6155-117">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="b6155-118">Дополнительные сведения о создании поисковых запросов можно узнать в статье [запросы и условия поиска контента](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="b6155-118">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="b6155-119">Создание запроса для поиска определенных типов сторонних данных</span><span class="sxs-lookup"><span data-stu-id="b6155-119">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="b6155-120">Вместо того чтобы искать все типы сторонних данных, можно создавать запросы, которые ищут только сведения об указанном типе сторонних данных, используя следующую комбинацию *свойств Message: value* в поле ключевое слово для поиска контента:</span><span class="sxs-lookup"><span data-stu-id="b6155-120">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property:value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="b6155-121">Например, чтобы найти данные Facebook, содержащие слово "contoso" в свойстве subject, используйте следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="b6155-121">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="b6155-122">В следующей таблице приведены типы данных третьих сторон, которые можно найти, а также значение, которое будет использоваться для `itemclass:` свойства Message для точного поиска этого типа сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="b6155-122">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="b6155-123">В синтаксисе запроса регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="b6155-123">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="b6155-124">**Сторонний тип данных**</span><span class="sxs-lookup"><span data-stu-id="b6155-124">**Third-party data type**</span></span>|<span data-ttu-id="b6155-125">**Значение `itemclass:` Свойства**</span><span class="sxs-lookup"><span data-stu-id="b6155-125">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6155-126">СТАРАЙТЕСЬ</span><span class="sxs-lookup"><span data-stu-id="b6155-126">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="b6155-127">American Idol;</span><span class="sxs-lookup"><span data-stu-id="b6155-127">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="b6155-128">AOL с клиентом Pivot;</span><span class="sxs-lookup"><span data-stu-id="b6155-128">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="b6155-129">Apple Juice;</span><span class="sxs-lookup"><span data-stu-id="b6155-129">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="b6155-130">арес</span><span class="sxs-lookup"><span data-stu-id="b6155-130">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="b6155-131">Axs Encrypted;</span><span class="sxs-lookup"><span data-stu-id="b6155-131">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="b6155-132">Axs Exchange;</span><span class="sxs-lookup"><span data-stu-id="b6155-132">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="b6155-133">Axs Local Archive;</span><span class="sxs-lookup"><span data-stu-id="b6155-133">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="b6155-134">Заполнитель AXS</span><span class="sxs-lookup"><span data-stu-id="b6155-134">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="b6155-135">Axs Signed;</span><span class="sxs-lookup"><span data-stu-id="b6155-135">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="b6155-136">базаарвоице</span><span class="sxs-lookup"><span data-stu-id="b6155-136">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="b6155-137">беаршаре</span><span class="sxs-lookup"><span data-stu-id="b6155-137">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="b6155-138">битторрент</span><span class="sxs-lookup"><span data-stu-id="b6155-138">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="b6155-139">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="b6155-139">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="b6155-140">Журналы звонков BlackBerry</span><span class="sxs-lookup"><span data-stu-id="b6155-140">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="b6155-141">Служба обмена сообщениями BlackBerry</span><span class="sxs-lookup"><span data-stu-id="b6155-141">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="b6155-142">ПИН-код BlackBerry</span><span class="sxs-lookup"><span data-stu-id="b6155-142">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="b6155-143">BlackBerry SMS</span><span class="sxs-lookup"><span data-stu-id="b6155-143">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="b6155-144">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="b6155-144">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="b6155-145">Bloomberg Mail;</span><span class="sxs-lookup"><span data-stu-id="b6155-145">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="b6155-146">Обмен сообщениями Bloomberg</span><span class="sxs-lookup"><span data-stu-id="b6155-146">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="b6155-147">Box</span><span class="sxs-lookup"><span data-stu-id="b6155-147">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="b6155-148">Сервер присутствия для обмена мгновенными сообщениями Cisco &amp;</span><span class="sxs-lookup"><span data-stu-id="b6155-148">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="b6155-149">Cisco Jabber;</span><span class="sxs-lookup"><span data-stu-id="b6155-149">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="b6155-150">CipherCloud для Salesforce Chatter;</span><span class="sxs-lookup"><span data-stu-id="b6155-150">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="b6155-151">Direct Connect;</span><span class="sxs-lookup"><span data-stu-id="b6155-151">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="b6155-152">Facebook</span><span class="sxs-lookup"><span data-stu-id="b6155-152">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="b6155-153">FastTrack</span><span class="sxs-lookup"><span data-stu-id="b6155-153">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="b6155-154">фксконнект</span><span class="sxs-lookup"><span data-stu-id="b6155-154">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="b6155-155">Flickr</span><span class="sxs-lookup"><span data-stu-id="b6155-155">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="b6155-156">гнутелла</span><span class="sxs-lookup"><span data-stu-id="b6155-156">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="b6155-157">Google +</span><span class="sxs-lookup"><span data-stu-id="b6155-157">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="b6155-158">Google говорите</span><span class="sxs-lookup"><span data-stu-id="b6155-158">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="b6155-159">готомипк</span><span class="sxs-lookup"><span data-stu-id="b6155-159">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="b6155-160">хипчат</span><span class="sxs-lookup"><span data-stu-id="b6155-160">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="b6155-161">хопстер</span><span class="sxs-lookup"><span data-stu-id="b6155-161">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="b6155-162">хубконнекс</span><span class="sxs-lookup"><span data-stu-id="b6155-162">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="b6155-163">Подключения IBM</span><span class="sxs-lookup"><span data-stu-id="b6155-163">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="b6155-164">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="b6155-164">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="b6155-165">Чат</span><span class="sxs-lookup"><span data-stu-id="b6155-165">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="b6155-166">Indii Messenger;</span><span class="sxs-lookup"><span data-stu-id="b6155-166">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="b6155-167">инстаграм</span><span class="sxs-lookup"><span data-stu-id="b6155-167">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="b6155-168">Instant Bloomberg;</span><span class="sxs-lookup"><span data-stu-id="b6155-168">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="b6155-169">инвестедже</span><span class="sxs-lookup"><span data-stu-id="b6155-169">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="b6155-170">IRC</span><span class="sxs-lookup"><span data-stu-id="b6155-170">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="b6155-171">Jive</span><span class="sxs-lookup"><span data-stu-id="b6155-171">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="b6155-172">живеапиретентион</span><span class="sxs-lookup"><span data-stu-id="b6155-172">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="b6155-173">жкста</span><span class="sxs-lookup"><span data-stu-id="b6155-173">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="b6155-174">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="b6155-174">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="b6155-175">мфтп</span><span class="sxs-lookup"><span data-stu-id="b6155-175">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="b6155-176">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="b6155-176">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="b6155-177">Выровнять по расмнению</span><span class="sxs-lookup"><span data-stu-id="b6155-177">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="b6155-178">Mobile Guard;</span><span class="sxs-lookup"><span data-stu-id="b6155-178">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="b6155-179">СЕТЬЮ</span><span class="sxs-lookup"><span data-stu-id="b6155-179">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="b6155-180">миспаце</span><span class="sxs-lookup"><span data-stu-id="b6155-180">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="b6155-181">неонетворк</span><span class="sxs-lookup"><span data-stu-id="b6155-181">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="b6155-182">опеннап</span><span class="sxs-lookup"><span data-stu-id="b6155-182">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="b6155-183">пинтерест</span><span class="sxs-lookup"><span data-stu-id="b6155-183">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="b6155-184">Сводка</span><span class="sxs-lookup"><span data-stu-id="b6155-184">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="b6155-185">QQ</span><span class="sxs-lookup"><span data-stu-id="b6155-185">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="b6155-186">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="b6155-186">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="b6155-187">Salesforce Chatter;</span><span class="sxs-lookup"><span data-stu-id="b6155-187">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="b6155-188">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b6155-188">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="b6155-189">Slack Enterprise Grid;</span><span class="sxs-lookup"><span data-stu-id="b6155-189">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="b6155-190">софтесер</span><span class="sxs-lookup"><span data-stu-id="b6155-190">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="b6155-191">скуавкер</span><span class="sxs-lookup"><span data-stu-id="b6155-191">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="b6155-192">симфони</span><span class="sxs-lookup"><span data-stu-id="b6155-192">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="b6155-193">Thomson Reuters.</span><span class="sxs-lookup"><span data-stu-id="b6155-193">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="b6155-194">Thomson Reuters Eikon Messenger.</span><span class="sxs-lookup"><span data-stu-id="b6155-194">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="b6155-195">тор</span><span class="sxs-lookup"><span data-stu-id="b6155-195">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="b6155-196">ттт</span><span class="sxs-lookup"><span data-stu-id="b6155-196">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="b6155-197">Twitter</span><span class="sxs-lookup"><span data-stu-id="b6155-197">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="b6155-198">UBS Chat;</span><span class="sxs-lookup"><span data-stu-id="b6155-198">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="b6155-199">Vimeo</span><span class="sxs-lookup"><span data-stu-id="b6155-199">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="b6155-200">винмкс</span><span class="sxs-lookup"><span data-stu-id="b6155-200">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="b6155-201">винни</span><span class="sxs-lookup"><span data-stu-id="b6155-201">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="b6155-202">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="b6155-202">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="b6155-203">Yammer</span><span class="sxs-lookup"><span data-stu-id="b6155-203">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="b6155-204">елловжаккет</span><span class="sxs-lookup"><span data-stu-id="b6155-204">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="b6155-205">YouTube</span><span class="sxs-lookup"><span data-stu-id="b6155-205">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
