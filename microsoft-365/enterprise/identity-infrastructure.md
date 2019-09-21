---
title: Этап 2. Идентификация
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как развернуть инфраструктуру идентификации для Microsoft 365 корпоративный.
ms.openlocfilehash: 2d9ffcc5122b5a5dfc94fb007167655e879d6799
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071698"
---
# <a name="phase-2-identity"></a><span data-ttu-id="582ae-103">Этап 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="582ae-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="582ae-104">В Microsoft 365 корпоративный хорошо спланированная и реализованная инфраструктура идентификации позволяет усилить защиту и предоставлять доступ к рабочим нагрузкам и их данным только пользователям и устройствам, прошедшим проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="582ae-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="582ae-105">Просмотрите это видео с обзором моделей удостоверений и проверки подлинности для Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="582ae-105">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="582ae-106"><p> </p></span><span class="sxs-lookup"><span data-stu-id="582ae-106"></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="582ae-107">Если вы уже развернули инфраструктуру идентификации, см. перечень обязательных и необязательных [условий](identity-exit-criteria.md), при выполнении которых можно считать инфраструктуру идентификации для Microsoft 365 корпоративный настроенной.</span><span class="sxs-lookup"><span data-stu-id="582ae-107">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="582ae-108">Сведения о функциях удостоверений для каждого плана Microsoft 365 корпоративный, роли Azure Active Directory (Azure AD), локальных и облачных компонентах, а также самых распространенных настройках проверки подлинности см. на [плакате инфраструктуры удостоверений](media/identity-infrastructure/M365E-ID-Infra.pdf).</span><span class="sxs-lookup"><span data-stu-id="582ae-108">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="582ae-109">[![Плакат инфраструктуры удостоверений](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="582ae-109">[![The Identity Infrastructure poster](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="582ae-110">Эту двухстраничный плакат позволяет быстро ознакомиться с основными понятиями и настройками Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="582ae-110">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="582ae-111">Вы также можете [скачать этот плакат](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) и распечатать его в формате письма, юридического документа или газетном формате (11 х 17).</span><span class="sxs-lookup"><span data-stu-id="582ae-111">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="582ae-112">Планирование и развертывание инфраструктуры идентификации Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="582ae-112">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="582ae-p101">Выполните указанные ниже шаги, чтобы спланировать и развернуть новую инфраструктуру идентификации в облаке. Кроме того, с помощью этих шагов можно адаптировать имеющуюся у вас локальную или гибридную инфраструктуру идентификации для работы с Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="582ae-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="582ae-115">Создание и защита учетных записей глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="582ae-115">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="582ae-116">Защита паролей</span><span class="sxs-lookup"><span data-stu-id="582ae-116">Secure your passwords</span></span>](identity-secure-your-passwords.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="582ae-117">Защита пользовательских входов и управление ими</span><span class="sxs-lookup"><span data-stu-id="582ae-117">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="582ae-118">Добавление учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="582ae-118">Add your user accounts</span></span>](identity-add-user-accounts.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="582ae-119">Управление с помощью групп</span><span class="sxs-lookup"><span data-stu-id="582ae-119">Use groups for easier management</span></span>](identity-use-group-management.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="582ae-120">Настройка управления удостоверениями</span><span class="sxs-lookup"><span data-stu-id="582ae-120">Configure identity governance</span></span>](identity-configure-identity-governance.md) |

<span data-ttu-id="582ae-121">Выполнив эти шаги, перейдите к перечню обязательных и необязательных [условий](identity-exit-criteria.md) для соответствия требованиям к удостоверениям Microsoft 365 корпоративный, при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="582ae-121">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="582ae-122">Рекомендации по доступу для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="582ae-122">Identity and device access recommendations</span></span>

<span data-ttu-id="582ae-p102">Корпорация Майкрософт предоставляет набор рекомендаций по [доступу для удостоверений и устройств ](microsoft-365-policies-configurations.md), обеспечивая тем самым безопасность и эффективность рабочих ресурсов. Для работы с удостоверениями вместе с действиями, указанными на этом этапе, используйте рекомендации и параметры, изложенные в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="582ae-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="582ae-125">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="582ae-125">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="582ae-126">Основные политики доступа для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="582ae-126">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="582ae-127">Как корпорация Майкрософт реализует Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="582ae-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="582ae-128">Узнайте, как ИТ-специалисты в корпорации Майкрософт [управляют удостоверениями и обеспечивают безопасный доступ](https://www.microsoft.com/ru-RU/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span><span class="sxs-lookup"><span data-stu-id="582ae-128">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/ru-RU/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="582ae-129">Как корпорация Contoso реализовала Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="582ae-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="582ae-130">Посмотрите, как Contoso, вымышленная, но типичная многонациональная корпорация, [развернула инфраструктуру гибридных удостоверений](contoso-identity.md) для облачных служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="582ae-130">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="582ae-131">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="582ae-131">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="582ae-132">Создание и защита учетных записей глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="582ae-132">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
