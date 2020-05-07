---
title: Разработка архитектуры схемы классификации для персональных данных
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Определите, целесообразно ли вашей организации внедрять метки в рамках плана по соблюдению Общего регламента по защите данных (GDPR).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17484e56206ba8f32db3c779623f2f8d7ed57496
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035171"
---
# <a name="architect-a-classification-schema-for-personal-data"></a><span data-ttu-id="7829a-103">Разработка архитектуры схемы классификации для персональных данных</span><span class="sxs-lookup"><span data-stu-id="7829a-103">Architect a classification schema for personal data</span></span>

<span data-ttu-id="7829a-p101">В предыдущих статьях из этой серии рассматривалось использование типов конфиденциальной информации для определения персональных данных, подпадающих под действие регламента GDPR. Типы конфиденциальной информации — это разновидность классификации. Возможно, вам понадобится только эта классификация. Тем не менее многие организации внедряют более широкую стратегию управления данными с использованием меток. Ознакомьтесь с этой статьей, чтобы решить, нужно ли вам внедрять метки в рамках своего плана по соблюдению регламента GDPR. Если вы примете это решение, воспользуйтесь инструкциями и примерами, приведенными в настоящей статье.</span><span class="sxs-lookup"><span data-stu-id="7829a-p101">Previous articles in this series focus on using sensitive information types to identify personal data that is subject to GDPR. Sensitive information types are a form of classification. This might be all the classification you need. However, many organizations implement a broader data governance strategy using labels. Use this topic to decide if you also want to implement labels as part of your GDPR plan. If you do, this topic provides some guidance and examples.</span></span>

<span data-ttu-id="7829a-p102">Примечание. Определение схемы классификации для организации и настройка политики, меток и условий требуют тщательного планирования и подготовки. Важно понимать, что за этот процесс не отвечает ваш ИТ-отдел. При разработке соответствующей схемы классификации и применения меток для данных вашей организации обязательно сотрудничайте со своим юридическим отделом и группой по обеспечению соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="7829a-p102">Note: Defining a classification schema for an organization and configuring policies, labels, and conditions requires careful planning and preparation. It's important to realize that this isn't an IT driven process. Be sure to work with your legal and compliance team to develop an appropriate classification and labeling schema for your organization's data.</span></span>

## <a name="decide-if-youre-using-labels-in-addition-to-sensitive-data-types"></a><span data-ttu-id="7829a-113">Принятие решения о целесообразности использования меток в дополнение к типам конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="7829a-113">Decide if you're using labels in addition to sensitive data types</span></span>

<span data-ttu-id="7829a-p103">Вы можете воспользоваться одним из двух подходов к классификации персональных данных в Microsoft 365. Любой из них можно применить для защиты данных в соответствии с регламентом GDPR. Если вы решили использовать для классификации только типы конфиденциальной информации, можете пропустить оставшуюся часть этой статьи.</span><span class="sxs-lookup"><span data-stu-id="7829a-p103">You can take one of two approaches for classification in Microsoft 365 for personal information. Either of these can be used for GDPR protection. If you decide to use only sensitive information types for classification, you can skip the rest of this topic.</span></span>

<span data-ttu-id="7829a-117">Выберите один из приведенных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="7829a-117">Choose one of the following options.</span></span>

### <a name="option-1-use-only-microsoft-365-sensitive-information-types"></a><span data-ttu-id="7829a-118">Вариант 1. Использование только типов конфиденциальной информации Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7829a-118">Option 1: Use only Microsoft 365 sensitive information types</span></span>

- <span data-ttu-id="7829a-119">Типы конфиденциальной информации целесообразно использовать для определения и защиты персональных данных, которые подпадают под действие регламента GDPR и других типов нормативных требований.</span><span class="sxs-lookup"><span data-stu-id="7829a-119">Sensitive information types work well to identify and protect personal data subject to GDPR and other types of regulations.</span></span>

- <span data-ttu-id="7829a-120">Этот вариант более простой, чем расширенный план по управлению данными с использованием меток.</span><span class="sxs-lookup"><span data-stu-id="7829a-120">These are simpler to use if your organization doesn't already have or plan to implement a broader data governance plan using labels.</span></span>

- <span data-ttu-id="7829a-121">Типы конфиденциальной информации используются с правилами защиты от потери данных (как и метки хранения).</span><span class="sxs-lookup"><span data-stu-id="7829a-121">These work with DLP rules (so do retention labels).</span></span>

- <span data-ttu-id="7829a-122">Типы конфиденциальной информации можно применять с Cloud App Security для обнаружения конфиденциальной информации в других приложениях SaaS.</span><span class="sxs-lookup"><span data-stu-id="7829a-122">Sensitive information types work with Cloud App Security so you can detect sensitive information in other SaaS apps.</span></span>

### <a name="option-2-use-sensitive-information-types--retention-labels"></a><span data-ttu-id="7829a-123">Вариант 2. Использование типов конфиденциальной информации и меток хранения</span><span class="sxs-lookup"><span data-stu-id="7829a-123">Option 2: Use sensitive information types + retention labels</span></span>

- <span data-ttu-id="7829a-124">Типы конфиденциальной информации нужны для автоматического применения меток к персональным данным, на которые распространяется регламент GDPR.</span><span class="sxs-lookup"><span data-stu-id="7829a-124">You'll need sensitive information types to automatically apply labels to personal data that is subject to GDPR, so these are a prerequisite.</span></span>

- <span data-ttu-id="7829a-125">Метки хранения позволяют включить персональные данные, на которые распространяется регламент GDPR, в расширенный план по управлению данными для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7829a-125">Using retention labels allows you to include personal data that is subject to GDPR into a broader data governance plan for your organization.</span></span>

## <a name="develop-a-label-schema-that-includes-personal-data"></a><span data-ttu-id="7829a-126">Разработка схемы меток, включающей персональные данные</span><span class="sxs-lookup"><span data-stu-id="7829a-126">Develop a label schema that includes personal data</span></span>

<span data-ttu-id="7829a-p104">Прежде чем воспользоваться техническими возможностями для применения меток и защиты, сначала определите схему классификации для своей организации. Возможно, у нее уже имеется схема классификации, что упрощает добавление персональных данных. В этой статье приведен пример схемы классификации. При необходимости вы можете использовать его в качестве отправной точки.</span><span class="sxs-lookup"><span data-stu-id="7829a-p104">Before using technical capabilities to apply labels and protection, first work across your organization to define a classification schema. Your organization might already have a classification schema, which makes it easier to add personal data. This topic includes an example classification schema. You can use this example as a starting point, if needed.</span></span>

### <a name="getting-started"></a><span data-ttu-id="7829a-131">Начало работы</span><span class="sxs-lookup"><span data-stu-id="7829a-131">Getting started</span></span>

<span data-ttu-id="7829a-p105">Сначала выберите количество и имена меток, которые необходимо внедрить. При этом не беспокойтесь об используемых технологиях и способах применения меток. Примените эту схему в пределах всей организации, в том числе к данным, которые хранятся в локальной среде и других облачных службах.</span><span class="sxs-lookup"><span data-stu-id="7829a-p105">Begin by deciding on the number and names of labels to implement. Do this activity without worrying about which technology to use and how labels will be applied. Apply this schema universally throughout your organization, including data that resides on premises and in other cloud services.</span></span>

### <a name="recommendations"></a><span data-ttu-id="7829a-135">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="7829a-135">Recommendations</span></span> 

<span data-ttu-id="7829a-136">Разрабатывая и внедряя политики, метки и условия, руководствуйтесь вот какими рекомендациями.</span><span class="sxs-lookup"><span data-stu-id="7829a-136">When designing and implementing policies, labels and conditions, consider following these recommendations:</span></span>

- <span data-ttu-id="7829a-p106">Используйте имеющуюся схему классификации (при наличии). Многие организации уже пользуются определенными разновидностями классификации данных. Тщательно проанализируйте имеющуюся схему меток и по возможности используйте ее без изменений. Использование знакомых пользователю меток повысит эффективность их принятия.</span><span class="sxs-lookup"><span data-stu-id="7829a-p106">Use existing classification schema (if any) &ndash; Many organizations already are using data classification in some form. Carefully evaluate the existing label schema and if possible use it as is. Using familiar labels that are recognizable to the end user will drive adoption.</span></span>

- <span data-ttu-id="7829a-p107">В начале используйте стандартные политики и метки. Все решения поставляются с набором предопределенных политик и меток. Тщательно оцените, насколько они соответствуют вашим юридическим и бизнес-требованиям, и по возможности используйте именно их, а не создавайте новые.</span><span class="sxs-lookup"><span data-stu-id="7829a-p107">Start with default policies and labels &ndash; All solutions come with a set of predefined policies and labels. Carefully evaluate these against the organization's legal and business requirements and consider using them instead of creating new ones.</span></span>

- <span data-ttu-id="7829a-p108">Начните с малого. Вы можете создать практически неограниченное количество меток. Тем не менее большое число основных и вложенных меток отрицательно скажется на их принятии. Слишком большое число вариантов часто приводит к невозможности выбора.</span><span class="sxs-lookup"><span data-stu-id="7829a-p108">Start small &ndash; There's virtually no limit to the number of labels that can be created. However, large numbers of labels and sub-labels will negatively impact the adoption. Too many choices often mean no choice at all.</span></span>

- <span data-ttu-id="7829a-145">Применяйте сценарии и варианты использования. Определите варианты использования, характерные для организации и созданные на основе регламента GDPR, чтобы проверить, будет ли предполагаемая конфигурация применения меток и классификации работать на практике.</span><span class="sxs-lookup"><span data-stu-id="7829a-145">Use scenarios and use cases &ndash; Identify common use cases within the organization and use scenarios derived from the GDPR to verify if the envisioned label and classification configuration will work in practice.</span></span>

- <span data-ttu-id="7829a-p109">Определите целесообразность каждого запроса на использование новой метки. Действительно ли для каждого сценария или варианта использования нужна новая метка или достаточно воспользоваться уже имеющейся меткой? Сведите число меток к минимуму, чтобы улучшить их принятие.</span><span class="sxs-lookup"><span data-stu-id="7829a-p109">Question every request for a new label &ndash; Does every scenario or use case really need a new label or can you use what you already have? Keeping the number of labels to a minimum improves adoption.</span></span>

- <span data-ttu-id="7829a-p110">Используйте вложенные метки для ключевых отделов. Некоторые отделы отличаются особыми требованиями, для которых требуются особенные метки. Определите эти метки в качестве вложенных меток. Кроме того, рассмотрите возможность использования политик с областью действия, которые применяются к группам пользователей, а не ко всей организации.</span><span class="sxs-lookup"><span data-stu-id="7829a-p110">Use sub-labels for key departments &ndash; Some departments will have specific needs that require specific labels. Define these labels as sub-labels to an existing label, and consider using scoped policies that are assigned to user groups instead of globally.</span></span>

- <span data-ttu-id="7829a-p111">Рассмотрите возможность использования политик с областью действия. Политики, нацеленные на определенные подмножества пользователей, предотвращают создание чрезмерного числа меток. Политика с областью действия позволяет назначить роль или относящиеся к конкретному отделу метки (в том числе вложенные) сотрудникам, работающим именно в этом отделе.</span><span class="sxs-lookup"><span data-stu-id="7829a-p111">Consider scoped policies &ndash; Policies targeted at subsets of users will prevent "label overload". A scoped policy lets you assign role or department-specific (sub-)labels to just employees that work for that specific department.</span></span>

- <span data-ttu-id="7829a-p112">Используйте понятные имена меток. В качестве имен меток не рекомендуется использовать жаргонные слова, стандартные сокращения или акронимы. Целесообразно использовать понятные пользователям имена, чтобы улучшить принятие меток. Например, вместо таких меток, как PII, PCI, HIPAA, LBI, MBI и HBI, используйте имена типа "Не бизнес-данные", "Общедоступные", "Общие", "Конфиденциально" и "Строго конфиденциально".</span><span class="sxs-lookup"><span data-stu-id="7829a-p112">Use meaningful label names &ndash; We recommend that you don't use jargon, standards, or acronyms as label names. Try to use names that resonate with the end user to improve adoption. Instead of using labels like PII, PCI, HIPAA, LBI, MBI, and HBI, consider names like Non-Business, Public, General, Confidential, and Highly Confidential.</span></span>

### <a name="example-classification-schema"></a><span data-ttu-id="7829a-155">Пример схемы классификации</span><span class="sxs-lookup"><span data-stu-id="7829a-155">Example classification schema</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7829a-156"><strong>Имя метки</strong></span><span class="sxs-lookup"><span data-stu-id="7829a-156"><strong>Label name</strong></span></span></th>
<th align="left"><span data-ttu-id="7829a-157"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="7829a-157"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="7829a-158">Персональные</span><span class="sxs-lookup"><span data-stu-id="7829a-158">Personal</span></span></td>
<td align="left"><span data-ttu-id="7829a-159">Не бизнес-данные, предназначенные только для личного использования.</span><span class="sxs-lookup"><span data-stu-id="7829a-159">Non-business data, for personal use only.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="7829a-160">Общедоступные</span><span class="sxs-lookup"><span data-stu-id="7829a-160">Public</span></span></td>
<td align="left"><span data-ttu-id="7829a-161">Бизнес-данные, специально подготовленные и утвержденные для предоставления широкой публике.</span><span class="sxs-lookup"><span data-stu-id="7829a-161">Business data that is specifically prepared and approved for public consumption.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="7829a-162">Данные клиента</span><span class="sxs-lookup"><span data-stu-id="7829a-162">Customer data</span></span></td>
<td align="left"><span data-ttu-id="7829a-p113">Бизнес-данные, содержащие личные сведения, например номера кредитных карт, банковских счетов и социального страхования.</span><span class="sxs-lookup"><span data-stu-id="7829a-p113">Business data that contains personal identifiable information. Examples are credit card numbers, bank account numbers, and social security numbers.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="7829a-165">Данные о персонале</span><span class="sxs-lookup"><span data-stu-id="7829a-165">HR data</span></span></td>
<td align="left"><span data-ttu-id="7829a-166">Данные отдела кадров о сотрудниках Contoso, например номер сотрудника и сведения о зарплате.</span><span class="sxs-lookup"><span data-stu-id="7829a-166">Human Resource data about Contoso employees, such as employee number and salary data.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="7829a-167">Конфиденциально</span><span class="sxs-lookup"><span data-stu-id="7829a-167">Confidential</span></span></td>
<td align="left"><span data-ttu-id="7829a-p114">Конфиденциальные бизнес-данные, предоставление которых не тем людям может нанести ущерб организации. Примеры: контракты, отчеты системы безопасности, прогнозные сводки и данные о продажах клиентам.</span><span class="sxs-lookup"><span data-stu-id="7829a-p114">Sensitive business data that could cause damage to the business if shared with unauthorized people. Examples include contracts, security reports, forecast summaries, and sales account data.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="7829a-170">Строго конфиденциально</span><span class="sxs-lookup"><span data-stu-id="7829a-170">Highly confidential</span></span></td>
<td align="left"><span data-ttu-id="7829a-p115">Строго конфиденциальные бизнес-данные, предоставление которых не тем людям может нанести ущерб организации. Примеры: информация о сотрудниках и клиентах, пароли, исходный код и финансовые отчеты, о которых объявляется заранее.</span><span class="sxs-lookup"><span data-stu-id="7829a-p115">Very sensitive business data that would cause damage to the business if it was shared with unauthorized people. Examples include employee and customer information, passwords, source code, and pre-announced financial reports.</span></span></td>
</tr>
</tbody>
</table>

## <a name="define-a-taxonomy-and-search-criteria-for-each-label"></a><span data-ttu-id="7829a-173">Определение таксономии и условий поиска для каждой метки</span><span class="sxs-lookup"><span data-stu-id="7829a-173">Define a taxonomy and search criteria for each label</span></span>

<span data-ttu-id="7829a-p116">Следующий шаг после разработки схемы классификации для вашей организации — разработать таксономию и условия поиска этих данных. Вы уже выполнили эти задачи для персональных данных, определив типы конфиденциальной информации и настроив или создав новые типы конфиденциальной информации для своей среды.</span><span class="sxs-lookup"><span data-stu-id="7829a-p116">After developing a classification schema for your organization, the next step is to develop the taxonomy and search criteria for finding this data. For personal data, you've already completed this work by identifying sensitive information types and customizing or creating new sensitive information types for your environment.</span></span>

<span data-ttu-id="7829a-p117">В таблице ниже приведен пример схемы, таксономии и условий поиска для организации. Метки упорядочены по уровню конфиденциальности от наименее до наиболее конфиденциальных, чтобы гарантировать назначение правильной метки данным, которые соответствуют нескольким условиям метки.</span><span class="sxs-lookup"><span data-stu-id="7829a-p117">The following table provides an example schema, taxonomy, and search criteria for an organization. The labels are ordered by sensitivity level from least sensitive to most sensitive to ensure that data that matches multiple label conditions is assigned the appropriate label.</span></span>

<span data-ttu-id="7829a-178">Примечание. Этот пример конфигурации приведен исключительно для иллюстрации и не предназначен для использования в качестве руководства или справки по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="7829a-178">Note: The configuration example is provided for illustration only and is not intended as deployment guidance or reference.</span></span>

<span data-ttu-id="7829a-179">Крайне важно убедиться, что ваши действия по классификации персональных данных для соответствия требованиям регламента GDPR сочетаются с целями всей организации.</span><span class="sxs-lookup"><span data-stu-id="7829a-179">The important takeaway is to ensure that the work you invest to classify personal data for GDPR compliance fits together with the objectives for your entire organization.</span></span>

### <a name="example-schema-taxonomy-and-search-criteria"></a><span data-ttu-id="7829a-180">Пример схемы, таксономии и условий поиска</span><span class="sxs-lookup"><span data-stu-id="7829a-180">Example schema, taxonomy, and search criteria</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7829a-181"><strong>Метка</strong></span><span class="sxs-lookup"><span data-stu-id="7829a-181"><strong>Label</strong></span></span></th>
<th align="left"><span data-ttu-id="7829a-182"><strong>Таксономия</strong></span><span class="sxs-lookup"><span data-stu-id="7829a-182"><strong>Taxonomy</strong></span></span></th>
<th align="left"><span data-ttu-id="7829a-183"><strong>Метод</strong></span><span class="sxs-lookup"><span data-stu-id="7829a-183"><strong>Method</strong></span></span></th>
<th align="left"><span data-ttu-id="7829a-184"><strong>Синтаксис поиска</strong></span><span class="sxs-lookup"><span data-stu-id="7829a-184"><strong>Search syntax</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="7829a-185">Личное</span><span class="sxs-lookup"><span data-stu-id="7829a-185">Personal</span></span></td>
<td align="left"><span data-ttu-id="7829a-186">Документы, к которым пользователь вручную применил метку как к персональным.</span><span class="sxs-lookup"><span data-stu-id="7829a-186">Documents manually labeled personal by the end user.</span></span></td>
<td align="left"><span data-ttu-id="7829a-187">Вручную</span><span class="sxs-lookup"><span data-stu-id="7829a-187">Manual</span></span></td>
<td align="left"><span data-ttu-id="7829a-188">Документы, к которым пользователь вручную применил метку как к персональным.</span><span class="sxs-lookup"><span data-stu-id="7829a-188">Documents manually labeled personal by the end user.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="7829a-189">Общедоступное</span><span class="sxs-lookup"><span data-stu-id="7829a-189">Public</span></span></td>
<td align="left"><span data-ttu-id="7829a-190">Документы, содержащие фразу Approved for Public Release ##/#### (без учета регистра), где # представляет собой любую цифру.</span><span class="sxs-lookup"><span data-stu-id="7829a-190">Documents containing the case insensitive phrase Approved for Public Release ##/#### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="7829a-191">KQL</span><span class="sxs-lookup"><span data-stu-id="7829a-191">KQL</span></span></p>
<p><span data-ttu-id="7829a-192">Регулярное выражение</span><span class="sxs-lookup"><span data-stu-id="7829a-192">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="7829a-193">KQL — Approved for Public Release (Утверждено для общедоступного выпуска)\*</span><span class="sxs-lookup"><span data-stu-id="7829a-193">KQL — Approved for Public Release\*</span></span></p>
<p><span data-ttu-id="7829a-194">Регулярное выражение — (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</span><span class="sxs-lookup"><span data-stu-id="7829a-194">RegEx — (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="7829a-195">Данные клиента</span><span class="sxs-lookup"><span data-stu-id="7829a-195">Customer data</span></span></td>
<td align="left"><span data-ttu-id="7829a-196">Типы конфиденциальной информации о гражданах стран ЕС.</span><span class="sxs-lookup"><span data-stu-id="7829a-196">Sensitive information types for EU citizen data.</span></span></td>
<td align="left"><span data-ttu-id="7829a-197">Типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="7829a-197">Sensitive information types</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="7829a-198">Отдел кадров — данные о сотрудниках</span><span class="sxs-lookup"><span data-stu-id="7829a-198">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="7829a-199">Документы, включающие идентификатор сотрудника (с учетом регистра) в формате CONTOSO-9#####, где # представляет собой любую цифру.</span><span class="sxs-lookup"><span data-stu-id="7829a-199">Documents that include the case-sensitive employee id in the format CONTOSO-9##### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="7829a-200">KQL</span><span class="sxs-lookup"><span data-stu-id="7829a-200">KQL</span></span></p>
<p><span data-ttu-id="7829a-201">Регулярное выражение</span><span class="sxs-lookup"><span data-stu-id="7829a-201">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="7829a-202">KQL — CONTOSO-9\*</span><span class="sxs-lookup"><span data-stu-id="7829a-202">KQL — CONTOSO-9\*</span></span></p>
<p><span data-ttu-id="7829a-203">Регулярное выражение — (\bCONTOSO-9\d{5}\b)</span><span class="sxs-lookup"><span data-stu-id="7829a-203">RegEx — (\bCONTOSO-9\d{5}\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="7829a-204">Отдел кадров — данные о зарплате</span><span class="sxs-lookup"><span data-stu-id="7829a-204">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="7829a-205">Документы, включающие ключевое слово (без учета регистра) Contoso и ключевое слово (без учета регистра) Salary или Compensation</span><span class="sxs-lookup"><span data-stu-id="7829a-205">Documents that include the keyword (not case sensitive) Contoso AND either keyword (not case sensitive) Salary OR Compensation</span></span></td>
<td align="left"><p><span data-ttu-id="7829a-206">KQL</span><span class="sxs-lookup"><span data-stu-id="7829a-206">KQL</span></span></p>
<p><span data-ttu-id="7829a-207">Регулярное выражение</span><span class="sxs-lookup"><span data-stu-id="7829a-207">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="7829a-208">KQL — Contoso AND (Salary OR Compensation)</span><span class="sxs-lookup"><span data-stu-id="7829a-208">KQL — Contoso AND (Salary OR Compensation)</span></span></p>
<p><span data-ttu-id="7829a-209">Регулярное выражение — (\bCONTOSO-9\d{5}\b)</span><span class="sxs-lookup"><span data-stu-id="7829a-209">RegEx — (\bCONTOSO-9\d{5}\b)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="7829a-210">Конфиденциально</span><span class="sxs-lookup"><span data-stu-id="7829a-210">Confidential</span></span></td>
<td align="left"><span data-ttu-id="7829a-211">Документы, содержащие фразу Contoso Confidential (без учета регистра).</span><span class="sxs-lookup"><span data-stu-id="7829a-211">Documents containing the phrase (not case sensitive) Contoso Confidential.</span></span></td>
<td align="left"><p><span data-ttu-id="7829a-212">KQL</span><span class="sxs-lookup"><span data-stu-id="7829a-212">KQL</span></span></p>
<p><span data-ttu-id="7829a-213">Регулярное выражение</span><span class="sxs-lookup"><span data-stu-id="7829a-213">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="7829a-214">KQL — Contoso Confidential</span><span class="sxs-lookup"><span data-stu-id="7829a-214">KQL — Contoso Confidential</span></span></p>
<p><span data-ttu-id="7829a-215">Регулярное выражение — (?i)(\bContoso Confidential\b)</span><span class="sxs-lookup"><span data-stu-id="7829a-215">RegEx — (?i)(\bContoso Confidential\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="7829a-216">Строго конфиденциально</span><span class="sxs-lookup"><span data-stu-id="7829a-216">Highly confidential</span></span></td>
<td align="left"><span data-ttu-id="7829a-217">Документы, содержащие фразу (с учетом регистра) Contoso Secret или Secret-C####, где # представляет собой любую цифру.</span><span class="sxs-lookup"><span data-stu-id="7829a-217">Documents that include either pharase (case sensitive) Contoso Secret or Secret-C#### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="7829a-218">KQL</span><span class="sxs-lookup"><span data-stu-id="7829a-218">KQL</span></span></p>
<p><span data-ttu-id="7829a-219">Регулярное выражение</span><span class="sxs-lookup"><span data-stu-id="7829a-219">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="7829a-220">KQL — Contoso Secret OR Secret-C\*</span><span class="sxs-lookup"><span data-stu-id="7829a-220">KQL — Contoso Secret OR Secret-C\*</span></span></p>
<p><span data-ttu-id="7829a-221">Регулярное выражение — (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</span><span class="sxs-lookup"><span data-stu-id="7829a-221">RegEx — (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</span></span></p></td>
</tr>
</tbody>
</table>
