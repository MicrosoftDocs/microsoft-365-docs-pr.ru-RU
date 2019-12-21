---
title: Автоматическое применение метки конфиденциальности к содержимому
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: 12/13/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: При создании метки конфиденциальности ее можно автоматически назначить документу или сообщению электронной почты или можно предложить пользователям выбрать рекомендованную метку.
ms.openlocfilehash: 77a0b3cdf88301677451fe7fe1bac58de2a40a5f
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807844"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="6909f-103">Автоматическое применение метки конфиденциальности к содержимому</span><span class="sxs-lookup"><span data-stu-id="6909f-103">Apply a sensitivity label to content automatically</span></span>

<span data-ttu-id="6909f-104">При создании метки конфиденциальности ее можно автоматически назначить содержимому с конфиденциальной информацией или можно предложить пользователям применить рекомендованную метку.</span><span class="sxs-lookup"><span data-stu-id="6909f-104">When you create a sensitivity label, you can automatically assign that label to content containing sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="6909f-105">Возможность автоматически применять метки конфиденциальности к содержимому важна, потому что:</span><span class="sxs-lookup"><span data-stu-id="6909f-105">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="6909f-106">вам не придется обучать пользователей работе со всеми категориями;</span><span class="sxs-lookup"><span data-stu-id="6909f-106">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="6909f-107">вам не нужно будет рассчитывать на то, что пользователи правильно классифицируют весь контент;</span><span class="sxs-lookup"><span data-stu-id="6909f-107">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="6909f-108">пользователям больше не нужно будет знать о ваших политиках — они могут сосредоточиться на своей работе.</span><span class="sxs-lookup"><span data-stu-id="6909f-108">Users no longer need to know about your policies - they can instead focus on their work.</span></span>

<span data-ttu-id="6909f-109">Сведения о требованиях к лицензиям см. в разделе [Требования к подпискам и лицензированию для меток конфиденциальности](sensitivity-labels-office-apps.md#subscription-and-licensing-requirements-for-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="6909f-109">For information about license requirements, see [Subscription and licensing requirements for sensitivity labels](sensitivity-labels-office-apps.md#subscription-and-licensing-requirements-for-sensitivity-labels).</span></span>

<span data-ttu-id="6909f-110">Параметры автоматического применения меток доступны при создании метки конфиденциальности в Центре соответствия требованиям Microsoft 365, Центре безопасности Microsoft 365 и Центре безопасности и соответствия требованиям Office 365 в разделе **Классификация** > **Метки конфиденциальности**.</span><span class="sxs-lookup"><span data-stu-id="6909f-110">The auto-labeling settings are available when you create a sensitivity label in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center under **Classification** > **Sensitivity labels**.</span></span>

![Параметры автоматического присвоения меток конфиденциальности](media/Sensitivity-labels-Auto-labeling-options.png)

## <a name="apply-a-sensitivity-label-automatically-based-on-conditions"></a><span data-ttu-id="6909f-112">Автоматическое присвоение меток конфиденциальности в соответствии с условиями</span><span class="sxs-lookup"><span data-stu-id="6909f-112">Apply a sensitivity label automatically based on conditions</span></span>

<span data-ttu-id="6909f-113">Одно из главных преимуществ меток конфиденциальности — возможность автоматически их присваивать содержимому, которое соответствует определенным условиям.</span><span class="sxs-lookup"><span data-stu-id="6909f-113">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches certain conditions.</span></span> <span data-ttu-id="6909f-114">В этом случае сотрудникам вашей организации не нужно будет самостоятельно присваивать метки конфиденциальности: Office 365 все сделает за них.</span><span class="sxs-lookup"><span data-stu-id="6909f-114">In this case, people in your organization don't need to apply the sensitivity labels — Office 365 does the work for them.</span></span>

<span data-ttu-id="6909f-p102">Вы можете настроить автоматическое применение меток конфиденциальности к содержимому, которое содержит определенные типы конфиденциальной информации. При настройке меток конфиденциальности, которые будут применяться, отображается тот же список типов конфиденциальной информации, что и при создании политики защиты от потери данных. Поэтому вы можете, например, применить метку "Строго конфиденциально" к любому содержимому с персональными данными клиента, такими как номера кредитных карт или номера социального страхования.</span><span class="sxs-lookup"><span data-stu-id="6909f-p102">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information. When you configure a sensitivity label to be applied automatically, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy. So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers.</span></span>

![Параметры количества экземпляров и точности совпадения](media/Sensitivity-labels-instance-count-match-accuracy.png)

<span data-ttu-id="6909f-119">После выбора типов конфиденциальной информации вы можете уточнить условия, изменив количество экземпляров или точность совпадения.</span><span class="sxs-lookup"><span data-stu-id="6909f-119">After you choose your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="6909f-120">Дополнительные сведения см. в разделе [Настройка правил для упрощения или усложнения сопоставления](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="6909f-120">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="6909f-121">Более того, можно задать условие, чтобы определялись все типы конфиденциальной информации или только один из них.</span><span class="sxs-lookup"><span data-stu-id="6909f-121">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="6909f-122">Чтобы условия были более гибкими или сложными, можно добавлять группы и использовать логические операторы в отношении групп.</span><span class="sxs-lookup"><span data-stu-id="6909f-122">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="6909f-123">Дополнительные сведения см. в разделе [Группировка и логические операторы](data-loss-prevention-policies.md#grouping-and-logical-operators).</span><span class="sxs-lookup"><span data-stu-id="6909f-123">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

<span data-ttu-id="6909f-p105">Если метка конфиденциальности применяется автоматически, пользователь видит соответствующее уведомление в своем приложении Office. Он может нажать кнопку **ОК**, чтобы закрыть уведомление.</span><span class="sxs-lookup"><span data-stu-id="6909f-p105">When a sensitivity label is automatically applied, the user sees a notification in their Office app. They can choose **OK** to dismiss the notification.</span></span>

![Уведомление о том, что к документу автоматически применена метка](media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="6909f-127">Рекомендация пользователю о применении метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="6909f-127">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="6909f-128">Если нужно, можно рекомендовать пользователю применить метку.</span><span class="sxs-lookup"><span data-stu-id="6909f-128">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="6909f-129">Этот вариант позволяет пользователям принять классификацию и соответствующую защиту или отклонить рекомендацию, если метка не подходит для документа или сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6909f-129">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their document or email.</span></span>

<span data-ttu-id="6909f-130">Рекомендация меток поддерживается в Word, PowerPoint и Excel (также требуется установка унифицированного клиента присвоения меток Azure Information Protection).</span><span class="sxs-lookup"><span data-stu-id="6909f-130">Recommended labels are supported in Word, PowerPoint, and Excel (and require that the Azure Information Protection unified labeling client is installed).</span></span>

![Параметр для рекомендации метки конфиденциальности пользователям](media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="6909f-p107">Ниже представлен пример рекомендации о применении метки с пользовательской подсказкой о политике, которая отображается во время настройки условия. Вы можете указать текст, отображаемый в подсказке о политике.</span><span class="sxs-lookup"><span data-stu-id="6909f-p107">Here's an example of a prompt when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![Предложение применить рекомендованную метку](media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="6909f-135">Применение автоматических или рекомендованных меток</span><span class="sxs-lookup"><span data-stu-id="6909f-135">How automatic or recommended labels are applied</span></span>

- <span data-ttu-id="6909f-136">Автоматическое применение меток используется в Word, Excel и PowerPoint, когда сохраняются документы, и в Outlook, когда отправляются сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6909f-136">Automatic labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span> <span data-ttu-id="6909f-137">Настраиваемые условия могут определять конфиденциальную информацию в тексте документов и сообщений, верхних и нижних колонтитулах, но не в строке темы или вложениях к сообщениям.</span><span class="sxs-lookup"><span data-stu-id="6909f-137">These conditions detect sensitive information in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

- <span data-ttu-id="6909f-138">Вы не можете использовать автоматическую классификацию для документов и сообщений электронной почты, которым ранее была присвоена метка вручную или которым ранее автоматически была присвоена метка классификации более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="6909f-138">You can't use automatic classification for documents and emails that were previously manually labeled, or previously automatically labeled with a higher classification.</span></span> <span data-ttu-id="6909f-139">Помните, что к документу или сообщению можно применить только одну метку конфиденциальности (в дополнение к одной метке хранения).</span><span class="sxs-lookup"><span data-stu-id="6909f-139">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="6909f-140">Рекомендованная классификация применяется в Word, Excel и PowerPoint при сохранении документов.</span><span class="sxs-lookup"><span data-stu-id="6909f-140">Recommended classification applies to Word, Excel, and PowerPoint when you save documents.</span></span>

- <span data-ttu-id="6909f-141">Нельзя использовать рекомендованную классификацию для документов, которым ранее была присвоена метка классификации более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="6909f-141">You can't use recommended classification for documents that were previously labeled with a higher classification.</span></span> <span data-ttu-id="6909f-142">В таких случаях для содержимого с меткой классификации более высокого уровня пользователю не отображается рекомендация с подсказкой о политике.</span><span class="sxs-lookup"><span data-stu-id="6909f-142">When the content's already labeled with a higher classification, the user won't see the prompt with the recommendation and policy tip.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="6909f-143">Оценка нескольких условий для нескольких меток</span><span class="sxs-lookup"><span data-stu-id="6909f-143">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="6909f-p111">Метки оцениваются в порядке, в котором они указаны в политике: первая метка имеет наименьший приоритет (самый низкий уровень конфиденциальности), а последняя — наибольший приоритет (самый высокий уровень конфиденциальности). Дополнительные сведения о приоритете см. в разделе "Приоритет метки (важен порядок)" [этой статьи](sensitivity-labels.md#label-priority-order-matters).</span><span class="sxs-lookup"><span data-stu-id="6909f-p111">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="6909f-146">Не настраивайте родительскую метку для автоматического применения или в качестве рекомендуемой</span><span class="sxs-lookup"><span data-stu-id="6909f-146">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="6909f-147">Помните, что нельзя применять родительскую метку (метку с подчиненными метками) к содержимому.</span><span class="sxs-lookup"><span data-stu-id="6909f-147">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="6909f-148">Не настраивайте родительскую метку на автоматическое применение или в качестве рекомендуемой, так как родительская метка не применяется к содержимому в приложениях Office, использующих унифицированный клиент присвоения меток Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="6909f-148">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="6909f-149">Дополнительные сведения о родительских и подчиненных метках см. в статье [Подчиненные метки (метки группирования)](sensitivity-labels.md#sublabels-grouping-labels).</span><span class="sxs-lookup"><span data-stu-id="6909f-149">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>
