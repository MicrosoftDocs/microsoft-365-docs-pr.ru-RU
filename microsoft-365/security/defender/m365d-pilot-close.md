---
title: Подводя итоги пилотного проекта Microsoft 365 Defender
description: Завершите пилотный проект Microsoft 365 Defender, заполнив свою карту показателей, проанализировав результаты отчета и решив, как двигаться вперед.
keywords: Пилот microsoft Threat Protection определите, что делать после пилотного проекта Microsoft Threat Protection, что делать после оценки microsoft Threat Protection в производстве, перехода от пилота Microsoft Threat Protection к развертыванию, кибербезопасности, передовой постоянной угрозы, корпоративной безопасности, устройств, устройств, удостоверений, пользователей, данных, приложений, инцидентов, автоматического расследования и исправлений, продвинутой охоты
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 2553e88992b7eca906b4697edee4cdf632929444
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076646"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="421e7-104">Закрытие и обобщение пилотного проекта Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="421e7-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="421e7-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="421e7-105">**Applies to:**</span></span>
- <span data-ttu-id="421e7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="421e7-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="421e7-107">[![Планирование](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="421e7-107">[![Planning](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)</span></span><br/>[<span data-ttu-id="421e7-108">Планирование</span><span class="sxs-lookup"><span data-stu-id="421e7-108">Planning</span></span>](m365d-pilot-plan.md) |<span data-ttu-id="421e7-109">[![Подготовка](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="421e7-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="421e7-110">Подготовка</span><span class="sxs-lookup"><span data-stu-id="421e7-110">Preparation</span></span>](prepare-m365d-eval.md) | <span data-ttu-id="421e7-111">[![Имитация атаки](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="421e7-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="421e7-112">Имитация атаки</span><span class="sxs-lookup"><span data-stu-id="421e7-112">Simulate attack</span></span>](m365d-pilot-simulate.md) | ![Закрытие и итоги](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="421e7-114">Закрытие и итоги</span><span class="sxs-lookup"><span data-stu-id="421e7-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="421e7-115">*Вы здесь!*</span><span class="sxs-lookup"><span data-stu-id="421e7-115">*You are here!*</span></span>|


<span data-ttu-id="421e7-116">В настоящее время вы в стадии закрытия и обобщения.</span><span class="sxs-lookup"><span data-stu-id="421e7-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="421e7-117">Вы только что запустили передовую имитацию атак только для памяти, которая удаленно выполняла код на контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="421e7-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="421e7-118">Вы видели, как Microsoft Defender для конечной точки и Microsoft Defender for Identity обнаруживают и создают оповещения о вредоносных действиях стелс.</span><span class="sxs-lookup"><span data-stu-id="421e7-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="421e7-119">Вы также видели, как оповещения из разных источников доставляются вместе с другими контекстными сведениями в один инцидент на портале Центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="421e7-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="421e7-120">Такая интеграция позволяет аналитикам SOC исследовать и принимать необходимые меры.</span><span class="sxs-lookup"><span data-stu-id="421e7-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="421e7-121">Вы также создали расширенный запрос на поиск, который определит входящие сообщения электронной почты, в которых пользователь открыл или сохранил вложение и создал обнаружение на основе этого запроса.</span><span class="sxs-lookup"><span data-stu-id="421e7-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="421e7-122">Вы завершили процесс после окончания всех тестов.</span><span class="sxs-lookup"><span data-stu-id="421e7-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="421e7-123">Конечный вывод должен быть:</span><span class="sxs-lookup"><span data-stu-id="421e7-123">The final output should be:</span></span>

- <span data-ttu-id="421e7-124">Завершенная система показателей</span><span class="sxs-lookup"><span data-stu-id="421e7-124">A completed scorecard</span></span>
- <span data-ttu-id="421e7-125">Подробный отчет о результатах эксперимента</span><span class="sxs-lookup"><span data-stu-id="421e7-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="421e7-126">Решение о том, как двигаться вперед</span><span class="sxs-lookup"><span data-stu-id="421e7-126">A decision on how to move forward</span></span>

<span data-ttu-id="421e7-127">Предопортите отчеты из итогового вывода внутренним заинтересованным [](./prepare-m365d-eval.md) лицам (которые вы определили на этапе подготовки) и контактам Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="421e7-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](./prepare-m365d-eval.md) phase) and Microsoft contacts.</span></span> <span data-ttu-id="421e7-128">Такое усилие гарантирует, что любые отзывы можно использовать для улучшения продуктов и документации.</span><span class="sxs-lookup"><span data-stu-id="421e7-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="421e7-129">Мы надеемся, что вам понравилось это моделирование.</span><span class="sxs-lookup"><span data-stu-id="421e7-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="421e7-130">Начните реализацию того, что вы узнали в более широком масштабе в организации, чтобы извлечь большую часть из интегрированного решения безопасности.</span><span class="sxs-lookup"><span data-stu-id="421e7-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="421e7-131">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="421e7-131">Next step</span></span>
<span data-ttu-id="421e7-132">Узнайте больше о столбах Защитника Microsoft 365 в следующих интерактивных руководствах:</span><span class="sxs-lookup"><span data-stu-id="421e7-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="421e7-133">Защита организации с помощью Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="421e7-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="421e7-134">Обнаружение подозрительных действий и возможных атак с помощью Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="421e7-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="421e7-135">Обнаружение угроз и управление оповещениями с помощью microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="421e7-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="421e7-136">Изучение и устранение угроз с помощью Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="421e7-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)