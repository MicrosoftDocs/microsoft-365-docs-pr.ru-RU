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
ms.openlocfilehash: af47f45ca4f3d14e835a39a334a9400002ac8560
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418077"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="29ce8-104">Запуск пилотного проекта Microsoft Threat protection</span><span class="sxs-lookup"><span data-stu-id="29ce8-104">Run your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="29ce8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="29ce8-105">**Applies to:**</span></span>
- <span data-ttu-id="29ce8-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="29ce8-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="29ce8-107">Чтобы эффективно определить преимущества и внедрение защиты от угроз Майкрософт (MTP), вы можете запустить пилотный проект.</span><span class="sxs-lookup"><span data-stu-id="29ce8-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="29ce8-108">Перед включением защиты от угроз Майкрософт в рабочей среде и начала работы с определенными вариантами использования рекомендуется выполнить процесс планирования, чтобы определить задачи, которые необходимо выполнить в этом пилотном проекте, и условия их успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="29ce8-108">Before enabling Microsoft Threat Protection in your production environment and starting with defined use cases, it is best to go through a planning process to determine the tasks that must be accomplished in this pilot project, and the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="29ce8-109">Как использовать эту пилотную стратегия</span><span class="sxs-lookup"><span data-stu-id="29ce8-109">How to use this pilot playbook</span></span>

<span data-ttu-id="29ce8-110">В этом руководстве представлен обзор защиты от угроз Майкрософт и пошаговые инструкции по настройке пилотного проекта.</span><span class="sxs-lookup"><span data-stu-id="29ce8-110">This guide provides an overview of Microsoft Threat Protection and step-by-step instructions on how to set up your pilot project.</span></span> 

![Этапы запуска пилотного проекта по защите от угроз Майкрософт](../../media/pilotphases.png)

<span data-ttu-id="29ce8-112">Ниже показана временная временная шкала, зависящая от наличия нужных ресурсов в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="29ce8-112">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="29ce8-113">Для некоторых обнаружений и рабочих процессов может потребоваться больше времени на обучение, чем для других.</span><span class="sxs-lookup"><span data-stu-id="29ce8-113">Some detections and workflows might need more learning time than the others.</span></span>

![Пример временной шкалы, в которой работает пилотный проект Microsoft Threat protection](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="29ce8-115">Для достижения оптимальных результатов выполните пробные инструкции, как можно ближе.</span><span class="sxs-lookup"><span data-stu-id="29ce8-115">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="29ce8-116">Пилотные фазы стратегия</span><span class="sxs-lookup"><span data-stu-id="29ce8-116">Pilot playbook phases</span></span> 

<span data-ttu-id="29ce8-117">Для запуска пилотного проекта по защите от угроз Майкрософт существует четыре этапа.</span><span class="sxs-lookup"><span data-stu-id="29ce8-117">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="29ce8-118">Этап</span><span class="sxs-lookup"><span data-stu-id="29ce8-118">Phase</span></span> | <span data-ttu-id="29ce8-119">Описание</span><span class="sxs-lookup"><span data-stu-id="29ce8-119">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="29ce8-120">![Планирование](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="29ce8-120">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="29ce8-121">Планирование</span><span class="sxs-lookup"><span data-stu-id="29ce8-121">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="29ce8-122">Сведения о том, что необходимо учесть перед запуском пилотного проекта Microsoft Threat protection:</span><span class="sxs-lookup"><span data-stu-id="29ce8-122">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="29ce8-123">Область действия</span><span class="sxs-lookup"><span data-stu-id="29ce8-123">- Scope</span></span> <br> <span data-ttu-id="29ce8-124">— Варианты использования</span><span class="sxs-lookup"><span data-stu-id="29ce8-124">- Use cases</span></span> <br><span data-ttu-id="29ce8-125">- Требования</span><span class="sxs-lookup"><span data-stu-id="29ce8-125">- Requirements</span></span> <br><span data-ttu-id="29ce8-126">-Тестовый план</span><span class="sxs-lookup"><span data-stu-id="29ce8-126">- Test plan</span></span> <br> <span data-ttu-id="29ce8-127">Условия успеха</span><span class="sxs-lookup"><span data-stu-id="29ce8-127">- Success criteria</span></span> <br> <span data-ttu-id="29ce8-128">— Система показателей</span><span class="sxs-lookup"><span data-stu-id="29ce8-128">- Scorecard</span></span> 
| <span data-ttu-id="29ce8-129">![Предваритель](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="29ce8-129">![Preparation](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="29ce8-130">Предваритель</span><span class="sxs-lookup"><span data-stu-id="29ce8-130">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="29ce8-131">Доступ к центру безопасности Microsoft 365 для настройки экспериментальной среды Майкрософт по защите от угроз.</span><span class="sxs-lookup"><span data-stu-id="29ce8-131">Access Microsoft 365 Security Center to setup your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="29ce8-132">Вы будете переработаны в следующих руководствах:</span><span class="sxs-lookup"><span data-stu-id="29ce8-132">You will be guided to:</span></span><br><br><span data-ttu-id="29ce8-133">— Определение заинтересованных лиц и поиск для пилотного проекта</span><span class="sxs-lookup"><span data-stu-id="29ce8-133">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="29ce8-134">Аспекты среды</span><span class="sxs-lookup"><span data-stu-id="29ce8-134">- Environment considerations</span></span> <br><span data-ttu-id="29ce8-135">Доступ</span><span class="sxs-lookup"><span data-stu-id="29ce8-135">- Access</span></span> <br><span data-ttu-id="29ce8-136">— Установка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="29ce8-136">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="29ce8-137">— Порядок настройки</span><span class="sxs-lookup"><span data-stu-id="29ce8-137">- Configuration order</span></span> <br> <span data-ttu-id="29ce8-138">— Подписаться на пробную версию Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="29ce8-138">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="29ce8-139">— Настройка домена</span><span class="sxs-lookup"><span data-stu-id="29ce8-139">- Configure domain</span></span> <br><span data-ttu-id="29ce8-140">— Назначение лицензий Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="29ce8-140">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="29ce8-141">— Завершите работу мастера установки на портале.</span><span class="sxs-lookup"><span data-stu-id="29ce8-141">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="29ce8-142">![Имитация атаки](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="29ce8-142">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="29ce8-143">Имитация атаки</span><span class="sxs-lookup"><span data-stu-id="29ce8-143">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="29ce8-144">Чтобы имитировать атаку, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="29ce8-144">To simulate an attack, you will be guided to:</span></span><br><br><span data-ttu-id="29ce8-145">-Проверка требований к тестовой среде</span><span class="sxs-lookup"><span data-stu-id="29ce8-145">- Verify the test environment requirements</span></span> <br><span data-ttu-id="29ce8-146">Запуск модели</span><span class="sxs-lookup"><span data-stu-id="29ce8-146">-  Run the simulation</span></span> <br><span data-ttu-id="29ce8-147">— Исследование инцидента</span><span class="sxs-lookup"><span data-stu-id="29ce8-147">- Investigate an incident</span></span> <br><span data-ttu-id="29ce8-148">— устранение инцидента</span><span class="sxs-lookup"><span data-stu-id="29ce8-148">- resolve the incident</span></span> 
| <span data-ttu-id="29ce8-149">![Заключение и заключение](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="29ce8-149">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="29ce8-150">Заключение и заключение</span><span class="sxs-lookup"><span data-stu-id="29ce8-150">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="29ce8-151">Когда вы достигли конца этого процесса, вы будете участником:</span><span class="sxs-lookup"><span data-stu-id="29ce8-151">When you've reached the end of the process, you will be guided to:</span></span><br><br><span data-ttu-id="29ce8-152">— Пройти по итоговым выходным данным</span><span class="sxs-lookup"><span data-stu-id="29ce8-152">- Go through your final output</span></span><br><span data-ttu-id="29ce8-153">— Предоставление вашим заинтересованным лицам выходных данных</span><span class="sxs-lookup"><span data-stu-id="29ce8-153">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="29ce8-154">— Оставить отзыв</span><span class="sxs-lookup"><span data-stu-id="29ce8-154">- Provide feedback</span></span> <br><span data-ttu-id="29ce8-155">Выполните следующие действия</span><span class="sxs-lookup"><span data-stu-id="29ce8-155">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="29ce8-156">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="29ce8-156">Next step</span></span>
|<span data-ttu-id="29ce8-157">![Этап планирования](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="29ce8-157">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="29ce8-158">Этап планирования</span><span class="sxs-lookup"><span data-stu-id="29ce8-158">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="29ce8-159">Планирование пилотного проекта Microsoft Threat protection</span><span class="sxs-lookup"><span data-stu-id="29ce8-159">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
