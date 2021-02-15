---
title: Итоги результатов пилотного проекта Microsoft 365 Defender
description: Завершите пилотный проект Защитника Microsoft 365, заполнив свою систему показателей, проанализировав результаты отчета и решив, как двигаться дальше.
keywords: Пилотный проект Защиты от угроз (Майкрософт) решите, что делать после пилотного проекта Защиты от угроз (Майкрософт), что делать после оценки защиты от угроз (Майкрософт) в производственной сфере, перехода от пилотного проекта Защиты от угроз (Майкрософт) к развертыванию, кибербезопасности, расширенных устойчивых угроз, корпоративной безопасности, устройств, устройств, удостоверений, пользователей, данных, приложений, инцидентов, автоматического исследования и устранения угроз, расширенный поиск
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c8608568301f11a20c940a5ff9f1c205ce6e48f1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930166"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="85b94-104">Закрытие пилотного проекта в Microsoft 365 Defender и краткое из них</span><span class="sxs-lookup"><span data-stu-id="85b94-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="85b94-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="85b94-105">**Applies to:**</span></span>
- <span data-ttu-id="85b94-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="85b94-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="85b94-107">[![Планирование](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="85b94-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="85b94-108">Планирование</span><span class="sxs-lookup"><span data-stu-id="85b94-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="85b94-109">[![Подготовка](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="85b94-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="85b94-110">Подготовка</span><span class="sxs-lookup"><span data-stu-id="85b94-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="85b94-111">[![Имитация атаки](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="85b94-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="85b94-112">Имитация атаки</span><span class="sxs-lookup"><span data-stu-id="85b94-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![Закрытие и итоги](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="85b94-114">Закрытие и итоги</span><span class="sxs-lookup"><span data-stu-id="85b94-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="85b94-115">*Вы здесь!*</span><span class="sxs-lookup"><span data-stu-id="85b94-115">*You are here!*</span></span>|


<span data-ttu-id="85b94-116">В настоящее время вы работаете на этапе закрытия и сведения итогов.</span><span class="sxs-lookup"><span data-stu-id="85b94-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="85b94-117">Вы только что выполнили имитацию атаки только на память, которая выполняла код удаленно на контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="85b94-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="85b94-118">Вы видели, как Microsoft Defender для конечной точки и Microsoft Defender для удостоверений обнаруживают и создают оповещения о вредоносных действиях с целью кражи.</span><span class="sxs-lookup"><span data-stu-id="85b94-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="85b94-119">Вы также видели, как оповещения из разных источников доставляются вместе с другими контекстными сведениями в один инцидент на портале Центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="85b94-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="85b94-120">Такая интеграция позволяет аналитикам SOC исследовать и принять необходимые меры.</span><span class="sxs-lookup"><span data-stu-id="85b94-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="85b94-121">Вы также создали запрос на расширенный поиск, который будет определять входящие сообщения электронной почты, в которых пользователь открыл или сохранил вложение, и создал обнаружение на основе этого запроса.</span><span class="sxs-lookup"><span data-stu-id="85b94-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="85b94-122">Процесс заканчивается после того, как все тесты завершены.</span><span class="sxs-lookup"><span data-stu-id="85b94-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="85b94-123">Конечные выходные данные должны быть:</span><span class="sxs-lookup"><span data-stu-id="85b94-123">The final output should be:</span></span>

- <span data-ttu-id="85b94-124">Завершенная система показателей</span><span class="sxs-lookup"><span data-stu-id="85b94-124">A completed scorecard</span></span>
- <span data-ttu-id="85b94-125">Подробный отчет о результатах пилотного проекта</span><span class="sxs-lookup"><span data-stu-id="85b94-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="85b94-126">Решение о том, как двигаться дальше</span><span class="sxs-lookup"><span data-stu-id="85b94-126">A decision on how to move forward</span></span>

<span data-ttu-id="85b94-127">Представлять отчеты из итогового отчета внутренним заинтересованным лицам (которые вы определили на этапе подготовки) и контактам Майкрософт. [](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval)</span><span class="sxs-lookup"><span data-stu-id="85b94-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="85b94-128">Такие усилия обеспечивают возможность использования любых отзывов для улучшения продуктов и документации.</span><span class="sxs-lookup"><span data-stu-id="85b94-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="85b94-129">Надеемся, что вам нравится это моделирование.</span><span class="sxs-lookup"><span data-stu-id="85b94-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="85b94-130">Начните реализовывать то, что вы узнали в масштабе своей организации, чтобы извлечь из интегрированного решения для обеспечения безопасности все больше и больше информации.</span><span class="sxs-lookup"><span data-stu-id="85b94-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="85b94-131">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="85b94-131">Next step</span></span>
<span data-ttu-id="85b94-132">Узнайте больше о основых Защитника Microsoft 365 с помощью следующих интерактивных руководств:</span><span class="sxs-lookup"><span data-stu-id="85b94-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="85b94-133">Защита организации с помощью Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="85b94-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="85b94-134">Обнаружение подозрительных действий и возможных атак с помощью Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="85b94-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="85b94-135">Обнаружение угроз и управление оповещениями с помощью Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="85b94-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="85b94-136">Изучение и устранение угроз с помощью Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="85b94-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
