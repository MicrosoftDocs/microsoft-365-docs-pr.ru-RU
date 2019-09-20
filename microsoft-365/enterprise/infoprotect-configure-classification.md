---
title: Шаг 2. Настройка классификации для среды
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
description: В этой статье рассказывается, как настроить различные способы классификации данных в организации.
ms.openlocfilehash: ca1b4aefca7ee63f1c8fe098c115fc4f0074d9f6
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047302"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="10f32-103">Шаг 2. Настройка классификации для среды</span><span class="sxs-lookup"><span data-stu-id="10f32-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="10f32-104">*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="10f32-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="10f32-105">На этом шаге вы проведете работу с юридическим отделом и отделом соответствия требованиям и определите схему классификации данных в своей организации.</span><span class="sxs-lookup"><span data-stu-id="10f32-105">In this step, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-365-classification-types"></a><span data-ttu-id="10f32-106">Типы классификации Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10f32-106">Microsoft 365 classification types</span></span>

<span data-ttu-id="10f32-107">В Microsoft 365 имеются четыре указанных ниже типа классификации.</span><span class="sxs-lookup"><span data-stu-id="10f32-107">Microsoft 365 includes four types of classification:</span></span>

- <span data-ttu-id="10f32-108">Типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="10f32-108">Sensitive information types</span></span>
- <span data-ttu-id="10f32-109">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="10f32-109">Retention labels</span></span>
- <span data-ttu-id="10f32-110">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="10f32-110">Sensitivity labels</span></span>
- <span data-ttu-id="10f32-111">Метки и защита Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="10f32-111">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="10f32-112">Типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="10f32-112">Sensitive information types</span></span>

<span data-ttu-id="10f32-113">Типы конфиденциальной информации для Microsoft 365 определяют порядок распознавания определенных типов информации,</span><span class="sxs-lookup"><span data-stu-id="10f32-113">Sensitive information types for Microsoft 365 define how automated processes such as search recognize specific information types.</span></span> <span data-ttu-id="10f32-114">в частности, конфиденциальных данных сотрудников или клиентов, таких как номера паспортов и кредитных карт.</span><span class="sxs-lookup"><span data-stu-id="10f32-114">These include sensitive employee or customer data such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="10f32-115">Типы конфиденциальной информации могут использоваться для поиска конфиденциальных данных и их защиты с помощью правил и политик защиты от потери данных (DLP).</span><span class="sxs-lookup"><span data-stu-id="10f32-115">You use sensitive information types to find sensitive data and apply data loss prevention (DLP) rules and policies to protect this data.</span></span> <span data-ttu-id="10f32-116">За дополнительной информацией обратитесь к статье [о составе политики DLP](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span><span class="sxs-lookup"><span data-stu-id="10f32-116">For more information, see [what a DLP policy contains](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span></span> 

<span data-ttu-id="10f32-117">Типы конфиденциальной информации особенно полезны для обеспечения соответствия требованиям и соблюдения нормативных актов, таких как Общий регламент по защите данных (GDPR).</span><span class="sxs-lookup"><span data-stu-id="10f32-117">Sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="10f32-118">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="10f32-118">Retention labels</span></span>

<span data-ttu-id="10f32-119">Одна из составляющих стратегии управления данными должна определять, как долго следует хранить документы определенных типов или с определенным содержимым в соответствии с правилами организации и региональными нормативными требованиями.</span><span class="sxs-lookup"><span data-stu-id="10f32-119">Part of defining a data governance strategy is deciding how long specific types of documents or documents with specific contents should be retained in compliance with organization policies and regional regulations.</span></span> <span data-ttu-id="10f32-120">Например документы некоторых типов должны храниться в течение установленного времени, а затем удаляться, а другие документы хранятся бессрочно.</span><span class="sxs-lookup"><span data-stu-id="10f32-120">For example, some types of documents should be retained for a set amount of time and then deleted and others must be retained indefinitely.</span></span>

<span data-ttu-id="10f32-121">Для документов, хранящихся в Microsoft 365, вы определяете метки хранения и применяете их к документам и данным, хранящимся в электронной почте Exchange, SharePoint Online, OneDrive для бизнеса и в сообщениях чата и каналов Teams.</span><span class="sxs-lookup"><span data-stu-id="10f32-121">For documents stored in Microsoft 365, you define and apply retention labels to documents and data stored in Exchange email, SharePoint Online, OneDrive for Business, and Teams chat and channel messages.</span></span> 

<span data-ttu-id="10f32-122">При использовании меток хранения необходимо задать метку для каждой категории файлов, к которым должна применяться политика хранения.</span><span class="sxs-lookup"><span data-stu-id="10f32-122">If you use retention labels, you should configure a label for each category of file that needs to have a retention policy applied.</span></span> <span data-ttu-id="10f32-123">В метке хранения можно указать следующие данные:</span><span class="sxs-lookup"><span data-stu-id="10f32-123">Within the retention label, you can specify:</span></span>

- <span data-ttu-id="10f32-124">Набор дескрипторов для файлов (например, для разных отделов, категорий файлов или нормативов).</span><span class="sxs-lookup"><span data-stu-id="10f32-124">A set of descriptors for the files (for example, by business department, file category, or regulation).</span></span>
- <span data-ttu-id="10f32-125">Параметры хранения файлов, к которым приложены метки хранения, такие как сроки хранения и действия по истечении срока.</span><span class="sxs-lookup"><span data-stu-id="10f32-125">The retention settings for the files that have the retention label attached, such as retain times and behaviors after the retain time has been reached.</span></span>

<span data-ttu-id="10f32-126">Также можно автоматически применять метки хранения к файлам, настроив сайт SharePoint Online так, чтобы ко всем новым документам на сайте применялась стандартная метка хранения.</span><span class="sxs-lookup"><span data-stu-id="10f32-126">You can also apply a retention label to files automatically by configuring a SharePoint Online site to apply a default retention label to all new documents in the site.</span></span> 

<span data-ttu-id="10f32-127">За дополнительной информацией обращайтесь к [обзору меток хранения](https://docs.microsoft.com/office365/securitycompliance/labels).</span><span class="sxs-lookup"><span data-stu-id="10f32-127">For more information, see the [overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="10f32-128">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="10f32-128">Sensitivity labels</span></span>

<span data-ttu-id="10f32-129">Одна из мер защиты и поддержания безопасности для документов определенного типа или с определенным содержимым состоит в применении к ним особой метки, которая говорит о необходимости применения дополнительной защиты.</span><span class="sxs-lookup"><span data-stu-id="10f32-129">Part of protecting and implementing security for specific types of documents or documents with specific contents is marking them with a label so that the additional security can be applied.</span></span> <span data-ttu-id="10f32-130">С помощью меток конфиденциальности в Microsoft 365 можно:</span><span class="sxs-lookup"><span data-stu-id="10f32-130">With sensitivity labels in Microsoft 365, you can:</span></span>

- <span data-ttu-id="10f32-131">Применять параметры защиты, такие как шифрование, разрешения или подложка.</span><span class="sxs-lookup"><span data-stu-id="10f32-131">Enforce protection settings such as encryption, permissions, or adding a watermark.</span></span>
- <span data-ttu-id="10f32-132">С помощью защиты конечных точек в Windows Information Protection (WIP) предотвращать копирование такого содержимого в сторонние приложения, такие как Twitter или Gmail, или копирование на съемные носители, такие как USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="10f32-132">Use Windows Information Protection (WIP) endpoint protection to prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>
- <span data-ttu-id="10f32-133">С помощью Microsoft Cloud App Security (CAS) защищать содержимое в сторонних приложениях и службах.</span><span class="sxs-lookup"><span data-stu-id="10f32-133">Use Microsoft Cloud App Security to protect content in third-party apps and services.</span></span> 
- <span data-ttu-id="10f32-134">Классифицировать содержимое, не используя параметры защиты.</span><span class="sxs-lookup"><span data-stu-id="10f32-134">Classify content without using any protection settings.</span></span>

<span data-ttu-id="10f32-135">При использовании меток конфиденциальности следует задать метку для каждого уровня защиты и безопасности информации.</span><span class="sxs-lookup"><span data-stu-id="10f32-135">If you use sensitivity labels, you should configure a label for each security and information protection level.</span></span> <span data-ttu-id="10f32-136">Например можно создать три метки конфиденциальности:</span><span class="sxs-lookup"><span data-stu-id="10f32-136">For example, create three sensitivity labels for:</span></span>

- <span data-ttu-id="10f32-137">Базовый уровень</span><span class="sxs-lookup"><span data-stu-id="10f32-137">Baseline</span></span>
- <span data-ttu-id="10f32-138">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="10f32-138">Sensitive</span></span>
- <span data-ttu-id="10f32-139">Строго контролируемый</span><span class="sxs-lookup"><span data-stu-id="10f32-139">Highly regulated</span></span>

<span data-ttu-id="10f32-140">Если вы храните файлы со строго регулируемыми данными на сайте SharePoint Online и хотите, чтобы у этих файлов вне сайта были такие же разрешения, как на сайте, требуется создать дополнительные метки конфиденциальности, разрешения которых совпадают с разрешениями сайта.</span><span class="sxs-lookup"><span data-stu-id="10f32-140">If you store files with highly regulated data in a SharePoint Online site and want those files to have the same permissions as the site if the files leave the site, you need to create an additional sensitivity label whose permissions are the same as the site.</span></span>

<span data-ttu-id="10f32-141">За дополнительными сведениями обратитесь к [обзору меток конфиденциальности](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="10f32-141">For more information, see this [overview of sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="10f32-142">Метки и защита Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="10f32-142">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="10f32-143">Метки Azure Information Protection можно использовать для классификации, а при необходимости и для защиты документов и сообщений электронной почты в организации.</span><span class="sxs-lookup"><span data-stu-id="10f32-143">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails.</span></span> <span data-ttu-id="10f32-144">Эти метки можно применять к документам, которые хранятся за пределами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10f32-144">These labels can apply to documents that are stored outside of Microsoft 365.</span></span> <span data-ttu-id="10f32-145">Они могут применяться автоматически (администраторами, которые определяют правила и условия), вручную (пользователями) или с сочетанием этих вариантов, когда пользователи получают рекомендации.</span><span class="sxs-lookup"><span data-stu-id="10f32-145">These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="10f32-146">Чтобы спланировать и развернуть метки Azure Information Protection, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="10f32-146">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="10f32-147">Изучите [требования для Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span><span class="sxs-lookup"><span data-stu-id="10f32-147">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="10f32-148">Выполните [стратегический план развертывания для классификации, маркирования и защиты](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span><span class="sxs-lookup"><span data-stu-id="10f32-148">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="10f32-149">Дополнительные сведения см. в [документации по библиотеке Azure Information Protection](https://docs.microsoft.com/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="10f32-149">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

<span data-ttu-id="10f32-150">Существующие метки Azure Information Protection без проблем работают с метками конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="10f32-150">Existing Azure Information Protection labels work seamlessly with sensitivity labels.</span></span> <span data-ttu-id="10f32-151">Например, можно одновременно использовать существующие метки Azure Information Protection и метки, которые применяются к документам и электронной почте.</span><span class="sxs-lookup"><span data-stu-id="10f32-151">For example, you can keep your existing Azure Information Protection labels and the labels that are applied to documents and email.</span></span>

<span data-ttu-id="10f32-152">Если имеются как метки конфиденциальности, так и метки Azure Information Protection, следует [перенести метки Azure Information Protection на метки конфиденциальности](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span><span class="sxs-lookup"><span data-stu-id="10f32-152">If you have both sensitivity and Azure Information Protection labels, you should [migrate your Azure Information Protection labels to sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span></span>

## <a name="example-classification-for-gdpr"></a><span data-ttu-id="10f32-153">Пример: классификация для GDPR</span><span class="sxs-lookup"><span data-stu-id="10f32-153">Example: Classification for GDPR</span></span>

<span data-ttu-id="10f32-154">Пример схемы классификации, включающей личные данные для GDPR, см. в статье [Разработка архитектуры схемы классификации для персональных данных](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span><span class="sxs-lookup"><span data-stu-id="10f32-154">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

## <a name="take-it-for-a-test-drive"></a><span data-ttu-id="10f32-155">Тестовый запуск</span><span class="sxs-lookup"><span data-stu-id="10f32-155">Take it for a test drive</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="10f32-157">Руководство по лаборатории тестирования: классификация данных</span><span class="sxs-lookup"><span data-stu-id="10f32-157">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="10f32-158">Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step2), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="10f32-158">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step2) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="10f32-159">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="10f32-159">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="10f32-160">Настройка усиленной защиты для Office 365</span><span class="sxs-lookup"><span data-stu-id="10f32-160">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

