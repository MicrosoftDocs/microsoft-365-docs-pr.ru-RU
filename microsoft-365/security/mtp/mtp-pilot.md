---
title: Запуск пилотного проекта Microsoft 365 Defender
description: Запустите пилотный проект Microsoft 365 Defender в производственной области, чтобы эффективно определить преимущества и внедрение Microsoft 365 Defender.
keywords: Пилотный проект Защиты от угроз (Майкрософт), запуск пилотного проекта Защиты от угроз (Майкрософт), оценка защиты от угроз (Майкрософт) в производственной сфере, пилотный проект Защиты от угроз (Майкрософт), кибербезопасность, расширенные устойчивые угрозы, корпоративная безопасность, устройства, устройство, удостоверение, пользователи, данные, приложения, инциденты, автоматизированное исследование и исправление, расширенный поиск
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
ms.openlocfilehash: f01e918d35ce77d9239c200355c7b4c48c9e2b84
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659325"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="78509-104">Запуск пилотного проекта Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78509-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="78509-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="78509-105">**Applies to:**</span></span>
- <span data-ttu-id="78509-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78509-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="78509-107">Это руководство поможет вам запустить пилотный проект, указав указатели, чтобы убедиться в том, что у вас есть хорошо структурированный план, помогают использовать функцию имитации атак и, наконец, заключите пилотный проект с ключевыми задачами, чтобы отразить и запланировать результаты.</span><span class="sxs-lookup"><span data-stu-id="78509-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Этапы пилотного проекта Microsoft 365 Defender](../../media/pilotphases.png)


<span data-ttu-id="78509-109">Пилотный проект помогает эффективно определить преимущества принятия Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="78509-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="78509-110">Перед включением Защитника Microsoft 365 в производственной среде и запуском вариантов использования лучше запланировать определение задач, которые необходимо выполнить для пилотного проекта, и установить критерии успеха.</span><span class="sxs-lookup"><span data-stu-id="78509-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="78509-111">Использование пилотной книги</span><span class="sxs-lookup"><span data-stu-id="78509-111">How to use this pilot playbook</span></span>

<span data-ttu-id="78509-112">В этом руководстве представлен обзор Защитника Microsoft 365 и пошаговая инструкция по настройкам пилотного проекта.</span><span class="sxs-lookup"><span data-stu-id="78509-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="78509-113">Microsoft 365 Defender — это единый набор защиты предприятия до и после взлома, который полностью координирует защиту, обнаружение, предотвращение, исследование и реагирование на них между конечными точками, удостоверениями, электронной почтой и приложениями для обеспечения интегрированной защиты от сложных атак.</span><span class="sxs-lookup"><span data-stu-id="78509-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="78509-114">Это делается путем объединения и оркестрирования следующих возможностей в единое решение для обеспечения безопасности:</span><span class="sxs-lookup"><span data-stu-id="78509-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="78509-115">Microsoft Defender для конечной точки, новое имя advanced Threat Protection в Microsoft Defender (конечные точки)</span><span class="sxs-lookup"><span data-stu-id="78509-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="78509-116">Microsoft Defender для Office 365— новое имя Office 365 ATP (электронная почта)</span><span class="sxs-lookup"><span data-stu-id="78509-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="78509-117">Microsoft Defender для удостоверений, новое имя azure ATP (удостоверение)</span><span class="sxs-lookup"><span data-stu-id="78509-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="78509-118">Microsoft Cloud App Security (приложения)</span><span class="sxs-lookup"><span data-stu-id="78509-118">Microsoft Cloud App Security (apps)</span></span>

![Изображение of_Microsoft 365 Defender для пользователей, Microsoft Defender для удостоверений, для конечных точек Microsoft Defender для конечной точки, для облачных приложений, Microsoft Cloud App Security и для данных, Microsoft Defender для Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="78509-120">Благодаря интегрированному решению Microsoft 365 Defender специалисты по безопасности могут собрать вместе сигналы об угрозах, получаемые Microsoft Defender для endpoint, Microsoft Defender для Office 365, Microsoft Defender для удостоверений и Microsoft Cloud App Security, а также определить полную область и влияние угрозы, способ ее выхода в среду, ее влияние и влияние на организацию.</span><span class="sxs-lookup"><span data-stu-id="78509-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="78509-121">Защитник Microsoft 365 автоматически предотвращает или останавливает атаки, а также самостоятельно исцеляет затронутые почтовые ящики, конечные точки и удостоверения пользователей.</span><span class="sxs-lookup"><span data-stu-id="78509-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="78509-122">Подробные сведения см. в обзоре [Защитника Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="78509-122">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>



<span data-ttu-id="78509-123">Следующая временная шкала зависит от написания необходимых ресурсов в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="78509-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="78509-124">Для некоторых обнаружений и рабочего процесса может потребоваться больше времени на обучение, чем для других.</span><span class="sxs-lookup"><span data-stu-id="78509-124">Some detections and workflows might need more learning time than the others.</span></span>

![Пример временной шкалы при запуске пилотного проекта Microsoft 365 Defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="78509-126">Для достижения оптимальных результатов следуйте инструкциям пилотного проекта максимально точно.</span><span class="sxs-lookup"><span data-stu-id="78509-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="78509-127">Этапы пилотного воспроизведения</span><span class="sxs-lookup"><span data-stu-id="78509-127">Pilot playbook phases</span></span> 

<span data-ttu-id="78509-128">Пилотный проект Microsoft 365 Defender можно запускать в четыре этапа:</span><span class="sxs-lookup"><span data-stu-id="78509-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="78509-129">Этап</span><span class="sxs-lookup"><span data-stu-id="78509-129">Phase</span></span> | <span data-ttu-id="78509-130">Описание</span><span class="sxs-lookup"><span data-stu-id="78509-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="78509-131">Планирование</span><span class="sxs-lookup"><span data-stu-id="78509-131">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="78509-132">~ 1 день</span><span class="sxs-lookup"><span data-stu-id="78509-132">~ 1 day</span></span>| <span data-ttu-id="78509-133">Узнайте, что необходимо учитывать перед запуском пилотного проекта Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="78509-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="78509-134">- Область действия</span><span class="sxs-lookup"><span data-stu-id="78509-134">- Scope</span></span> <br> <span data-ttu-id="78509-135">- Случаи использования</span><span class="sxs-lookup"><span data-stu-id="78509-135">- Use cases</span></span> <br><span data-ttu-id="78509-136">- Требования</span><span class="sxs-lookup"><span data-stu-id="78509-136">- Requirements</span></span> <br><span data-ttu-id="78509-137">- План тестирования</span><span class="sxs-lookup"><span data-stu-id="78509-137">- Test plan</span></span> <br> <span data-ttu-id="78509-138">- Критерии успешности</span><span class="sxs-lookup"><span data-stu-id="78509-138">- Success criteria</span></span> <br> <span data-ttu-id="78509-139">- Система показателей</span><span class="sxs-lookup"><span data-stu-id="78509-139">- Scorecard</span></span> 
| [<span data-ttu-id="78509-140">Подготовка</span><span class="sxs-lookup"><span data-stu-id="78509-140">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="78509-141">~2 дня</span><span class="sxs-lookup"><span data-stu-id="78509-141">~2 days</span></span>|  <span data-ttu-id="78509-142">Чтобы настроить пилотную среду Microsoft 365 Defender, можно получить доступ к Центру безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78509-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="78509-143">Вы получите руководство по:</span><span class="sxs-lookup"><span data-stu-id="78509-143">You'll be guided to:</span></span><br><br><span data-ttu-id="78509-144">- Определите заинтересованных лиц и выищите вход для пилотного проекта</span><span class="sxs-lookup"><span data-stu-id="78509-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="78509-145">- Вопросы среды</span><span class="sxs-lookup"><span data-stu-id="78509-145">- Environment considerations</span></span> <br><span data-ttu-id="78509-146">- Access</span><span class="sxs-lookup"><span data-stu-id="78509-146">- Access</span></span> <br><span data-ttu-id="78509-147">- Настройка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="78509-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="78509-148">- Порядок настройки</span><span class="sxs-lookup"><span data-stu-id="78509-148">- Configuration order</span></span> <br> <span data-ttu-id="78509-149">- Зарегистрироваться для пробной пробной пробной службы Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="78509-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="78509-150">- Настройка домена</span><span class="sxs-lookup"><span data-stu-id="78509-150">- Configure domain</span></span> <br><span data-ttu-id="78509-151">- Назначение лицензий Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="78509-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="78509-152">— Завершение работы мастера настройки на портале</span><span class="sxs-lookup"><span data-stu-id="78509-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="78509-153">Имитация атаки</span><span class="sxs-lookup"><span data-stu-id="78509-153">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="78509-154">~2 дня</span><span class="sxs-lookup"><span data-stu-id="78509-154">~2 days</span></span>| <span data-ttu-id="78509-155">Чтобы смоделировать атаку, вы получите руководство по:</span><span class="sxs-lookup"><span data-stu-id="78509-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="78509-156">- Проверка требований тестовой среды</span><span class="sxs-lookup"><span data-stu-id="78509-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="78509-157">- Запуск имитации</span><span class="sxs-lookup"><span data-stu-id="78509-157">-  Run the simulation</span></span> <br><span data-ttu-id="78509-158">- Исследовать инцидент</span><span class="sxs-lookup"><span data-stu-id="78509-158">- Investigate an incident</span></span> <br><span data-ttu-id="78509-159">- уладить инцидент</span><span class="sxs-lookup"><span data-stu-id="78509-159">- resolve the incident</span></span> 
| [<span data-ttu-id="78509-160">Закрытие и сводка</span><span class="sxs-lookup"><span data-stu-id="78509-160">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="78509-161">~ 1 день</span><span class="sxs-lookup"><span data-stu-id="78509-161">~ 1 day</span></span>| <span data-ttu-id="78509-162">По завершении процесса вы получите руководство по:</span><span class="sxs-lookup"><span data-stu-id="78509-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="78509-163">- Пройдите окончательный вывод</span><span class="sxs-lookup"><span data-stu-id="78509-163">- Go through your final output</span></span><br><span data-ttu-id="78509-164">– Представлять свои выходные данные заинтересованным лицам</span><span class="sxs-lookup"><span data-stu-id="78509-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="78509-165">- Обратная связь</span><span class="sxs-lookup"><span data-stu-id="78509-165">- Provide feedback</span></span> <br><span data-ttu-id="78509-166">- Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="78509-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="78509-167">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="78509-167">Next step</span></span>
|[<span data-ttu-id="78509-168">Этап планирования</span><span class="sxs-lookup"><span data-stu-id="78509-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="78509-169">Планирование пилотного проекта Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78509-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
