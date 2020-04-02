---
title: Автоматическое применение метки конфиденциальности к содержимому
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: При создании метки конфиденциальности ее можно автоматически назначить документу или сообщению электронной почты или можно предложить пользователям выбрать рекомендованную метку.
ms.openlocfilehash: a087d142843ce74de3a930aea9286034b8617db6
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106075"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="bb8d6-103">Автоматическое применение метки конфиденциальности к содержимому</span><span class="sxs-lookup"><span data-stu-id="bb8d6-103">Apply a sensitivity label to content automatically</span></span>

><span data-ttu-id="bb8d6-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="bb8d6-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="bb8d6-105">При создании метки конфиденциальности ее можно автоматически назначить содержимому с конфиденциальной информацией или можно предложить пользователям применить рекомендованную метку.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-105">When you create a sensitivity label, you can automatically assign that label to content when it contains sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="bb8d6-106">Возможность автоматически применять метки конфиденциальности к содержимому важна, потому что:</span><span class="sxs-lookup"><span data-stu-id="bb8d6-106">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="bb8d6-107">вам не придется обучать пользователей работе со всеми категориями;</span><span class="sxs-lookup"><span data-stu-id="bb8d6-107">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="bb8d6-108">вам не нужно будет рассчитывать на то, что пользователи правильно классифицируют весь контент;</span><span class="sxs-lookup"><span data-stu-id="bb8d6-108">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="bb8d6-109">пользователям больше не нужно будет знать о ваших политиках — они могут сосредоточиться на своей работе.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-109">Users no longer need to know about your policies — they can instead focus on their work.</span></span>

<span data-ttu-id="bb8d6-110">Автоматическое применение меток в приложениях Office для Windows поддерживается клиентом унифицированных меток Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-110">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="bb8d6-111">Эта возможность для встроенных меток доступна только [в предварительной версии для некоторых приложений Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span><span class="sxs-lookup"><span data-stu-id="bb8d6-111">For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="bb8d6-112">Параметры автоматического присвоения меток в приложениях Office доступны при [создании и редактировании меток конфиденциальности](create-sensitivity-labels.md):</span><span class="sxs-lookup"><span data-stu-id="bb8d6-112">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md):</span></span>

![Параметры автоматического присвоения меток конфиденциальности](../media/sensitivity-labels-auto-labeling-options.png)

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="bb8d6-114">Настройка автоматического присвоения меток в приложениях Office</span><span class="sxs-lookup"><span data-stu-id="bb8d6-114">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="bb8d6-115">Одной из самых мощных функций меток чувствительности является возможность их автоматического применения к содержимому, которое соответствует определенным условиям.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-115">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches specific conditions.</span></span> <span data-ttu-id="bb8d6-116">В этом случае сотрудникам вашей организации не нужно будет самостоятельно присваивать метки конфиденциальности: Office 365 все сделает за них.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-116">In this case, people in your organization don't need to apply the sensitivity labels — Office 365 does the work for them.</span></span>

<span data-ttu-id="bb8d6-117">Вы можете автоматически присваивать метки конфиденциальности содержимому, если оно содержит определенные типы конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-117">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information.</span></span> <span data-ttu-id="bb8d6-118">Выберите классификаторы или типы конфиденциальной информации из списка:</span><span class="sxs-lookup"><span data-stu-id="bb8d6-118">Choose from a list of sensitive info types or classifers:</span></span>

![Условия автоматического присвоения меток в приложениях Office](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> <span data-ttu-id="bb8d6-120">В настоящее время параметр **классификаторов** доступен в ограниченной предварительной версии. Чтобы включить эту возможность для клиента, необходимо отправить форму в Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-120">Currently, the option for **Classifers** is in limited preview and requires you to submit a form to Microsoft to enable this capability for your tenant.</span></span> <span data-ttu-id="bb8d6-121">Дополнительные сведения см. в записи блога [Объявление об автоматическом присвоении меток в приложениях Office с использованием встроенных классификаторов — ограниченная предварительная версия](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span><span class="sxs-lookup"><span data-stu-id="bb8d6-121">For more information, see the blog post [Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span></span>

<span data-ttu-id="bb8d6-122">Если метка конфиденциальности применяется автоматически, пользователь видит соответствующее уведомление в своем приложении Office.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-122">When this sensitivity label is automatically applied, the user sees a notification in their Office app.</span></span> <span data-ttu-id="bb8d6-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="bb8d6-123">For example:</span></span>

![Уведомление о том, что к документу автоматически применена метка](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="bb8d6-125">Настройка типов конфиденциальной информации для метки</span><span class="sxs-lookup"><span data-stu-id="bb8d6-125">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="bb8d6-126">При выборе параметра **Типы конфиденциальной информации** вы видите тот же список типов конфиденциальной информации, что и при создании политики защиты от потери данных (DLP).</span><span class="sxs-lookup"><span data-stu-id="bb8d6-126">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="bb8d6-127">Например, вы можете автоматически применить метку "Строго конфиденциально" к любому содержимому с персональными данными (PII), такими как номера кредитных карт или номера социального страхования (SSN):</span><span class="sxs-lookup"><span data-stu-id="bb8d6-127">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:</span></span>

![Типы конфиденциальной информации для автоматического присвоения меток в приложениях Office](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="bb8d6-129">Выбрав типы конфиденциальной информации, вы можете уточнить условия, изменив количество экземпляров или точность совпадения.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-129">After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="bb8d6-130">Дополнительные сведения см. в разделе [Настройка правил для упрощения или усложнения сопоставления](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="bb8d6-130">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="bb8d6-131">Более того, можно задать условие, чтобы определялись все типы конфиденциальной информации или только один из них.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-131">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="bb8d6-132">Чтобы условия были более гибкими или сложными, можно добавлять группы и использовать логические операторы в отношении групп.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-132">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="bb8d6-133">Дополнительные сведения см. в разделе [Группировка и логические операторы](data-loss-prevention-policies.md#grouping-and-logical-operators).</span><span class="sxs-lookup"><span data-stu-id="bb8d6-133">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

![Параметры количества экземпляров и точности совпадения](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a><span data-ttu-id="bb8d6-135">Настройка классификаторов для метки</span><span class="sxs-lookup"><span data-stu-id="bb8d6-135">Configuring classifers for a label</span></span>

<span data-ttu-id="bb8d6-136">При выборе параметра **Классификаторы** укажите один или несколько встроенных классификаторов:</span><span class="sxs-lookup"><span data-stu-id="bb8d6-136">When you select the **Classifers** option, select one or more of the built-in classifiers:</span></span>

![Параметры классификаторов и меток конфиденциальности](../media/sensitivity-labels-classifers.png)

<span data-ttu-id="bb8d6-138">Дополнительные сведения об этих классификаторах см. в статье [Начало работы с обучаемыми классификаторами (предварительная версия)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="bb8d6-138">For more information about these classifers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="bb8d6-139">В течение периода использования предварительной версии следующие приложения поддерживают классификаторы для меток конфиденциальности:</span><span class="sxs-lookup"><span data-stu-id="bb8d6-139">During the preview period, the following apps support classifers for sensitivity labels:</span></span>

- <span data-ttu-id="bb8d6-140">Классические приложения Office 365 профессиональный плюс для Windows от [участников программы предварительной оценки Office](https://office.com/insider):</span><span class="sxs-lookup"><span data-stu-id="bb8d6-140">Office 365 ProPlus desktop apps for Windows, from [Office Insider](https://office.com/insider):</span></span>
    - <span data-ttu-id="bb8d6-141">Word</span><span class="sxs-lookup"><span data-stu-id="bb8d6-141">Word</span></span>
    - <span data-ttu-id="bb8d6-142">Excel</span><span class="sxs-lookup"><span data-stu-id="bb8d6-142">Excel</span></span>
    - <span data-ttu-id="bb8d6-143">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="bb8d6-143">PowerPoint</span></span>

- <span data-ttu-id="bb8d6-144">Приложения Office для Интернета, если [включены метки конфиденциальности для файлов Office в SharePoint и OneDrive (общедоступная предварительная версия)](sensitivity-labels-sharepoint-onedrive-files.md):</span><span class="sxs-lookup"><span data-stu-id="bb8d6-144">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="bb8d6-145">Word</span><span class="sxs-lookup"><span data-stu-id="bb8d6-145">Word</span></span>
    - <span data-ttu-id="bb8d6-146">Excel</span><span class="sxs-lookup"><span data-stu-id="bb8d6-146">Excel</span></span>
    - <span data-ttu-id="bb8d6-147">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="bb8d6-147">PowerPoint</span></span>
    - <span data-ttu-id="bb8d6-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="bb8d6-148">Outlook</span></span>

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="bb8d6-149">Рекомендация пользователю о применении метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="bb8d6-149">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="bb8d6-150">Если нужно, можно рекомендовать пользователю применить метку.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-150">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="bb8d6-151">Этот вариант позволяет пользователям принять классификацию и соответствующую защиту или отклонить рекомендацию, если метка не подходит для содержания.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-151">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

![Параметр для рекомендации метки конфиденциальности пользователям](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="bb8d6-153">Ниже приведен пример запроса от клиента унифицированной маркировки Azure Information Protection, когда вы настраиваете условие для применения метки в качестве рекомендуемого действия с подсказкой настраиваемой политики.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-153">Here's an example of a prompt from the Azure Information Protection unified labeling client when you configure a condition to apply a label as a recommended action, with a custom policy tip.</span></span> <span data-ttu-id="bb8d6-154">Вы можете выбрать, какой текст будет отображаться в подсказке политики.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-154">You can choose what text is displayed in the policy tip.</span></span>

![Предложение применить рекомендованную метку](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="bb8d6-156">Применение автоматических или рекомендованных меток</span><span class="sxs-lookup"><span data-stu-id="bb8d6-156">How automatic or recommended labels are applied</span></span>

<span data-ttu-id="bb8d6-157">Реализация автоматической и рекомендуемой маркировки в приложениях Office зависит от того, используете ли вы встроенную в Office маркировку или клиента унифицированной маркировки Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-157">The implementation of automatic and recommended labeling in Office apps depend on whether you're using labeling that's built into Office, or the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="bb8d6-158">Однако в обоих случаях:</span><span class="sxs-lookup"><span data-stu-id="bb8d6-158">In both cases, however:</span></span>

- <span data-ttu-id="bb8d6-159">Вы не можете использовать автоматическое присвоение меток для документов и сообщений электронной почты, которым ранее была присвоена метка вручную или которым ранее была автоматически присвоена метка более высокого уровня конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-159">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity.</span></span> <span data-ttu-id="bb8d6-160">Помните, что к документу или сообщению можно применить только одну метку конфиденциальности (в дополнение к одной метке хранения).</span><span class="sxs-lookup"><span data-stu-id="bb8d6-160">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="bb8d6-161">Вы не можете использовать рекомендуемую маркировку для документов или электронных писем, которые ранее были маркированы с более высокой чувствительностью.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-161">You can't use recommended labeling for documents or emails that were previously labeled with a higher sensitivity.</span></span> <span data-ttu-id="bb8d6-162">Для содержимого с меткой более высокого уровня конфиденциальности рекомендация с подсказкой политики не отображается.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-162">When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

<span data-ttu-id="bb8d6-163">Специфично для встроенной маркировки:</span><span class="sxs-lookup"><span data-stu-id="bb8d6-163">Specific to built-in labeling:</span></span>

- <span data-ttu-id="bb8d6-164">Не все приложения Office поддерживают автоматическую (и рекомендуемую) маркировку.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-164">Not all Office apps support automatic (and recommended) labeling.</span></span> <span data-ttu-id="bb8d6-165">Для получения дополнительной информации см. [Поддержка возможностей меток чувствительности в приложениях](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span><span class="sxs-lookup"><span data-stu-id="bb8d6-165">For more information, see [Support for sensitivity label capabilities in apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

- <span data-ttu-id="bb8d6-166">Для рекомендованных меток в настольных версиях Word конфиденциальный контент, вызвавший рекомендацию, помечается, чтобы пользователи могли просматривать и удалять конфиденциальный контент вместо применения рекомендуемой метки чувствительности.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-166">For recommended labels in the desktop versions of Word, the sensitive content that triggered the recommendation is flagged so that users can review and remove the sensitive content instead of applying the recommended sensitivity label.</span></span>

- <span data-ttu-id="bb8d6-167">Подробные сведения о том, как эти метки применяются в приложениях Office, примеры снимков экрана и способ обнаружения конфиденциальной информации, см. в разделе [Автоматически применять или рекомендовать метки чувствительности к файлам и сообщениям электронной почты в Office](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).</span><span class="sxs-lookup"><span data-stu-id="bb8d6-167">For details about how these labels are applied in Office apps, example screenshots, and how sensitive information is detected, see [Automatically apply or recommend sensitivity labels to your files and emails in Office](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).</span></span>

<span data-ttu-id="bb8d6-168">Для клиента унифицированной маркировки Azure Information Protection:</span><span class="sxs-lookup"><span data-stu-id="bb8d6-168">Specific to the Azure Information Protection unified labeling client:</span></span>

-  <span data-ttu-id="bb8d6-169">Автоматическая и рекомендуемая маркировка применяется к Word, Excel и PowerPoint при сохранении документа и к Outlook при отправке электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-169">Automatic and recommended labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span>

- <span data-ttu-id="bb8d6-170">Чтобы Outlook поддерживал рекомендуемую маркировку, сначала необходимо настроить [расширенный параметр политики](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook).</span><span class="sxs-lookup"><span data-stu-id="bb8d6-170">For Outlook to support recommended labeling, you must first configure an [advanced policy setting](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook).</span></span>

- <span data-ttu-id="bb8d6-171">Конфиденциальная информация может быть обнаружена в основном тексте документов и электронных писем, а также в верхних и нижних колонтитулах, но не в строке темы или вложениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-171">Sensitive information can be detected in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="bb8d6-172">Оценка нескольких условий для нескольких меток</span><span class="sxs-lookup"><span data-stu-id="bb8d6-172">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="bb8d6-p115">Метки оцениваются в порядке, в котором они указаны в политике: первая метка имеет наименьший приоритет (самый низкий уровень конфиденциальности), а последняя — наибольший приоритет (самый высокий уровень конфиденциальности). Дополнительные сведения о приоритете см. в разделе "Приоритет метки (важен порядок)" [этой статьи](sensitivity-labels.md#label-priority-order-matters).</span><span class="sxs-lookup"><span data-stu-id="bb8d6-p115">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="bb8d6-175">Не настраивайте родительскую метку для автоматического применения или в качестве рекомендуемой</span><span class="sxs-lookup"><span data-stu-id="bb8d6-175">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="bb8d6-176">Помните, что нельзя применять родительскую метку (метку с подчиненными метками) к содержимому.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-176">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="bb8d6-177">Не настраивайте родительскую метку на автоматическое применение или в качестве рекомендуемой, так как родительская метка не применяется к содержимому в приложениях Office, использующих унифицированный клиент присвоения меток Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-177">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="bb8d6-178">Дополнительные сведения о родительских и подчиненных метках см. в статье [Подчиненные метки (метки группирования)](sensitivity-labels.md#sublabels-grouping-labels).</span><span class="sxs-lookup"><span data-stu-id="bb8d6-178">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>
