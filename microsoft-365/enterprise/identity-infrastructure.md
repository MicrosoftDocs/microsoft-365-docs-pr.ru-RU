---
title: Шаг 2. Идентификация
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как развернуть инфраструктуру идентификации для Microsoft 365 корпоративный.
ms.openlocfilehash: 07f95a249912826b80e0654cac4063b3d5763267
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981958"
---
# <a name="phase-2-identity"></a><span data-ttu-id="118bc-103">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="118bc-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="118bc-104">В Microsoft 365 корпоративный хорошо спланированная и реализованная инфраструктура идентификации позволяет усилить защиту и предоставлять доступ к рабочим нагрузкам и их данным только пользователям и устройствам, прошедшим проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="118bc-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="118bc-105">Просмотрите это видео с обзором моделей удостоверений и проверки подлинности для Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="118bc-105">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="118bc-106">Если вы уже развернули инфраструктуру идентификации, см. перечень обязательных и необязательных [условий](identity-exit-criteria.md), при выполнении которых можно считать инфраструктуру идентификации для Microsoft 365 корпоративный настроенной.</span><span class="sxs-lookup"><span data-stu-id="118bc-106">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="118bc-107">Сведения о функциях удостоверений для каждого плана Microsoft 365 корпоративный, роли Azure Active Directory (Azure AD), локальных и облачных компонентах, а также самых распространенных настройках проверки подлинности см. на [плакате инфраструктуры удостоверений](media/identity-infrastructure/M365E-ID-Infra.pdf).</span><span class="sxs-lookup"><span data-stu-id="118bc-107">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="118bc-108">[![Плакат инфраструктуры удостоверений](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="118bc-108">[![The Identity Infrastructure poster](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="118bc-109">Эту двухстраничный плакат позволяет быстро ознакомиться с основными понятиями и настройками Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="118bc-109">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="118bc-110">Вы также можете [скачать этот плакат](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) и распечатать его в формате письма, юридического документа или газетном формате (11 х 17).</span><span class="sxs-lookup"><span data-stu-id="118bc-110">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="118bc-111">Планирование и развертывание инфраструктуры идентификации Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="118bc-111">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="118bc-p101">Выполните указанные ниже шаги, чтобы спланировать и развернуть новую инфраструктуру идентификации в облаке. Кроме того, с помощью этих шагов можно адаптировать имеющуюся у вас локальную или гибридную инфраструктуру идентификации для работы с Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="118bc-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="118bc-114">Планирование пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="118bc-114">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="118bc-115">Защита привилегированных удостоверений</span><span class="sxs-lookup"><span data-stu-id="118bc-115">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="118bc-116">Настройка гибридного удостоверения</span><span class="sxs-lookup"><span data-stu-id="118bc-116">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="118bc-117">Настройка безопасной проверки подлинности пользователей</span><span class="sxs-lookup"><span data-stu-id="118bc-117">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="118bc-118">Упрощение доступа для пользователей</span><span class="sxs-lookup"><span data-stu-id="118bc-118">Simplify access for users</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="118bc-119">Упрощение управления с помощью групп</span><span class="sxs-lookup"><span data-stu-id="118bc-119">Use groups for easier management</span></span>](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="118bc-120">Настройка управления удостоверениями</span><span class="sxs-lookup"><span data-stu-id="118bc-120">Configure identity governance</span></span>](identity-governance.md) |

<span data-ttu-id="118bc-121">Выполнив эти шаги, перейдите к перечню обязательных и необязательных [условий](identity-exit-criteria.md) для соответствия требованиям к удостоверениям Microsoft 365 корпоративный, при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="118bc-121">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="118bc-122">Рекомендации по доступу для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="118bc-122">Identity and device access recommendations</span></span>

<span data-ttu-id="118bc-p102">Корпорация Майкрософт предоставляет набор рекомендаций по [доступу для удостоверений и устройств ](microsoft-365-policies-configurations.md), обеспечивая тем самым безопасность и эффективность рабочих ресурсов. Для работы с удостоверениями вместе с действиями, указанными на этом этапе, используйте рекомендации и параметры, изложенные в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="118bc-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="118bc-125">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="118bc-125">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="118bc-126">Основные политики доступа для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="118bc-126">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="118bc-127">Как корпорация Майкрософт реализует Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="118bc-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="118bc-128">Узнайте, как ИТ-специалисты в корпорации Майкрософт [управляют удостоверениями и обеспечивают безопасный доступ](https://www.microsoft.com/ru-RU/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span><span class="sxs-lookup"><span data-stu-id="118bc-128">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/ru-RU/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="118bc-129">Как корпорация Contoso реализовала Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="118bc-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="118bc-130">Посмотрите, как Contoso, вымышленная, но типичная многонациональная корпорация, [развернула инфраструктуру гибридных удостоверений](contoso-identity.md) для облачных служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="118bc-130">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="118bc-131">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="118bc-131">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="118bc-132">Планирование пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="118bc-132">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
