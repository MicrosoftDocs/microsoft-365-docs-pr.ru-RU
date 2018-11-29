---
title: Развертывание Microsoft 365 корпоративный в существующей инфраструктуре
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/04/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Если у вас уже есть инфраструктура, проверьте условия, необходимые для развертывания Microsoft 365 корпоративный.
ms.openlocfilehash: 6ade8282e72d18dac78f08ce386dbdf102184ebe
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870427"
---
# <a name="deployment-of-microsoft-365-enterprise-with-existing-infrastructure"></a><span data-ttu-id="2c24b-103">Развертывание Microsoft 365 корпоративный в существующей инфраструктуре</span><span class="sxs-lookup"><span data-stu-id="2c24b-103">Deployment of Microsoft 365 Enterprise with existing infrastructure</span></span>

<span data-ttu-id="2c24b-p101">У многих организаций имеются компоненты сети, идентификации и другие компоненты либо локальные продукты Майкрософт и облачные службы. В этой статье пошагово описан каждый этап развертывания Microsoft 365 корпоративный, чтобы вы могли быстро определить, как адаптировать или изменить имеющуюся у вас инфраструктуру.</span><span class="sxs-lookup"><span data-stu-id="2c24b-p101">Many organizations have exisiting networking, identity, and other components or Microsoft on-premises products and cloud-based services. This article steps through each phase of the deployment of Microsoft 365 Enterprise so you can quickly determine how to adapt or change your existing infrastructure.</span></span>

<span data-ttu-id="2c24b-p102">Прежде чем завершить какой-либо шаг, вам необходимо проверить условия выполнения этого шага. Они представляют собой набор обязательных (которые вы должны выполнить) и необязательных (которые вы должны рассмотреть) требований. Выполнение соответствующих условий для каждого шага гарантирует соответствие вашей локальной и облачной инфраструктур и полученной в итоге сквозной конфигурации требованиям для развертывания Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="2c24b-p102">Before you can exit each phase, you must examine its exit criteria, which is a set of required conditions that you must meet and optional conditions to consider. Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meets the requirements for a Microsoft 365 Enterprise deployment.</span></span>

> [!Note] 
> <span data-ttu-id="2c24b-p103">FastTrack — это преимущество, которым можно воспользоваться в любой момент и не один раз. Это средство доступно в рамках вашей подписки. Инженеры Корпорации Майкрософт создали его, чтобы упростить вам переход в облако удобным для вас способом. Кроме того, с помощью FastTrack вы можете получить доступ к дополнительным услугам наших квалифицированных партнеров (при необходимости). На данный момент у нас более 40 000 клиентов, и FastTrack помогает достичь им максимальной рентабельности инвестиций, ускорить развертывание и повысить степень внедрения необходимых технологий в организации. См. статью [FastTrack для Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span><span class="sxs-lookup"><span data-stu-id="2c24b-p103">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span>

## <a name="exit-criteria-for-networking-phase-1"></a><span data-ttu-id="2c24b-112">Условия, при выполнении которых можно считать сеть настроенной (шаг 1)</span><span class="sxs-lookup"><span data-stu-id="2c24b-112">Exit criteria for networking (phase 1)</span></span>

<span data-ttu-id="2c24b-113">Просмотрите перечисленные ниже обязательные и необязательные требования для сетевой инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="2c24b-113">Step through the following required and optional conditions for the networking infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for networking](./includes/deployment-exit-criteria-networking.md)]

## <a name="exit-criteria-for-identity-phase-2"></a><span data-ttu-id="2c24b-114">Условия, при выполнении которых можно считать инфраструктуру идентификации настроенной (шаг 2)</span><span class="sxs-lookup"><span data-stu-id="2c24b-114">Exit criteria for identity (phase 2)</span></span>

<span data-ttu-id="2c24b-115">Просмотрите перечисленные ниже обязательные и необязательные требования для инфраструктуры идентификации.</span><span class="sxs-lookup"><span data-stu-id="2c24b-115">Step through the following required and optional conditions for the identity infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for identity](./includes/deployment-exit-criteria-identity.md)]

## <a name="exit-criteria-for-windows-10-enterprise-phase-3"></a><span data-ttu-id="2c24b-116">Условия выхода для Windows 10 Корпоративная (шаг 3)</span><span class="sxs-lookup"><span data-stu-id="2c24b-116">Exit criteria for Windows 10 Enterprise (phase 3)</span></span>

<span data-ttu-id="2c24b-117">Просмотрите перечисленные ниже обязательные и необязательные требования для инфраструктуры Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="2c24b-117">Step through the following required and optional conditions for the Windows 10 Enterprise infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for identity](./includes/deployment-exit-criteria-windows10.md)]

## <a name="exit-criteria-for-office-365-proplus-phase-4"></a><span data-ttu-id="2c24b-118">Условия, при выполнении которых можно считать Office 365 профессиональный плюс настроенным (шаг 4)</span><span class="sxs-lookup"><span data-stu-id="2c24b-118">Exit criteria for Office 365 ProPlus (phase 4)</span></span>

<span data-ttu-id="2c24b-119">Обеспечьте соответствие требованиям для планирования развертывания, оценки, а также развертывания инфраструктуры Office 365 профессиональный плюс для Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="2c24b-119">Meet the requirements for assessment, deployment planning, and deployment of the Office 365 ProPlus infrastructure for Microsoft 365 Enterprise.</span></span>

[!INCLUDE [Deployment exit criteria for Office 365 ProPlus](./includes/deployment-exit-criteria-office365proplus.md)]

## <a name="exit-criteria-for-mobile-device-management-phase-5"></a><span data-ttu-id="2c24b-120">Условия, при выполнении которых можно считать управление мобильными устройствами настроенным (шаг 5)</span><span class="sxs-lookup"><span data-stu-id="2c24b-120">Exit criteria for mobile device management (phase 5)</span></span>

<span data-ttu-id="2c24b-121">Обеспечьте соответствие указанным ниже требованиям для инфраструктуры управления мобильными устройствами.</span><span class="sxs-lookup"><span data-stu-id="2c24b-121">Meet the following requirements for the mobile device management infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for mobile device management](./includes/deployment-exit-criteria-mobility.md)]

## <a name="exit-criteria-for-information-protection-phase-6"></a><span data-ttu-id="2c24b-122">Условия, при выполнении которых можно считать защиту информации настроенной (шаг 6)</span><span class="sxs-lookup"><span data-stu-id="2c24b-122">Exit criteria for information protection (phase 6)</span></span>

<span data-ttu-id="2c24b-123">Просмотрите перечисленные ниже обязательные и необязательные требования для инфраструктуры защиты информации.</span><span class="sxs-lookup"><span data-stu-id="2c24b-123">Step through the following required and optional conditions for the information protection infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for information protection](./includes/deployment-exit-criteria-infoprotect.md)]

