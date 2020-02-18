---
title: Шаг 6. Information Protection
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как развернуть инфраструктуру Information Protection для Microsoft 365 корпоративный.
ms.openlocfilehash: 418506927885948cd917061d99bb69163b1e44a5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067153"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="4bda8-103">Этап 6. Защита данных</span><span class="sxs-lookup"><span data-stu-id="4bda8-103">Phase 6: Information protection</span></span>

![Этап 6. Защита данных](../media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="4bda8-p101">Information Protection — это набор политик и технологий, определяющих порядок передачи, хранения и обработки конфиденциальной информации. На этапе 6 вы постепенно настроите параметры и функции Information Protection в Microsoft 365 корпоративный, которые помогут защитить данные облачных рабочих нагрузок и сценариев.</span><span class="sxs-lookup"><span data-stu-id="4bda8-p101">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information. In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads and scenarios.</span></span>

>[!Note]
><span data-ttu-id="4bda8-107">Если вы уже развернули Information Protection, см. перечень обязательных и необязательных [условий](infoprotect-exit-criteria.md), при выполнении которых можно считать Information Protection для Microsoft 365 корпоративный настроенной.</span><span class="sxs-lookup"><span data-stu-id="4bda8-107">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="4bda8-108">В этом разделе рассказывается, как спланировать и развернуть инфраструктуру Information Protection для Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="4bda8-108">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="4bda8-p102">Совместно с юридическим отделом и отделом, отвечающим за соответствие требованиям в вашей организации, определите, необходимо ли вашей организации соблюдать какие-либо стандарты соответствия требованиям, например HIPPA, CJIS или GDPR. Кроме того, вам следует провести работу с группой обеспечения безопасности вашей организации и определить цели Information Protection для организации и ее отделов или групп, которым необходима дополнительная защита.</span><span class="sxs-lookup"><span data-stu-id="4bda8-p102">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR. You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="4bda8-111">Затем создайте Information Protection для Microsoft 365 корпоративный, выполнив указанные ниже шаги.</span><span class="sxs-lookup"><span data-stu-id="4bda8-111">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![Шаг 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="4bda8-113">Определение уровней безопасности и создание Information Protection</span><span class="sxs-lookup"><span data-stu-id="4bda8-113">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![Шаг 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="4bda8-115">Настройка классификации для среды</span><span class="sxs-lookup"><span data-stu-id="4bda8-115">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![Шаг 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="4bda8-117">Настройка усиленной защиты для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4bda8-117">Configure increased security for Microsoft 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![Шаг 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="4bda8-119">Настройка Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="4bda8-119">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|
|![Шаг 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="4bda8-121">Настройка защиты от потери данных Office 365</span><span class="sxs-lookup"><span data-stu-id="4bda8-121">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|
|![Шаг 6](../media/stepnumbers/Step6.png)|[<span data-ttu-id="4bda8-123">Настройка шифрования электронной почты</span><span class="sxs-lookup"><span data-stu-id="4bda8-123">Configure email encryption</span></span>](infoprotect-email-encryption.md)|
|![Шаг 7](../media/stepnumbers/Step7.png)|[<span data-ttu-id="4bda8-125">Настройка управления привилегированным доступом для Office 365</span><span class="sxs-lookup"><span data-stu-id="4bda8-125">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
|||

<span data-ttu-id="4bda8-126">Выполнив эти шаги, перейдите к перечню обязательных и необязательных [условий](infoprotect-exit-criteria.md) для соответствия требованиям Microsoft 365 корпоративный, при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="4bda8-126">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="4bda8-127">Как корпорация Майкрософт реализует Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="4bda8-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4bda8-128">Узнайте, как ИТ-специалисты корпорации Майкрософт используют [Azure Information Protection](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9)и обеспечивают безопасность данных.</span><span class="sxs-lookup"><span data-stu-id="4bda8-128">Learn how IT experts at Microsoft use [Azure Information Protection and safeguard data](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="4bda8-129">Как корпорация Contoso реализовала Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="4bda8-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4bda8-130">Посмотрите, как корпорация Contoso, вымышленная многонациональная компания, [реализовала защиту информации](contoso-info-protect.md) для облачных служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4bda8-130">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![Корпорация Contoso](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="4bda8-132">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="4bda8-132">Next step</span></span>

|||
|:-------|:-----|
|![Шаг 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="4bda8-134">Определение уровней безопасности и создание Information Protection</span><span class="sxs-lookup"><span data-stu-id="4bda8-134">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

