---
title: Принципы работы защиты от потери данных в Центре безопасности и соответствия требованиям и Центре администрирования Exchange
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
description: Узнайте, как защита от потери данных в центре безопасности & соответствия требованиям использует правила защиты от потери данных и почтовых ящиков (правила транспорта) в центре администрирования Exchange.
ms.openlocfilehash: 65df871361eca66dca543cd2a6dcb0a529446169
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090178"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="a3d59-103">Принципы работы защиты от потери данных в Центре безопасности и соответствия требованиям и Центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="a3d59-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="a3d59-104">В Office 365 вы можете создать политику защиты от потери данных (DLP) в двух разных центрах администрирования:</span><span class="sxs-lookup"><span data-stu-id="a3d59-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="a3d59-105">В **центре безопасности & соответствия требованиям**можно создать единую политику защиты от потери данных, которая поможет защитить контент в SharePoint, OneDrive, Exchange и теперь Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a3d59-105">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, and now Microsoft Teams.</span></span> <span data-ttu-id="a3d59-106">По возможности рекомендуется создать политику защиты от потери данных здесь.</span><span class="sxs-lookup"><span data-stu-id="a3d59-106">When possible, we recommend that you create a DLP policy here.</span></span> <span data-ttu-id="a3d59-107">Для получения дополнительных сведений обратитесь [к разделу защита от потери данных в центре безопасности & соответствия требованиям](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a3d59-107">For more information, see [DLP in the Security & Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="a3d59-108">В **центре администрирования Exchange**можно создать политику защиты от потери данных, которая поможет защитить контент только в Exchange.</span><span class="sxs-lookup"><span data-stu-id="a3d59-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="a3d59-109">Эта политика может использовать правила для обработки почтового ящика Exchange (также называемые правилами транспорта), поэтому у нее есть дополнительные параметры обработки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a3d59-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="a3d59-110">Для получения дополнительных сведений обратитесь к разделу защита [от потери данных в центре администрирования Exchange](https://go.microsoft.com/fwlink/?linkid=852311).</span><span class="sxs-lookup"><span data-stu-id="a3d59-110">For more information, see [DLP in the Exchange admin center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="a3d59-111">Политики DLP, созданные в этих центрах администрирования, работают параллельно — в этом разделе описывается, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="a3d59-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![Страницы защиты от потери данных в центре безопасности и соответствия требованиям и центре администрирования Exchange](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="a3d59-113">Принципы работы защиты от потери данных в центре безопасности &, а также правила защиты от потери данных и обработки почты в центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="a3d59-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="a3d59-114">После создания политики защиты от потери данных в центре безопасности & соответствия политике она развертывается во всех расположениях, включенных в политику.</span><span class="sxs-lookup"><span data-stu-id="a3d59-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="a3d59-115">Если политика включает Exchange Online, политика синхронизируется и применяется точно так же, как и политика защиты от потери данных, созданная в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="a3d59-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="a3d59-116">Если вы создали политики защиты от потери данных в центре администрирования Exchange, эти политики продолжат работать параллельно с политиками для электронной почты, созданными в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a3d59-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="a3d59-117">Но обратите внимание, что правила, созданные в центре администрирования Exchange, имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="a3d59-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="a3d59-118">Все правила для почтовых ящиков Exchange обрабатываются первыми, а затем обрабатываются правила защиты от потери данных из центра безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a3d59-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="a3d59-119">Это означает, что:</span><span class="sxs-lookup"><span data-stu-id="a3d59-119">This means that:</span></span>
  
- <span data-ttu-id="a3d59-120">Сообщения, заблокированные правилами для почтовых ящиков Exchange, не отсканированы правилами DLP, созданными в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a3d59-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="a3d59-121">Если правило почтовых ящиков Exchange изменяет сообщение таким образом, что оно соответствует политике защиты от потери данных в центре безопасности & соответствия требованиям (например, Добавление внешних пользователей), то правила защиты от потери данных будут обнаруживать эту политику и применять ее при необходимости.</span><span class="sxs-lookup"><span data-stu-id="a3d59-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="a3d59-122">Кроме того, обратите внимание, что правила для почтовых ящиков Exchange, использующие действие "остановить обработку", не влияют на обработку правил DLP в центре безопасности & соответствия требованиям — они по-прежнему будут обрабатываться.</span><span class="sxs-lookup"><span data-stu-id="a3d59-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="a3d59-123">Советы политики в центре безопасности & соответствия требованиям и центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="a3d59-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="a3d59-124">Подсказки политики могут работать с политиками DLP и правилами обработки почты, созданными в центре администрирования Exchange, или с политиками защиты от потери данных, созданными в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a3d59-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="a3d59-125">Это связано с тем, что эти политики хранятся в разных расположениях, но подсказки политики можно изобразить только из одного места.</span><span class="sxs-lookup"><span data-stu-id="a3d59-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="a3d59-126">Если вы настроили подсказки политики в центре администрирования Exchange, любые подсказки политики, которые вы настроили в центре безопасности & соответствия требованиям, не будут отображаться для пользователей в Outlook в Интернете и Outlook 2013 и более поздних версий до тех пор, пока вы не отключите советы в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="a3d59-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="a3d59-127">Это гарантирует, что текущие правила для почтовых ящиков Exchange продолжат работать, пока не будет выбрано переключиться на центр безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a3d59-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="a3d59-128">Обратите внимание, что хотя подсказки политики могут рисовать только из одного места, уведомления по электронной почте всегда отправляются, даже если вы используете политики защиты от потери данных в центре безопасности & соответствия требованиям и центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="a3d59-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
  

