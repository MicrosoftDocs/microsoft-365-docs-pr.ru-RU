---
title: Получение аналитики с помощью обучения имитации атаки
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Администраторы могут узнать, как обучение имитации атаки в центре безопасности Microsoft 365 влияет на сотрудников и может получить сведения о результатах моделирования и обучения.
ms.technology: mdo
ms.openlocfilehash: 0fcb88406558f73b587d8452375c33dbbec1c78b
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51600011"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="0e9c6-103">Получение аналитики с помощью обучения имитации атаки</span><span class="sxs-lookup"><span data-stu-id="0e9c6-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="0e9c6-104">В рамках обучения моделированию атак Корпорация Майкрософт предоставляет вам сведения, основанные на результатах имитаций и тренингов, которые прошли сотрудники.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="0e9c6-105">Эти сведения помогут вам узнать о ходе подготовки сотрудников к готовности к угрозам, а также рекомендовать следующие действия для лучшей подготовки сотрудников и среды к атакам.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-105">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

<span data-ttu-id="0e9c6-106">Мы постоянно работаем над расширением доступных вам данных.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-106">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="0e9c6-107">Влияние поведения и рекомендуемые действия в настоящее время доступны.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-107">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="0e9c6-108">Для начала перенахайте обучение имитации attack в центре Microsoft 365 [безопасности.](https://security.microsoft.com/attacksimulator?viewid=overview)</span><span class="sxs-lookup"><span data-stu-id="0e9c6-108">To start, head over to [Attack simulation training in the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="0e9c6-109">Влияние поведения на скорость компромисса</span><span class="sxs-lookup"><span data-stu-id="0e9c6-109">Behavior impact on compromise rate</span></span>

<span data-ttu-id="0e9c6-110">На **вкладке Обзор** обучения имитации атаки вы найдете влияние поведения на **карту коэффициента** компромисса.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-110">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="0e9c6-111">На этой карте показано, как сотрудники справились с симуляциями, которые вы запустили, в отличие от **прогнозируемого коэффициента компромисса.**</span><span class="sxs-lookup"><span data-stu-id="0e9c6-111">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="0e9c6-112">Эти сведения можно использовать для отслеживания прогресса в готовности сотрудников к угрозам, запуская несколько имитаций для одной и той же группы сотрудников.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-112">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="0e9c6-113">На графике вы можете увидеть:</span><span class="sxs-lookup"><span data-stu-id="0e9c6-113">In the graph you can see:</span></span>

- <span data-ttu-id="0e9c6-114">**Прогнозируемая** скорость компромисса, которая отражает среднюю скорость компрометации для моделирования с использованием того же типа полезной нагрузки для других Microsoft 365, использующих обучение имитации attack.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-114">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="0e9c6-115">**Фактический уровень компромисса** отражает процент сотрудников, которые попались на моделирование.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-115">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="0e9c6-116">Кроме того, отражает разницу между фактическим числом сотрудников, скомпрометируемых атакой, и `<number> less susceptible to phishing` прогнозируемым коэффициентом компромисса.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-116">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="0e9c6-117">Это число сотрудников менее вероятно, будет скомпрометировано подобными атаками в будущем, в то время как указывает, как сотрудники сделали в целом в отличие от `<percent%> better than predicted rate` прогнозируемого коэффициента компромисса.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-117">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e9c6-118">![Карта влияния поведения на обзор подготовки к имитации атаки](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="0e9c6-118">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="0e9c6-119">Чтобы просмотреть более подробный отчет, щелкните Просмотр имитаций **и отчет об эффективности обучения.**</span><span class="sxs-lookup"><span data-stu-id="0e9c6-119">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="0e9c6-120">В этом отчете содержится та же информация с дополнительным контекстом из самого моделирования (например, метод моделирования и общее число целевых пользователей).</span><span class="sxs-lookup"><span data-stu-id="0e9c6-120">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="0e9c6-121">Рекомендуемые действия</span><span class="sxs-lookup"><span data-stu-id="0e9c6-121">Recommended actions</span></span>

<span data-ttu-id="0e9c6-122">На [ **вкладке Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations)выбор имитации поможет вам узнать подробности моделирования, где вы найдете раздел **Рекомендуемые** действия.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-122">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="0e9c6-123">В разделе Рекомендуемые действия подробные рекомендации, доступные в [Microsoft Secure Score.](../defender/microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="0e9c6-123">The recommended actions section details recommendations as available in [Microsoft Secure Score](../defender/microsoft-secure-score.md).</span></span> <span data-ttu-id="0e9c6-124">Эти рекомендации основаны на полезной нагрузке, используемой в моделировании, и помогут защитить сотрудников и среду.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-124">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="0e9c6-125">Нажав на каждое действие по улучшению, вы сможете получить сведения о них.</span><span class="sxs-lookup"><span data-stu-id="0e9c6-125">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e9c6-126">![Раздел Рекомендации действий по обучению имитации атаки](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="0e9c6-126">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="0e9c6-127">Дополнительные ссылки</span><span class="sxs-lookup"><span data-stu-id="0e9c6-127">Related Links</span></span>

[<span data-ttu-id="0e9c6-128">Начало использования обучения имитации атаки</span><span class="sxs-lookup"><span data-stu-id="0e9c6-128">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="0e9c6-129">Создание имитации фишинговых атак</span><span class="sxs-lookup"><span data-stu-id="0e9c6-129">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="0e9c6-130">создание полезной нагрузки для обучения сотрудников</span><span class="sxs-lookup"><span data-stu-id="0e9c6-130">create a payload for training your people</span></span>](attack-simulation-training-payloads.md)
