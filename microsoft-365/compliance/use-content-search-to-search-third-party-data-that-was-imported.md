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
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a>Использование поиска контента для поиска сторонних данных, импортируемых пользовательским соединитетелем партнеров

Вы можете [](content-search.md) использовать средство поиска содержимого в Центре & обеспечения соответствия требованиям для поиска элементов, импортируемых в почтовые ящики Microsoft 365 из сторонних источников данных. Можно создать запрос для поиска всех импортируемых сторонних элементов данных или создать запрос для поиска определенных сторонних элементов данных. Кроме того, можно также создать политику хранения на основе запросов или удержание электронных данных на основе запросов для сохранения сторонних данных.
  
Дополнительные сведения о работе с партнером по импорту сторонних данных и списке типов сторонних данных, которые можно импортировать в Microsoft 365, см. в статью Работа с партнером по архивам [сторонних](work-with-partner-to-archive-third-party-data.md)данных в Office 365 .

> [!IMPORTANT]
> Руководство в этой статье применяется только к сторонним данным, импортируемым пользовательским соединитетелем партнеров. Эта статья не применяется к сторонним данным, импортируемым с помощью сторонних соединители данных [в](archiving-third-party-data.md#third-party-data-connectors) центре соответствия требованиям Майкрософт.
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>Создание запроса для поиска всех сторонних данных

Для поиска (или удержания) любых сторонних данных, импортируемых в Office 365, можно использовать пару свойств сообщения в поле ключевого слова для поиска контента или при создании удержания на основе `kind:externaldata` запросов. Например, для поиска элементов, импортируемых из любого источника сторонних данных и содержащих слово "contoso" в свойстве Subject импортируемого элемента, можно использовать следующий запрос: 
  
```powershell
kind:externaldata AND subject:contoso
```

В предыдущем примере запроса ключевого слова содержится свойство субъекта. Список других свойств сторонних элементов данных, которые могут включаться в запрос ключевого слова, см. в разделе "Дополнительные сведения" в разделе Работа с партнером для архива сторонних данных в [Office 365](work-with-partner-to-archive-third-party-data.md#more-information).
  
При создании запросов для поиска и хранения сторонних данных можно также использовать условия, чтобы сузить результаты поиска. Дополнительные сведения о создании запросов поиска контента см. в статье [Keyword queries and search conditions for Content Search.](keyword-queries-and-search-conditions.md)
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>Создание запроса для поиска определенных типов сторонних данных

Вместо поиска всех типов сторонних данных можно создавать запросы, которые ищут только для конкретного типа сторонних данных, используя следующее свойство *сообщения:* пара значений в поле ключевого слова для поиска контента:
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

Например, для поиска данных Facebook, которые содержат слово "contoso" в свойстве Subject, используется следующий запрос:
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

В следующей таблице перечислены типы сторонних данных, которые можно искать, и значение, которое необходимо использовать для свойства сообщения для конкретного поиска для этого типа  `itemclass:` сторонних данных. Синтаксис запроса не является чувствительным к делу. 
  
|**Тип сторонних данных**|**Значение для  `itemclass:` свойства**|
|:-----|:-----|
|AIM  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol;  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL с клиентом Pivot;  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice;  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|Ares  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted;  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange;  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive;  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Axs Placeholder  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed;  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazaarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|Bearshare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|Blackberry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|Журналы вызовов BlackBerry  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|Посыльный ежевики  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|ПИН-код BlackBerry  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry SMS  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Сообщение Bloomberg  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|Обмен сообщениями Bloomberg  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Box  <br/> | `ipm.externaldata.Box*` <br/> |
|Сервер присутствия Cisco IM &amp;  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud для Salesforce Chatter;  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Direct Connect;  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google+  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google Talk  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|Подключения IBM  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|ICE Chat  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|Indii Messenger;  <br/> | `ipm.externaldata.Indii*` <br/> |
|Instagram  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|IRC  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|JXTA  <br/> | `ipm.externaldata.JXTA*` <br/> |
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|Microsoft UC  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|Согласование умов  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard;  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|MSN  <br/> | `ipm.externaldata.MSN*` <br/> |
|MySpace  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|OpenNap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|Pinterest  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|Pivot  <br/> | `ipm.externaldata.Pivot*` <br/> |
|QQ  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|Skype для бизнеса  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack Enterprise Grid;  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|SoftEther  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|Squawker  <br/> | `ipm.externaldata.Squawker*` <br/> |
|Symphony  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters.  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger.  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|UBS Chat;  <br/> | `ipm.externaldata.UBS*` <br/> |
|Vimeo  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo!  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
