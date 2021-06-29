---
title: Работа DLP с центром & & Exchange администрирования
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
description: Узнайте, как DLP в Центре & безопасности работает с правилами потока DLP и почты (правила транспорта) в центре администрирования Exchange безопасности.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34ddee1c1f0997852b6e59295ab9b630acc3ba3c
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177181"
---
# <a name="how-dlp-works-between-the-microsoft-365-compliance-center-and-exchange-admin-center"></a><span data-ttu-id="b5c88-103">Работа DLP между центром Microsoft 365 соответствия требованиям и Exchange центром администрирования</span><span class="sxs-lookup"><span data-stu-id="b5c88-103">How DLP works between the Microsoft 365 Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="b5c88-104">В Microsoft 365 вы можете создать политику предотвращения потери данных (DLP) в двух разных центрах администрирования:</span><span class="sxs-lookup"><span data-stu-id="b5c88-104">In Microsoft 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="b5c88-105">В **центре Microsoft 365** вы можете создать единую политику DLP для защиты контента в SharePoint, OneDrive, Exchange, Teams, а теперь и в конечных устройствах.</span><span class="sxs-lookup"><span data-stu-id="b5c88-105">In the **Microsoft 365 Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, Teams, and now Endpoint Devices.</span></span> <span data-ttu-id="b5c88-106">Мы рекомендуем создать политику DLP здесь.</span><span class="sxs-lookup"><span data-stu-id="b5c88-106">We recommend that you create a DLP policy here.</span></span> <span data-ttu-id="b5c88-107">Дополнительные сведения см. в [справке о предотвращении потери данных.](data-loss-prevention-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b5c88-107">For more information, see [Data Loss Prevention reference](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="b5c88-108">В центре **Exchange** можно создать политику DLP, чтобы защитить контент только в Exchange.</span><span class="sxs-lookup"><span data-stu-id="b5c88-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="b5c88-109">Эта политика может Exchange правил потока почты (также называемых правилами транспорта), поэтому она имеет больше возможностей, определенных для обработки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b5c88-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="b5c88-110">Дополнительные сведения см. в [центре администрирования Exchange DLP.](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)</span><span class="sxs-lookup"><span data-stu-id="b5c88-110">For more information, see [DLP in the Exchange admin center](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).</span></span>
    
<span data-ttu-id="b5c88-111">Полицейские службы DLP, созданные в этих центрах администрирования, работают бок о бок — в этом разделе объясняется, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="b5c88-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![Страницы DLP в Центре безопасности и соответствия требованиям и Exchange центре администрирования](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="b5c88-113">Как DLP в Центре & безопасности работает с правилами потока DLP и почты в центре администрирования Exchange безопасности</span><span class="sxs-lookup"><span data-stu-id="b5c88-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="b5c88-114">После создания политики DLP в Центре & безопасности политика развертывается во всех расположениях, включенных в политику.</span><span class="sxs-lookup"><span data-stu-id="b5c88-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="b5c88-115">Если политика включает Exchange Online, она синхронизирована там и выполняется точно так же, как политика DLP, созданная в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="b5c88-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="b5c88-116">Если вы создали политики DLP в центре администрирования Exchange, эти политики будут продолжать работать бок о бок с любыми политиками для электронной почты, созданными в центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="b5c88-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="b5c88-117">Но обратите внимание, что правила, созданные Exchange центре администрирования, имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="b5c88-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="b5c88-118">Сначала Exchange правила потока почты, а затем обрабатываются правила DLP из Центра & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="b5c88-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="b5c88-119">Это означает, что:</span><span class="sxs-lookup"><span data-stu-id="b5c88-119">This means that:</span></span>
  
- <span data-ttu-id="b5c88-120">Сообщения, заблокированные Exchange правил потока почты, не будут проверяться по правилам DLP, созданным в Центре & безопасности.</span><span class="sxs-lookup"><span data-stu-id="b5c88-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>

- <span data-ttu-id="b5c88-121">Сообщения, которые находятся на карантине по Exchange правилами потока почты или любыми другими фильтрами, которые запускаются перед DLP, не будут отсканированы DLP</span><span class="sxs-lookup"><span data-stu-id="b5c88-121">Messages that are quarantined by Exchange mail flow rules or any other filters run before DLP will not be scanned by DLP</span></span>
    
- <span data-ttu-id="b5c88-122">Если правило потока Exchange изменяет сообщение таким образом, чтобы оно совпадает с политикой DLP в Центре соответствия требованиям безопасности & , например добавление внешних пользователей, то правила DLP будут обнаруживать это и применять политику по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="b5c88-122">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="b5c88-123">Кроме того, Exchange правила потока почты, которые используют действие "стоп-обработка", не влияют на обработку правил DLP в Центре & безопасности , они все равно будут обработаны.</span><span class="sxs-lookup"><span data-stu-id="b5c88-123">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="b5c88-124">Советы по политике в Центре & безопасности и центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="b5c88-124">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="b5c88-125">Советы по политике могут работать либо с политиками DLP и правилами потока почты, созданными в центре администрирования Exchange, так и с политиками DLP, созданными в Центре & безопасности, но не обоими.</span><span class="sxs-lookup"><span data-stu-id="b5c88-125">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="b5c88-126">Это потому, что эти политики хранятся в разных расположениях, но советы политики можно использовать только из одного расположения.</span><span class="sxs-lookup"><span data-stu-id="b5c88-126">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="b5c88-127">Если вы настроили советы по политике в центре администрирования Exchange, советы политики, настроенные в Центре соответствия требованиям безопасности &, не будут отображаться пользователям в Outlook в Интернете и Outlook 2013 г. и позднее, пока не отключите советы в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="b5c88-127">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="b5c88-128">Это гарантирует, что текущие правила Exchange потока почты будут работать до тех пор, пока вы не решите перейти в Центр & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="b5c88-128">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="b5c88-129">Обратите внимание, что, хотя советы по политике можно использовать только из одного расположения, уведомления электронной почты всегда отправляются, даже если вы используете политики DLP как в Центре & безопасности, так и в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="b5c88-129">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
