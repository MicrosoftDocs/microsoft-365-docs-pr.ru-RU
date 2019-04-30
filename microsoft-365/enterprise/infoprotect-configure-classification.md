---
title: Шаг 2. Настройка классификации для среды
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается, как настроить различные способы классификации данных в организации.
ms.openlocfilehash: 5323e4f682e8a530601308877423502f64878a4c
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400093"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="d25dd-103">Шаг 2. Настройка классификации для среды</span><span class="sxs-lookup"><span data-stu-id="d25dd-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="d25dd-104">*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="d25dd-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="d25dd-105">На этом шаге вы проведете работу с юридическим отделом и отделом соответствия требованиям и определите схему классификации данных в своей организации.</span><span class="sxs-lookup"><span data-stu-id="d25dd-105">In this step, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-365-classification-types"></a><span data-ttu-id="d25dd-106">Типы классификации Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d25dd-106">Microsoft 365 classification types</span></span>

<span data-ttu-id="d25dd-107">В Microsoft 365 имеются четыре указанных ниже типа классификации.</span><span class="sxs-lookup"><span data-stu-id="d25dd-107">Microsoft 365 includes three types of classification:</span></span>

- <span data-ttu-id="d25dd-108">Типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="d25dd-108">Sensitive information types</span></span>
- <span data-ttu-id="d25dd-109">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="d25dd-109">Retention labels</span></span>
- <span data-ttu-id="d25dd-110">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="d25dd-110">Sensitivity labels</span></span>
- <span data-ttu-id="d25dd-111">Метки и защита Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="d25dd-111">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="d25dd-112">Типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="d25dd-112">Sensitive information types</span></span>

<span data-ttu-id="d25dd-113">Типы конфиденциальной информации для Microsoft 365 определяют порядок распознавания определенных типов информации,</span><span class="sxs-lookup"><span data-stu-id="d25dd-113">Sensitive information types for Microsoft 365 define how automated processes such as search recognize specific information types.</span></span> <span data-ttu-id="d25dd-114">в частности, конфиденциальных данных сотрудников или клиентов, таких как номера паспортов и кредитных карт.</span><span class="sxs-lookup"><span data-stu-id="d25dd-114">These include sensitive employee or customer data such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="d25dd-115">Типы конфиденциальной информации могут использоваться для поиска конфиденциальных данных и их защиты с помощью правил и политик защиты от потери данных (DLP).</span><span class="sxs-lookup"><span data-stu-id="d25dd-115">You use sensitive information types to find sensitive data and apply data loss prevention (DLP) rules and policies to protect this data.</span></span> <span data-ttu-id="d25dd-116">За дополнительной информацией обратитесь к статье [о составе политики DLP](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span><span class="sxs-lookup"><span data-stu-id="d25dd-116">For more information, see [what a DLP policy contains](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span></span> 

<span data-ttu-id="d25dd-117">Типы конфиденциальной информации особенно полезны для обеспечения соответствия требованиям и соблюдения нормативных актов, таких как Общий регламент по защите данных (GDPR).</span><span class="sxs-lookup"><span data-stu-id="d25dd-117">Sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="d25dd-118">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="d25dd-118">Retention labels</span></span>

<span data-ttu-id="d25dd-119">Одна из составляющих стратегии управления данными должна определять, как долго следует хранить документы определенных типов или с определенным содержимым в соответствии с правилами организации и региональными нормативными требованиями.</span><span class="sxs-lookup"><span data-stu-id="d25dd-119">Part of defining a data governance strategy is deciding how long specific types of documents or documents with specific contents should be retained in compliance with organization policies and regional regulations.</span></span> <span data-ttu-id="d25dd-120">Например документы некоторых типов должны храниться в течение установленного времени, а затем удаляться, а другие документы хранятся бессрочно.</span><span class="sxs-lookup"><span data-stu-id="d25dd-120">For example, some types of documents should be retained for a set amount of time and then deleted and others must be retained indefinitely.</span></span>

<span data-ttu-id="d25dd-121">Для документов, хранящихся в Microsoft 365, вы определяете метки хранения и применяете их к документам и данным, хранящимся в электронной почте Exchange, SharePoint Online, OneDrive для бизнеса и в сообщениях чата и каналов Teams.</span><span class="sxs-lookup"><span data-stu-id="d25dd-121">For documents stored in Microsoft 365, you define and apply retention labels to documents and data stored in Exchange email, SharePoint Online, OneDrive for Business, and Teams chat and channel messages.</span></span> 

<span data-ttu-id="d25dd-122">При использовании меток хранения необходимо задать метку для каждой категории файлов, к которым должна применяться политика хранения.</span><span class="sxs-lookup"><span data-stu-id="d25dd-122">If you use retention labels, you should configure a label for each category of file that needs to have a retention policy applied.</span></span> <span data-ttu-id="d25dd-123">В метке хранения можно указать следующие данные:</span><span class="sxs-lookup"><span data-stu-id="d25dd-123">Within the retention label, you can specify:</span></span>

- <span data-ttu-id="d25dd-124">Набор дескрипторов для файлов (например, для разных отделов, категорий файлов или нормативов).</span><span class="sxs-lookup"><span data-stu-id="d25dd-124">A set of descriptors for the files (for example, by business department, file category, or regulation).</span></span>
- <span data-ttu-id="d25dd-125">Параметры хранения файлов, к которым приложены метки хранения, такие как сроки хранения и действия по истечении срока.</span><span class="sxs-lookup"><span data-stu-id="d25dd-125">The retention settings for the files that have the retention label attached, such as retain times and behaviors after the retain time has been reached.</span></span>

<span data-ttu-id="d25dd-126">Также можно автоматически применять метки хранения к файлам, настроив сайт SharePoint Online так, чтобы ко всем новым документам на сайте применялась стандартная метка хранения.</span><span class="sxs-lookup"><span data-stu-id="d25dd-126">You can also apply a retention label to files automatically by configuring a SharePoint Online site to apply a default retention label to all new documents in the site.</span></span> 

<span data-ttu-id="d25dd-127">За дополнительной информацией обращайтесь к [обзору меток хранения](https://docs.microsoft.com/office365/securitycompliance/labels).</span><span class="sxs-lookup"><span data-stu-id="d25dd-127">For more information, see the [overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="d25dd-128">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="d25dd-128">Sensitivity labels</span></span>

<span data-ttu-id="d25dd-129">Одна из мер защиты и поддержания безопасности для документов определенного типа или с определенным содержимым состоит в применении к ним особой метки, которая говорит о необходимости применения дополнительной защиты.</span><span class="sxs-lookup"><span data-stu-id="d25dd-129">Part of protecting and implementing security for specific types of documents or documents with specific contents is marking them with a label so that the additional security can be applied.</span></span> <span data-ttu-id="d25dd-130">С помощью меток конфиденциальности в Microsoft 365 можно:</span><span class="sxs-lookup"><span data-stu-id="d25dd-130">With sensitivity labels in Microsoft 365, you can:</span></span>

- <span data-ttu-id="d25dd-131">Применять параметры защиты, такие как шифрование, разрешения или подложка.</span><span class="sxs-lookup"><span data-stu-id="d25dd-131">Enforce protection settings such as encryption, permissions, or adding a watermark.</span></span>
- <span data-ttu-id="d25dd-132">Запрещать выход конфиденциального содержимого за пределы вашей организации на устройствах под управлением Windows, используя защиту конечных точек в Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="d25dd-132">Prevent sensitive content from leaving your organization on devices running Windows, by using endpoint protection in Microsoft Intune.</span></span> 
- <span data-ttu-id="d25dd-133">С помощью защиты конечных точек в Windows Information Protection (WIP) предотвращать копирование такого содержимого в сторонние приложения, такие как Twitter или Gmail, или копирование на съемные носители, такие как USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="d25dd-133">Use Windows Information Protection (WIP) endpoint protection to prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>
- <span data-ttu-id="d25dd-134">С помощью Microsoft Cloud App Security защищать содержимое в сторонних приложениях и службах.</span><span class="sxs-lookup"><span data-stu-id="d25dd-134">Use Microsoft Cloud App Security to protect content in third-party apps and services.</span></span> 
- <span data-ttu-id="d25dd-135">Классифицировать содержимое, не используя параметры защиты.</span><span class="sxs-lookup"><span data-stu-id="d25dd-135">Classify content without using any protection settings.</span></span>

<span data-ttu-id="d25dd-136">При использовании меток конфиденциальности следует задать метку для каждого уровня защиты и безопасности информации.</span><span class="sxs-lookup"><span data-stu-id="d25dd-136">If you use sensitivity labels, you should configure a label for each security and information protection level.</span></span> <span data-ttu-id="d25dd-137">Например можно создать три метки конфиденциальности:</span><span class="sxs-lookup"><span data-stu-id="d25dd-137">For example, create three sensitivity labels for:</span></span>

- <span data-ttu-id="d25dd-138">Базовый уровень</span><span class="sxs-lookup"><span data-stu-id="d25dd-138">Baseline</span></span>
- <span data-ttu-id="d25dd-139">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="d25dd-139">Sensitive</span></span>
- <span data-ttu-id="d25dd-140">Строго регулируемый уровень</span><span class="sxs-lookup"><span data-stu-id="d25dd-140">Highly regulated</span></span>

<span data-ttu-id="d25dd-141">За дополнительными сведениями обратитесь к [обзору меток конфиденциальности](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="d25dd-141">For more information, see [Overview of sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="d25dd-142">Метки и защита Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="d25dd-142">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="d25dd-143">Метки Azure Information Protection можно использовать для классификации, а при необходимости и для защиты документов и сообщений электронной почты в организации.</span><span class="sxs-lookup"><span data-stu-id="d25dd-143">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails.</span></span> <span data-ttu-id="d25dd-144">Эти метки можно применять к документам, которые хранятся за пределами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d25dd-144">These labels can apply to documents that are stored outside of Microsoft 365.</span></span> <span data-ttu-id="d25dd-145">Они могут применяться автоматически (администраторами, которые определяют правила и условия), вручную (пользователями) или с сочетанием этих вариантов, когда пользователи получают рекомендации.</span><span class="sxs-lookup"><span data-stu-id="d25dd-145">This can be done automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="d25dd-146">Чтобы спланировать и развернуть метки Azure Information Protection, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d25dd-146">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="d25dd-147">Изучите [требования для Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span><span class="sxs-lookup"><span data-stu-id="d25dd-147">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="d25dd-148">Выполните [стратегический план развертывания для классификации, маркирования и защиты](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span><span class="sxs-lookup"><span data-stu-id="d25dd-148">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="d25dd-149">Дополнительные сведения см. в [документации по библиотеке Azure Information Protection](https://docs.microsoft.com/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="d25dd-149">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

<span data-ttu-id="d25dd-150">Существующие метки Azure Information Protection без проблем работают с метками конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="d25dd-150">Existing Azure Information Protection labels work seamlessly with sensitivity labels.</span></span> <span data-ttu-id="d25dd-151">Например, можно одновременно использовать существующие метки Azure Information Protection и метки, которые применяются к документам и электронной почте.</span><span class="sxs-lookup"><span data-stu-id="d25dd-151">For example, you can keep your existing Azure Information Protection labels and the labels that are applied to documents and email.</span></span>

<span data-ttu-id="d25dd-152">Если имеются как метки конфиденциальности, так и метки Azure Information Protection, следует [перенести метки Azure Information Protection на метки конфиденциальности](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span><span class="sxs-lookup"><span data-stu-id="d25dd-152">If you have both sensitivity and Azure Information Protection labels, you should [migrate your Azure Information Protection labels to sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span></span>

## <a name="example-classification-for-gdpr"></a><span data-ttu-id="d25dd-153">Пример: классификация для GDPR</span><span class="sxs-lookup"><span data-stu-id="d25dd-153">Classification for GDPR</span></span>

<span data-ttu-id="d25dd-154">Пример схемы классификации, включающей личные данные для GDPR, см. в статье [Разработка архитектуры схемы классификации для персональных данных](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span><span class="sxs-lookup"><span data-stu-id="d25dd-154">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

## <a name="take-it-for-a-test-drive"></a><span data-ttu-id="d25dd-155">Тестовый запуск</span><span class="sxs-lookup"><span data-stu-id="d25dd-155">Take it for a test drive</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d25dd-157">Руководство по лаборатории тестирования: классификация данных</span><span class="sxs-lookup"><span data-stu-id="d25dd-157">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="d25dd-158">Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step2), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="d25dd-158">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step2) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="d25dd-159">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="d25dd-159">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="d25dd-160">Настройка усиленной защиты для Office 365</span><span class="sxs-lookup"><span data-stu-id="d25dd-160">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

