---
title: Пилот microsoft Defender for Identity, настройка контрольных показателей конфигурации, стандартов, рекомендаций и руководство по обнаружению и исправлению различных угроз удостоверений, таких как разведка, скомпрометированная учетная запись, поодальное перемещение, доминирование домена и оповещений об эксфильтрации, проведение исследования путей пользовательского, компьютерного, юридического и более позднего движения.
description: Пилот Microsoft Defender for Identity, задайте ориентиры, сдайте учебники по разведке, скомпрометированию учетных данных, дальнейшему движению, доминированию домена и оповещениям об эксфильтрации.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 14c5b9252e980d1f693139393d26b9405cb1b812
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458550"
---
# <a name="pilot-microsoft-defender-for-identity"></a><span data-ttu-id="3a9ad-103">Пилотный защитник Майкрософт для удостоверений</span><span class="sxs-lookup"><span data-stu-id="3a9ad-103">Pilot Microsoft Defender for Identity</span></span>


<span data-ttu-id="3a9ad-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3a9ad-104">**Applies to:**</span></span>
- <span data-ttu-id="3a9ad-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3a9ad-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="3a9ad-106">Эта статья — [шаг 3 из 3](eval-defender-identity-overview.md) в процессе настройки среды оценки для Microsoft Defender для identity.</span><span class="sxs-lookup"><span data-stu-id="3a9ad-106">This article is [Step 3 of 3](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="3a9ad-107">Дополнительные сведения об этом процессе см. в статье [обзор.](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3a9ad-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="3a9ad-108">Чтобы настроить пилотный пилот для Microsoft Defender для удостоверений, используйте следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3a9ad-108">Use the following steps to setup and configure the pilot for Microsoft Defender for identity.</span></span> <span data-ttu-id="3a9ad-109">Обратите внимание, что рекомендации не включают настройку пилотной группы.</span><span class="sxs-lookup"><span data-stu-id="3a9ad-109">Note that the recommendations don't include setting up a pilot group.</span></span> <span data-ttu-id="3a9ad-110">Передовой практикой является установка датчика на всех серверах с службами домена Active Directory (AD DS) и Active Directory Federated Services (AD FS).</span><span class="sxs-lookup"><span data-stu-id="3a9ad-110">The best practice is to go ahead and install the sensor on all of your servers running Active Directory Domain Services (AD DS) and Active Directory Federated Services (AD FS).</span></span>

![Действия по добавлению защитника Microsoft Defender для удостоверений в среду оценки Defender](../../media/defender/m365-defender-identity-pilot-steps.png)

<span data-ttu-id="3a9ad-112">В следующей таблице описываются действия на иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="3a9ad-112">The following table describes the steps in the illustration.</span></span>

- [<span data-ttu-id="3a9ad-113">Шаг 1. Настройка базовых рекомендаций для среды удостоверений</span><span class="sxs-lookup"><span data-stu-id="3a9ad-113">Step 1: Configure benchmark recommendations for your identity environment</span></span>](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [<span data-ttu-id="3a9ad-114">Шаг 2. Опробуйте возможности — пройдитесь по учебникам по выявлению и исправлению различных типов атак </span><span class="sxs-lookup"><span data-stu-id="3a9ad-114">Step 2: Try out capabilities — Walk through tutorials for identifying and remediating different attack types </span></span>](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a><span data-ttu-id="3a9ad-115">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="3a9ad-115">Step 1.</span></span> <span data-ttu-id="3a9ad-116">Настройка базовых рекомендаций для среды удостоверений</span><span class="sxs-lookup"><span data-stu-id="3a9ad-116">Configure benchmark recommendations for your identity environment</span></span>

<span data-ttu-id="3a9ad-117">Корпорация Майкрософт предоставляет базовые рекомендации по безопасности для клиентов, использующих облачные службы Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3a9ad-117">Microsoft provides security benchmark recommendations for customers using Microsoft Cloud services.</span></span> <span data-ttu-id="3a9ad-118">Эталон [безопасности Azure (ASB)](/security/benchmark/azure/overview) содержит рекомендации и рекомендации, которые помогут повысить безопасность рабочих нагрузок, данных и служб в Azure.</span><span class="sxs-lookup"><span data-stu-id="3a9ad-118">The [Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) provides prescriptive best practices and recommendations to help improve the security of workloads, data, and services on Azure.</span></span>

<span data-ttu-id="3a9ad-119">Эти базовые рекомендации включают [базовую базу безопасности Azure для Microsoft Defender for Identity.](/security/benchmark/azure/baselines/defender-for-identity-security-baseline)</span><span class="sxs-lookup"><span data-stu-id="3a9ad-119">These benchmark recommendations include [Azure security baseline for Microsoft Defender for Identity](/security/benchmark/azure/baselines/defender-for-identity-security-baseline).</span></span> <span data-ttu-id="3a9ad-120">Реализация этих рекомендаций может занять некоторое время для планирования и реализации.</span><span class="sxs-lookup"><span data-stu-id="3a9ad-120">Implementing these recommendations can take some time to plan and implement.</span></span> <span data-ttu-id="3a9ad-121">Хотя это значительно повышает безопасность среды удостоверений, они не должны препятствовать продолжению оценки и реализации Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="3a9ad-121">While these will greatly increase the security of your identity environment, they shouldn't prevent you from continuing to evaluate and implement Microsoft Defender for Identity.</span></span> <span data-ttu-id="3a9ad-122">Эти данные предоставляются здесь для вашего информирования.</span><span class="sxs-lookup"><span data-stu-id="3a9ad-122">These are provided here for your awareness.</span></span>

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a><span data-ttu-id="3a9ad-123">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="3a9ad-123">Step 2.</span></span> <span data-ttu-id="3a9ad-124">Опробуйте возможности — пройдитесь по учебникам по выявлению и исправлению различных типов атак</span><span class="sxs-lookup"><span data-stu-id="3a9ad-124">Try out capabilities — Walk through tutorials for identifying and remediating different attack types</span></span>

<span data-ttu-id="3a9ad-125">Документация По защитнику удостоверений Майкрософт включает ряд учебных пособий, которые проходят процесс выявления и устранения различных типов атак.</span><span class="sxs-lookup"><span data-stu-id="3a9ad-125">The Microsoft Defender for Identity documentation includes a series of tutorials that walk through the process of identifying and remediating various attack types.</span></span>

<span data-ttu-id="3a9ad-126">Опробуйте учебники Defender для identity:</span><span class="sxs-lookup"><span data-stu-id="3a9ad-126">Try out Defender for Identity tutorials:</span></span>
- [<span data-ttu-id="3a9ad-127">Оповещений о разведке</span><span class="sxs-lookup"><span data-stu-id="3a9ad-127">Reconnaissance alerts</span></span>](/defender-for-identity/reconnaissance-alerts)
- [<span data-ttu-id="3a9ad-128">Скомпрометированная оповещение учетных данных</span><span class="sxs-lookup"><span data-stu-id="3a9ad-128">Compromised credential alerts</span></span>](/defender-for-identity/compromised-credentials-alerts)
- [<span data-ttu-id="3a9ad-129">Оповещений о дальнейшем движении</span><span class="sxs-lookup"><span data-stu-id="3a9ad-129">Lateral movement alerts</span></span>](/defender-for-identity/lateral-movement-alerts)
- [<span data-ttu-id="3a9ad-130">Оповещений о доминировании домена</span><span class="sxs-lookup"><span data-stu-id="3a9ad-130">Domain dominance alerts</span></span>](/defender-for-identity/domain-dominance-alerts)
- [<span data-ttu-id="3a9ad-131">Оповещений exfiltration</span><span class="sxs-lookup"><span data-stu-id="3a9ad-131">Exfiltration alerts</span></span>](/defender-for-identity/exfiltration-alerts)
- [<span data-ttu-id="3a9ad-132">Исследование пользователя</span><span class="sxs-lookup"><span data-stu-id="3a9ad-132">Investigate a user</span></span>](/defender-for-identity/investigate-a-user)
- [<span data-ttu-id="3a9ad-133">Исследование компьютера</span><span class="sxs-lookup"><span data-stu-id="3a9ad-133">Investigate a computer</span></span>](/defender-for-identity/investigate-a-computer)
- [<span data-ttu-id="3a9ad-134">Изучение путей движения на более поздних путях</span><span class="sxs-lookup"><span data-stu-id="3a9ad-134">Investigate lateral movement paths</span></span>](/defender-for-identity/investigate-lateral-movement-path)
- [<span data-ttu-id="3a9ad-135">Исследование сущностями</span><span class="sxs-lookup"><span data-stu-id="3a9ad-135">Investigate entities</span></span>](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a><span data-ttu-id="3a9ad-136">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="3a9ad-136">Next steps</span></span>

[<span data-ttu-id="3a9ad-137">Оценка Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="3a9ad-137">Evaluate Microsoft Defender for Office 365</span></span>](eval-defender-office-365-overview.md)

<span data-ttu-id="3a9ad-138">Вернись к обзору [для Оценки Microsoft Defender для Office 365](eval-defender-office-365-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3a9ad-138">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="3a9ad-139">Возвращайся к обзору [для оценки и пилотных Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3a9ad-139">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>