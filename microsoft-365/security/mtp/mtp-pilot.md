---
title: Запуск пилотного проекта Microsoft Threat protection
description: Запустите пилотный проект Microsoft Threat Protection в рабочей среде, чтобы эффективно определить преимущества и внедрение защиты от угроз Майкрософт (MTP).
keywords: Пилотная программа Microsoft Threat Protection, выполнение пилотного проекта Microsoft Threat Protection, оценка защиты от угроз Майкрософт, пилотный проект Майкрософт по защите от угроз, кибератак безопасность, повышенная постоянная угроза, Корпоративная защита, устройства, устройства, удостоверения, пользователи, данные, приложения, инциденты, автоматическое исследование и исправление, расширенный поиск
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
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 4ec46891248c09f580b19d888573544ad2b4930f
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446871"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="b0903-104">Запуск пилотного проекта Microsoft Threat protection</span><span class="sxs-lookup"><span data-stu-id="b0903-104">Run your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b0903-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b0903-105">**Applies to:**</span></span>
- <span data-ttu-id="b0903-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="b0903-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b0903-107">Чтобы эффективно определить преимущества и внедрение защиты от угроз Майкрософт (MTP), вы можете запустить пилотный проект.</span><span class="sxs-lookup"><span data-stu-id="b0903-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="b0903-108">Перед включением защиты от угроз Майкрософт в рабочей среде и при запуске вариантов использования лучше всего определить задачи, которые необходимо выполнить для пилотного проекта, и задать критерии успеха.</span><span class="sxs-lookup"><span data-stu-id="b0903-108">Before enabling Microsoft Threat Protection in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="b0903-109">Как использовать эту пилотную стратегия</span><span class="sxs-lookup"><span data-stu-id="b0903-109">How to use this pilot playbook</span></span>

<span data-ttu-id="b0903-110">В этом руководстве представлен обзор защиты от угроз Майкрософт и пошаговые инструкции по настройке пилотного проекта.</span><span class="sxs-lookup"><span data-stu-id="b0903-110">This guide provides an overview of Microsoft Threat Protection and step-by-step instructions on how to set up your pilot project.</span></span> 

![Этапы запуска пилотного проекта по защите от угроз Майкрософт](../../media/pilotphases.png)

<span data-ttu-id="b0903-112">Ниже показана временная временная шкала, зависящая от наличия нужных ресурсов в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="b0903-112">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="b0903-113">Для некоторых обнаружений и рабочих процессов может потребоваться больше времени на обучение, чем для других.</span><span class="sxs-lookup"><span data-stu-id="b0903-113">Some detections and workflows might need more learning time than the others.</span></span>

![Пример временной шкалы, в которой работает пилотный проект Microsoft Threat protection](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="b0903-115">Для достижения оптимальных результатов выполните пробные инструкции, как можно ближе.</span><span class="sxs-lookup"><span data-stu-id="b0903-115">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="b0903-116">Пилотные фазы стратегия</span><span class="sxs-lookup"><span data-stu-id="b0903-116">Pilot playbook phases</span></span> 

<span data-ttu-id="b0903-117">Для запуска пилотного проекта по защите от угроз Майкрософт существует четыре этапа.</span><span class="sxs-lookup"><span data-stu-id="b0903-117">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="b0903-118">Этап</span><span class="sxs-lookup"><span data-stu-id="b0903-118">Phase</span></span> | <span data-ttu-id="b0903-119">Описание</span><span class="sxs-lookup"><span data-stu-id="b0903-119">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="b0903-120">![Планирование](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="b0903-120">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="b0903-121">Планирование</span><span class="sxs-lookup"><span data-stu-id="b0903-121">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="b0903-122">Сведения о том, что необходимо учесть перед запуском пилотного проекта Microsoft Threat protection:</span><span class="sxs-lookup"><span data-stu-id="b0903-122">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="b0903-123">Область действия</span><span class="sxs-lookup"><span data-stu-id="b0903-123">- Scope</span></span> <br> <span data-ttu-id="b0903-124">— Варианты использования</span><span class="sxs-lookup"><span data-stu-id="b0903-124">- Use cases</span></span> <br><span data-ttu-id="b0903-125">- Требования</span><span class="sxs-lookup"><span data-stu-id="b0903-125">- Requirements</span></span> <br><span data-ttu-id="b0903-126">-Тестовый план</span><span class="sxs-lookup"><span data-stu-id="b0903-126">- Test plan</span></span> <br> <span data-ttu-id="b0903-127">Условия успеха</span><span class="sxs-lookup"><span data-stu-id="b0903-127">- Success criteria</span></span> <br> <span data-ttu-id="b0903-128">— Система показателей</span><span class="sxs-lookup"><span data-stu-id="b0903-128">- Scorecard</span></span> 
| <span data-ttu-id="b0903-129">![Предваритель](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="b0903-129">![Preparation](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="b0903-130">Предваритель</span><span class="sxs-lookup"><span data-stu-id="b0903-130">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="b0903-131">Получите доступ к центру безопасности Microsoft 365, чтобы настроить пилотную среду Майкрософт для защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="b0903-131">Access Microsoft 365 Security Center to set up your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="b0903-132">Вы будете переработаны в следующих руководствах:</span><span class="sxs-lookup"><span data-stu-id="b0903-132">You'll be guided to:</span></span><br><br><span data-ttu-id="b0903-133">— Определение заинтересованных лиц и поиск для пилотного проекта</span><span class="sxs-lookup"><span data-stu-id="b0903-133">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="b0903-134">Аспекты среды</span><span class="sxs-lookup"><span data-stu-id="b0903-134">- Environment considerations</span></span> <br><span data-ttu-id="b0903-135">Доступ</span><span class="sxs-lookup"><span data-stu-id="b0903-135">- Access</span></span> <br><span data-ttu-id="b0903-136">— Установка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b0903-136">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="b0903-137">— Порядок настройки</span><span class="sxs-lookup"><span data-stu-id="b0903-137">- Configuration order</span></span> <br> <span data-ttu-id="b0903-138">— Подписаться на пробную версию Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0903-138">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="b0903-139">— Настройка домена</span><span class="sxs-lookup"><span data-stu-id="b0903-139">- Configure domain</span></span> <br><span data-ttu-id="b0903-140">— Назначение лицензий Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0903-140">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="b0903-141">— Завершите работу мастера установки на портале.</span><span class="sxs-lookup"><span data-stu-id="b0903-141">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="b0903-142">![Имитация атаки](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="b0903-142">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="b0903-143">Имитация атаки</span><span class="sxs-lookup"><span data-stu-id="b0903-143">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="b0903-144">Чтобы имитировать атаку, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b0903-144">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="b0903-145">-Проверка требований к тестовой среде</span><span class="sxs-lookup"><span data-stu-id="b0903-145">- Verify the test environment requirements</span></span> <br><span data-ttu-id="b0903-146">Запуск модели</span><span class="sxs-lookup"><span data-stu-id="b0903-146">-  Run the simulation</span></span> <br><span data-ttu-id="b0903-147">— Исследование инцидента</span><span class="sxs-lookup"><span data-stu-id="b0903-147">- Investigate an incident</span></span> <br><span data-ttu-id="b0903-148">— устранение инцидента</span><span class="sxs-lookup"><span data-stu-id="b0903-148">- resolve the incident</span></span> 
| <span data-ttu-id="b0903-149">![Заключение и заключение](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="b0903-149">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="b0903-150">Заключение и заключение</span><span class="sxs-lookup"><span data-stu-id="b0903-150">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="b0903-151">Когда вы достигли конца процесса, вы будете участником следующих действий:</span><span class="sxs-lookup"><span data-stu-id="b0903-151">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="b0903-152">— Пройти по итоговым выходным данным</span><span class="sxs-lookup"><span data-stu-id="b0903-152">- Go through your final output</span></span><br><span data-ttu-id="b0903-153">— Предоставление вашим заинтересованным лицам выходных данных</span><span class="sxs-lookup"><span data-stu-id="b0903-153">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="b0903-154">— Оставить отзыв</span><span class="sxs-lookup"><span data-stu-id="b0903-154">- Provide feedback</span></span> <br><span data-ttu-id="b0903-155">Выполните следующие действия</span><span class="sxs-lookup"><span data-stu-id="b0903-155">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="b0903-156">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="b0903-156">Next step</span></span>
|<span data-ttu-id="b0903-157">![Этап планирования](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="b0903-157">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="b0903-158">Этап планирования</span><span class="sxs-lookup"><span data-stu-id="b0903-158">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="b0903-159">Планирование пилотного проекта Microsoft Threat protection</span><span class="sxs-lookup"><span data-stu-id="b0903-159">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
