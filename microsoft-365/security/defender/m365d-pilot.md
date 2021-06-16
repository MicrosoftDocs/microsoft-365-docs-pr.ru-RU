---
title: Запуск пилотного проекта Microsoft 365 Defender
description: Запустите пилотный Microsoft 365 Defender в производстве, чтобы эффективно определить преимущества и Microsoft 365 Defender.
keywords: Microsoft 365 Пилот defender, запуск пилотного проекта Microsoft 365 Defender, оценка Microsoft 365 Defender в производстве, пилотный проект Microsoft 365 Defender, кибербезопасность, расширенные постоянные угрозы, безопасность предприятия, устройства, устройства, удостоверения, пользователи, данные, приложения, инциденты, автоматическое расследование и исправление, продвинутая охота
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
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 3219b329c53c32e02cd29acdd41a48cd93b2e8bb
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930515"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="31772-104">Запуск пилотного проекта Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31772-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="31772-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="31772-105">**Applies to:**</span></span>
- <span data-ttu-id="31772-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31772-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="31772-107">Это руководство поможет вам запустить пилотный проект, предоставив указатели, чтобы убедиться, что у вас есть хорошо структурированный план, направляя вас с помощью функции имитации атаки, и, наконец, заключение пилота с ключом take-aways для вас, чтобы размышлять и документировать результаты.</span><span class="sxs-lookup"><span data-stu-id="31772-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Этапы запуска пилотного Microsoft 365 Defender](../../media/pilotphases.png)


<span data-ttu-id="31772-109">Запуск пилотного проекта позволяет эффективно определять преимущества принятия Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="31772-109">Running a pilot helps you effectively determine the benefit of adopting Microsoft 365 Defender.</span></span> <span data-ttu-id="31772-110">Перед включением Microsoft 365 Defender в производственной среде и запуском случаев использования лучше всего спланировать определение задач, которые необходимо выполнить для пилотного проекта, и задавая критерии успешности.</span><span class="sxs-lookup"><span data-stu-id="31772-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="31772-111">Использование этой экспериментальной книги воспроизведения</span><span class="sxs-lookup"><span data-stu-id="31772-111">How to use this pilot playbook</span></span>

<span data-ttu-id="31772-112">В этом руководстве представлен обзор Microsoft 365 defender и пошаговая инструкция по настройкам пилотного проекта.</span><span class="sxs-lookup"><span data-stu-id="31772-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="31772-113">Microsoft 365 Defender — это объединенный пакет защиты предприятия до и после нарушения, который в основном координирует защиту, обнаружение, предотвращение, расследование и ответные действия между конечными точками, удостоверениями, электронной почтой и приложениями для обеспечения комплексной защиты от сложных атак.</span><span class="sxs-lookup"><span data-stu-id="31772-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="31772-114">Это делается путем объединения и оркестровки следующих возможностей в единое решение безопасности:</span><span class="sxs-lookup"><span data-stu-id="31772-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="31772-115">Защитник Microsoft для конечной точки (конечные точки)</span><span class="sxs-lookup"><span data-stu-id="31772-115">Microsoft Defender for Endpoint (endpoints)</span></span>
  - <span data-ttu-id="31772-116">Microsoft Defender для Office 365 (электронная почта)</span><span class="sxs-lookup"><span data-stu-id="31772-116">Microsoft Defender for Office 365 (email)</span></span> 
  - <span data-ttu-id="31772-117">Защитник Microsoft для удостоверений (удостоверение)</span><span class="sxs-lookup"><span data-stu-id="31772-117">Microsoft Defender for Identity (identity)</span></span> 
  - <span data-ttu-id="31772-118">Microsoft Cloud App Security (приложения)</span><span class="sxs-lookup"><span data-stu-id="31772-118">Microsoft Cloud App Security (apps)</span></span>

![Решение of_Microsoft 365 Defender для пользователей, Microsoft Defender for Identity, для конечных точек Microsoft Defender для конечной точки, для облачных приложений, Microsoft Cloud App Security и для данных, Microsoft Defender для Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="31772-120">С интегрированным решением Microsoft 365 Defender специалисты по безопасности могут сшить вместе сигналы угрозы, которые получают Microsoft Defender для endpoint, Microsoft Defender для Office 365, Microsoft Defender для удостоверений и Microsoft Cloud App Security, а также определить всю область и влияние угрозы, как она попала в среду, на что она влияет и как она в настоящее время влияет на организацию.</span><span class="sxs-lookup"><span data-stu-id="31772-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="31772-121">Microsoft 365 Defender принимает автоматические меры для предотвращения или остановки атаки и самообувления затронутых почтовых ящиков, конечных точек и удостоверений пользователей.</span><span class="sxs-lookup"><span data-stu-id="31772-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="31772-122">Подробные [сведения см. в Microsoft 365 Обзор защитника.](microsoft-365-defender.md)</span><span class="sxs-lookup"><span data-stu-id="31772-122">See the [Microsoft 365 Defender overview](microsoft-365-defender.md) for details.</span></span>



<span data-ttu-id="31772-123">Следующая временная шкала выборки зависит от написания нужных ресурсов в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="31772-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="31772-124">Некоторым обнаружениям и рабочего процессам может потребоваться больше времени на обучение, чем другим.</span><span class="sxs-lookup"><span data-stu-id="31772-124">Some detections and workflows might need more learning time than the others.</span></span>

![Пример временной шкалы при запуске пилотного Microsoft 365 Defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="31772-126">Чтобы получить оптимальные результаты, выполните пилотные инструкции как можно ближе.</span><span class="sxs-lookup"><span data-stu-id="31772-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="31772-127">Пилотные этапы воспроизведения</span><span class="sxs-lookup"><span data-stu-id="31772-127">Pilot playbook phases</span></span> 

<span data-ttu-id="31772-128">Существует четыре этапа в запуске пилотного Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="31772-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="31772-129">Этап</span><span class="sxs-lookup"><span data-stu-id="31772-129">Phase</span></span> | <span data-ttu-id="31772-130">Описание</span><span class="sxs-lookup"><span data-stu-id="31772-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="31772-131">Планирование</span><span class="sxs-lookup"><span data-stu-id="31772-131">Planning</span></span>](m365d-pilot-plan.md)<br> <span data-ttu-id="31772-132">~ 1 день</span><span class="sxs-lookup"><span data-stu-id="31772-132">~ 1 day</span></span>| <span data-ttu-id="31772-133">Узнайте, что необходимо рассмотреть перед запуском пилотного проекта Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="31772-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="31772-134">- Область</span><span class="sxs-lookup"><span data-stu-id="31772-134">- Scope</span></span> <br> <span data-ttu-id="31772-135">- Использование случаев</span><span class="sxs-lookup"><span data-stu-id="31772-135">- Use cases</span></span> <br><span data-ttu-id="31772-136">- Требования</span><span class="sxs-lookup"><span data-stu-id="31772-136">- Requirements</span></span> <br><span data-ttu-id="31772-137">- План тестирования</span><span class="sxs-lookup"><span data-stu-id="31772-137">- Test plan</span></span> <br> <span data-ttu-id="31772-138">- Критерии успешности</span><span class="sxs-lookup"><span data-stu-id="31772-138">- Success criteria</span></span> <br> <span data-ttu-id="31772-139">- Система показателей</span><span class="sxs-lookup"><span data-stu-id="31772-139">- Scorecard</span></span> 
| [<span data-ttu-id="31772-140">Подготовка</span><span class="sxs-lookup"><span data-stu-id="31772-140">Preparation</span></span>](m365d-evaluation.md) <br><span data-ttu-id="31772-141">~2 дня</span><span class="sxs-lookup"><span data-stu-id="31772-141">~2 days</span></span>|  <span data-ttu-id="31772-142">Доступ Microsoft 365 центр безопасности, чтобы настроить пилотную среду Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="31772-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="31772-143">Вы будете руководствоваться:</span><span class="sxs-lookup"><span data-stu-id="31772-143">You'll be guided to:</span></span><br><br><span data-ttu-id="31772-144">- Определите заинтересованных лиц и обратитесь за входом для пилота</span><span class="sxs-lookup"><span data-stu-id="31772-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="31772-145">- Соображения среды</span><span class="sxs-lookup"><span data-stu-id="31772-145">- Environment considerations</span></span> <br><span data-ttu-id="31772-146">- Доступ</span><span class="sxs-lookup"><span data-stu-id="31772-146">- Access</span></span> <br><span data-ttu-id="31772-147">- Azure Active Directory установки</span><span class="sxs-lookup"><span data-stu-id="31772-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="31772-148">- Порядок конфигурации</span><span class="sxs-lookup"><span data-stu-id="31772-148">- Configuration order</span></span> <br> <span data-ttu-id="31772-149">- Подпишитесь на Microsoft 365 E5 пробную</span><span class="sxs-lookup"><span data-stu-id="31772-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="31772-150">- Настройка домена</span><span class="sxs-lookup"><span data-stu-id="31772-150">- Configure domain</span></span> <br><span data-ttu-id="31772-151">- Назначение Microsoft 365 E5 лицензий</span><span class="sxs-lookup"><span data-stu-id="31772-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="31772-152">- Завершите мастер установки на портале</span><span class="sxs-lookup"><span data-stu-id="31772-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="31772-153">Имитация атаки</span><span class="sxs-lookup"><span data-stu-id="31772-153">Attack simulation</span></span>](m365d-pilot-simulate.md) <br><span data-ttu-id="31772-154">~2 дня</span><span class="sxs-lookup"><span data-stu-id="31772-154">~2 days</span></span>| <span data-ttu-id="31772-155">Чтобы смоделировать атаку, вы будете руководствоваться:</span><span class="sxs-lookup"><span data-stu-id="31772-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="31772-156">- Проверка требований к тестовой среде</span><span class="sxs-lookup"><span data-stu-id="31772-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="31772-157">- Запуск моделирования</span><span class="sxs-lookup"><span data-stu-id="31772-157">-  Run the simulation</span></span> <br><span data-ttu-id="31772-158">- Расследование инцидента</span><span class="sxs-lookup"><span data-stu-id="31772-158">- Investigate an incident</span></span> <br><span data-ttu-id="31772-159">- разрешить инцидент</span><span class="sxs-lookup"><span data-stu-id="31772-159">- resolve the incident</span></span> 
| [<span data-ttu-id="31772-160">Закрытие и сводка</span><span class="sxs-lookup"><span data-stu-id="31772-160">Closing and summary</span></span>](m365d-pilot-close.md) <br><span data-ttu-id="31772-161">~ 1 день</span><span class="sxs-lookup"><span data-stu-id="31772-161">~ 1 day</span></span>| <span data-ttu-id="31772-162">По завершении процесса вы будете руководствоваться:</span><span class="sxs-lookup"><span data-stu-id="31772-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="31772-163">- Перейдите через конечный вывод</span><span class="sxs-lookup"><span data-stu-id="31772-163">- Go through your final output</span></span><br><span data-ttu-id="31772-164">- Презентуйте результаты заинтересованным лицам</span><span class="sxs-lookup"><span data-stu-id="31772-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="31772-165">- Предоставление обратной связи</span><span class="sxs-lookup"><span data-stu-id="31772-165">- Provide feedback</span></span> <br><span data-ttu-id="31772-166">- Предпринять следующие действия</span><span class="sxs-lookup"><span data-stu-id="31772-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="31772-167">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="31772-167">Next step</span></span>
|[<span data-ttu-id="31772-168">Этап планирования</span><span class="sxs-lookup"><span data-stu-id="31772-168">Planning phase</span></span>](m365d-pilot-plan.md) | <span data-ttu-id="31772-169">Планирование пилотного проекта Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31772-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
