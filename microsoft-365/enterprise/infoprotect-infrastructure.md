---
title: Шаг 6. Information Protection
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/01/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как развернуть инфраструктуру Information Protection для Microsoft 365 корпоративный.
ms.openlocfilehash: a0d2c485b05e0969fe45cfd79c86e4e7dcb1d5ff
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400003"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="90e4f-103">Шаг 6. Information Protection</span><span class="sxs-lookup"><span data-stu-id="90e4f-103">Phase 6: Information protection</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="90e4f-p101">Information Protection — это набор политик и технологий, определяющих порядок передачи, хранения и обработки конфиденциальной информации. На этапе 6 вы постепенно настроите параметры и функции Information Protection в Microsoft 365 корпоративный, которые помогут защитить данные облачных рабочих нагрузок и сценариев.</span><span class="sxs-lookup"><span data-stu-id="90e4f-p101">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information. In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads and scenarios.</span></span>

>[!Note]
><span data-ttu-id="90e4f-106">Если вы уже развернули Information Protection, см. перечень обязательных и необязательных [условий](infoprotect-exit-criteria.md), при выполнении которых можно считать Information Protection для Microsoft 365 корпоративный настроенной.</span><span class="sxs-lookup"><span data-stu-id="90e4f-106">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="90e4f-107">В этом разделе рассказывается, как спланировать и развернуть инфраструктуру Information Protection для Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="90e4f-107">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="90e4f-p102">Совместно с юридическим отделом и отделом, отвечающим за соответствие требованиям в вашей организации, определите, необходимо ли вашей организации соблюдать какие-либо стандарты соответствия требованиям, например HIPPA, CJIS или GDPR. Кроме того, вам следует провести работу с группой обеспечения безопасности вашей организации и определить цели Information Protection для организации и ее отделов или групп, которым необходима дополнительная защита.</span><span class="sxs-lookup"><span data-stu-id="90e4f-p102">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR. You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="90e4f-110">Затем создайте Information Protection для Microsoft 365 корпоративный, выполнив указанные ниже шаги.</span><span class="sxs-lookup"><span data-stu-id="90e4f-110">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="90e4f-111">Определение уровней безопасности и создание Information Protection</span><span class="sxs-lookup"><span data-stu-id="90e4f-111">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="90e4f-112">Настройка классификации для среды</span><span class="sxs-lookup"><span data-stu-id="90e4f-112">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="90e4f-113">Настройка усиленной защиты для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="90e4f-113">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="90e4f-114">Настройка Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="90e4f-114">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="90e4f-115">Настройка защиты от потери данных Office 365</span><span class="sxs-lookup"><span data-stu-id="90e4f-115">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|
|![](./media/stepnumbers/Step6.png)|[<span data-ttu-id="90e4f-116">Настройка управления привилегированным доступом для Office 365</span><span class="sxs-lookup"><span data-stu-id="90e4f-116">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|


<span data-ttu-id="90e4f-117">Выполнив эти шаги, перейдите к перечню обязательных и необязательных [условий](infoprotect-exit-criteria.md) для соответствия требованиям Microsoft 365 корпоративный, при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="90e4f-117">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="90e4f-118">Как корпорация Майкрософт реализует Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="90e4f-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="90e4f-119">Узнайте, как ИТ-специалисты корпорации Майкрософт используют возможности защиты информации в Microsoft 356 корпоративный, чтобы защищать данные и отражать кибератаки:</span><span class="sxs-lookup"><span data-stu-id="90e4f-119">Learn how IT experts at Microsoft use the information protection capabilities of Microsoft 356 Enterprise to protect information and defend against cyber attacks:</span></span>

- [<span data-ttu-id="90e4f-120">Защита файлов в облаке с помощью Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="90e4f-120">Protecting files in the cloud with Azure Information Protection</span></span>](https://www.microsoft.com/itshowcase/Article/Content/924/Protecting-files-in-the-cloud-with-Azure-Information-Protection)
- [<span data-ttu-id="90e4f-121">Корпорация Майкрософт использует аналитику угроз для защиты, обнаружения угроз и реагирования на них</span><span class="sxs-lookup"><span data-stu-id="90e4f-121">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="90e4f-122">Корпорация Майкрософт предотвращает попытки фишинга с помощью Office 365</span><span class="sxs-lookup"><span data-stu-id="90e4f-122">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="90e4f-123">Как корпорация Contoso реализовала Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="90e4f-123">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="90e4f-124">Посмотрите, как корпорация Contoso, вымышленная многонациональная компания, [реализовала защиту информации](contoso-info-protect.md) для облачных служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="90e4f-124">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="90e4f-125">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="90e4f-125">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="90e4f-126">Определение уровней безопасности и создание Information Protection</span><span class="sxs-lookup"><span data-stu-id="90e4f-126">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

