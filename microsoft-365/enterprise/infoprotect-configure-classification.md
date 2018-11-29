---
title: Шаг 2. Настройка классификации для среды
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается, как настроить различные способы классификации данных в организации.
ms.openlocfilehash: bee0885eb3f8899560532895d1558723b281ab02
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870637"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="73677-103">Шаг 2. Настройка классификации для среды</span><span class="sxs-lookup"><span data-stu-id="73677-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="73677-104">*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="73677-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="73677-105">На этом шаге вы проведете работу с юридическим отделом и отделом соответствия требованиям и определите схему классификации данных в своей организации.</span><span class="sxs-lookup"><span data-stu-id="73677-105">In Step 3, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-classifications"></a><span data-ttu-id="73677-106">Классификация Корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="73677-106">Microsoft classifications</span></span>

<span data-ttu-id="73677-107">В Microsoft 365 имеются три указанных ниже типа классификации.</span><span class="sxs-lookup"><span data-stu-id="73677-107">Microsoft 365 includes three types of classification:</span></span>

- <span data-ttu-id="73677-108">Типы конфиденциальной информации для Office 365</span><span class="sxs-lookup"><span data-stu-id="73677-108">Sensitive information types for Office 365</span></span>
- <span data-ttu-id="73677-109">Метки Office 365</span><span class="sxs-lookup"><span data-stu-id="73677-109">Office 365 labels</span></span>
- <span data-ttu-id="73677-110">Метки и защита Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="73677-110">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types-for-office-365"></a><span data-ttu-id="73677-111">Типы конфиденциальной информации для Office 365</span><span class="sxs-lookup"><span data-stu-id="73677-111">Sensitive information types for Office 365</span></span>

<span data-ttu-id="73677-p101">Типы конфиденциальной информации для Office 365 определяют порядок распознавания определенных типов информации, например номеров службы здравоохранения или номеров кредитных карт, автоматическими процессами, например функцией поиска. Вы можете использовать типы конфиденциальной информации для поиска конфиденциальных данных и их защиты с помощью правил и политик защиты от потери данных. Дополнительные сведения см. в статье [Обзор политик защиты от потери данных](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). Например, типы конфиденциальной информации особенно полезны для обеспечения соответствия требованиям и выполнения требований нормативных актов, например Общего регламента по защите данных (GDPR).</span><span class="sxs-lookup"><span data-stu-id="73677-p101">Sensitive information types for Office 365 define how automated processes such as search recognize specific information types such as health service numbers and credit card numbers. You use sensitive information types to find sensitive data and apply data loss prevention rules and policies to protect this data. For more information, see [Overview of data loss prevention policies](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). For example, sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="office-365-labels"></a><span data-ttu-id="73677-116">Метки Office 365</span><span class="sxs-lookup"><span data-stu-id="73677-116">Office 365 labels</span></span>
<span data-ttu-id="73677-p102">Вы можете использовать метки Office 365 для личных данных и для файлов, являющихся объектом строгого регулирования или коммерческой тайны и хранящихся в SharePoint Online и OneDrive для бизнеса. Дополнительные сведения (в том числе о том, как создавать такие типы) см. в статье [Общие сведения о метках](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).</span><span class="sxs-lookup"><span data-stu-id="73677-p102">You can use Office 365 labels for personal data and for highly regulated and trade secret files stored in SharePoint Online and OneDrive for Business. For more information, including how to create them, see [Overview of labels](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).</span></span>

<span data-ttu-id="73677-p103">Если вы решите использовать метки Office 365, вам следует настроить хотя бы одну метку для каждого уровня защиты. Например, вы можете создать три метки для указанных ниже уровней.</span><span class="sxs-lookup"><span data-stu-id="73677-p103">If you decide to use Office 365 labels, you should configure at least one for each level of protection. For example, create three labels for:</span></span>

- <span data-ttu-id="73677-121">Базовый уровень</span><span class="sxs-lookup"><span data-stu-id="73677-121">Baseline</span></span>
- <span data-ttu-id="73677-122">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="73677-122">Sensitive</span></span>
- <span data-ttu-id="73677-123">Строго регулируемый уровень</span><span class="sxs-lookup"><span data-stu-id="73677-123">Highly regulated</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="73677-124">Метки и защита Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="73677-124">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="73677-p104">Вы можете использовать метки Azure Information Protection для классификации и (необязательно) защиты документов и электронных писем вашей организации. Эти метки можно применять к документам, хранящимся за пределами Office 365. Эти метки можно применять автоматически (это делают администраторы, задающие правила и условия), вручную (это делают пользователи) или в смешанном порядке, когда пользователям предоставляют необходимые рекомендации.</span><span class="sxs-lookup"><span data-stu-id="73677-p104">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails. These labels can apply to documents that are stored outside of Office 365. These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="73677-128">Чтобы спланировать и развернуть метки Azure Information Protection, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="73677-128">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="73677-129">Изучите [требования для Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span><span class="sxs-lookup"><span data-stu-id="73677-129">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="73677-130">Выполните [стратегический план развертывания для классификации, маркирования и защиты](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span><span class="sxs-lookup"><span data-stu-id="73677-130">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="73677-131">Дополнительные сведения см. в [документации по библиотеке Azure Information Protection](https://docs.microsoft.com/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="73677-131">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

## <a name="classification-for-gdpr"></a><span data-ttu-id="73677-132">Классификация для GDPR</span><span class="sxs-lookup"><span data-stu-id="73677-132">Classification for GDPR</span></span>

<span data-ttu-id="73677-133">Пример схемы классификации, включающей личные данные для GDPR, см. в статье [Разработка архитектуры схемы классификации для персональных данных](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span><span class="sxs-lookup"><span data-stu-id="73677-133">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="73677-135">Руководство по лаборатории тестирования: классификация данных</span><span class="sxs-lookup"><span data-stu-id="73677-135">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="73677-136">Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step3), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="73677-136">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="73677-137">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="73677-137">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="73677-138">Настройка усиленной защиты для Office 365</span><span class="sxs-lookup"><span data-stu-id="73677-138">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

