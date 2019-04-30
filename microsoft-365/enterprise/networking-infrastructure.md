---
title: Шаг 1. Сетевая инфраструктура для Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как развернуть сетевую инфраструктуру для Microsoft 365 корпоративный.
ms.openlocfilehash: 9b8c23d543eca97147801d70e42de7105266c52d
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "33399963"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="cc6ee-103">Шаг 1. Сетевая инфраструктура для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="cc6ee-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="cc6ee-104">Microsoft 365 корпоративный включает Office 365 и Microsoft Intune в составе Enterprise Management + Security (EMS).</span><span class="sxs-lookup"><span data-stu-id="cc6ee-104">Microsoft 365 Enterprise includes Office 365 and Microsoft Intune as part of Enterprise Management + Security (EMS).</span></span> <span data-ttu-id="cc6ee-105">Для обеих этих облачных служб используются безопасные, производительные и надежные подключения с клиентских устройств через Интернет или выделенные каналы.</span><span class="sxs-lookup"><span data-stu-id="cc6ee-105">Both of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="cc6ee-106">Чтобы разместить эти службы и сделать их доступными клиентам по всему миру, корпорация Майкрософт разработала сетевую инфраструктуру, в которой основное внимание уделено производительности и интеграции.</span><span class="sxs-lookup"><span data-stu-id="cc6ee-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="cc6ee-p102">На этом шаге вы постепенно рассмотрите ключевые вопросы создания производительного подключения к облачным службам Microsoft 365 корпоративный. Общие сведения см. в статье [Принципы работы сети Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span><span class="sxs-lookup"><span data-stu-id="cc6ee-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="cc6ee-109">Если вы уже развернули сетевую инфраструктуру, см. перечень обязательных и необязательных [условий](networking-exit-criteria.md), при выполнении которых можно считать сетевую инфраструктуру для Microsoft 365 корпоративный настроенной.</span><span class="sxs-lookup"><span data-stu-id="cc6ee-109">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="cc6ee-110">Планирование и развертывание сетевой инфраструктуры Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="cc6ee-110">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="cc6ee-111">Чтобы создать свою сетевую инфраструктуру, соответствующую требованиям Microsoft 365 корпоративный, выполните указанные ниже шаги.</span><span class="sxs-lookup"><span data-stu-id="cc6ee-111">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="cc6ee-112">Подготовка сети к Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc6ee-112">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="cc6ee-113">Настройка локальных подключений к Интернету для всех офисов</span><span class="sxs-lookup"><span data-stu-id="cc6ee-113">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="cc6ee-114">Удаление разворотов пакетов</span><span class="sxs-lookup"><span data-stu-id="cc6ee-114">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="cc6ee-115">Настройка обхода трафика</span><span class="sxs-lookup"><span data-stu-id="cc6ee-115">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="cc6ee-116">Оптимизация производительности клиентов и служб Office 365</span><span class="sxs-lookup"><span data-stu-id="cc6ee-116">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="cc6ee-117">Выполнив эти шаги, перейдите к перечню обязательных и необязательных [условий](networking-exit-criteria.md) для соответствия требованиям Microsoft 365 корпоративный, при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="cc6ee-117">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="cc6ee-118">Как корпорация Майкрософт реализует Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="cc6ee-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="cc6ee-119">Загляните в корпорацию Майкрософт и узнайте, как компания подготовила и оптимизировала сеть Майкрософт для облачных служб Office 365, в этом вам поможет статья [Оптимизация производительности сети для Microsoft Office 365](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).</span><span class="sxs-lookup"><span data-stu-id="cc6ee-119">Peek inside Microsoft and learn how the company prepared for and optimized the Microsoft network for the Office 365 cloud services with [Optimizing network performance for Microsoft Office 365](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="cc6ee-120">Как корпорация Contoso реализовала Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="cc6ee-120">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="cc6ee-121">Посмотрите, как корпорация Contoso, вымышленная многонациональная компания, [оптимизировала свою сеть](contoso-networking.md) для облачных служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cc6ee-121">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="cc6ee-122">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="cc6ee-122">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="cc6ee-123">Подготовка сети к Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc6ee-123">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

