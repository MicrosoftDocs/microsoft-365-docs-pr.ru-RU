---
title: Как DLP работает с Центром & соответствия & Администрирование Exchange
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Узнайте, как DLP в Центре & соответствия требованиям работает с DLP и правилами потока обработки почты (правилами транспорта) в Центре администрирования Exchange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 05e3c6342ab6d57c1f22de96e64a01df5fd15131
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036200"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="fbab7-103">Принципы работы защиты от потери данных в Центре безопасности и соответствия требованиям и Центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="fbab7-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="fbab7-104">В Office 365 вы можете создать политику защиты от потери данных (DLP) в двух разных центрах администрирования:</span><span class="sxs-lookup"><span data-stu-id="fbab7-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="fbab7-105">В Центре **безопасности & соответствия** требованиям вы можете создать одну политику DLP, чтобы защитить контент в SharePoint, OneDrive, Exchange, а теперь и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fbab7-105">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, and now Microsoft Teams.</span></span> <span data-ttu-id="fbab7-106">По возможности рекомендуется создать здесь политику DLP.</span><span class="sxs-lookup"><span data-stu-id="fbab7-106">When possible, we recommend that you create a DLP policy here.</span></span> <span data-ttu-id="fbab7-107">Дополнительные сведения см. в центре безопасности [& соответствия требованиям.](data-loss-prevention-policies.md)</span><span class="sxs-lookup"><span data-stu-id="fbab7-107">For more information, see [DLP in the Security & Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="fbab7-108">В Центре **администрирования Exchange** можно создать политику DLP, чтобы защитить контент только в Exchange.</span><span class="sxs-lookup"><span data-stu-id="fbab7-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="fbab7-109">Эта политика может использовать правила потока обработки почты Exchange (также называемые правилами транспорта), поэтому имеет больше возможностей, характерных для обработки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="fbab7-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="fbab7-110">Дополнительные сведения см. в [DLP в Центре администрирования Exchange.](https://go.microsoft.com/fwlink/?linkid=852311)</span><span class="sxs-lookup"><span data-stu-id="fbab7-110">For more information, see [DLP in the Exchange admin center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="fbab7-111">Рядом с этими центрами администрирования работают и созданные в этих центрах администрирования, и в этом разделе объясняется, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="fbab7-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![Страницы DLP в Центре безопасности и соответствия требованиям и Центре администрирования Exchange](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="fbab7-113">Как DLP в Центре & соответствия требованиям работает с DLP и правилами потока обработки почты в Центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="fbab7-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="fbab7-114">После создания политики DLP в Центре & соответствия требованиям политика развертывается во всех расположениях, включенных в политику.</span><span class="sxs-lookup"><span data-stu-id="fbab7-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="fbab7-115">Если политика включает Exchange Online, она синхронизируется там и принудительно выполняется точно так же, как политика DLP, созданная в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="fbab7-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="fbab7-116">Если вы создали политики DLP в Центре администрирования Exchange, эти политики продолжат работать вместе с любыми политиками для электронной почты, созданными в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fbab7-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="fbab7-117">Но обратите внимание, что правила, созданные в Центре администрирования Exchange, имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="fbab7-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="fbab7-118">В первую очередь обрабатываются все правила потока обработки почты Exchange, а затем правила DLP из Центра безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fbab7-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="fbab7-119">Это означает, что:</span><span class="sxs-lookup"><span data-stu-id="fbab7-119">This means that:</span></span>
  
- <span data-ttu-id="fbab7-120">Сообщения, заблокированные правилами потока обработки почты Exchange, не будут сканироваться правилами DLP, созданными в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fbab7-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="fbab7-121">Если правило потока обработки почты Exchange изменяет сообщение таким образом, чтобы оно совпадает с политикой DLP в Центре безопасности и & соответствия требованиям (например, при добавлении внешних пользователей), то правила DLP обнаружят это и при необходимости при необходимости применят политику.</span><span class="sxs-lookup"><span data-stu-id="fbab7-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="fbab7-122">Также обратите внимание, что правила потока обработки почты Exchange, которые используют действие "остановить обработку", не влияют на обработку правил DLP в Центре безопасности & соответствия требованиям — они будут по-прежнему обрабатываться.</span><span class="sxs-lookup"><span data-stu-id="fbab7-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="fbab7-123">Подсказки политики в Центре безопасности & соответствия требованиям и Центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="fbab7-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="fbab7-124">Подсказки политики могут работать как с политиками защиты от lp, так и с правилами потока обработки почты, созданными в Центре администрирования Exchange, или с политиками DLP, созданными в Центре безопасности & соответствия требованиям, но не с обоими политиками.</span><span class="sxs-lookup"><span data-stu-id="fbab7-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="fbab7-125">Это потому, что эти политики хранятся в разных расположениях, но подсказки политики могут рисовать только из одного расположения.</span><span class="sxs-lookup"><span data-stu-id="fbab7-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="fbab7-126">Если вы настроили подсказки политики в Центре администрирования Exchange, советы политики, настроенные в Центре безопасности и & соответствия требованиям, не будут отображаться пользователям в Outlook в Интернете и Outlook 2013 и более поздних, пока вы не отключите их в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="fbab7-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="fbab7-127">Это гарантирует, что текущие правила потока обработки почты Exchange продолжат работать, пока вы не решите переключиться на Центр безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fbab7-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="fbab7-128">Обратите внимание, что несмотря на то что подсказки политики могут рисовать только из одного расположения, уведомления по электронной почте всегда отправляются, даже если вы используете политики DLP как в Центре безопасности & и соответствия требованиям, так и в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="fbab7-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
  

