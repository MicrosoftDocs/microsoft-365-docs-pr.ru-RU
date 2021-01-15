---
title: Получение аналитики с помощью обучения имитации атаки
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Администраторы могут узнать, как обучение моделированию атак в Центре безопасности Microsoft 365 влияет на сотрудников и может получить представление о результатах моделирования и обучения.
ms.openlocfilehash: c283819550872691d8dd23d3921c22cb23637633
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870959"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="a41f7-103">Получение аналитики с помощью обучения имитации атаки</span><span class="sxs-lookup"><span data-stu-id="a41f7-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="a41f7-104">В рамках обучения моделированию атак корпорация Майкрософт предоставляет вам анализ результатов моделирования и учебных занятий, которые прошли сотрудники.</span><span class="sxs-lookup"><span data-stu-id="a41f7-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="a41f7-105">Эти сведения помогут вам проинформировать вас о ходе готовности ваших сотрудников к угрозам, а также порекомендовать дальнейшие действия для лучшей подготовки сотрудников и вашей среды к атакам.</span><span class="sxs-lookup"><span data-stu-id="a41f7-105">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="a41f7-106">Мы постоянно работаем над расширением доступных вам данных.</span><span class="sxs-lookup"><span data-stu-id="a41f7-106">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="a41f7-107">Влияние на поведение и рекомендуемые действия в настоящее время доступны.</span><span class="sxs-lookup"><span data-stu-id="a41f7-107">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="a41f7-108">Для начала перенаначните обучение моделированию [атак в Центре безопасности Microsoft 365.](https://security.microsoft.com/attacksimulator?viewid=overview)</span><span class="sxs-lookup"><span data-stu-id="a41f7-108">To start, head over to [Attack simulation training in the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="a41f7-109">Влияние поведения на уровень компрометации</span><span class="sxs-lookup"><span data-stu-id="a41f7-109">Behavior impact on compromise rate</span></span>

<span data-ttu-id="a41f7-110">На **вкладке "Обзор"** обучения моделированию атак вы найдете влияние на поведение карты **коэффициента компрометации.**</span><span class="sxs-lookup"><span data-stu-id="a41f7-110">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="a41f7-111">На этой карточке показано, как сотрудники работают с имитациями, которые вы запустили в отличие от **прогнозируемой скорости компрометации.**</span><span class="sxs-lookup"><span data-stu-id="a41f7-111">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="a41f7-112">Эти сведения можно использовать для отслеживания хода выполнения в готовности сотрудников к угрозам путем выполнения нескольких имитаций для одной и той же группы сотрудников.</span><span class="sxs-lookup"><span data-stu-id="a41f7-112">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="a41f7-113">На графике вы можете увидеть:</span><span class="sxs-lookup"><span data-stu-id="a41f7-113">In the graph you can see:</span></span>

- <span data-ttu-id="a41f7-114">**Прогнозируемая скорость** компрометации, которая отражает среднюю скорость компрометации для имитаций с использованием того же типа полезной нагрузки в других клиентах Microsoft 365, использующих обучение моделированию атак.</span><span class="sxs-lookup"><span data-stu-id="a41f7-114">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="a41f7-115">**Фактическая доля компрометации** отражает процент сотрудников, которые были в моделировании.</span><span class="sxs-lookup"><span data-stu-id="a41f7-115">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="a41f7-116">Кроме того, отражает разницу между фактическим количеством сотрудников, скомпрометированных в результате атаки, и `<number> less susceptible to phishing` прогнозируемым коэффициентом компрометации.</span><span class="sxs-lookup"><span data-stu-id="a41f7-116">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="a41f7-117">Это число сотрудников с меньшей вероятностью будет скомпрометировано аналогичными атаками в будущем, а также указывает, как сотрудники в целом сделали это в противоположность прогнозируемой скорости `<percent%> better than predicted rate` компрометации.</span><span class="sxs-lookup"><span data-stu-id="a41f7-117">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a41f7-118">![Обзор обучения моделированию атак на карточку влияния на поведение](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="a41f7-118">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="a41f7-119">Чтобы просмотреть более подробный отчет, щелкните **"Просмотр имитаций и учебный отчет".**</span><span class="sxs-lookup"><span data-stu-id="a41f7-119">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="a41f7-120">В этом отчете предоставляется та же информация с дополнительным контекстом из самого моделирования (например, методика моделирования и общее количество целевых пользователей).</span><span class="sxs-lookup"><span data-stu-id="a41f7-120">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="a41f7-121">Рекомендуемые действия</span><span class="sxs-lookup"><span data-stu-id="a41f7-121">Recommended actions</span></span>

<span data-ttu-id="a41f7-122">На [ **вкладке**](https://security.microsoft.com/attacksimulator?viewid=simulations)"Имитации" выбор имитации поможет вам получить сведения о моделировании, где вы найдете раздел "Рекомендуемые **действия".**</span><span class="sxs-lookup"><span data-stu-id="a41f7-122">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="a41f7-123">В разделе рекомендуемых действий подробно рекомендоваться рекомендации, доступные в [оценке безопасности (Майкрософт).](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)</span><span class="sxs-lookup"><span data-stu-id="a41f7-123">The recommended actions section details recommendations as available in [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span> <span data-ttu-id="a41f7-124">Эти рекомендации основаны на полезной нагрузке, используемой в моделировании, и помогут защитить сотрудников и среду.</span><span class="sxs-lookup"><span data-stu-id="a41f7-124">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="a41f7-125">Щелкнув каждое действие по улучшению, вы сможете получить сведения о них.</span><span class="sxs-lookup"><span data-stu-id="a41f7-125">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a41f7-126">![Раздел "Действия с рекомендациями" по обучению моделированию атак](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="a41f7-126">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="a41f7-127">Дополнительные ссылки</span><span class="sxs-lookup"><span data-stu-id="a41f7-127">Related Links</span></span>

[<span data-ttu-id="a41f7-128">Начало работы с обучением моделированию атак</span><span class="sxs-lookup"><span data-stu-id="a41f7-128">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="a41f7-129">Создание имитации фишинговой атаки</span><span class="sxs-lookup"><span data-stu-id="a41f7-129">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="a41f7-130">создание полезной нагрузки для обучения сотрудников</span><span class="sxs-lookup"><span data-stu-id="a41f7-130">create a payload for training your people</span></span>](attack-simulation-training-payloads.md)
