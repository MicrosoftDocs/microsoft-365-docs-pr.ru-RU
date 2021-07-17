---
title: Создание среды Microsoft 365 Defender оценки. Активируйте или включив пробные лицензии и перенаправляя их в Microsoft Defender for Identity (MDI).
description: Настройка пробной Microsoft 365 Defender или пилотной среды путем активации пробных лицензий. Затем установите Microsoft Defender для удостоверений (MDI) и все другие оценки M365D.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/19/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: 04f7a746788ebcf67525020515cdc7bb20c41bb6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458688"
---
# <a name="create-the-microsoft-365-defender-evaluation-environment"></a><span data-ttu-id="a3250-105">Создание среды Microsoft 365 Defender оценки</span><span class="sxs-lookup"><span data-stu-id="a3250-105">Create the Microsoft 365 Defender Evaluation Environment</span></span>

<span data-ttu-id="a3250-106">Существует два распространенных способа сделать следующий шаг в оценке.</span><span class="sxs-lookup"><span data-stu-id="a3250-106">There are two common ways to do this next step in evaluation.</span></span> <span data-ttu-id="a3250-107">В этом документе предполагается, что у вас уже есть клиент производства M365, и вы активируете пробные лицензии E5 для оценки M365 Defender в *текущей среде.*</span><span class="sxs-lookup"><span data-stu-id="a3250-107">This document assumes you already have a production M365 tenant, and will activate E5 trial licenses to evaluate M365 Defender in *the current environment*.</span></span> <span data-ttu-id="a3250-108">Оценка на месте позволит вам сохранить любые методы безопасности при покупке лицензий после периода оценки.</span><span class="sxs-lookup"><span data-stu-id="a3250-108">An in-place evaluation will let you keep any security methods with the purchase of licenses after the evaluation period.</span></span>

<span data-ttu-id="a3250-109">Во-вторых, настройка [среды Microsoft 365 Defender](setup-m365deval.md) лаборатории для целей оценки.</span><span class="sxs-lookup"><span data-stu-id="a3250-109">The second is to  [Set up your Microsoft 365 Defender trial lab environment](setup-m365deval.md) for the purpose of evaluation.</span></span> <span data-ttu-id="a3250-110">Он может не иметь много реальных сигналов от бизнеса, поэтому следует помнить о том, что оговорка.</span><span class="sxs-lookup"><span data-stu-id="a3250-110">It may not have many real signals from the business, so be aware of that caveat.</span></span>

## <a name="to-activate-e5-trial-licenses-to-evaluate-microsoft-365-defender"></a><span data-ttu-id="a3250-111">Активация пробных лицензий E5 для оценки Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a3250-111">To activate E5 trial licenses to evaluate Microsoft 365 Defender</span></span> 
1. <span data-ttu-id="a3250-112">Войдите на существующий портал администрирования клиента M365.</span><span class="sxs-lookup"><span data-stu-id="a3250-112">Log on to your existing M365 tenant administration portal.</span></span>
2. <span data-ttu-id="a3250-113">Выберите *Службы покупки* из меню навигации.</span><span class="sxs-lookup"><span data-stu-id="a3250-113">Select *Purchase Services* from the navigation menu.</span></span>
3. <span data-ttu-id="a3250-114">Прокрутите *вниз до раздела Office 365* и выберите кнопку "Детали" в Office 365 E5 лицензии.</span><span class="sxs-lookup"><span data-stu-id="a3250-114">Scroll down to the *Office 365* section and select "Details" button under Office 365 E5 license.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="В Office 365 разделе есть кнопка &quot;Сведения&quot;.":::

4. <span data-ttu-id="a3250-116">Выберите *бесплатную пробную ссылку Start.*</span><span class="sxs-lookup"><span data-stu-id="a3250-116">Select *Start free trial* link.</span></span>

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Нажмите кнопку &quot;Начните бесплатную пробную пробную версия&quot; (за нее взимается плата в размере 35$).":::

5. <span data-ttu-id="a3250-118">Подтвердите запрос и *нажмите кнопку "Попробуйте* сейчас".</span><span class="sxs-lookup"><span data-stu-id="a3250-118">Confirm your request and click *Try now* button.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="На панели &quot;Проверьте, подтвердите свой заказ&quot; (для пробной Office 365 E5 месяца для 25 пользователей) есть кнопка &quot;Попробуйте сейчас&quot;.":::

## <a name="next-steps"></a><span data-ttu-id="a3250-120">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="a3250-120">Next steps</span></span>
[<span data-ttu-id="a3250-121">Включить Microsoft 365 для identity</span><span class="sxs-lookup"><span data-stu-id="a3250-121">Enable Microsoft 365 for Identity</span></span>](eval-defender-identity-overview.md)

<span data-ttu-id="a3250-122">Возвращайся к обзору [для оценки и пилотных Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a3250-122">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>