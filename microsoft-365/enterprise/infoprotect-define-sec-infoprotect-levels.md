---
title: Шаг 1. Определение уровней безопасности и Information Protection
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается об уровнях безопасности и Information Protection в организации и о том, как их настроить.
ms.openlocfilehash: bc55fab7b450685268ae89648ae18292e5494ce8
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870680"
---
# <a name="step-1-define-security-and-information-protection-levels"></a><span data-ttu-id="d0eca-103">Шаг 1. Определение уровней безопасности и Information Protection</span><span class="sxs-lookup"><span data-stu-id="d0eca-103">Step 1: Define security and information protection levels</span></span>

<span data-ttu-id="d0eca-104">*Этот шаг — обязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="d0eca-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="d0eca-p101">На этом шаге вы определите уровни безопасности и Information Protection для своей организации. Например, для отдела продаж может быть достаточно низкого уровня безопасности, а для исследовательского отдела и его ценной интеллектуальной собственности может потребоваться высокий уровень безопасности с шифрованием файлов и предоставлением доступа к ним только сотрудникам исследовательского отдела.</span><span class="sxs-lookup"><span data-stu-id="d0eca-p101">In Step 1, you'll define the levels of security and protection for your organization. For example, your sales department might only require a low security level, However, your research department and its highly valuable intellectual property might require a high security level that encrypts files and limits access to only research staff.</span></span>

<span data-ttu-id="d0eca-p102">Несмотря на то что вы можете определить собственные уровни безопасности и, возможно, уже используете некоторые из них, Корпорация Майкрософт рекомендует вам разработать план использования не менее трех различных уровней безопасности и защиты. Ниже приведен список, который можно использовать в качестве отправной точки.</span><span class="sxs-lookup"><span data-stu-id="d0eca-p102">Although you can define your own security levels and might already have some in place, Microsoft recommendations that you develop a plan to use at least three different levels of security and protection that can be applied. Here is a list to get you started:</span></span> 

- <span data-ttu-id="d0eca-p103">**Базовый уровень.** Это минимальный стандарт для защиты данных, а также для удостоверений и устройств, получающих доступ к вашим данным. Следуя рекомендациям по обеспечению базовой безопасности и защиты, вы можете организовать надежную защиту, используемую по умолчанию и соответствующую потребностям многих организаций и их подразделений.</span><span class="sxs-lookup"><span data-stu-id="d0eca-p103">**Baseline:** This is a minimum standard for protecting data and for the identities and devices that access your data. You can follow baseline security and protection recommendations to provide strong default protection that meets the needs of many organizations or their departments.</span></span>
- <span data-ttu-id="d0eca-p104">**Конфиденциальный уровень.** Это дополнительная защита той части ваших данных, для которой недостаточно защиты, обеспечиваемой базовым уровнем. Вы можете применять усиленную защиту для определенных наборов данных в своей среде Office 365. Кроме того, Корпорация Майкрософт рекомендует применять конфиденциальный уровень безопасности к удостоверениям и устройствам, получающим доступ к конфиденциальным данным.</span><span class="sxs-lookup"><span data-stu-id="d0eca-p104">**Sensitive:** This is additional protection for a subset of your data that must be protected beyond the baseline level. You can apply this increased protection to specific data sets in your Office 365 environment. Microsoft also recommends applying the sensitive security level to identities and devices that access sensitive data.</span></span>
- <span data-ttu-id="d0eca-p105">**Строго регулируемый уровень.** Это самый высокий уровень защиты для организаций, у которых обычно имеется очень небольшой объем особо секретных данных, представляющих собой интеллектуальную собственность или коммерческую тайну, или данных, для которых необходимо применять строгие меры обеспечения безопасности согласно соответствующим нормативным актам. В Microsoft 365 корпоративный имеются средства, с помощью которых организации могут выполнять такие строгие требования к обеспечению безопасности, включая равнозначную защиту удостоверений и устройств.</span><span class="sxs-lookup"><span data-stu-id="d0eca-p105">**Highly regulated:** This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span>

<span data-ttu-id="d0eca-116">Дополнительные сведения см. в разделе [Три уровня защиты](microsoft-365-policies-configurations.md#three-tiers-of-protection).</span><span class="sxs-lookup"><span data-stu-id="d0eca-116">For more information, see [Three tiers of protection](microsoft-365-policies-configurations.md#three-tiers-of-protection).</span></span>

<span data-ttu-id="d0eca-117">Результат выполнения шага: определение необходимых вам уровней безопасности и Information Protection.</span><span class="sxs-lookup"><span data-stu-id="d0eca-117">The result is a determination of your security and information protection levels.</span></span>

<span data-ttu-id="d0eca-118">Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step1), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="d0eca-118">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="d0eca-119">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="d0eca-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="d0eca-120">Настройка классификации для среды</span><span class="sxs-lookup"><span data-stu-id="d0eca-120">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
