---
title: Шаг 1. Определение уровней безопасности и Information Protection
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
description: В этой статье рассказывается об уровнях безопасности и Information Protection в организации и о том, как их настроить.
ms.openlocfilehash: 0fa3e9fa11070ea505752d781ecdd21b344c8222
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636968"
---
# <a name="step-1-define-security-and-information-protection-levels"></a><span data-ttu-id="200cb-103">Шаг 1. Определение уровней безопасности и Information Protection</span><span class="sxs-lookup"><span data-stu-id="200cb-103">Step 1: Define security and information protection levels</span></span>

<span data-ttu-id="200cb-104">*Этот шаг — обязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="200cb-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Этап 6. Защита данных](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="200cb-106">На этом этапе вы определите уровни безопасности и защиты для организации.</span><span class="sxs-lookup"><span data-stu-id="200cb-106">In this step, you'll define the levels of security and protection for your organization.</span></span> <span data-ttu-id="200cb-107">Например, вашему отделу продаж может требоваться только низкий уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="200cb-107">For example, your sales department might only require a low security level.</span></span> <span data-ttu-id="200cb-108">Однако вашему исследовательский отдел и его интеллектуальной собственности, представляющей высокую ценность, может потребоваться высокий уровень защиты, при использовании которого файлы шифруются, а доступ предоставляется только исследовательскому персоналу.</span><span class="sxs-lookup"><span data-stu-id="200cb-108">However, your research department and its highly valuable intellectual property might require a high security level that encrypts files and limits access to only research staff.</span></span>

<span data-ttu-id="200cb-109">Несмотря на то что вы можете определить собственные уровни безопасности и, возможно, уже используете некоторые из них, корпорация Майкрософт рекомендует вам разработать план использования не менее трех различных уровней безопасности и защиты.</span><span class="sxs-lookup"><span data-stu-id="200cb-109">Although you can define your own security levels and might already have some in place, Microsoft recommends that you develop a plan to use at least three different levels of security and protection that can be applied.</span></span> <span data-ttu-id="200cb-110">Ниже приведен список с общими сведениями об этих уровнях.</span><span class="sxs-lookup"><span data-stu-id="200cb-110">Here is a list to get you started:</span></span> 

- <span data-ttu-id="200cb-p103">**Базовый уровень.** Это минимальный стандарт для защиты данных, а также для удостоверений и устройств, получающих доступ к вашим данным. Следуя рекомендациям по обеспечению базовой безопасности и защиты, вы можете организовать надежную защиту, используемую по умолчанию и соответствующую потребностям многих организаций и их подразделений.</span><span class="sxs-lookup"><span data-stu-id="200cb-p103">**Baseline:** This is a minimum standard for protecting data and for the identities and devices that access your data. You can follow baseline security and protection recommendations to provide strong default protection that meets the needs of many organizations or their departments.</span></span>
- <span data-ttu-id="200cb-p104">**Конфиденциальный уровень.** Это дополнительная защита той части ваших данных, для которой недостаточно защиты, обеспечиваемой базовым уровнем. Вы можете применять усиленную защиту для определенных наборов данных в своей среде Microsoft 365. Кроме того, Майкрософт рекомендует применять конфиденциальный уровень безопасности к удостоверениям и устройствам, получающим доступ к конфиденциальным данным.</span><span class="sxs-lookup"><span data-stu-id="200cb-p104">**Sensitive:** This is additional protection for a subset of your data that must be protected beyond the baseline level. You can apply this increased protection to specific data sets in your Microsoft 365 environment. Microsoft also recommends applying the sensitive security level to identities and devices that access sensitive data.</span></span>
- <span data-ttu-id="200cb-p105">**Строго регулируемый уровень.** Это самый высокий уровень защиты для организаций, у которых обычно имеется очень небольшой объем особо секретных данных, представляющих собой интеллектуальную собственность или коммерческую тайну, или данных, для которых необходимо применять строгие меры обеспечения безопасности согласно соответствующим нормативным актам. В Microsoft 365 корпоративный имеются средства, с помощью которых организации могут выполнять такие строгие требования к обеспечению безопасности, включая равнозначную защиту удостоверений и устройств.</span><span class="sxs-lookup"><span data-stu-id="200cb-p105">**Highly regulated:** This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span>

<span data-ttu-id="200cb-118">Дополнительные сведения см. в разделе [Три уровня защиты](microsoft-365-policies-configurations.md#three-tiers-of-protection).</span><span class="sxs-lookup"><span data-stu-id="200cb-118">For more information, see [Three tiers of protection](microsoft-365-policies-configurations.md#three-tiers-of-protection).</span></span>

<span data-ttu-id="200cb-119">Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step1), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="200cb-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="200cb-120">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="200cb-120">Next step</span></span>

|||
|:-------|:-----|
|![Шаг 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="200cb-122">Настройка классификации для среды</span><span class="sxs-lookup"><span data-stu-id="200cb-122">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
