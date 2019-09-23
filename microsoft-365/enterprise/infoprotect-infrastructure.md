---
title: Шаг 6. Information Protection
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
ms.openlocfilehash: 3174790d1ee6c9ed05605dd1c3c75405e3eac42b
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047312"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="26217-103">Шаг 6. Information Protection</span><span class="sxs-lookup"><span data-stu-id="26217-103">Phase 6: Information protection</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="26217-p101">Information Protection — это набор политик и технологий, определяющих порядок передачи, хранения и обработки конфиденциальной информации. На этапе 6 вы постепенно настроите параметры и функции Information Protection в Microsoft 365 корпоративный, которые помогут защитить данные облачных рабочих нагрузок и сценариев.</span><span class="sxs-lookup"><span data-stu-id="26217-p101">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information. In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads and scenarios.</span></span>

>[!Note]
><span data-ttu-id="26217-106">Если вы уже развернули Information Protection, см. перечень обязательных и необязательных [условий](infoprotect-exit-criteria.md), при выполнении которых можно считать Information Protection для Microsoft 365 корпоративный настроенной.</span><span class="sxs-lookup"><span data-stu-id="26217-106">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="26217-107">В этом разделе рассказывается, как спланировать и развернуть инфраструктуру Information Protection для Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="26217-107">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="26217-p102">Совместно с юридическим отделом и отделом, отвечающим за соответствие требованиям в вашей организации, определите, необходимо ли вашей организации соблюдать какие-либо стандарты соответствия требованиям, например HIPPA, CJIS или GDPR. Кроме того, вам следует провести работу с группой обеспечения безопасности вашей организации и определить цели Information Protection для организации и ее отделов или групп, которым необходима дополнительная защита.</span><span class="sxs-lookup"><span data-stu-id="26217-p102">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR. You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="26217-110">Затем создайте Information Protection для Microsoft 365 корпоративный, выполнив указанные ниже шаги.</span><span class="sxs-lookup"><span data-stu-id="26217-110">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="26217-111">Определение уровней безопасности и создание Information Protection</span><span class="sxs-lookup"><span data-stu-id="26217-111">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="26217-112">Настройка классификации для среды</span><span class="sxs-lookup"><span data-stu-id="26217-112">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="26217-113">Настройка усиленной защиты для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="26217-113">Configure increased security for Microsoft 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="26217-114">Настройка Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="26217-114">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="26217-115">Настройка защиты от потери данных Office 365</span><span class="sxs-lookup"><span data-stu-id="26217-115">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|
|![](./media/stepnumbers/Step6.png)|[<span data-ttu-id="26217-116">Настройка шифрования электронной почты</span><span class="sxs-lookup"><span data-stu-id="26217-116">Configure email encryption</span></span>](infoprotect-email-encryption.md)|
|![](./media/stepnumbers/Step7.png)|[<span data-ttu-id="26217-117">Настройка управления привилегированным доступом для Office 365</span><span class="sxs-lookup"><span data-stu-id="26217-117">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
|||

<span data-ttu-id="26217-118">Выполнив эти шаги, перейдите к перечню обязательных и необязательных [условий](infoprotect-exit-criteria.md) для соответствия требованиям Microsoft 365 корпоративный, при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="26217-118">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="26217-119">Как корпорация Майкрософт реализует Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="26217-119">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="26217-120">Узнайте, как ИТ-специалисты корпорации Майкрософт используют [Azure Information Protection](https://www.microsoft.com/ru-RU/itshowcase/deploying-and-managing-microsoft-365#primaryR9)и обеспечивают безопасность данных.</span><span class="sxs-lookup"><span data-stu-id="26217-120">Learn how IT experts at Microsoft use [Azure Information Protection and safeguard data](https://www.microsoft.com/ru-RU/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="26217-121">Как корпорация Contoso реализовала Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="26217-121">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="26217-122">Посмотрите, как корпорация Contoso, вымышленная многонациональная компания, [реализовала защиту информации](contoso-info-protect.md) для облачных служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26217-122">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="26217-123">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="26217-123">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="26217-124">Определение уровней безопасности и создание Information Protection</span><span class="sxs-lookup"><span data-stu-id="26217-124">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

