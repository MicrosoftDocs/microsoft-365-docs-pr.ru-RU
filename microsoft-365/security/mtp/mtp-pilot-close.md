---
title: Общие сведения о пилотных результатах проекта защитника Microsoft 365
description: Завершите пилотный проект Microsoft 365 Defender, выполнив систему показателей, анализируя результаты отчета и принимая решение о том, как перемещаться вперед.
keywords: Пилотный проект по защите от угроз Майкрософт, выберите дальнейшие действия после пробного развертывания Microsoft Threat Protection, что делать после оценки защиты от угроз Майкрософт в рабочей среде, перехода от пилотной системы защиты от угроз Майкрософт к развертыванию, безопасности кибератак, расширенной постоянной угрозе, корпоративной безопасности, устройств, устройств, удостоверений, пользователей, данных, приложений, инцидентов, автоматизированного исследования и исправления
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 3fe5bfdec566b0988d9f565595624fc8dd597788
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130947"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="b2662-104">Заключение и подведение итогов для пилотного проекта защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b2662-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b2662-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b2662-105">**Applies to:**</span></span>
- <span data-ttu-id="b2662-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b2662-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="b2662-107">[![Планирование](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="b2662-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="b2662-108">Планирование</span><span class="sxs-lookup"><span data-stu-id="b2662-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="b2662-109">[![Подготовка](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="b2662-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="b2662-110">Предваритель</span><span class="sxs-lookup"><span data-stu-id="b2662-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="b2662-111">[![Имитация атаки](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="b2662-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="b2662-112">Имитация атаки</span><span class="sxs-lookup"><span data-stu-id="b2662-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![Закрытие и итоги](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="b2662-114">Закрытие и итоги</span><span class="sxs-lookup"><span data-stu-id="b2662-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="b2662-115">*Вот что вам!*</span><span class="sxs-lookup"><span data-stu-id="b2662-115">*You are here!*</span></span>|


<span data-ttu-id="b2662-116">В настоящее время вы находитесь на этапе закрытия и создания итогов.</span><span class="sxs-lookup"><span data-stu-id="b2662-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="b2662-117">Вы только что выполнили расширенную атаку "только для памяти", которая выполнила код удаленно на контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="b2662-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="b2662-118">Вы видели, как защитник Майкрософт для конечной точки и защитник Майкрософт для обнаружения удостоверения и создания оповещений на стеалси вредоносных действиях.</span><span class="sxs-lookup"><span data-stu-id="b2662-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="b2662-119">Вы также видели, как оповещения из различных источников доставляются вместе с другими контекстными сведениями в один инцидент на портале центра обеспечения безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b2662-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="b2662-120">Такая интеграция позволяет аналитикам SOC исследовать и предпринимать необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="b2662-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="b2662-121">Вы также создали Расширенный запрос поиска, который определит входящие сообщения электронной почты, в которых пользователь открыл или сохранил вложение и создал обнаружение на основе этого запроса.</span><span class="sxs-lookup"><span data-stu-id="b2662-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="b2662-122">Вы достигли конца процесса после завершения всех тестов.</span><span class="sxs-lookup"><span data-stu-id="b2662-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="b2662-123">Ниже приведен полный результат.</span><span class="sxs-lookup"><span data-stu-id="b2662-123">The final output should be:</span></span>

- <span data-ttu-id="b2662-124">Завершенная система показателей</span><span class="sxs-lookup"><span data-stu-id="b2662-124">A completed scorecard</span></span>
- <span data-ttu-id="b2662-125">Подробный отчет о результатах пилотного проекта</span><span class="sxs-lookup"><span data-stu-id="b2662-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="b2662-126">Решение о перемещении вперед</span><span class="sxs-lookup"><span data-stu-id="b2662-126">A decision on how to move forward</span></span>

<span data-ttu-id="b2662-127">Предоставление отчетов из итогового выхода внутренним заинтересованным лицам (которые определены на этапе [подготовки](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) ) и контактах Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b2662-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="b2662-128">Это гарантирует, что любые отзывы можно использовать для усовершенствования продуктов и документации.</span><span class="sxs-lookup"><span data-stu-id="b2662-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="b2662-129">Мы надеемся, что вы довольны этим моделированием.</span><span class="sxs-lookup"><span data-stu-id="b2662-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="b2662-130">Начните внедрять то, что вы узнали из большого масштаба в вашей организации, чтобы максимально эффективно использовать встроенную систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="b2662-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="b2662-131">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="b2662-131">Next step</span></span>
<span data-ttu-id="b2662-132">Узнайте больше о возвыстях защитника Microsoft 365 с помощью следующих интерактивных руководств:</span><span class="sxs-lookup"><span data-stu-id="b2662-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="b2662-133">Защита Организации с помощью защитника Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="b2662-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="b2662-134">Обнаружение подозрительных действий и возможных атак с помощью Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="b2662-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="b2662-135">Обнаружение угроз и Управление оповещениями с помощью Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b2662-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="b2662-136">Исследование и исправление угроз с помощью защитника Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b2662-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
