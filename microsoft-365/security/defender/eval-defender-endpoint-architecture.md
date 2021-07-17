---
title: Просмотрите требования к архитектуре Конечной точки и ключевые концепции Microsoft Defender для конечной точки
description: Техническая схема для Microsoft Defender для конечной точки в Microsoft 365 Defender поможет вам понять личность в Microsoft 365 перед созданием пробной лаборатории или пилотной среды.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
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
ms.openlocfilehash: 4df1ac2ca5fdfaa88ec2d08c85112f52da26b873
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458604"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a><span data-ttu-id="f2d61-103">Просмотрите требования к архитектуре Конечной точки и ключевые концепции Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f2d61-103">Review Microsoft Defender for Endpoint architecture requirements and key concepts</span></span>

<span data-ttu-id="f2d61-104">**Применяется к:** Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2d61-104">**Applies to:** Microsoft 365 Defender</span></span>

<span data-ttu-id="f2d61-105">Эта статья поможет вам в процессе настройки оценки для среды Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f2d61-105">This article will guide you in the process of setting up the evaluation for Microsoft Defender for Endpoint environment.</span></span>

<span data-ttu-id="f2d61-106">Дополнительные сведения об этом процессе см. в статье [обзор.](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f2d61-106">For more information about this process, see the [overview article](eval-defender-endpoint-overview.md).</span></span>

<span data-ttu-id="f2d61-107">Прежде чем включить Microsoft Defender для конечной точки, убедитесь, что вы понимаете архитектуру и можете соответствовать требованиям.</span><span class="sxs-lookup"><span data-stu-id="f2d61-107">Before enabling Microsoft Defender for Endpoint, be sure you understand the architecture and can meet the requirements.</span></span>

## <a name="understand-the-architecture"></a><span data-ttu-id="f2d61-108">Знакомство с архитектурой</span><span class="sxs-lookup"><span data-stu-id="f2d61-108">Understand the architecture</span></span>

<span data-ttu-id="f2d61-109">Следующая схема иллюстрирует архитектуру и интеграцию Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="f2d61-109">The following diagram illustrates Microsoft Defender for Endpoint architecture and integrations.</span></span> 

![Действия по добавлению Microsoft Defender для Office среды оценки Defender](../../media/defender/m365-defender-endpoint-architecture.png)

<span data-ttu-id="f2d61-111">В следующей таблице описывается иллюстрация.</span><span class="sxs-lookup"><span data-stu-id="f2d61-111">The following table describes the illustration.</span></span>

<span data-ttu-id="f2d61-112">Вызов</span><span class="sxs-lookup"><span data-stu-id="f2d61-112">Call-out</span></span> | <span data-ttu-id="f2d61-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f2d61-113">Description</span></span>
:---|:---|
<span data-ttu-id="f2d61-114">1</span><span class="sxs-lookup"><span data-stu-id="f2d61-114">1</span></span> | <span data-ttu-id="f2d61-115">Устройства находятся на борту с помощью одного из поддерживаемых средств управления.</span><span class="sxs-lookup"><span data-stu-id="f2d61-115">Devices are on-boarded through one of the supported management tools.</span></span> 
<span data-ttu-id="f2d61-116">2</span><span class="sxs-lookup"><span data-stu-id="f2d61-116">2</span></span> | <span data-ttu-id="f2d61-117">На бортовые устройства предоставляют и реагируют на данные сигнала Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="f2d61-117">On-boarded devices provide and respond to Microsoft Defender for Endpoint signal data.</span></span>
<span data-ttu-id="f2d61-118">3</span><span class="sxs-lookup"><span data-stu-id="f2d61-118">3</span></span> | <span data-ttu-id="f2d61-119">Управляемые устройства присоединяются и/или регистрются в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f2d61-119">Managed devices are joined and/or enrolled in Azure Active Directory.</span></span>
<span data-ttu-id="f2d61-120">4 </span><span class="sxs-lookup"><span data-stu-id="f2d61-120">4</span></span> | <span data-ttu-id="f2d61-121">Устройства с Windows 10 с доменом синхронизируются с Azure Active Directory с Azure Active Directory Подключение.</span><span class="sxs-lookup"><span data-stu-id="f2d61-121">Domain-joined Windows 10 devices are synchronized to Azure Active Directory using Azure Active Directory Connect.</span></span>
<span data-ttu-id="f2d61-122">5 </span><span class="sxs-lookup"><span data-stu-id="f2d61-122">5</span></span> | <span data-ttu-id="f2d61-123">Microsoft Defender для оповещений конечной точки, расследований и ответов управляется в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f2d61-123">Microsoft Defender for Endpoint alerts, investigations, and responses are managed in Microsoft 365 Defender.</span></span>

## <a name="understand-key-concepts"></a><span data-ttu-id="f2d61-124">Понимание ключевых понятий</span><span class="sxs-lookup"><span data-stu-id="f2d61-124">Understand key concepts</span></span>

<span data-ttu-id="f2d61-125">В следующей таблице определены ключевые понятия, которые важны для понимания при оценке, настройке и развертывании Microsoft Defender для конечной точки:</span><span class="sxs-lookup"><span data-stu-id="f2d61-125">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Defender for Endpoint:</span></span> 

<span data-ttu-id="f2d61-126">Понятие</span><span class="sxs-lookup"><span data-stu-id="f2d61-126">Concept</span></span> | <span data-ttu-id="f2d61-127">Описание</span><span class="sxs-lookup"><span data-stu-id="f2d61-127">Description</span></span> | <span data-ttu-id="f2d61-128">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="f2d61-128">More information</span></span>
:---|:---|:---|
<span data-ttu-id="f2d61-129">Портал администрирования</span><span class="sxs-lookup"><span data-stu-id="f2d61-129">Administration Portal</span></span> | <span data-ttu-id="f2d61-130">Microsoft 365 Defender для мониторинга и оказания помощи в реагировании на оповещения о потенциальной постоянной угрозе или нарушениях данных.</span><span class="sxs-lookup"><span data-stu-id="f2d61-130">Microsoft 365 Defender portal to monitor and assist in responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> | [<span data-ttu-id="f2d61-131">Обзор портала Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="f2d61-131">Microsoft Defender for Endpoint portal overview</span></span>](/defender-endpoint/portal-overview)
<span data-ttu-id="f2d61-132">Уменьшение поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="f2d61-132">Attack Surface Reduction</span></span> | <span data-ttu-id="f2d61-133">Помогите уменьшить поверхности атак, минимизируя места, в которых ваша организация уязвима для киберугроз и атак.</span><span class="sxs-lookup"><span data-stu-id="f2d61-133">Help reduce your attack surfaces by minimizing the places where your organization is vulnerable to cyberthreats and attacks.</span></span> | [<span data-ttu-id="f2d61-134">Обзор сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="f2d61-134">Overview of attack surface reduction</span></span>](/defender-endpoint/overview-attack-surface-reduction)
<span data-ttu-id="f2d61-135">Обнаружение и реагирование конечных точек</span><span class="sxs-lookup"><span data-stu-id="f2d61-135">Endpoint Detection and Response</span></span> | <span data-ttu-id="f2d61-136">Возможности обнаружения и реагирования конечных точек обеспечивают расширенные обнаружения атак, которые находятся в режиме реального времени и могут быть готовы к действию.</span><span class="sxs-lookup"><span data-stu-id="f2d61-136">Endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> | [<span data-ttu-id="f2d61-137">Обзор обнаружение и нейтрализация атак на конечные точки возможностей</span><span class="sxs-lookup"><span data-stu-id="f2d61-137">Overview of endpoint detection and response capabilities</span></span>](/defender-endpoint/overview-endpoint-detection-response)
<span data-ttu-id="f2d61-138">Поведенческая блокировка и сдерживание</span><span class="sxs-lookup"><span data-stu-id="f2d61-138">Behavioral Blocking and Containment</span></span> | <span data-ttu-id="f2d61-139">Возможности поведенческой блокировки и сдерживания могут помочь определить и остановить угрозы, основываясь на их поведении и деревьях обработки даже при выполнении угрозы.</span><span class="sxs-lookup"><span data-stu-id="f2d61-139">Behavioral blocking and containment capabilities can help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> | [<span data-ttu-id="f2d61-140">Блокировка с учетом поведения и автономность</span><span class="sxs-lookup"><span data-stu-id="f2d61-140">Behavioral blocking and containment</span></span>](/defender-endpoint/behavioral-blocking-containment)
<span data-ttu-id="f2d61-141">Автоматическое исследование и ответ</span><span class="sxs-lookup"><span data-stu-id="f2d61-141">Automated Investigation and Response</span></span> | <span data-ttu-id="f2d61-142">Автоматизированное расследование использует различные алгоритмы проверки на основе процессов, используемых аналитиками безопасности и предназначенных для проверки оповещений и принятия незамедлительных действий для устранения нарушений.</span><span class="sxs-lookup"><span data-stu-id="f2d61-142">Automated investigation uses various inspection algorithms based on processes that are used by security analysts and designed to examine alerts and take immediate action to resolve breaches.</span></span> | [<span data-ttu-id="f2d61-143">Использование автоматизированных расследований для расследования и устранения угроз</span><span class="sxs-lookup"><span data-stu-id="f2d61-143">Use automated investigations to investigate and remediate threats</span></span>](/defender-endpoint/automated-investigations)
<span data-ttu-id="f2d61-144">Расширенная охота</span><span class="sxs-lookup"><span data-stu-id="f2d61-144">Advanced Hunting</span></span> | <span data-ttu-id="f2d61-145">Расширенный поиск — это средство охоты на угрозы на основе запросов, которое позволяет исследовать до 30 дней необработанных данных, чтобы можно было активно проверять события в сети, чтобы найти индикаторы и объекты угрозы.</span><span class="sxs-lookup"><span data-stu-id="f2d61-145">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data so that you can proactively inspect events in your network to locate threat indicators and entities.</span></span> | [<span data-ttu-id="f2d61-146">Обзор передовой охоты</span><span class="sxs-lookup"><span data-stu-id="f2d61-146">Overview of advanced hunting</span></span>](/defender-endpoint/advanced-hunting-overview)
<span data-ttu-id="f2d61-147">Аналитика угроз</span><span class="sxs-lookup"><span data-stu-id="f2d61-147">Threat Analytics</span></span> | <span data-ttu-id="f2d61-148">Аналитика угроз — это набор отчетов экспертов microsoft security researchers, охватывающих наиболее релевантные угрозы.</span><span class="sxs-lookup"><span data-stu-id="f2d61-148">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats.</span></span> | [<span data-ttu-id="f2d61-149">Отслеживание возникающих угроз и реагирование на них</span><span class="sxs-lookup"><span data-stu-id="f2d61-149">Track and respond to emerging threats</span></span>](/defender-endpoint/threat-analytics)


<span data-ttu-id="f2d61-150">Дополнительные сведения о возможностях, включенных в Microsoft Defender для конечной точки, см. в дополнительных сведениях о том, что такое [Microsoft Defender для конечной точки.](/defender-endpoint/microsoft-defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="f2d61-150">For more detailed information about the capabilities included with Microsoft Defender for Endpoint, see [What is Microsoft Defender for Endpoint](/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="siem-integration"></a><span data-ttu-id="f2d61-151">Интеграция SIEM</span><span class="sxs-lookup"><span data-stu-id="f2d61-151">SIEM integration</span></span>

<span data-ttu-id="f2d61-152">Вы можете интегрировать Microsoft Defender для конечной точки с Azure Sentinel для более полного анализа событий безопасности в организации и создания книг для эффективного и немедленного реагирования.</span><span class="sxs-lookup"><span data-stu-id="f2d61-152">You can integrate Microsoft Defender for Endpoint with Azure Sentinel to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span> 

<span data-ttu-id="f2d61-153">Microsoft Defender для конечной точки также может быть интегрирован в другие решения по управлению сведениями о безопасности и событиями (SIEM).</span><span class="sxs-lookup"><span data-stu-id="f2d61-153">Microsoft Defender for Endpoint can also be integrated into other Security Information and Event Management (SIEM) solutions.</span></span> <span data-ttu-id="f2d61-154">Дополнительные сведения см. в [веб-сайте Включить интеграцию SIEM в Microsoft Defender для конечной точки.](/defender-endpoint/enable-siem-integration)</span><span class="sxs-lookup"><span data-stu-id="f2d61-154">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](/defender-endpoint/enable-siem-integration).</span></span>


## <a name="next-steps"></a><span data-ttu-id="f2d61-155">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="f2d61-155">Next steps</span></span>
[<span data-ttu-id="f2d61-156">Включить оценку</span><span class="sxs-lookup"><span data-stu-id="f2d61-156">Enable the evaluation</span></span>](eval-defender-endpoint-enable-eval.md)

<span data-ttu-id="f2d61-157">Возвращение к обзору [оценки Microsoft Defender для конечной точки](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f2d61-157">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="f2d61-158">Возвращайся к обзору [для оценки и пилотных Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f2d61-158">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>