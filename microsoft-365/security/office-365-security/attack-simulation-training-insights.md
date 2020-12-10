---
title: Получение аналитики с помощью обучения имитации атаки
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: В этой статье рассказывается о том, как обучение по моделированию атак в центре безопасности Microsoft 365 влияет на сотрудников и получение ценных сведений из результатов имитации и обучения.
ms.openlocfilehash: 772815add47d2e0a61187f2d687ff047a4de9c31
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615184"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="7a548-103">Получение аналитики с помощью обучения имитации атаки</span><span class="sxs-lookup"><span data-stu-id="7a548-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="7a548-104">В учебном курсе по моделированию атак Майкрософт предоставляет подробные сведения, основанные на результатах имитации и обучающих сотрудников.</span><span class="sxs-lookup"><span data-stu-id="7a548-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and training employees went through.</span></span> <span data-ttu-id="7a548-105">Эти сведения помогут вам сообщать о ходе выполнения ваших сотрудников, а также рекомендовать дальнейшие действия по подготовке ваших сотрудников и среды к атакам.</span><span class="sxs-lookup"><span data-stu-id="7a548-105">These insights will help inform you on progress your employees are doing on threat readiness, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="7a548-106">Мы постоянно работаем над расширенными аналитическими сведениями, с влиянием поведения и рекомендуемыми действиями, которые в настоящее время доступны.</span><span class="sxs-lookup"><span data-stu-id="7a548-106">We are continuously working on expanding insights available to you, with behavior impact and recommended actions currently available.</span></span>
<span data-ttu-id="7a548-107">Чтобы начать, перейдите к [учебному обучению атак в центре безопасности Microsoft 365](https://security.microsoft.com/attacksimulator?viewid=overview).</span><span class="sxs-lookup"><span data-stu-id="7a548-107">To start, head over to [Attack simulation training on the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="7a548-108">Влияние на скорость компромиссов</span><span class="sxs-lookup"><span data-stu-id="7a548-108">Behavior impact on compromise rate</span></span>

<span data-ttu-id="7a548-109">На вкладке " **Обзор** эмуляции атак" вы найдете **влияние на карту компромиссного курса** .</span><span class="sxs-lookup"><span data-stu-id="7a548-109">On the Attack simulation training **Overview** tab, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="7a548-110">В этой карточке показано, как сотрудники работали с моделированием, в котором вы работали в контрасте с **прогнозируемой частотой компромисса**.</span><span class="sxs-lookup"><span data-stu-id="7a548-110">This card shows how employees dealt with simulation you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="7a548-111">Вы можете использовать эти аналитические данные для отслеживания хода работ по подготовке угроз для сотрудников, выполняя несколько моделей для одних и тех же групп сотрудников.</span><span class="sxs-lookup"><span data-stu-id="7a548-111">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="7a548-112">На диаграмме вы можете увидеть следующее:</span><span class="sxs-lookup"><span data-stu-id="7a548-112">In the graph you can see:</span></span>

- <span data-ttu-id="7a548-113">**Предсказуемая частота компромиссов** , отражающая среднюю частоту компромиссов для эмуляций, использующих один и тот же тип полезных данных для клиентов, использующих обучение по моделированию атак.</span><span class="sxs-lookup"><span data-stu-id="7a548-113">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across tenants using Attack simulation training.</span></span>
- <span data-ttu-id="7a548-114">**Фактическая скорость защиты** отражает процент сотрудников, которые проявляются за имитацию.</span><span class="sxs-lookup"><span data-stu-id="7a548-114">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="7a548-115">Кроме того, `<number> less susceptible to phishing` отражает разницу между фактическим числом сотрудников, скомпрометированных атакой, и прогнозируемым коэффициентом компромисса.</span><span class="sxs-lookup"><span data-stu-id="7a548-115">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="7a548-116">Это количество сотрудников менее вероятно снижается при схожих атаках в будущем, а `<percent%> better than predicted rate` также показывает, как сотрудники в целом отличаются в соответствии с прогнозируемой скоростью компромиссов.</span><span class="sxs-lookup"><span data-stu-id="7a548-116">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a548-117">![Карточка, влияющая на поведение при работе с моделированием атак обзор](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="7a548-117">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="7a548-118">Чтобы просмотреть более подробный отчет, щелкните **Просмотр имитаций и обучающий еффикаци отчет** , который предоставляет одни и те же сведения с дополнительным контекстом от модели, такой как методика имитации и общее число целевых пользователей.</span><span class="sxs-lookup"><span data-stu-id="7a548-118">To see a more detailed report, click on **View simulations and training efficacy report** which provides the same information with additional context from the simulation itself, like simulation technique and total users targeted.</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="7a548-119">Рекомендуемые действия</span><span class="sxs-lookup"><span data-stu-id="7a548-119">Recommended actions</span></span>

<span data-ttu-id="7a548-120">На вкладке [ **имитация**](https://security.microsoft.com/attacksimulator?viewid=simulations)при выборе любой из моделей будет выбрана информация о моделировании.</span><span class="sxs-lookup"><span data-stu-id="7a548-120">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting any of the simulations will take you to simulation details.</span></span> <span data-ttu-id="7a548-121">Здесь вы найдете раздел **Рекомендуемые действия** .</span><span class="sxs-lookup"><span data-stu-id="7a548-121">Here you will find the **Recommended actions** section.</span></span>

<span data-ttu-id="7a548-122">Раздел Рекомендуемые действия подробно описывает рекомендации, доступные в [Microsoft Secure Score](../mtp/microsoft-secure-score.md).</span><span class="sxs-lookup"><span data-stu-id="7a548-122">The recommended actions section details recommendations as available in [Microsoft Secure Score](../mtp/microsoft-secure-score.md).</span></span> <span data-ttu-id="7a548-123">Эти рекомендации основаны на полезных данных, используемых в имитации, и помогут защитить сотрудников и окружающую среду.</span><span class="sxs-lookup"><span data-stu-id="7a548-123">These recommendations are based on the payload used in the simulation and will help you protect your employees and your environment.</span></span> <span data-ttu-id="7a548-124">Щелкнув каждое действие улучшения, вы получите дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="7a548-124">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a548-125">![Рекомендации по использованию руководства по моделированию атак](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="7a548-125">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="7a548-126">Дополнительные ссылки</span><span class="sxs-lookup"><span data-stu-id="7a548-126">Related Links</span></span>

<span data-ttu-id="7a548-127">**Симулятор атак** [создает имитацию атаки фишинга](attack-simulation-training.md) и [создает полезные данные для обучения людей](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="7a548-127">**Attack Simulator** [Create a phishing attack simulation](attack-simulation-training.md) and [create a payload for training your people](attack-simulation-training-payloads.md)</span></span>
