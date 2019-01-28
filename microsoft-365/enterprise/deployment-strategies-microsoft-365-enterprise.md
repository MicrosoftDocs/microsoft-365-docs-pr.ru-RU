---
title: Стратегии развертывания базовой инфраструктуры Microsoft 365 корпоративный
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 01/23/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Сведения о некоторых возможных способах поэтапного развертывания базовой инфраструктуры для Microsoft 365 корпоративный.
ms.openlocfilehash: 5ffe00c9eb975a0f8c2d193a71d8b613e827cc70
ms.sourcegitcommit: f2eae6ec367f7b69043105d117a2a7e3da4153aa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "29538972"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-deployment-strategies"></a><span data-ttu-id="18f7a-103">Стратегии развертывания базовой инфраструктуры Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="18f7a-103">Microsoft 365 Enterprise foundation infrastructure deployment strategies</span></span>

<span data-ttu-id="18f7a-p101">Существует множество способов, с помощью которых можно развернуть этапы [базовой инфраструктуры](deploy-foundation-infrastructure.md) Microsoft 365 корпоративный и реализовать ее возможности, программное обеспечение и службы для пользователей. Чтобы начать управление таким проектом, который может быть масштабным и сложным в зависимости от размера организации и существующей инфраструктуры, рассмотрите указанные ниже стратегии развертывания.</span><span class="sxs-lookup"><span data-stu-id="18f7a-p101">There are many ways you can deploy the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) of Microsoft 365 Enterprise and roll out its capabilities, software, and services to your users. To get you started on the project management of this undertaking, which can be large and complex depending on the size of your organization and its existing infrastructure, consider the following deployment strategies:</span></span>

- <span data-ttu-id="18f7a-106">Последовательное развертывание</span><span class="sxs-lookup"><span data-stu-id="18f7a-106">Serial deployment</span></span>
- <span data-ttu-id="18f7a-107">Параллельное развертывание без перекрытия пользовательского развертывания</span><span class="sxs-lookup"><span data-stu-id="18f7a-107">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="18f7a-108">Параллельное развертывание с перекрытием пользовательского развертывания</span><span class="sxs-lookup"><span data-stu-id="18f7a-108">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="18f7a-109">Предварительная подготовка инфраструктуры и внедрение комплексной настройки</span><span class="sxs-lookup"><span data-stu-id="18f7a-109">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="18f7a-110">Используйте эти стратегии для выбора способа управления общим проектом и ускоренной реализации бизнес-преимуществ Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="18f7a-110">Use these strategies for ideas on how to manage the overall project and more quickly realize the business benefits of Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="18f7a-p102">В этой статье содержатся допущения и упрощения для единообразного способа описания стратегий развертывания. Эти стратегии развертывания являются обобщенными, не подразумевают конкретных временных рамок и не предназначены для применения во всех организациях и ситуациях.</span><span class="sxs-lookup"><span data-stu-id="18f7a-p102">This article contains assumptions and simplifications for a consistent way to describe the deployment strategies. These deployment strategies are generalized and are not meant to imply any specific timeframes, nor are they meant to apply to all organizations and situations.</span></span>
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a><span data-ttu-id="18f7a-113">Элементы управления ИТ-проектами для типовых корпоративных организаций</span><span class="sxs-lookup"><span data-stu-id="18f7a-113">Elements of IT project management for typical enterprise organizations</span></span>

<span data-ttu-id="18f7a-p103">ИТ-инфраструктура включает серверные службы, развертывание новых или улучшенных возможностей или установленного программного обеспечения для конечных пользователей. Развертывание ИТ-отделами элементов ИТ-инфраструктуры обычно выполняется систематично. Этапы одного из способов успешного развертывания элемента ИТ-инфраструктуры:</span><span class="sxs-lookup"><span data-stu-id="18f7a-p103">IT infrastructure includes both backend services and the rollout of new or improved capabilities or installed software to end users. IT departments typically deploy elements of an IT infrastructure in a methodical way. One approach to the successful deployment of an element of IT infrastructure consists of:</span></span>

- <span data-ttu-id="18f7a-117">Пилотное развертывание</span><span class="sxs-lookup"><span data-stu-id="18f7a-117">A pilot rollout</span></span> 

  <span data-ttu-id="18f7a-118">Включает исходную настройку инфраструктуры и развертывание для пилотной группы пользователей, тестирование и последующие изменения в настройке инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="18f7a-118">This includes initial infrastructure configuration and rollout to a pilot set of users, testing, and subsequent modifications to the infrastructure configuration.</span></span>

- <span data-ttu-id="18f7a-119">Пользовательское развертывание</span><span class="sxs-lookup"><span data-stu-id="18f7a-119">A user rollout</span></span>

  <span data-ttu-id="18f7a-120">Включает развертывание для остальной организации на основе областей, отделов, групп и других типов системного распространения настройки или программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="18f7a-120">This includes the rollout to the rest of your organization based on regions, departments, groups, or other types of systematic propagation of configuration or software.</span></span>

<span data-ttu-id="18f7a-121">Группа пользователей в пилотном развертывании отличается от группы пользовательского развертывания.</span><span class="sxs-lookup"><span data-stu-id="18f7a-121">The set of users in the pilot rollout are not the same as those in the user rollout.</span></span>

<span data-ttu-id="18f7a-122">В этой статье используются указанные ниже изображения для этих определений.</span><span class="sxs-lookup"><span data-stu-id="18f7a-122">This article uses the following graphics to depict these definitions:</span></span> 

![](./media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

<span data-ttu-id="18f7a-123">Затенение изображения пользовательского развертывания указывает развертывание в организации от 0 до 100 % с использованием структурного или методичного подхода, например по группам, отделам или областям.</span><span class="sxs-lookup"><span data-stu-id="18f7a-123">The shading for the user rollout graphic indicates the rollout across your organization from 0% to 100% using a structured or methodical approach such as groups, departments, or regions.</span></span>

## <a name="deployment-strategies"></a><span data-ttu-id="18f7a-124">Стратегии развертывания</span><span class="sxs-lookup"><span data-stu-id="18f7a-124">Deployment strategies</span></span>

<span data-ttu-id="18f7a-125">Рассмотрите указанные ниже стратегии развертывания.</span><span class="sxs-lookup"><span data-stu-id="18f7a-125">Consider the following deployment strategies:</span></span>

- <span data-ttu-id="18f7a-126">Последовательное развертывание</span><span class="sxs-lookup"><span data-stu-id="18f7a-126">Serial deployment</span></span>
- <span data-ttu-id="18f7a-127">Параллельное развертывание без перекрытия пользовательского развертывания</span><span class="sxs-lookup"><span data-stu-id="18f7a-127">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="18f7a-128">Параллельное развертывание с перекрытием пользовательского развертывания</span><span class="sxs-lookup"><span data-stu-id="18f7a-128">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="18f7a-129">Предварительная подготовка инфраструктуры и внедрение комплексной настройки</span><span class="sxs-lookup"><span data-stu-id="18f7a-129">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

### <a name="serial-deployment"></a><span data-ttu-id="18f7a-130">Последовательное развертывание</span><span class="sxs-lookup"><span data-stu-id="18f7a-130">Serial deployment</span></span>

<span data-ttu-id="18f7a-p104">При последовательном развертывании перед переходом к следующему этапу выполняется полное развертывание текущего этапа с достижением 100 % завершения для всех пользователей. Причины возможного применения этого способа развертывания:</span><span class="sxs-lookup"><span data-stu-id="18f7a-p104">With a serial deployment, you completely roll out a phase, allowing the phase to reach 100% completion of deployment to all of your users, before moving on to the next one. Here are some of the reasons why you might deploy this way:</span></span>

- <span data-ttu-id="18f7a-133">Устранение рисков</span><span class="sxs-lookup"><span data-stu-id="18f7a-133">Risk mitigation</span></span>
- <span data-ttu-id="18f7a-134">Ограничения ресурсов</span><span class="sxs-lookup"><span data-stu-id="18f7a-134">Resourcing constraints</span></span>
- <span data-ttu-id="18f7a-135">Циклы финансирования ИТ-отделов</span><span class="sxs-lookup"><span data-stu-id="18f7a-135">IT department funding cycles</span></span>
- <span data-ttu-id="18f7a-136">Зависимости от ИТ-технологии</span><span class="sxs-lookup"><span data-stu-id="18f7a-136">IT technology dependencies</span></span>
- <span data-ttu-id="18f7a-137">Управление изменениями в компании и сопротивление конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="18f7a-137">Business change management and end-user resistance</span></span>

<span data-ttu-id="18f7a-138">На этой диаграмме Ганта показано упрощенное последовательное развертывание этапов 2–6 базовой инфраструктуры для Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="18f7a-138">This Gantt chart shows a simplified serial deployment of phases 2-6 of the foundation infrastructure for Microsoft 365 Enterprise.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
<span data-ttu-id="18f7a-139">Для упрощения обсуждения и примера предполагается, что каждый этап и сегмент развертывания в каждом этапе занимают одинаковое время.</span><span class="sxs-lookup"><span data-stu-id="18f7a-139">To simplify the discussion and example, each phase and deployment segment within each phase are assumed to take the same amount of time.</span></span>

>[!Note]
><span data-ttu-id="18f7a-p105">Этап 1. Сетевые подключения базовой инфраструктуры Microsoft 365 корпоративный являются этапом, относящимся только к ИТ-отделу. Пользователи используют преимущества оптимизированного подключения к облачным ресурсам Майкрософт, но не обязаны участвовать в реализации этого этапа.</span><span class="sxs-lookup"><span data-stu-id="18f7a-p105">Phase 1: Networking of the Microsoft 365 Enterprise Foundation Infrastructure is an IT department-only phase. Users reap the benefits of optimized connectivity to Microsoft’s cloud resources but are not imposed upon to achieve it.</span></span>
>

<span data-ttu-id="18f7a-142">Упрощенный пример опыта пилотного пользователя:</span><span class="sxs-lookup"><span data-stu-id="18f7a-142">Simplified example pilot user experience:</span></span>

- <span data-ttu-id="18f7a-p106">В декабре пользователю нужно использовать свой смартфон для многофакторной проверки подлинности. (Удостоверение)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p106">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="18f7a-p107">В марте на компьютере пользователя с Windows 8.1 устанавливается Windows 10 Корпоративная. (Windows 10 Корпоративная)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p107">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="18f7a-p108">В июне для пользователя устанавливается Office 365 профессиональный плюс, заменяющий Office 2013. (Office 365 профессиональный плюс)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p108">In June, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="18f7a-p109">В сентябре выполняется развертывание устройства и применение политик приложения и условного доступа. (Управление мобильными устройствами)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p109">In September, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="18f7a-p110">В декабре для пользователя устанавливается клиент Azure Information Protection и он проходит обучение по применению меток к документам. (Защита информации)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p110">In December, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="18f7a-153">В результате обеспечивается периодичность в 90 дней между успешными пилотными развертываниями.</span><span class="sxs-lookup"><span data-stu-id="18f7a-153">The result is a 90-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="18f7a-154">Упрощенный пример опыта конечного пользователя:</span><span class="sxs-lookup"><span data-stu-id="18f7a-154">Simplified example end-user experience:</span></span>

- <span data-ttu-id="18f7a-p111">В январе пользователю нужно использовать свой смартфон для многофакторной проверки подлинности. (Удостоверение)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p111">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="18f7a-p112">В апреле на компьютере пользователя с Windows 8.1 устанавливается Windows 10 Корпоративная. (Windows 10 Корпоративная)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p112">In April, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="18f7a-p113">В июле для пользователя устанавливается Office 365 профессиональный плюс, заменяющий Office 2013. (Office 365 профессиональный плюс)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p113">In July, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="18f7a-p114">В октябре выполняется развертывание устройства и применение политик приложения и условного доступа. (Управление мобильными устройствами)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p114">In October, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="18f7a-p115">В январе следующего года для пользователя устанавливается клиент Azure Information Protection и он проходит обучение по применению меток к документам. (Защита информации)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p115">In January of the following year, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="18f7a-165">В результате обеспечивается периодичность в 90 дней между успешными пользовательскими развертываниями.</span><span class="sxs-lookup"><span data-stu-id="18f7a-165">The result is a 90-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="18f7a-166">Недостатком этой стратегии развертывания является возможная продолжительность полного развертывания базовой инфраструктуры Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="18f7a-166">The disadvantage to this deployment strategy is that it can take a long time to fully deploy the Microsoft 365 Enterprise foundation infrastructure.</span></span>

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a><span data-ttu-id="18f7a-167">Параллельное развертывание без перекрытия пользовательского развертывания (параллельное 1)</span><span class="sxs-lookup"><span data-stu-id="18f7a-167">Parallel deployment with non-overlapping user rollout (Parallel 1)</span></span>

<span data-ttu-id="18f7a-p116">При этой стратегии пилотное развертывание следующего этапа начинается на последнем шаге пользовательского развертывания текущего этапа. Ниже представлено развертывание этапов 2–6 при выполнении пилотного развертывания во время завершения пользовательского развертывания предыдущего этапа.</span><span class="sxs-lookup"><span data-stu-id="18f7a-p116">For this deployment strategy, you start the pilot rollout of the next phase during the last part of the user rollout of the current phase. Here is the deployment of phases 2-6 when the pilot rollout occurs as the user rollout of the previous phase is wrapping up.</span></span>

<span data-ttu-id="18f7a-170">Ниже приведено упрощенное сравнение стратегий параллельного и последовательного развертывания.</span><span class="sxs-lookup"><span data-stu-id="18f7a-170">Here is a simplified comparison between parallel and serial deployment strategies.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
<span data-ttu-id="18f7a-p117">Итоговым результатом является завершение в организации пользовательского развертывания текущего этапа до начала следующего. Пользователи, не участвующие в пилотных развертываниях, не сталкиваются с одновременным развертыванием нескольких этапов, но пилотные развертывания выполняются параллельно с пользовательскими.</span><span class="sxs-lookup"><span data-stu-id="18f7a-p117">The end result is that user rollout for the current phase completes across your organization before the next one starts. Users that are not in pilot rollouts are not dealing with the rollouts of multiple phases at the same time, but pilot rollouts are done in parallel with user rollouts.</span></span>

<span data-ttu-id="18f7a-173">Упрощенный пример опыта пилотного пользователя:</span><span class="sxs-lookup"><span data-stu-id="18f7a-173">Simplified example pilot user experience:</span></span> 

- <span data-ttu-id="18f7a-p118">В декабре пользователю нужно использовать свой смартфон для многофакторной проверки подлинности. (Удостоверение)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p118">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="18f7a-p119">В феврале на компьютере пользователя с Windows 8.1 устанавливается Windows 10 Корпоративная. (Windows 10 Корпоративная)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p119">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="18f7a-p120">В апреле для пользователя устанавливается Office 365 профессиональный плюс, заменяющий Office 2013. (Office 365 профессиональный плюс)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p120">In April, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="18f7a-p121">В июне выполняется развертывание устройства и применение политик приложения и условного доступа. (Управление мобильными устройствами)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p121">In June, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="18f7a-p122">В августе для пользователя устанавливается клиент Azure Information Protection и он проходит обучение по применению меток к документам. (Защита информации)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p122">In August, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="18f7a-184">В результате обеспечивается периодичность в 60 дней между успешными пилотными развертываниями.</span><span class="sxs-lookup"><span data-stu-id="18f7a-184">The result is a 60-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="18f7a-185">Упрощенный пример опыта конечного пользователя:</span><span class="sxs-lookup"><span data-stu-id="18f7a-185">Simplified example end-user experience:</span></span>

- <span data-ttu-id="18f7a-p123">В январе пользователю нужно использовать свой смартфон для многофакторной проверки подлинности. (Удостоверение)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p123">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="18f7a-p124">В марте на компьютере пользователя с Windows 8.1 устанавливается Windows 10 Корпоративная. (Windows 10 Корпоративная)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p124">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="18f7a-p125">В мае для пользователя устанавливается Office 365 профессиональный плюс, заменяющий Office 2013. (Office 365 профессиональный плюс)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p125">In May, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="18f7a-p126">В июле выполняется развертывание устройства и применение политик приложения и условного доступа. (Управление мобильными устройствами)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p126">In July, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="18f7a-p127">В сентябре для пользователя устанавливается клиент Azure Information Protection и он проходит обучение по применению меток к документам. (Защита информации)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p127">In September, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="18f7a-196">В результате обеспечивается периодичность в 60 дней между успешными пользовательскими развертываниями.</span><span class="sxs-lookup"><span data-stu-id="18f7a-196">The result is a 60-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="18f7a-197">Преимущество этой стратегии развертывания заключается в возможности быстрее выполнить полное развертывание базовой инфраструктуры Microsoft 365 корпоративный без необходимости ИТ-отделу и пользователям сталкиваться с несколькими развертываниями одновременно.</span><span class="sxs-lookup"><span data-stu-id="18f7a-197">The advantage to this deployment strategy is that it can take less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, without having your IT department and users deal with multiple rollouts the same time.</span></span>

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a><span data-ttu-id="18f7a-198">Параллельное развертывание с перекрытием пользовательского развертывания (параллельное 2)</span><span class="sxs-lookup"><span data-stu-id="18f7a-198">Parallel deployment with overlapping user rollout (Parallel 2)</span></span>

<span data-ttu-id="18f7a-199">При этой стратегия развертывания вы начинаете:</span><span class="sxs-lookup"><span data-stu-id="18f7a-199">For this deployment strategy, you start the:</span></span>

- <span data-ttu-id="18f7a-200">пилотное развертывание следующего этапа во время последней части пользовательского развертывания текущего этапа.</span><span class="sxs-lookup"><span data-stu-id="18f7a-200">Pilot rollout of the next phase during the last part of the user rollout of the current phase.</span></span>
- <span data-ttu-id="18f7a-p128">пользовательское развертывание следующего этапа во время пользовательского развертывания текущего этапа таким образом, что пользователям не приходится сталкиваться одновременным развертыванием нескольких этапов. Предполагается, что развертывание каждого этапа базовой инфраструктуры выполняется аналогично (по областям, отделам или другим единицам).</span><span class="sxs-lookup"><span data-stu-id="18f7a-p128">User rollout of the next phase during the user rollout of the current phase in such a way that no user is dealing with the rollouts of multiple phases at the same time. This assumes that you are rolling out each phase of the foundation infrastructure in the same way, via regions, departments, or other.</span></span>

<span data-ttu-id="18f7a-203">Ниже приведено упрощенное сравнение разных стратегий развертывания.</span><span class="sxs-lookup"><span data-stu-id="18f7a-203">Here is a simplified comparison between the different deployment strategies.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

<span data-ttu-id="18f7a-204">Итоговый результат:</span><span class="sxs-lookup"><span data-stu-id="18f7a-204">The end result is that:</span></span>

- <span data-ttu-id="18f7a-205">Переход пилотных развертываний с одного этапа на следующий выполняется без задержек.</span><span class="sxs-lookup"><span data-stu-id="18f7a-205">Pilot rollouts go from one phase to the next without a pause.</span></span>
- <span data-ttu-id="18f7a-206">Пользовательское развертывание для этапа начинается до завершения пользовательского развертывания предыдущего этапа, но отдельные пользователи не выполняют одновременное развертывание нескольких этапов.</span><span class="sxs-lookup"><span data-stu-id="18f7a-206">The user rollout for a phase begins before the completion of the user rollout of the previous phase, but no individual user is rolling out more than one phase at a time.</span></span>

<span data-ttu-id="18f7a-207">Упрощенный пример опыта пилотного пользователя:</span><span class="sxs-lookup"><span data-stu-id="18f7a-207">Simplified example pilot user experience:</span></span> 

- <span data-ttu-id="18f7a-p129">В декабре пользователю нужно использовать свой смартфон для многофакторной проверки подлинности. (Удостоверение)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p129">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="18f7a-p130">В январе на компьютере пользователя с Windows 8.1 устанавливается Windows 10 Корпоративная. (Windows 10 Корпоративная)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p130">In January, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="18f7a-p131">В феврале для пользователя устанавливается Office 365 профессиональный плюс, заменяющий Office 2013. (Office 365 профессиональный плюс)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p131">In February, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="18f7a-p132">В марте выполняется развертывание устройства и применение политик приложения и условного доступа. (Управление мобильными устройствами)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p132">In March, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="18f7a-p133">В апреле для пользователя устанавливается клиент Azure Information Protection и он проходит обучение по применению меток к документам. (Защита информации)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p133">In April, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="18f7a-218">В результате обеспечивается периодичность в 30 дней между успешными пилотными развертываниями.</span><span class="sxs-lookup"><span data-stu-id="18f7a-218">The result is a 30-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="18f7a-219">Упрощенный пример опыта конечного пользователя:</span><span class="sxs-lookup"><span data-stu-id="18f7a-219">Simplified example end-user experience:</span></span>

- <span data-ttu-id="18f7a-p134">В январе пользователю нужно использовать свой смартфон для многофакторной проверки подлинности. (Удостоверение)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p134">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="18f7a-p135">В феврале на компьютере пользователя с Windows 8.1 устанавливается Windows 10 Корпоративная. (Windows 10 Корпоративная)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p135">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="18f7a-p136">В марте для пользователя устанавливается Office 365 профессиональный плюс, заменяющий Office 2013. (Office 365 профессиональный плюс)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p136">In March, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="18f7a-p137">В апреле выполняется развертывание устройства и применение политик приложения и условного доступа. (Управление мобильными устройствами)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p137">In April, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="18f7a-p138">В мае для пользователя устанавливается клиент Azure Information Protection и он проходит обучение по применению меток к документам. (Защита информации)</span><span class="sxs-lookup"><span data-stu-id="18f7a-p138">In May, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="18f7a-230">В результате обеспечивается периодичность в 30 дней между успешными пользовательскими развертываниями.</span><span class="sxs-lookup"><span data-stu-id="18f7a-230">The result is a 30-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="18f7a-p139">Преимущество этой стратегии развертывания заключается в возможности еще быстрее выполнить полное развертывание базовой инфраструктуры Microsoft 365 корпоративный без необходимости отдельным пользователям сталкиваться с несколькими развертываниями одновременно. Но для пользователей отсутствует перерыв между успешно выполненными этапами.</span><span class="sxs-lookup"><span data-stu-id="18f7a-p139">The advantage to this deployment strategy is that it can take even less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, still without having individual users deal with multiple rollouts the same time. However, users don’t get a break between successive phases.</span></span>

### <a name="up-front-infrastructure-and-rollout-of-end-to-end-configuration"></a><span data-ttu-id="18f7a-233">Предварительная настройка инфраструктуры и внедрение комплексной настройки</span><span class="sxs-lookup"><span data-stu-id="18f7a-233">Up-front infrastructure and rollout of end-to-end configuration</span></span>

<span data-ttu-id="18f7a-234">Для небольших организаций с возможностью сжатия этапов 2–6 в один сегмент развертывания итоговое развертывание выглядит представленным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="18f7a-234">For smaller organizations with the ability to compress phases 2-6 into a single deployment segment, the resulting deployment looks like this:</span></span>
 
![](./media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

<span data-ttu-id="18f7a-p140">ИТ-отдел настраивает инфраструктуру для этапов 2–6, а затем развертывает ее для пилотных пользователей, чтобы проверить комплексные функции. Например, пилотные пользователи получают все эти функциональные возможности одновременно:</span><span class="sxs-lookup"><span data-stu-id="18f7a-p140">The IT department configures the infrastructure for phases 2-6, then rolls out to the pilot users to check for the end-to-end functionality. For example, pilot users get all of this functionality at the same time:</span></span>

- <span data-ttu-id="18f7a-237">многофакторная проверка подлинности и другие функции удостоверений (удостоверение);</span><span class="sxs-lookup"><span data-stu-id="18f7a-237">MFA and other identity features (Identity)</span></span>
- <span data-ttu-id="18f7a-238">Windows 10 Корпоративная на устройствах с Windows (Windows 10 Корпоративная);</span><span class="sxs-lookup"><span data-stu-id="18f7a-238">Windows 10 Enterprise on Windows devices (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="18f7a-239">Office 365 профессиональный плюс для набора Office (Office 365 профессиональный плюс);</span><span class="sxs-lookup"><span data-stu-id="18f7a-239">Office 365 ProPlus for the Office suite (Office 365 ProPlus)</span></span>
- <span data-ttu-id="18f7a-240">политики приложения и условного доступа (управление мобильными устройствами);</span><span class="sxs-lookup"><span data-stu-id="18f7a-240">App and conditional access policies (Mobile device management)</span></span>
- <span data-ttu-id="18f7a-241">установленный клиент Azure Information Protection и обучение по применению меток к документам (защита информации).</span><span class="sxs-lookup"><span data-stu-id="18f7a-241">Azure Information Protection client installed and training on how to apply labels to documents (Information protection)</span></span>

<span data-ttu-id="18f7a-242">После завершения пилотного развертывания начинается пользовательское развертывание, при котором пользователь получает все функциональные возможности одновременно.</span><span class="sxs-lookup"><span data-stu-id="18f7a-242">Once the pilot rollout is concluded, the user rollout begins in which each user gets all the functionality the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="18f7a-243">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="18f7a-243">Next step</span></span>

<span data-ttu-id="18f7a-244">Начните развертывание Microsoft 365 корпоративный в [базовой инфраструктуре](deploy-foundation-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="18f7a-244">Start your deployment of Microsoft 365 Enterprise with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
