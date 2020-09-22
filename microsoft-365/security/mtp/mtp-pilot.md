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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 88d92558d86e0aa2e90ef04d88a3cd4676386f15
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195631"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="ffe72-104">Запуск пилотного проекта Microsoft Threat protection</span><span class="sxs-lookup"><span data-stu-id="ffe72-104">Run your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ffe72-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ffe72-105">**Applies to:**</span></span>
- <span data-ttu-id="ffe72-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="ffe72-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="ffe72-107">Чтобы эффективно определить преимущества и внедрение защиты от угроз Майкрософт (MTP), вы можете запустить пилотный проект.</span><span class="sxs-lookup"><span data-stu-id="ffe72-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="ffe72-108">Перед включением защиты от угроз Майкрософт в рабочей среде и начала работы с определенными вариантами использования рекомендуется выполнить процесс планирования, чтобы определить задачи, которые необходимо выполнить в этом пилотном проекте, и условия их успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="ffe72-108">Before enabling Microsoft Threat Protection in your production environment and starting with defined use cases, it is best to go through a planning process to determine the tasks that must be accomplished in this pilot project, and the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="ffe72-109">Как использовать эту пилотную стратегия</span><span class="sxs-lookup"><span data-stu-id="ffe72-109">How to use this pilot playbook</span></span>

<span data-ttu-id="ffe72-110">В этом руководстве представлен обзор защиты от угроз Майкрософт и пошаговое руководство по настройке пилотного проекта.</span><span class="sxs-lookup"><span data-stu-id="ffe72-110">This guide provides an overview of Microsoft Threat Protection and step-by-step guidance on how to set up your pilot project.</span></span> 

![Этапы запуска пилотного проекта по защите от угроз Майкрософт](../../media/pilotphases.png)

<span data-ttu-id="ffe72-112">Ниже показана временная временная шкала, зависящая от наличия нужных ресурсов в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="ffe72-112">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="ffe72-113">Для некоторых обнаружений и рабочих процессов может потребоваться больше времени на обучение, чем для других.</span><span class="sxs-lookup"><span data-stu-id="ffe72-113">Some detections and workflows might need more learning time than the others.</span></span>

![Пример временной шкалы, в которой работает пилотный проект Microsoft Threat protection](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="ffe72-115">Для достижения оптимальных результатов выполните пробные инструкции, как можно ближе.</span><span class="sxs-lookup"><span data-stu-id="ffe72-115">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="ffe72-116">Пилотные фазы стратегия</span><span class="sxs-lookup"><span data-stu-id="ffe72-116">Pilot playbook phases</span></span> 

<span data-ttu-id="ffe72-117">Для запуска пилотного проекта по защите от угроз Майкрософт существует четыре этапа.</span><span class="sxs-lookup"><span data-stu-id="ffe72-117">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="ffe72-118">Этап</span><span class="sxs-lookup"><span data-stu-id="ffe72-118">Phase</span></span> | <span data-ttu-id="ffe72-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ffe72-119">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="ffe72-120">![Планирование](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="ffe72-120">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="ffe72-121">Планирование</span><span class="sxs-lookup"><span data-stu-id="ffe72-121">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="ffe72-122">Сведения о том, что необходимо учесть перед запуском пилотного проекта Microsoft Threat protection:</span><span class="sxs-lookup"><span data-stu-id="ffe72-122">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="ffe72-123">Область действия</span><span class="sxs-lookup"><span data-stu-id="ffe72-123">- Scope</span></span> <br> <span data-ttu-id="ffe72-124">— Варианты использования</span><span class="sxs-lookup"><span data-stu-id="ffe72-124">- Use cases</span></span> <br><span data-ttu-id="ffe72-125">- Требования</span><span class="sxs-lookup"><span data-stu-id="ffe72-125">- Requirements</span></span> <br><span data-ttu-id="ffe72-126">-Тестовый план</span><span class="sxs-lookup"><span data-stu-id="ffe72-126">- Test plan</span></span> <br> <span data-ttu-id="ffe72-127">Условия успеха</span><span class="sxs-lookup"><span data-stu-id="ffe72-127">- Success criteria</span></span> <br> <span data-ttu-id="ffe72-128">— Система показателей</span><span class="sxs-lookup"><span data-stu-id="ffe72-128">- Scorecard</span></span> 
| <span data-ttu-id="ffe72-129">![Предваритель](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="ffe72-129">![Preparation](../../media/prepare.png)</span></span> <br>[<span data-ttu-id="ffe72-130">Предваритель</span><span class="sxs-lookup"><span data-stu-id="ffe72-130">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="ffe72-131">Доступ к центру безопасности Microsoft 365 для настройки экспериментальной среды Майкрософт по защите от угроз.</span><span class="sxs-lookup"><span data-stu-id="ffe72-131">Access Microsoft 365 Security Center to setup your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="ffe72-132">Вы будете переработаны в следующих руководствах:</span><span class="sxs-lookup"><span data-stu-id="ffe72-132">You will be guided to:</span></span><br><br><span data-ttu-id="ffe72-133">— Определение заинтересованных лиц и поиск для пилотного проекта</span><span class="sxs-lookup"><span data-stu-id="ffe72-133">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="ffe72-134">Аспекты среды</span><span class="sxs-lookup"><span data-stu-id="ffe72-134">- Environment considerations</span></span> <br><span data-ttu-id="ffe72-135">Доступ</span><span class="sxs-lookup"><span data-stu-id="ffe72-135">- Access</span></span> <br><span data-ttu-id="ffe72-136">— Установка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ffe72-136">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="ffe72-137">— Порядок настройки</span><span class="sxs-lookup"><span data-stu-id="ffe72-137">- Configuration order</span></span> <br> <span data-ttu-id="ffe72-138">— Подписаться на пробную версию Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ffe72-138">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="ffe72-139">— Настройка домена</span><span class="sxs-lookup"><span data-stu-id="ffe72-139">- Configure domain</span></span> <br><span data-ttu-id="ffe72-140">— Назначение лицензий Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ffe72-140">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="ffe72-141">— Завершите работу мастера установки на портале.</span><span class="sxs-lookup"><span data-stu-id="ffe72-141">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="ffe72-142">![Имитация атаки](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="ffe72-142">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="ffe72-143">Имитация атаки</span><span class="sxs-lookup"><span data-stu-id="ffe72-143">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="ffe72-144">Чтобы имитировать атаку, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ffe72-144">To simulate an attack, you will be guided to:</span></span><br><br><span data-ttu-id="ffe72-145">-Проверка требований к тестовой среде</span><span class="sxs-lookup"><span data-stu-id="ffe72-145">- Verify the test environment requirements</span></span> <br><span data-ttu-id="ffe72-146">Запуск модели</span><span class="sxs-lookup"><span data-stu-id="ffe72-146">-  Run the simulation</span></span> <br><span data-ttu-id="ffe72-147">— Исследование инцидента</span><span class="sxs-lookup"><span data-stu-id="ffe72-147">- Investigate an incident</span></span> <br><span data-ttu-id="ffe72-148">— устранение инцидента</span><span class="sxs-lookup"><span data-stu-id="ffe72-148">- resolve the incident</span></span> 
| <span data-ttu-id="ffe72-149">![Заключение и заключение](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="ffe72-149">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="ffe72-150">Заключение и заключение</span><span class="sxs-lookup"><span data-stu-id="ffe72-150">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="ffe72-151">Когда вы достигли конца этого процесса, вы будете участником:</span><span class="sxs-lookup"><span data-stu-id="ffe72-151">When you've reached the end of the process, you will be guided to:</span></span><br><br><span data-ttu-id="ffe72-152">— Пройти по итоговым выходным данным</span><span class="sxs-lookup"><span data-stu-id="ffe72-152">- Go through your final output</span></span><br><span data-ttu-id="ffe72-153">— Предоставление вашим заинтересованным лицам выходных данных</span><span class="sxs-lookup"><span data-stu-id="ffe72-153">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="ffe72-154">— Оставить отзыв</span><span class="sxs-lookup"><span data-stu-id="ffe72-154">- Provide feedback</span></span> <br><span data-ttu-id="ffe72-155">Выполните следующие действия</span><span class="sxs-lookup"><span data-stu-id="ffe72-155">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="ffe72-156">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="ffe72-156">Next step</span></span>
|<span data-ttu-id="ffe72-157">![Этап планирования](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="ffe72-157">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="ffe72-158">Этап планирования</span><span class="sxs-lookup"><span data-stu-id="ffe72-158">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="ffe72-159">Планирование пилотного проекта Microsoft Threat protection</span><span class="sxs-lookup"><span data-stu-id="ffe72-159">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
