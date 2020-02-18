---
title: Стратегии развертывания базовой инфраструктуры Microsoft 365 для предприятий
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 09/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Сведения о некоторых возможных способах поэтапного развертывания базовой инфраструктуры для Microsoft 365 для предприятий.
ms.openlocfilehash: 765bba743485c13c65cd6377abe01f80f2df4c23
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067826"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure-deployment-strategies"></a><span data-ttu-id="449b6-103">Стратегии развертывания базовой инфраструктуры Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="449b6-103">Microsoft 365 for enterprise foundation infrastructure deployment strategies</span></span>

<span data-ttu-id="449b6-p101">Существует множество способов, с помощью которых можно развернуть этапы [базовой инфраструктуры](deploy-foundation-infrastructure.md) Microsoft 365 для предприятий и реализовать ее возможности, программное обеспечение и службы для пользователей. Чтобы начать управление таким проектом, который может быть масштабным и сложным в зависимости от размера организации и существующей инфраструктуры, рассмотрите указанные ниже стратегии развертывания.</span><span class="sxs-lookup"><span data-stu-id="449b6-p101">There are many ways you can deploy the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) of Microsoft 365 for enterprise and roll out its capabilities, software, and services to your users. To get you started on the project management of this undertaking, which can be large and complex depending on the size of your organization and its existing infrastructure, consider the following deployment strategies:</span></span>

- <span data-ttu-id="449b6-106">Последовательное развертывание</span><span class="sxs-lookup"><span data-stu-id="449b6-106">Serial deployment</span></span>
- <span data-ttu-id="449b6-107">Параллельное развертывание без перекрытия пользовательского развертывания</span><span class="sxs-lookup"><span data-stu-id="449b6-107">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="449b6-108">Параллельное развертывание с перекрытием пользовательского развертывания</span><span class="sxs-lookup"><span data-stu-id="449b6-108">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="449b6-109">Предварительная подготовка инфраструктуры и внедрение комплексной настройки</span><span class="sxs-lookup"><span data-stu-id="449b6-109">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="449b6-110">Используйте эти стратегии для выбора способа управления общим проектом и ускоренной реализации бизнес-преимуществ Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="449b6-110">Use these strategies for ideas on how to manage the overall project and more quickly realize the business benefits of Microsoft 365 for enterprise.</span></span>

>[!Note]
><span data-ttu-id="449b6-p102">В этой статье содержатся допущения и упрощения для единообразного способа описания стратегий развертывания. Эти стратегии развертывания являются обобщенными, не подразумевают конкретных временных рамок и не предназначены для применения во всех организациях и ситуациях.</span><span class="sxs-lookup"><span data-stu-id="449b6-p102">This article contains assumptions and simplifications for a consistent way to describe the deployment strategies. These deployment strategies are generalized and are not meant to imply any specific timeframes, nor are they meant to apply to all organizations and situations.</span></span>
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a><span data-ttu-id="449b6-113">Элементы управления ИТ-проектами для типовых корпоративных организаций</span><span class="sxs-lookup"><span data-stu-id="449b6-113">Elements of IT project management for typical enterprise organizations</span></span>

<span data-ttu-id="449b6-p103">ИТ-инфраструктура включает серверные службы, развертывание новых или улучшенных возможностей или установленного программного обеспечения для конечных пользователей. Развертывание ИТ-отделами элементов ИТ-инфраструктуры обычно выполняется систематично. Этапы одного из способов успешного развертывания элемента ИТ-инфраструктуры:</span><span class="sxs-lookup"><span data-stu-id="449b6-p103">IT infrastructure includes both backend services and the rollout of new or improved capabilities or installed software to end users. IT departments typically deploy elements of an IT infrastructure in a methodical way. One approach to the successful deployment of an element of IT infrastructure consists of:</span></span>

- <span data-ttu-id="449b6-117">Пилотное развертывание</span><span class="sxs-lookup"><span data-stu-id="449b6-117">A pilot rollout</span></span> 

  <span data-ttu-id="449b6-118">Включает исходную настройку инфраструктуры и развертывание для пилотной группы пользователей, тестирование и последующие изменения в настройке инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="449b6-118">This includes initial infrastructure configuration and rollout to a pilot set of users, testing, and subsequent modifications to the infrastructure configuration.</span></span>

- <span data-ttu-id="449b6-119">Пользовательское развертывание</span><span class="sxs-lookup"><span data-stu-id="449b6-119">A user rollout</span></span>

  <span data-ttu-id="449b6-120">Включает развертывание для остальной организации на основе регионов, отделов, групп и других типов системного распространения настройки или программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="449b6-120">This includes the rollout to the rest of your organization based on regions, departments, groups, or other types of systematic propagation of configuration or software.</span></span>

<span data-ttu-id="449b6-121">Группа пользователей в пилотном развертывании отличается от группы пользовательского развертывания.</span><span class="sxs-lookup"><span data-stu-id="449b6-121">The set of users in the pilot rollout are not the same as those in the user rollout.</span></span>

<span data-ttu-id="449b6-122">В этой статье используются указанные ниже изображения для этих определений.</span><span class="sxs-lookup"><span data-stu-id="449b6-122">This article uses the following graphics to depict these definitions:</span></span> 

![Изображение, отображающее определения пилотного и пользовательского развертывания](../media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

<span data-ttu-id="449b6-124">Затенение изображения пользовательского развертывания указывает процентное значение в организации от 0 до 100 % с использованием структурного или методичного подхода, например по группам, отделам или регионам.</span><span class="sxs-lookup"><span data-stu-id="449b6-124">The shading for the user rollout graphic indicates the percentage across your organization from 0% to 100% using a structured or methodical approach such as groups, departments, or regions.</span></span>

## <a name="deployment-strategies"></a><span data-ttu-id="449b6-125">Стратегии развертывания</span><span class="sxs-lookup"><span data-stu-id="449b6-125">Deployment strategies</span></span>

<span data-ttu-id="449b6-126">Рассмотрите указанные ниже стратегии развертывания.</span><span class="sxs-lookup"><span data-stu-id="449b6-126">Consider the following deployment strategies:</span></span>

- <span data-ttu-id="449b6-127">Последовательное развертывание</span><span class="sxs-lookup"><span data-stu-id="449b6-127">Serial deployment</span></span>
- <span data-ttu-id="449b6-128">Параллельное развертывание без перекрытия пользовательского развертывания</span><span class="sxs-lookup"><span data-stu-id="449b6-128">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="449b6-129">Параллельное развертывание с перекрытием пользовательского развертывания</span><span class="sxs-lookup"><span data-stu-id="449b6-129">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="449b6-130">Предварительная подготовка инфраструктуры и внедрение комплексной настройки</span><span class="sxs-lookup"><span data-stu-id="449b6-130">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

### <a name="serial-deployment"></a><span data-ttu-id="449b6-131">Последовательное развертывание</span><span class="sxs-lookup"><span data-stu-id="449b6-131">Serial deployment</span></span>

<span data-ttu-id="449b6-p104">При последовательном развертывании перед переходом к следующему этапу выполняется полное развертывание текущего этапа с достижением 100 % завершения для всех пользователей. Причины возможного применения этого способа развертывания:</span><span class="sxs-lookup"><span data-stu-id="449b6-p104">With a serial deployment, you completely roll out a phase, allowing the phase to reach 100% completion of deployment to all of your users, before moving on to the next one. Here are some of the reasons why you might deploy this way:</span></span>

- <span data-ttu-id="449b6-134">Устранение рисков</span><span class="sxs-lookup"><span data-stu-id="449b6-134">Risk mitigation</span></span>
- <span data-ttu-id="449b6-135">Ограничения ресурсов</span><span class="sxs-lookup"><span data-stu-id="449b6-135">Resourcing constraints</span></span>
- <span data-ttu-id="449b6-136">Циклы финансирования ИТ-отделов</span><span class="sxs-lookup"><span data-stu-id="449b6-136">IT department funding cycles</span></span>
- <span data-ttu-id="449b6-137">Зависимости от ИТ-технологии</span><span class="sxs-lookup"><span data-stu-id="449b6-137">IT technology dependencies</span></span>
- <span data-ttu-id="449b6-138">Управление изменениями в компании и сопротивление конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="449b6-138">Business change management and end-user resistance</span></span>

<span data-ttu-id="449b6-139">На этой диаграмме Ганта показано упрощенное последовательное развертывание этапов 2–6 базовой инфраструктуры для Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="449b6-139">This Gantt chart shows a simplified serial deployment of phases 2-6 of the foundation infrastructure for Microsoft 365 for enterprise.</span></span>

![Последовательное развертывание этапов 2–6 базовой инфраструктуры](../media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
<span data-ttu-id="449b6-141">Для упрощения обсуждения и примера предполагается, что каждый этап и сегмент развертывания в каждом этапе занимают одинаковое время.</span><span class="sxs-lookup"><span data-stu-id="449b6-141">To simplify the discussion and example, each phase and deployment segment within each phase are assumed to take the same amount of time.</span></span>

>[!Note]
><span data-ttu-id="449b6-p105">Этап 1. Сетевые подключения базовой инфраструктуры Microsoft 365 для предприятий являются этапом, относящимся только к ИТ-отделу. Пользователи используют преимущества оптимизированного подключения к облачным ресурсам Майкрософт, но не обязаны участвовать в реализации этого этапа.</span><span class="sxs-lookup"><span data-stu-id="449b6-p105">Phase 1: Networking of the Microsoft 365 for enterprise Foundation Infrastructure is an IT department-only phase. Users reap the benefits of optimized connectivity to Microsoft’s cloud resources but are not imposed upon to achieve it.</span></span>
>

<span data-ttu-id="449b6-144">Пример упрощенного опыта пилотного пользователя:</span><span class="sxs-lookup"><span data-stu-id="449b6-144">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="449b6-p106">В декабре пользователю нужно использовать свой смартфон для многофакторной проверки подлинности. (Удостоверение)</span><span class="sxs-lookup"><span data-stu-id="449b6-p106">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="449b6-p107">В марте на компьютере пользователя с Windows 8.1 устанавливается Windows 10 Корпоративная. (Windows 10 Корпоративная)</span><span class="sxs-lookup"><span data-stu-id="449b6-p107">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="449b6-p108">В июне для пользователя устанавливается Office 365 профессиональный плюс, заменяющий Office 2013. (Office 365 профессиональный плюс)</span><span class="sxs-lookup"><span data-stu-id="449b6-p108">In June, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="449b6-151">В сентябре выполняется развертывание устройства и применение политик приложения и устройства.</span><span class="sxs-lookup"><span data-stu-id="449b6-151">In September, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="449b6-152">(Управление мобильными устройствами)</span><span class="sxs-lookup"><span data-stu-id="449b6-152">(Mobile device management)</span></span>
- <span data-ttu-id="449b6-p110">В декабре для пользователя устанавливается клиент Azure Information Protection и он проходит обучение по применению меток к документам. (Защита информации)</span><span class="sxs-lookup"><span data-stu-id="449b6-p110">In December, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="449b6-155">В результате обеспечивается периодичность в 90 дней между успешными пилотными развертываниями.</span><span class="sxs-lookup"><span data-stu-id="449b6-155">The result is a 90-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="449b6-156">Пример упрощенного опыта конечного пользователя:</span><span class="sxs-lookup"><span data-stu-id="449b6-156">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="449b6-p111">В январе пользователю нужно использовать свой смартфон для многофакторной проверки подлинности. (Удостоверение)</span><span class="sxs-lookup"><span data-stu-id="449b6-p111">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="449b6-p112">В апреле на компьютере пользователя с Windows 8.1 устанавливается Windows 10 Корпоративная. (Windows 10 Корпоративная)</span><span class="sxs-lookup"><span data-stu-id="449b6-p112">In April, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="449b6-p113">В июле для пользователя устанавливается Office 365 профессиональный плюс, заменяющий Office 2013. (Office 365 профессиональный плюс)</span><span class="sxs-lookup"><span data-stu-id="449b6-p113">In July, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="449b6-163">В октябре выполняется развертывание устройства и применение политик приложения и устройства.</span><span class="sxs-lookup"><span data-stu-id="449b6-163">In October, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="449b6-164">(Управление мобильными устройствами)</span><span class="sxs-lookup"><span data-stu-id="449b6-164">(Mobile device management)</span></span>
- <span data-ttu-id="449b6-p115">В январе следующего года для пользователя устанавливается клиент Azure Information Protection и он проходит обучение по применению меток к документам. (Защита информации)</span><span class="sxs-lookup"><span data-stu-id="449b6-p115">In January of the following year, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="449b6-167">В результате обеспечивается периодичность в 90 дней между успешными пользовательскими развертываниями.</span><span class="sxs-lookup"><span data-stu-id="449b6-167">The result is a 90-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="449b6-168">Недостатком этой стратегии развертывания является возможная продолжительность полного развертывания базовой инфраструктуры Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="449b6-168">The disadvantage to this deployment strategy is that it can take a long time to fully deploy the Microsoft 365 for enterprise foundation infrastructure.</span></span>

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a><span data-ttu-id="449b6-169">Параллельное развертывание без перекрытия пользовательского развертывания (параллельное 1)</span><span class="sxs-lookup"><span data-stu-id="449b6-169">Parallel deployment with non-overlapping user rollout (Parallel 1)</span></span>

<span data-ttu-id="449b6-p116">При этой стратегии пилотное развертывание следующего этапа начинается на последнем шаге пользовательского развертывания текущего этапа. Ниже представлено развертывание этапов 2–6 при выполнении пилотного развертывания во время завершения пользовательского развертывания предыдущего этапа.</span><span class="sxs-lookup"><span data-stu-id="449b6-p116">For this deployment strategy, you start the pilot rollout of the next phase during the last part of the user rollout of the current phase. Here is the deployment of phases 2-6 when the pilot rollout occurs as the user rollout of the previous phase is wrapping up.</span></span>

![Параллельное развертывание этапов 2–6 без перекрытия пользовательского развертывания](../media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
<span data-ttu-id="449b6-p117">Итоговым результатом является завершение в организации пользовательского развертывания текущего этапа до начала следующего. Пользователи, не участвующие в пилотных развертываниях, не сталкиваются с одновременным развертыванием нескольких этапов, но пилотные развертывания выполняются параллельно с пользовательскими.</span><span class="sxs-lookup"><span data-stu-id="449b6-p117">The end result is that user rollout for the current phase completes across your organization before the next one starts. Users that are not in pilot rollouts are not dealing with the rollouts of multiple phases at the same time, but pilot rollouts are done in parallel with user rollouts.</span></span>

<span data-ttu-id="449b6-175">Пример упрощенного опыта пилотного пользователя:</span><span class="sxs-lookup"><span data-stu-id="449b6-175">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="449b6-p118">В декабре пользователю нужно использовать свой смартфон для многофакторной проверки подлинности. (Удостоверение)</span><span class="sxs-lookup"><span data-stu-id="449b6-p118">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="449b6-p119">В феврале на компьютере пользователя с Windows 8.1 устанавливается Windows 10 Корпоративная. (Windows 10 Корпоративная)</span><span class="sxs-lookup"><span data-stu-id="449b6-p119">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="449b6-p120">В апреле для пользователя устанавливается Office 365 профессиональный плюс, заменяющий Office 2013. (Office 365 профессиональный плюс)</span><span class="sxs-lookup"><span data-stu-id="449b6-p120">In April, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="449b6-182">В июне выполняется развертывание устройства и применение политик приложения и устройства.</span><span class="sxs-lookup"><span data-stu-id="449b6-182">In June, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="449b6-183">(Управление мобильными устройствами)</span><span class="sxs-lookup"><span data-stu-id="449b6-183">(Mobile device management)</span></span>
- <span data-ttu-id="449b6-p122">В августе для пользователя устанавливается клиент Azure Information Protection и он проходит обучение по применению меток к документам. (Защита информации)</span><span class="sxs-lookup"><span data-stu-id="449b6-p122">In August, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="449b6-186">В результате обеспечивается периодичность в 60 дней между успешными пилотными развертываниями.</span><span class="sxs-lookup"><span data-stu-id="449b6-186">The result is a 60-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="449b6-187">Пример упрощенного опыта конечного пользователя:</span><span class="sxs-lookup"><span data-stu-id="449b6-187">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="449b6-p123">В январе пользователю нужно использовать свой смартфон для многофакторной проверки подлинности. (Удостоверение)</span><span class="sxs-lookup"><span data-stu-id="449b6-p123">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="449b6-p124">В марте на компьютере пользователя с Windows 8.1 устанавливается Windows 10 Корпоративная. (Windows 10 Корпоративная)</span><span class="sxs-lookup"><span data-stu-id="449b6-p124">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="449b6-p125">В мае для пользователя устанавливается Office 365 профессиональный плюс, заменяющий Office 2013. (Office 365 профессиональный плюс)</span><span class="sxs-lookup"><span data-stu-id="449b6-p125">In May, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="449b6-194">В июле выполняется развертывание устройства и применение политик приложения и устройства.</span><span class="sxs-lookup"><span data-stu-id="449b6-194">In July, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="449b6-195">(Управление мобильными устройствами)</span><span class="sxs-lookup"><span data-stu-id="449b6-195">(Mobile device management)</span></span>
- <span data-ttu-id="449b6-p127">В сентябре для пользователя устанавливается клиент Azure Information Protection и он проходит обучение по применению меток к документам. (Защита информации)</span><span class="sxs-lookup"><span data-stu-id="449b6-p127">In September, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="449b6-198">В результате обеспечивается периодичность в 60 дней между успешными пользовательскими развертываниями.</span><span class="sxs-lookup"><span data-stu-id="449b6-198">The result is a 60-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="449b6-199">Преимущество этой стратегии развертывания заключается в возможности быстрее выполнить полное развертывание базовой инфраструктуры Microsoft 365 для предприятий без необходимости ИТ-отделу и пользователям сталкиваться с несколькими развертываниями одновременно.</span><span class="sxs-lookup"><span data-stu-id="449b6-199">The advantage to this deployment strategy is that it can take less time to fully deploy the Microsoft 365 for enterprise foundation infrastructure, without having your IT department and users deal with multiple rollouts the same time.</span></span>

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a><span data-ttu-id="449b6-200">Параллельное развертывание с перекрытием пользовательского развертывания (параллельное 2)</span><span class="sxs-lookup"><span data-stu-id="449b6-200">Parallel deployment with overlapping user rollout (Parallel 2)</span></span>

<span data-ttu-id="449b6-201">При этой стратегия развертывания вы начинаете:</span><span class="sxs-lookup"><span data-stu-id="449b6-201">For this deployment strategy, you start the:</span></span>

- <span data-ttu-id="449b6-202">пилотное развертывание следующего этапа во время последней части пользовательского развертывания текущего этапа.</span><span class="sxs-lookup"><span data-stu-id="449b6-202">Pilot rollout of the next phase during the last part of the user rollout of the current phase.</span></span>
- <span data-ttu-id="449b6-203">пользовательское развертывание следующего этапа во время пользовательского развертывания текущего этапа таким образом, что пользователям не приходится сталкиваться с одновременным развертыванием нескольких этапов.</span><span class="sxs-lookup"><span data-stu-id="449b6-203">User rollout of the next phase during the user rollout of the current phase in such a way that no user is dealing with the rollouts of multiple phases at the same time.</span></span> <span data-ttu-id="449b6-204">Предполагается, что развертывание каждого этапа базовой инфраструктуры выполняется аналогично (по регионам, отделам или другим единицам).</span><span class="sxs-lookup"><span data-stu-id="449b6-204">This assumes that you are rolling out each phase of the foundation infrastructure in the same way, using regions, departments, or other groupings.</span></span>

<span data-ttu-id="449b6-205">Ниже приведено упрощенное сравнение разных стратегий развертывания.</span><span class="sxs-lookup"><span data-stu-id="449b6-205">Here is a simplified comparison between the different deployment strategies.</span></span>

![Параллельное развертывание этапов 2–6 с перекрытием пользовательского развертывания](../media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

<span data-ttu-id="449b6-207">Итоговый результат:</span><span class="sxs-lookup"><span data-stu-id="449b6-207">The end result is that:</span></span>

- <span data-ttu-id="449b6-208">Переход пилотных развертываний с одного этапа на следующий выполняется без задержек.</span><span class="sxs-lookup"><span data-stu-id="449b6-208">Pilot rollouts go from one phase to the next without a pause.</span></span>
- <span data-ttu-id="449b6-209">Пользовательское развертывание для этапа начинается до завершения пользовательского развертывания предыдущего этапа, но отдельные пользователи не выполняют одновременное развертывание нескольких этапов.</span><span class="sxs-lookup"><span data-stu-id="449b6-209">The user rollout for a phase begins before the completion of the user rollout of the previous phase, but no individual user is rolling out more than one phase at a time.</span></span>

<span data-ttu-id="449b6-210">Пример упрощенного опыта пилотного пользователя:</span><span class="sxs-lookup"><span data-stu-id="449b6-210">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="449b6-p129">В декабре пользователю нужно использовать свой смартфон для многофакторной проверки подлинности. (Удостоверение)</span><span class="sxs-lookup"><span data-stu-id="449b6-p129">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="449b6-p130">В январе на компьютере пользователя с Windows 8.1 устанавливается Windows 10 Корпоративная. (Windows 10 Корпоративная)</span><span class="sxs-lookup"><span data-stu-id="449b6-p130">In January, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="449b6-p131">В феврале для пользователя устанавливается Office 365 профессиональный плюс, заменяющий Office 2013. (Office 365 профессиональный плюс)</span><span class="sxs-lookup"><span data-stu-id="449b6-p131">In February, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="449b6-217">В марте выполняется развертывание устройства и применение политик приложения и устройства.</span><span class="sxs-lookup"><span data-stu-id="449b6-217">In March, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="449b6-218">(Управление мобильными устройствами)</span><span class="sxs-lookup"><span data-stu-id="449b6-218">(Mobile device management)</span></span>
- <span data-ttu-id="449b6-p133">В апреле для пользователя устанавливается клиент Azure Information Protection и он проходит обучение по применению меток к документам. (Защита информации)</span><span class="sxs-lookup"><span data-stu-id="449b6-p133">In April, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="449b6-221">В результате обеспечивается периодичность в 30 дней между успешными пилотными развертываниями.</span><span class="sxs-lookup"><span data-stu-id="449b6-221">The result is a 30-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="449b6-222">Пример упрощенного опыта конечного пользователя:</span><span class="sxs-lookup"><span data-stu-id="449b6-222">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="449b6-p134">В январе пользователю нужно использовать свой смартфон для многофакторной проверки подлинности. (Удостоверение)</span><span class="sxs-lookup"><span data-stu-id="449b6-p134">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="449b6-p135">В феврале на компьютере пользователя с Windows 8.1 устанавливается Windows 10 Корпоративная. (Windows 10 Корпоративная)</span><span class="sxs-lookup"><span data-stu-id="449b6-p135">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="449b6-p136">В марте для пользователя устанавливается Office 365 профессиональный плюс, заменяющий Office 2013. (Office 365 профессиональный плюс)</span><span class="sxs-lookup"><span data-stu-id="449b6-p136">In March, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="449b6-229">В апреле выполняется развертывание устройства и применение политик приложения и устройства.</span><span class="sxs-lookup"><span data-stu-id="449b6-229">In April, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="449b6-230">(Управление мобильными устройствами)</span><span class="sxs-lookup"><span data-stu-id="449b6-230">(Mobile device management)</span></span>
- <span data-ttu-id="449b6-p138">В мае для пользователя устанавливается клиент Azure Information Protection и он проходит обучение по применению меток к документам. (Защита информации)</span><span class="sxs-lookup"><span data-stu-id="449b6-p138">In May, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="449b6-233">В результате обеспечивается периодичность в 30 дней между успешными пользовательскими развертываниями.</span><span class="sxs-lookup"><span data-stu-id="449b6-233">The result is a 30-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="449b6-234">Преимущество этой стратегии развертывания заключается в возможности еще быстрее выполнить полное развертывание базовой инфраструктуры Microsoft 365 для предприятий без необходимости конечным пользователям сталкиваться с несколькими развертываниями одновременно.</span><span class="sxs-lookup"><span data-stu-id="449b6-234">The advantage to this deployment strategy is that it can take even less time to fully deploy the Microsoft 365 for enterprise foundation infrastructure, still without having end-users deal with multiple rollouts the same time.</span></span> <span data-ttu-id="449b6-235">Но между успешными этапами для пользователей не предусматриваются перерывы.</span><span class="sxs-lookup"><span data-stu-id="449b6-235">However, users don’t get a break between successive phases.</span></span>

### <a name="up-front-infrastructure-and-rollout-of-the-end-to-end-configuration"></a><span data-ttu-id="449b6-236">Предварительная подготовка инфраструктуры и внедрение комплексной настройки</span><span class="sxs-lookup"><span data-stu-id="449b6-236">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="449b6-237">Для небольших организаций с возможностью сжатия этапов 2–6 в один сегмент развертывания итоговое развертывание выглядит представленным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="449b6-237">For smaller organizations with the ability to compress phases 2-6 into a single deployment segment, the resulting deployment looks like this:</span></span>
 
![Предварительная подготовка инфраструктуры и внедрение комплексной настройки](../media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

<span data-ttu-id="449b6-p140">ИТ-отдел настраивает инфраструктуру для этапов 2–6, а затем развертывает ее для пилотных пользователей, чтобы проверить комплексные функции. Например, пилотные пользователи получают все эти функциональные возможности одновременно:</span><span class="sxs-lookup"><span data-stu-id="449b6-p140">The IT department configures the infrastructure for phases 2-6, then rolls out to the pilot users to check for the end-to-end functionality. For example, pilot users get all of this functionality at the same time:</span></span>

- <span data-ttu-id="449b6-241">многофакторная проверка подлинности и другие функции удостоверений (удостоверение);</span><span class="sxs-lookup"><span data-stu-id="449b6-241">MFA and other identity features (Identity)</span></span>
- <span data-ttu-id="449b6-242">Windows 10 Корпоративная на устройствах с Windows (Windows 10 Корпоративная);</span><span class="sxs-lookup"><span data-stu-id="449b6-242">Windows 10 Enterprise on Windows devices (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="449b6-243">Office 365 профессиональный плюс для набора Office (Office 365 профессиональный плюс);</span><span class="sxs-lookup"><span data-stu-id="449b6-243">Office 365 ProPlus for the Office suite (Office 365 ProPlus)</span></span>
- <span data-ttu-id="449b6-244">политики приложения и устройства (управление мобильными устройствами);</span><span class="sxs-lookup"><span data-stu-id="449b6-244">App and device policies (Mobile device management)</span></span>
- <span data-ttu-id="449b6-245">установленный клиент Azure Information Protection и обучение по применению меток к документам (защита информации).</span><span class="sxs-lookup"><span data-stu-id="449b6-245">Azure Information Protection client installed and training on how to apply labels to documents (Information protection)</span></span>

<span data-ttu-id="449b6-246">После завершения пилотного развертывания начинается пользовательское развертывание, при котором пользователь получает все функциональные возможности одновременно.</span><span class="sxs-lookup"><span data-stu-id="449b6-246">Once the pilot rollout is concluded, the user rollout begins in which each user gets all the functionality the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="449b6-247">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="449b6-247">Next step</span></span>

<span data-ttu-id="449b6-248">Начните развертывание Microsoft 365 для предприятий в [базовой инфраструктуре](deploy-foundation-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="449b6-248">Start your deployment of Microsoft 365 for enterprise with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
