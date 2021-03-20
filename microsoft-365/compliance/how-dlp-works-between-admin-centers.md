---
title: Работа DLP с центром & безопасности & Центра администрирования Exchange
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
description: Узнайте, как DLP в Центре & безопасности работает с правилами потока DLP и почты (правила транспорта) в центре администрирования Exchange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cd8a3eb0e7bb859ab9e10551fadd22cc7dcb2a39
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905941"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="ab22b-103">Принципы работы защиты от потери данных в Центре безопасности и соответствия требованиям и Центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="ab22b-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="ab22b-104">В Office 365 можно создать политику предотвращения потери данных (DLP) в двух разных центрах администрирования:</span><span class="sxs-lookup"><span data-stu-id="ab22b-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="ab22b-105">В Центре **&** безопасности можно создать единую политику DLP для защиты контента в SharePoint, OneDrive, Exchange и теперь Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ab22b-105">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, and now Microsoft Teams.</span></span> <span data-ttu-id="ab22b-106">По возможности рекомендуется создать политику DLP здесь.</span><span class="sxs-lookup"><span data-stu-id="ab22b-106">When possible, we recommend that you create a DLP policy here.</span></span> <span data-ttu-id="ab22b-107">Дополнительные сведения см. в [таблице DLP в](data-loss-prevention-policies.md)центре & безопасности.</span><span class="sxs-lookup"><span data-stu-id="ab22b-107">For more information, see [DLP in the Security & Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="ab22b-108">В центре **администрирования Exchange** можно создать политику DLP для защиты контента только в Exchange.</span><span class="sxs-lookup"><span data-stu-id="ab22b-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="ab22b-109">Эта политика может использовать правила потока почтовой почты Exchange (также известные как правила транспорта), поэтому она имеет больше возможностей, определенных для обработки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ab22b-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="ab22b-110">Дополнительные сведения см. в [таблице DLP в центре администрирования Exchange.](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)</span><span class="sxs-lookup"><span data-stu-id="ab22b-110">For more information, see [DLP in the Exchange admin center](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).</span></span>
    
<span data-ttu-id="ab22b-111">Полицейские службы DLP, созданные в этих центрах администрирования, работают бок о бок — в этом разделе объясняется, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="ab22b-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![Страницы DLP в Центре безопасности и соответствия требованиям и центре администрирования Exchange](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="ab22b-113">Как DLP в Центре & безопасности работает с правилами потока DLP и почты в центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="ab22b-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="ab22b-114">После создания политики DLP в Центре & безопасности политика развертывается во всех расположениях, включенных в политику.</span><span class="sxs-lookup"><span data-stu-id="ab22b-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="ab22b-115">Если политика включает Exchange Online, она синхронизирована там и выполняется точно так же, как политика DLP, созданная в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="ab22b-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="ab22b-116">Если вы создали политики DLP в центре администрирования Exchange, эти политики будут продолжать работать бок о бок с любыми политиками электронной почты, созданными в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ab22b-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="ab22b-117">Но обратите внимание, что правила, созданные в центре администрирования Exchange, имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="ab22b-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="ab22b-118">Сначала обрабатываются все правила потока почты Exchange, а затем обрабатываются правила DLP из Центра & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ab22b-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="ab22b-119">Это означает, что:</span><span class="sxs-lookup"><span data-stu-id="ab22b-119">This means that:</span></span>
  
- <span data-ttu-id="ab22b-120">Сообщения, заблокированные правилами потока почты Exchange, не будут проверяться по правилам DLP, созданным в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ab22b-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="ab22b-121">Если правило потока почты Exchange изменяет сообщение таким образом, чтобы оно совпадает с политикой DLP в Центре соответствия требованиям безопасности &, например добавлением внешних пользователей, то правила DLP будут обнаруживать это и применять политику по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="ab22b-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="ab22b-122">Кроме того, обратите внимание, что правила потока почты Exchange, которые используют действие "стоп-обработка", не влияют на обработку правил DLP в Центре соответствия требованиям & безопасности , они все равно будут обработаны.</span><span class="sxs-lookup"><span data-stu-id="ab22b-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="ab22b-123">Советы по политике в Центре & безопасности и центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="ab22b-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="ab22b-124">Советы по политике могут работать как с политиками DLP и правилами потока почты, созданными в центре администрирования Exchange, так и с политиками DLP, созданными в Центре & безопасности, но не обоими.</span><span class="sxs-lookup"><span data-stu-id="ab22b-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="ab22b-125">Это потому, что эти политики хранятся в разных расположениях, но советы политики можно использовать только из одного расположения.</span><span class="sxs-lookup"><span data-stu-id="ab22b-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="ab22b-126">Если вы настроили советы по политике в центре администрирования Exchange, советы политики, настроенные в Центре соответствия требованиям безопасности &, не будут отображаться пользователям в Outlook в Интернете и Outlook 2013 и позднее, пока вы не отключите подсказки в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="ab22b-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="ab22b-127">Это гарантирует, что текущие правила потока почты Exchange будут работать до тех пор, пока вы не решите перейти к Центру & безопасности.</span><span class="sxs-lookup"><span data-stu-id="ab22b-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="ab22b-128">Обратите внимание, что, хотя советы политики можно использовать только из одного расположения, уведомления электронной почты всегда отправляются, даже если вы используете политики DLP как в Центре обеспечения безопасности &, так и в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="ab22b-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
