---
title: Шаг 1. Сетевая инфраструктура для Microsoft 365 корпоративный
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как развернуть сетевую инфраструктуру для Microsoft 365 корпоративный.
ms.openlocfilehash: 9a805ffbdbdc19ef5943a0c0ba0ff8f010d3e19b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066606"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="6444a-103">Шаг 1. Сетевая инфраструктура для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="6444a-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![Шаг 1. Сеть](../media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="6444a-105">Microsoft 365 корпоративный включает Office 365, Microsoft Intune и различные службы удостоверений и безопасности Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="6444a-105">Microsoft 365 Enterprise includes Office 365, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="6444a-106">Для всех этих облачных служб используются безопасные, производительные и надежные подключения с клиентских устройств через Интернет или выделенные каналы.</span><span class="sxs-lookup"><span data-stu-id="6444a-106">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="6444a-107">Чтобы разместить эти службы и сделать их доступными клиентам по всему миру, корпорация Майкрософт разработала сетевую инфраструктуру, в которой основное внимание уделено производительности и интеграции.</span><span class="sxs-lookup"><span data-stu-id="6444a-107">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="6444a-p102">На этом шаге вы постепенно рассмотрите ключевые вопросы создания производительного подключения к облачным службам Microsoft 365 корпоративный. Общие сведения см. в статье [Принципы работы сети Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span><span class="sxs-lookup"><span data-stu-id="6444a-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="6444a-110">Если вы уже развернули сетевую инфраструктуру, см. перечень обязательных и необязательных [условий](networking-exit-criteria.md), при выполнении которых можно считать сетевую инфраструктуру для Microsoft 365 корпоративный настроенной.</span><span class="sxs-lookup"><span data-stu-id="6444a-110">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="6444a-111">Планирование и развертывание сетевой инфраструктуры Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="6444a-111">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="6444a-112">Чтобы создать свою сетевую инфраструктуру, соответствующую требованиям Microsoft 365 корпоративный, выполните указанные ниже шаги.</span><span class="sxs-lookup"><span data-stu-id="6444a-112">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![Шаг 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="6444a-114">Подготовка сети к Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6444a-114">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![Шаг 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="6444a-116">Настройка локальных подключений к Интернету для всех офисов</span><span class="sxs-lookup"><span data-stu-id="6444a-116">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![Шаг 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="6444a-118">Удаление разворотов пакетов</span><span class="sxs-lookup"><span data-stu-id="6444a-118">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![Шаг 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="6444a-120">Настройка обхода трафика</span><span class="sxs-lookup"><span data-stu-id="6444a-120">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![Шаг 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="6444a-122">Оптимизация производительности клиентов и служб Office 365</span><span class="sxs-lookup"><span data-stu-id="6444a-122">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="6444a-123">Выполнив эти шаги, перейдите к перечню обязательных и необязательных [условий](networking-exit-criteria.md) для соответствия требованиям Microsoft 365 корпоративный, при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="6444a-123">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="6444a-124">Как корпорация Майкрософт реализует Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="6444a-124">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="6444a-125">Познакомьтесь ближе с Майкрософт и узнайте, как компания [оптимизировала сеть Майкрософт для облачных служб](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span><span class="sxs-lookup"><span data-stu-id="6444a-125">Peek inside Microsoft and learn how the company [optimized the Microsoft network for cloud services](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="6444a-126">Как корпорация Contoso реализовала Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="6444a-126">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="6444a-127">Посмотрите, как корпорация Contoso, вымышленная представительская многонациональная компания, [оптимизировала сетевые устройства и подключения к Интернету](contoso-networking.md) для облачных служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6444a-127">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Корпорация Contoso](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="6444a-129">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="6444a-129">Next step</span></span>

|||
|:-------|:-----|
|![Шаг 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="6444a-131">Подготовка сети к Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6444a-131">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

