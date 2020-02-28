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
ms.openlocfilehash: a1ea81bf8c65d3f54d26b19eae3b590f11283c30
ms.sourcegitcommit: 109b44aa71bb8453d0a602663df0fcf7ed7dfdbe
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/25/2020
ms.locfileid: "42277216"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="58360-103">Автоматическое применение метки конфиденциальности к содержимому</span><span class="sxs-lookup"><span data-stu-id="58360-103">Apply a sensitivity label to content automatically</span></span>

<span data-ttu-id="58360-104">При создании метки конфиденциальности ее можно автоматически назначить содержимому с конфиденциальной информацией или можно предложить пользователям применить рекомендованную метку.</span><span class="sxs-lookup"><span data-stu-id="58360-104">When you create a sensitivity label, you can automatically assign that label to content when it contains sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="58360-105">Возможность автоматически применять метки конфиденциальности к содержимому важна, потому что:</span><span class="sxs-lookup"><span data-stu-id="58360-105">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="58360-106">вам не придется обучать пользователей работе со всеми категориями;</span><span class="sxs-lookup"><span data-stu-id="58360-106">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="58360-107">вам не нужно будет рассчитывать на то, что пользователи правильно классифицируют весь контент;</span><span class="sxs-lookup"><span data-stu-id="58360-107">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="58360-108">пользователям больше не нужно будет знать о ваших политиках — они могут сосредоточиться на своей работе.</span><span class="sxs-lookup"><span data-stu-id="58360-108">Users no longer need to know about your policies — they can instead focus on their work.</span></span>

<span data-ttu-id="58360-109">Автоматическое применение меток в приложениях Office для Windows поддерживается клиентом унифицированных меток Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="58360-109">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="58360-110">Эта возможность для встроенных меток доступна только [в предварительной версии для некоторых приложений Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span><span class="sxs-lookup"><span data-stu-id="58360-110">For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="58360-111">Параметры автоматического присвоения меток в приложениях Office доступны при [создании и редактировании меток конфиденциальности](create-sensitivity-labels.md):</span><span class="sxs-lookup"><span data-stu-id="58360-111">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md):</span></span>

![Параметры автоматического присвоения меток конфиденциальности](../media/sensitivity-labels-auto-labeling-options.png)

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="58360-113">Настройка автоматического присвоения меток в приложениях Office</span><span class="sxs-lookup"><span data-stu-id="58360-113">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="58360-114">Одно из главных преимуществ меток конфиденциальности — возможность автоматически их присваивать содержимому, которое соответствует определенным условиям.</span><span class="sxs-lookup"><span data-stu-id="58360-114">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches certain conditions.</span></span> <span data-ttu-id="58360-115">В этом случае сотрудникам вашей организации не нужно будет самостоятельно присваивать метки конфиденциальности: Office 365 все сделает за них.</span><span class="sxs-lookup"><span data-stu-id="58360-115">In this case, people in your organization don't need to apply the sensitivity labels — Office 365 does the work for them.</span></span>

<span data-ttu-id="58360-116">Вы можете автоматически присваивать метки конфиденциальности содержимому, если оно содержит определенные типы конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="58360-116">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information.</span></span> <span data-ttu-id="58360-117">Выберите классификаторы или типы конфиденциальной информации из списка:</span><span class="sxs-lookup"><span data-stu-id="58360-117">Choose from a list of sensitive info types or classifers:</span></span>

![Условия автоматического присвоения меток в приложениях Office](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> <span data-ttu-id="58360-119">В настоящее время параметр **классификаторов** доступен в ограниченной предварительной версии. Чтобы включить эту возможность для клиента, необходимо отправить форму в Microsoft.</span><span class="sxs-lookup"><span data-stu-id="58360-119">Currently, the option for **Classifers** is in limited preview and requires you to submit a form to Microsoft to enable this capability for your tenant.</span></span> <span data-ttu-id="58360-120">Дополнительные сведения см. в записи блога [Объявление об автоматическом присвоении меток в приложениях Office с использованием встроенных классификаторов — ограниченная предварительная версия](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span><span class="sxs-lookup"><span data-stu-id="58360-120">For more information, see the blog post [Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span></span>

<span data-ttu-id="58360-121">Если метка конфиденциальности применяется автоматически, пользователь видит соответствующее уведомление в своем приложении Office.</span><span class="sxs-lookup"><span data-stu-id="58360-121">When this sensitivity label is automatically applied, the user sees a notification in their Office app.</span></span> <span data-ttu-id="58360-122">Он может нажать кнопку **OK**, чтобы закрыть уведомление.</span><span class="sxs-lookup"><span data-stu-id="58360-122">They can choose **OK** to dismiss the notification.</span></span>

![Уведомление о том, что к документу автоматически применена метка](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="58360-124">Настройка типов конфиденциальной информации для метки</span><span class="sxs-lookup"><span data-stu-id="58360-124">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="58360-125">При выборе параметра **Типы конфиденциальной информации** вы видите тот же список типов конфиденциальной информации, что и при создании политики защиты от потери данных (DLP).</span><span class="sxs-lookup"><span data-stu-id="58360-125">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="58360-126">Например, вы можете автоматически применить метку "Строго конфиденциально" к любому содержимому с персональными данными (PII), такими как номера кредитных карт или номера социального страхования (SSN):</span><span class="sxs-lookup"><span data-stu-id="58360-126">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:</span></span>

![Типы конфиденциальной информации для автоматического присвоения меток в приложениях Office](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="58360-128">Выбрав типы конфиденциальной информации, вы можете уточнить условия, изменив количество экземпляров или точность совпадения.</span><span class="sxs-lookup"><span data-stu-id="58360-128">After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="58360-129">Дополнительные сведения см. в разделе [Настройка правил для упрощения или усложнения сопоставления](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="58360-129">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="58360-130">Более того, можно задать условие, чтобы определялись все типы конфиденциальной информации или только один из них.</span><span class="sxs-lookup"><span data-stu-id="58360-130">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="58360-131">Чтобы условия были более гибкими или сложными, можно добавлять группы и использовать логические операторы в отношении групп.</span><span class="sxs-lookup"><span data-stu-id="58360-131">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="58360-132">Дополнительные сведения см. в разделе [Группировка и логические операторы](data-loss-prevention-policies.md#grouping-and-logical-operators).</span><span class="sxs-lookup"><span data-stu-id="58360-132">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

![Параметры количества экземпляров и точности совпадения](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a><span data-ttu-id="58360-134">Настройка классификаторов для метки</span><span class="sxs-lookup"><span data-stu-id="58360-134">Configuring classifers for a label</span></span>

<span data-ttu-id="58360-135">При выборе параметра **Классификаторы** укажите один или несколько встроенных классификаторов:</span><span class="sxs-lookup"><span data-stu-id="58360-135">When you select the **Classifers** option, select one or more of the built-in classifiers:</span></span>

![Параметры классификаторов и меток конфиденциальности](../media/sensitivity-labels-classifers.png)

<span data-ttu-id="58360-137">Дополнительные сведения об этих классификаторах см. в статье [Начало работы с обучаемыми классификаторами (предварительная версия)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="58360-137">For more information about these classifers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="58360-138">В течение периода использования предварительной версии следующие приложения поддерживают классификаторы для меток конфиденциальности:</span><span class="sxs-lookup"><span data-stu-id="58360-138">During the preview period, the following apps support classifers for sensitivity labels:</span></span>

- <span data-ttu-id="58360-139">Классические приложения Office 365 профессиональный плюс для Windows от [участников программы предварительной оценки Office](https://office.com/insider):</span><span class="sxs-lookup"><span data-stu-id="58360-139">Office 365 ProPlus desktop apps for Windows, from [Office Insider](https://office.com/insider):</span></span>
    - <span data-ttu-id="58360-140">Word</span><span class="sxs-lookup"><span data-stu-id="58360-140">Word</span></span>
    - <span data-ttu-id="58360-141">Excel</span><span class="sxs-lookup"><span data-stu-id="58360-141">Excel</span></span>
    - <span data-ttu-id="58360-142">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="58360-142">PowerPoint</span></span>

- <span data-ttu-id="58360-143">Приложения Office для Интернета, если [включены метки конфиденциальности для файлов Office в SharePoint и OneDrive (общедоступная предварительная версия)](sensitivity-labels-sharepoint-onedrive-files.md):</span><span class="sxs-lookup"><span data-stu-id="58360-143">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="58360-144">Word</span><span class="sxs-lookup"><span data-stu-id="58360-144">Word</span></span>
    - <span data-ttu-id="58360-145">Excel</span><span class="sxs-lookup"><span data-stu-id="58360-145">Excel</span></span>
    - <span data-ttu-id="58360-146">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="58360-146">PowerPoint</span></span>
    - <span data-ttu-id="58360-147">Outlook</span><span class="sxs-lookup"><span data-stu-id="58360-147">Outlook</span></span>

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="58360-148">Рекомендация пользователю о применении метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="58360-148">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="58360-149">Если нужно, можно рекомендовать пользователю применить метку.</span><span class="sxs-lookup"><span data-stu-id="58360-149">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="58360-150">Этот вариант позволяет пользователям принять классификацию и соответствующую защиту или отклонить рекомендацию, если метка не подходит для содержания.</span><span class="sxs-lookup"><span data-stu-id="58360-150">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

<span data-ttu-id="58360-151">Рекомендуемые метки поддерживаются в Word, PowerPoint и Excel.</span><span class="sxs-lookup"><span data-stu-id="58360-151">Recommended labels are supported for Word, PowerPoint, and Excel.</span></span>

![Параметр для рекомендации метки конфиденциальности пользователям](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="58360-p110">Ниже представлен пример рекомендации о применении метки с пользовательской подсказкой о политике, которая отображается во время настройки условия. Вы можете указать текст, отображаемый в подсказке о политике.</span><span class="sxs-lookup"><span data-stu-id="58360-p110">Here's an example of a prompt when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![Предложение применить рекомендованную метку](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="58360-156">Применение автоматических или рекомендованных меток</span><span class="sxs-lookup"><span data-stu-id="58360-156">How automatic or recommended labels are applied</span></span>

- <span data-ttu-id="58360-157">Автоматическое применение меток используется в Word, Excel и PowerPoint, когда сохраняются документы, и в Outlook, когда отправляются сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="58360-157">Automatic labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span> <span data-ttu-id="58360-158">Настраиваемые условия могут определять конфиденциальную информацию в тексте документов и сообщений, верхних и нижних колонтитулах, но не в строке темы или вложениях к сообщениям.</span><span class="sxs-lookup"><span data-stu-id="58360-158">These conditions detect sensitive information in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

- <span data-ttu-id="58360-159">Вы не можете использовать автоматическое присвоение меток для документов и сообщений электронной почты, которым ранее была присвоена метка вручную или которым ранее была автоматически присвоена метка более высокого уровня конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="58360-159">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity.</span></span> <span data-ttu-id="58360-160">Помните, что к документу или сообщению можно применить только одну метку конфиденциальности (в дополнение к одной метке хранения).</span><span class="sxs-lookup"><span data-stu-id="58360-160">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="58360-161">Рекомендованное присвоение меток применяется в Word, Excel и PowerPoint при сохранении документов.</span><span class="sxs-lookup"><span data-stu-id="58360-161">Recommended labeling applies to Word, Excel, and PowerPoint when you save documents.</span></span>

- <span data-ttu-id="58360-162">Нельзя использовать рекомендованное присвоение меток для документов, которым ранее была присвоена метка более высокого уровня конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="58360-162">You can't use recommended labeling for documents that were previously labeled with a higher sensitivity.</span></span> <span data-ttu-id="58360-163">Для содержимого с меткой более высокого уровня конфиденциальности рекомендация с подсказкой политики не отображается.</span><span class="sxs-lookup"><span data-stu-id="58360-163">When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="58360-164">Оценка нескольких условий для нескольких меток</span><span class="sxs-lookup"><span data-stu-id="58360-164">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="58360-p114">Метки оцениваются в порядке, в котором они указаны в политике: первая метка имеет наименьший приоритет (самый низкий уровень конфиденциальности), а последняя — наибольший приоритет (самый высокий уровень конфиденциальности). Дополнительные сведения о приоритете см. в разделе "Приоритет метки (важен порядок)" [этой статьи](sensitivity-labels.md#label-priority-order-matters).</span><span class="sxs-lookup"><span data-stu-id="58360-p114">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="58360-167">Не настраивайте родительскую метку для автоматического применения или в качестве рекомендуемой</span><span class="sxs-lookup"><span data-stu-id="58360-167">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="58360-168">Помните, что нельзя применять родительскую метку (метку с подчиненными метками) к содержимому.</span><span class="sxs-lookup"><span data-stu-id="58360-168">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="58360-169">Не настраивайте родительскую метку на автоматическое применение или в качестве рекомендуемой, так как родительская метка не применяется к содержимому в приложениях Office, использующих унифицированный клиент присвоения меток Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="58360-169">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="58360-170">Дополнительные сведения о родительских и подчиненных метках см. в статье [Подчиненные метки (метки группирования)](sensitivity-labels.md#sublabels-grouping-labels).</span><span class="sxs-lookup"><span data-stu-id="58360-170">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>
