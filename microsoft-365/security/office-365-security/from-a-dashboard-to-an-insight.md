---
title: Пошаговое руководство. Из панели мониторинга к аналитике
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/04/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 703c41df-b3e2-4e7e-9eeb-1a0b8d60fb56
ms.collection:
- M365-security-compliance
description: Сведения о том, как можно переходить с панели мониторинга в представление о рекомендуемых действиях &amp; в центре безопасности и соответствия требованиям.
ms.openlocfilehash: ceb00301ca8c58072f6f34b19c633a0d11565e77
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599306"
---
# <a name="walkthrough---from-a-dashboard-to-an-insight"></a><span data-ttu-id="bb975-103">Пошаговое руководство. Из панели мониторинга к аналитике</span><span class="sxs-lookup"><span data-stu-id="bb975-103">Walkthrough - From a dashboard to an insight</span></span>

<span data-ttu-id="bb975-104">Если вы не знакомы с [отчетами и аналитическими сведениями в центре безопасности &amp; и соответствия требованиям Office 365](reports-and-insights-in-security-and-compliance.md), то можете понять, как легко переходить с панели мониторинга на подробные и рекомендуемые действия.</span><span class="sxs-lookup"><span data-stu-id="bb975-104">If you're new to [reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span> 
  
<span data-ttu-id="bb975-105">Это одно из нескольких пошаговых руководств для центра &amp; безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="bb975-105">This is one of several walkthroughs for the Security &amp; Compliance Center.</span></span> <span data-ttu-id="bb975-106">Дополнительные пошаговые руководства можно найти в разделе [связанные темы](#related-topics) .</span><span class="sxs-lookup"><span data-stu-id="bb975-106">To see additional walkthroughs, see the [Related topics](#related-topics) section.</span></span> 
  
## <a name="walkthrough-from-a-dashboard-to-an-insight"></a><span data-ttu-id="bb975-107">Пошаговое руководство: из панели мониторинга в представление</span><span class="sxs-lookup"><span data-stu-id="bb975-107">Walkthrough: From a dashboard to an insight</span></span>

<span data-ttu-id="bb975-108">Давайте рассмотрим процесс передачи данных из панели мониторинга в отчет для анализа и действия.</span><span class="sxs-lookup"><span data-stu-id="bb975-108">Let's walk through the flow from a dashboard to a report to an insight and action.</span></span> <span data-ttu-id="bb975-109">(Это краткий пример службы [подделки](learn-about-spoof-intelligence.md) .)</span><span class="sxs-lookup"><span data-stu-id="bb975-109">(This is a brief [spoof intelligence](learn-about-spoof-intelligence.md) example.)</span></span> 
  
1. <span data-ttu-id="bb975-110">Мы начнем с панели мониторинга безопасности в [центре безопасности &amp; и соответствия требованиям](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="bb975-110">We begin with the Security dashboard in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="bb975-111">(Перейдите на \> **панель мониторинга** **управления угрозами** .)</span><span class="sxs-lookup"><span data-stu-id="bb975-111">(Go to **Threat management** \> **Dashboard**.)</span></span><br><span data-ttu-id="bb975-112">![В центре безопасности &amp; и соответствия требованиям выберите панель мониторинга \> управления угрозами](../media/05a38660-eb13-4960-a266-11809c453d95.png)</span><span class="sxs-lookup"><span data-stu-id="bb975-112">![In the Security &amp; Compliance Center, choose Threat management \> Dashboard](../media/05a38660-eb13-4960-a266-11809c453d95.png)</span></span><br>
  
2. <span data-ttu-id="bb975-113">В строке **Insights** мы рассмотрели информацию о том, что нам нужно проверить некоторые домены, которые могут быть подозрительными.</span><span class="sxs-lookup"><span data-stu-id="bb975-113">In the **Insights** row, we notice an insight indicating we need to review some domains that might be suspicious.</span></span> <span data-ttu-id="bb975-114">В строке **Insights** (сведения о домене) выберите пункт **пары доменов**.</span><span class="sxs-lookup"><span data-stu-id="bb975-114">(In the **Insights** row, click **Domain pairs**.)</span></span><br><span data-ttu-id="bb975-115">![В строке Insights упоминаются потенциальные проблемы подмены](../media/dd1d0cb3-3201-45d7-b41d-18a0944fe85d.png)</span><span class="sxs-lookup"><span data-stu-id="bb975-115">![The Insights row mentions potential spoofing concerns](../media/dd1d0cb3-3201-45d7-b41d-18a0944fe85d.png)</span></span><br>
  
3. <span data-ttu-id="bb975-116">Мы получаем список действий, связанных с логикой подделки.</span><span class="sxs-lookup"><span data-stu-id="bb975-116">We get a list of activities related to spoof intelligence.</span></span> <span data-ttu-id="bb975-117">Это экземпляры, в которых сообщения электронной почты отправляются так, как они поступили из нашей Организации, но на самом деле были отправлены из другой организации.</span><span class="sxs-lookup"><span data-stu-id="bb975-117">These are instances where email messages were sent that look like they came from our organization but were, in fact, sent from another organization.</span></span> <span data-ttu-id="bb975-118">Цель состоит в том, чтобы определить, авторизованы ли подложные сообщения.</span><span class="sxs-lookup"><span data-stu-id="bb975-118">The goal is to determine whether the spoofed messages are authorized or not.</span></span><br><span data-ttu-id="bb975-119">![Советы по подделке](../media/a2e2b4fd-0c1e-499f-8401-cf3089da82fa.png)</span><span class="sxs-lookup"><span data-stu-id="bb975-119">![Spoof intelligence insights](../media/a2e2b4fd-0c1e-499f-8401-cf3089da82fa.png)</span></span><br><span data-ttu-id="bb975-120">В этом списке можно отсортировать информацию по количеству сообщений, дате и времени последнего обнаружения поддельных сообщений.</span><span class="sxs-lookup"><span data-stu-id="bb975-120">In this list, we can sort the information by message count, date the spoofing was last detected, and more.</span></span> <span data-ttu-id="bb975-121">(Щелкните заголовки столбцов, например, **количество сообщений** или **Последнее** отображение, чтобы увидеть, как работает сортировка.)</span><span class="sxs-lookup"><span data-stu-id="bb975-121">(Click column headings, such as **Message count** or **Last seen** to see how sorting works.)</span></span> 
    
4. <span data-ttu-id="bb975-122">При выборе элемента в списке открывается область сведений, в которой можно увидеть дополнительные сведения, в том числе Похожие сообщения электронной почты, которые были обнаружены.</span><span class="sxs-lookup"><span data-stu-id="bb975-122">Selecting an item in the list opens a details pane where we can see additional information, including similar email messages that were detected.</span></span> <span data-ttu-id="bb975-123">(Щелкните элемент в списке и ознакомьтесь со сведениями и рекомендациями.)</span><span class="sxs-lookup"><span data-stu-id="bb975-123">(Click an item in the list, and review the information and recommendations.)</span></span><br>![При выборе элемента открывается область сведений](../media/7ad1faa5-6ca2-474e-a609-eb275e0a8e59.png)<br>
  
5. <span data-ttu-id="bb975-125">Обратите внимание, что в верхней части области можно добавить отправителя в список разрешенных отправителей организации.</span><span class="sxs-lookup"><span data-stu-id="bb975-125">Notice that at the top of the pane, we have the option to add the sender to our organization's allowed senders list.</span></span> <span data-ttu-id="bb975-126">(Не выбирайте **Добавить в список "алловедтоспуф" отправителя** , пока вы не подтвердите это.</span><span class="sxs-lookup"><span data-stu-id="bb975-126">(Do not select **Add to 'AllowedtoSpoof' sender allow list** until you are sure you want to do this.</span></span> <span data-ttu-id="bb975-127">[Узнайте больше о логике подделки](learn-about-spoof-intelligence.md).)</span><span class="sxs-lookup"><span data-stu-id="bb975-127">[Learn more about spoof intelligence](learn-about-spoof-intelligence.md).)</span></span><br><span data-ttu-id="bb975-128">![Вы можете авторизовать отправителя](../media/caf0c20a-6047-486d-8060-5a229a3de49f.png)</span><span class="sxs-lookup"><span data-stu-id="bb975-128">![You can authorize a sender](../media/caf0c20a-6047-486d-8060-5a229a3de49f.png)</span></span>
  
<span data-ttu-id="bb975-129">Таким образом, мы можем перейти с панели мониторинга к ценным и рекомендуемым действиям.</span><span class="sxs-lookup"><span data-stu-id="bb975-129">In this way, we can move from a dashboard to insights and recommended actions.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bb975-130">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="bb975-130">Related topics</span></span>

[<span data-ttu-id="bb975-131">Пошаговое руководство: из подробного отчета</span><span class="sxs-lookup"><span data-stu-id="bb975-131">Walkthrough: From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)
  
[<span data-ttu-id="bb975-132">Пошаговое руководство: из подробного отчета в представление</span><span class="sxs-lookup"><span data-stu-id="bb975-132">Walkthrough: From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)
  

