---
title: Шаг 2. Идентификация
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как развернуть инфраструктуру идентификации для Microsoft 365 корпоративный.
ms.openlocfilehash: 7b5d62f5c09a1ea6d46449b113bff59dbf07ebad
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870844"
---
# <a name="phase-2-identity"></a><span data-ttu-id="5b59a-103">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="5b59a-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="5b59a-104">В Microsoft 365 корпоративный хорошо спланированная и реализованная инфраструктура идентификации позволяет усилить защиту и предоставлять доступ к рабочим нагрузкам и их данным только пользователям и устройствам, прошедшим проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="5b59a-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

>[!Note]
><span data-ttu-id="5b59a-105">Если вы уже развернули инфраструктуру идентификации, см. перечень обязательных и необязательных [условий](identity-exit-criteria.md), при выполнении которых можно считать инфраструктуру идентификации для Microsoft 365 корпоративный настроенной.</span><span class="sxs-lookup"><span data-stu-id="5b59a-105">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="5b59a-106">Планирование и развертывание инфраструктуры идентификации Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="5b59a-106">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="5b59a-p101">Выполните указанные ниже шаги, чтобы спланировать и развернуть новую инфраструктуру идентификации в облаке. Кроме того, с помощью этих шагов можно адаптировать имеющуюся у вас локальную или гибридную инфраструктуру идентификации для работы с Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="5b59a-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="5b59a-109">Планирование пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="5b59a-109">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="5b59a-110">Защита учетных записей глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="5b59a-110">Protect global administrator accounts</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="5b59a-111">Настройка глобальных администраторов по требованию</span><span class="sxs-lookup"><span data-stu-id="5b59a-111">Set up on-demand global administrators</span></span>](identity-privileged-identity-management.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="5b59a-112">Упрощение процедуры сброса паролей</span><span class="sxs-lookup"><span data-stu-id="5b59a-112">Simplify password resets</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="5b59a-113">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="5b59a-113">Set up multi-factor authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="5b59a-114">Защита от компрометации учетных данных</span><span class="sxs-lookup"><span data-stu-id="5b59a-114">Protect against credential compromise</span></span>](identity-azure-ad-identity-protection.md) |
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="5b59a-115">Синхронизация каталогов</span><span class="sxs-lookup"><span data-stu-id="5b59a-115">Synchronize directories</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step8.png)| [<span data-ttu-id="5b59a-116">Отслеживание работоспособности функции синхронизации</span><span class="sxs-lookup"><span data-stu-id="5b59a-116">Monitor synchronization health</span></span>](identity-azure-ad-connect-health.md) |
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="5b59a-117">Упрощение процедуры обновления паролей</span><span class="sxs-lookup"><span data-stu-id="5b59a-117">Simplify password updates</span></span>](identity-password-writeback.md) |
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="5b59a-118">Упрощение входа в систему для пользователей</span><span class="sxs-lookup"><span data-stu-id="5b59a-118">Simplify user sign-in</span></span>](identity-single-sign-on.md) |
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="5b59a-119">Настройка страницы входа в Office 365</span><span class="sxs-lookup"><span data-stu-id="5b59a-119">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |
|![](./media/stepnumbers/Step12.png)| [<span data-ttu-id="5b59a-120">Настройка автоматического лицензирования</span><span class="sxs-lookup"><span data-stu-id="5b59a-120">Set up automatic licensing</span></span>](identity-group-based-licensing.md) |
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="5b59a-121">Отслеживание действий в клиенте и при входе в систему</span><span class="sxs-lookup"><span data-stu-id="5b59a-121">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="5b59a-122">Разрешение пользователям создавать собственные группы и управлять ими</span><span class="sxs-lookup"><span data-stu-id="5b59a-122">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step15.png)| [<span data-ttu-id="5b59a-123">Настройка динамического членства в группах</span><span class="sxs-lookup"><span data-stu-id="5b59a-123">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |

<span data-ttu-id="5b59a-124">Выполнив эти шаги, перейдите к перечню обязательных и необязательных [условий](identity-exit-criteria.md) для соответствия требованиям Microsoft 365 корпоративный, при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="5b59a-124">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="5b59a-125">Рекомендации по доступу для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="5b59a-125">Identity and device access prerequisites</span></span>

<span data-ttu-id="5b59a-p102">Корпорация Майкрософт предоставляет набор рекомендаций по [доступу для удостоверений и устройств ](microsoft-365-policies-configurations.md), обеспечивая тем самым безопасность и эффективность рабочих ресурсов. Для работы с удостоверениями вместе с действиями, указанными на этом этапе, используйте рекомендации и параметры, изложенные в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="5b59a-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="5b59a-128">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="5b59a-128">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="5b59a-129">Основные политики доступа для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="5b59a-129">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="5b59a-130">Как корпорация Майкрософт реализует Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="5b59a-130">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="5b59a-131">Узнайте, как ИТ-специалисты корпорации Майкрософт спланировали и развернули возможности работы с удостоверениями в Microsoft 365 корпоративный, из следующих ресурсов:</span><span class="sxs-lookup"><span data-stu-id="5b59a-131">Learn how IT experts at Microsoft planned for and deployed the identity capabilities of Microsoft 365 Enterprise with these resources:</span></span>

- [<span data-ttu-id="5b59a-132">Управление удостоверениями пользователей и защита доступа в корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5b59a-132">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="5b59a-133">Использование Azure AD Privileged Identity Management для повышения прав доступа</span><span class="sxs-lookup"><span data-stu-id="5b59a-133">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="5b59a-134">Как корпорация Contoso реализовала Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="5b59a-134">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="5b59a-135">Посмотрите, как Contoso, вымышленная, но типичная многонациональная корпорация, [развернула инфраструктуру гибридных удостоверений](contoso-identity.md) для облачных служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5b59a-135">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="5b59a-136">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="5b59a-136">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="5b59a-137">Планирование пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="5b59a-137">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
