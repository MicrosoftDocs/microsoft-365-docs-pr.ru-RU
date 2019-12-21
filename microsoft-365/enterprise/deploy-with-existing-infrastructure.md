---
title: Развертывание Microsoft 365 для предприятий в существующей инфраструктуре
ms.author: josephd
author: JoeDavies-MSFT
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
description: При наличии существующей инфраструктуры проверьте условия, необходимые для развертывания Microsoft 365 для предприятий.
ms.openlocfilehash: 1b3ed8edd84a1879f4cd46795fc55e3625a97be2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801934"
---
# <a name="deployment-of-microsoft-365-for-enterprise-with-existing-infrastructure"></a><span data-ttu-id="7a561-103">Развертывание Microsoft 365 для предприятий в существующей инфраструктуре</span><span class="sxs-lookup"><span data-stu-id="7a561-103">Deployment of Microsoft 365 Enterprise with existing infrastructure</span></span>

<span data-ttu-id="7a561-p101">У многих организаций имеются сети, удостоверения и другие компоненты либо локальные продукты Майкрософт и облачные службы. В этой статье пошагово описан каждый этап развертывания Microsoft 365 для предприятий, чтобы вы могли быстро определить, как адаптировать или изменить имеющуюся у вас инфраструктуру.</span><span class="sxs-lookup"><span data-stu-id="7a561-p101">Many organizations have existing networking, identity, and other components or Microsoft on-premises products and cloud-based services. This article steps through each phase of the deployment of Microsoft 365 Enterprise so you can quickly determine how to adapt or change your existing infrastructure.</span></span>

<span data-ttu-id="7a561-p102">Прежде чем завершить какой-либо шаг, вам необходимо проверить условия выполнения этого шага. Они представляют собой набор обязательных (которые вы должны выполнить) и необязательных (которые вы должны рассмотреть) требований. Выполнение соответствующих условий для каждого шага гарантирует соответствие вашей локальной и облачной инфраструктуры и полученной в итоге сквозной конфигурации требованиям для развертывания Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="7a561-p102">Before you can exit each phase, you must examine its exit criteria, which is a set of required conditions that you must meet and optional conditions to consider. Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meets the requirements for a Microsoft 365 Enterprise deployment.</span></span>

> [!Note] 
> <span data-ttu-id="7a561-p103">FastTrack — это преимущество, которым можно воспользоваться в любой момент и не один раз. Это средство бесплатно доступно в рамках вашей подписки. Инженеры корпорации Майкрософт создали его, чтобы упростить вам переход в облако удобным для вас способом. Кроме того, с помощью FastTrack вы можете получить доступ к дополнительным услугам наших квалифицированных партнеров (при необходимости). На данный момент у нас более 40 000 клиентов, и FastTrack помогает достичь им максимальной рентабельности инвестиций, ускорить развертывание и повысить степень внедрения необходимых технологий в организации. См. статью [FastTrack для Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span><span class="sxs-lookup"><span data-stu-id="7a561-p103">FastTrack is an ongoing and repeatable benefit—available for free as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span>

## <a name="exit-criteria-for-networking-phase-1"></a><span data-ttu-id="7a561-112">Условия, при выполнении которых можно считать сеть настроенной (шаг 1)</span><span class="sxs-lookup"><span data-stu-id="7a561-112">Exit criteria for networking (phase 1)</span></span>

<span data-ttu-id="7a561-113">Просмотрите перечисленные ниже обязательные и необязательные требования для сетевой инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="7a561-113">Step through the following required and optional conditions for your networking infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for networking](./includes/deployment-exit-criteria-networking.md)]

## <a name="exit-criteria-for-identity-phase-2"></a><span data-ttu-id="7a561-114">Условия, при выполнении которых можно считать инфраструктуру идентификации настроенной (шаг 2)</span><span class="sxs-lookup"><span data-stu-id="7a561-114">Exit criteria for identity (phase 2)</span></span>

<span data-ttu-id="7a561-115">Просмотрите перечисленные ниже обязательные и необязательные требования для инфраструктуры идентификации.</span><span class="sxs-lookup"><span data-stu-id="7a561-115">Step through the following required and optional conditions for your identity infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for identity](./includes/deployment-exit-criteria-identity.md)]

## <a name="exit-criteria-for-windows-10-enterprise-phase-3"></a><span data-ttu-id="7a561-116">Условия выхода для Windows 10 Корпоративная (шаг 3)</span><span class="sxs-lookup"><span data-stu-id="7a561-116">Exit criteria for Windows 10 Enterprise (phase 3)</span></span>

<span data-ttu-id="7a561-117">Просмотрите перечисленные ниже обязательные и необязательные требования для инфраструктуры Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="7a561-117">Step through the following required and optional conditions for your Windows 10 Enterprise infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for identity](./includes/deployment-exit-criteria-windows10.md)]

## <a name="exit-criteria-for-office-365-proplus-phase-4"></a><span data-ttu-id="7a561-118">Условия, при выполнении которых можно считать Office 365 профессиональный плюс настроенным (шаг 4)</span><span class="sxs-lookup"><span data-stu-id="7a561-118">Exit criteria for Office 365 ProPlus (phase 4)</span></span>

<span data-ttu-id="7a561-119">Обеспечьте соответствие требованиям для планирования развертывания, оценки, а также развертывания инфраструктуры Office 365 профессиональный плюс.</span><span class="sxs-lookup"><span data-stu-id="7a561-119">Meet the requirements for assessment, deployment planning, and deployment of your Office 365 ProPlus infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for Office 365 ProPlus](./includes/deployment-exit-criteria-office365proplus.md)]

## <a name="exit-criteria-for-mobile-device-management-phase-5"></a><span data-ttu-id="7a561-120">Условия, при выполнении которых можно считать управление мобильными устройствами настроенным (шаг 5)</span><span class="sxs-lookup"><span data-stu-id="7a561-120">Exit criteria for mobile device management (phase 5)</span></span>

<span data-ttu-id="7a561-121">Обеспечьте соответствие указанным ниже требованиям для инфраструктуры управления мобильными устройствами.</span><span class="sxs-lookup"><span data-stu-id="7a561-121">Meet the following requirements for your mobile device management infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for mobile device management](./includes/deployment-exit-criteria-mobility.md)]

## <a name="exit-criteria-for-information-protection-phase-6"></a><span data-ttu-id="7a561-122">Условия, при выполнении которых можно считать защиту информации настроенной (шаг 6)</span><span class="sxs-lookup"><span data-stu-id="7a561-122">Exit criteria for information protection (phase 6)</span></span>

<span data-ttu-id="7a561-123">Просмотрите перечисленные ниже обязательные и необязательные требования для инфраструктуры защиты информации.</span><span class="sxs-lookup"><span data-stu-id="7a561-123">Step through the following required and optional conditions for your information protection infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for information protection](./includes/deployment-exit-criteria-infoprotect.md)]

