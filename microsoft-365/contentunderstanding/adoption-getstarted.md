---
title: 'Microsoft SharePoint Syntex: начало работы'
description: Узнайте, как использовать и внедрять SharePoint Syntex в организации, чтобы помочь вам решить бизнес-проблемы.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 8a5442fcf8dd50cdee6be97ba7c9bbf5e21408a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288159"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="4eaf0-103">Microsoft SharePoint Syntex: начало работы</span><span class="sxs-lookup"><span data-stu-id="4eaf0-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="4eaf0-104">Думайте о том, что интеллектуальные службы контента, доступные в SharePoint Syntex, имеют три части:</span><span class="sxs-lookup"><span data-stu-id="4eaf0-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="4eaf0-105">**Понимание контента:** Создайте модели AI без кода, чтобы классифицировать и извлекать информацию из контента, чтобы автоматически применять метаданные для обнаружения и повторного использования знаний.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-105">**Content understanding:** Create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="4eaf0-106">Узнайте больше о [понимании контента.](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4eaf0-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="4eaf0-107">**Обработка контента:** Автоматизация захвата, ingestion и классификации контента и оптимизация процессов, ориентированных на контент, с помощью Power Automate.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-107">**Content processing:** Automate capture, ingestion, and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="4eaf0-108">Дополнительные материалы об [обработке контента.](form-processing-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4eaf0-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="4eaf0-109">**Соответствие требованиям контента:** Управление и управление контентом для повышения безопасности и управления с интеграцией Microsoft Information Protection.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="4eaf0-110">С помощью новых служб и возможностей ИИ можно создавать приложения для понимания контента и классификации непосредственно в поток управления контентом с помощью SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex.</span></span> <span data-ttu-id="4eaf0-111">Существует два различных способа понимания контента.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-111">There are two different ways of understanding your content.</span></span> <span data-ttu-id="4eaf0-112">Тип модели, который вы используете, основан на формате файла и случае использования:</span><span class="sxs-lookup"><span data-stu-id="4eaf0-112">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="4eaf0-113">Обработка форм</span><span class="sxs-lookup"><span data-stu-id="4eaf0-113">Form processing</span></span> | <span data-ttu-id="4eaf0-114">Осмысление документации</span><span class="sxs-lookup"><span data-stu-id="4eaf0-114">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="4eaf0-115">Создан из библиотеки документов.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-115">Created from document library.</span></span> | <span data-ttu-id="4eaf0-116">Созданная в центре контента часть SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-116">Created in the content center, part of SharePoint Syntex.</span></span> |
| <span data-ttu-id="4eaf0-117">Модель, созданная в конструкторе ИИ.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-117">Model created in AI builder.</span></span> | <span data-ttu-id="4eaf0-118">Модель, созданная в родном интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-118">Model created in native interface.</span></span> |
| <span data-ttu-id="4eaf0-119">Используется для полуструктурных форматов файлов.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-119">Used for semi-structured file formats.</span></span> | <span data-ttu-id="4eaf0-120">Используется для неструктурированных форматов файлов.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-120">Used for unstructured file formats.</span></span> |
| <span data-ttu-id="4eaf0-121">Классификатор settable.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-121">Settable classifier.</span></span> | <span data-ttu-id="4eaf0-122">Классификатор с необязательными экстракторами.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-122">Trainable classifier with optional extractors.</span></span> |
| <span data-ttu-id="4eaf0-123">Ограничен одной библиотекой.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-123">Restricted to a single library.</span></span> | <span data-ttu-id="4eaf0-124">Может применяться к нескольким библиотекам.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-124">Can be applied to multiple libraries.</span></span> |
| <span data-ttu-id="4eaf0-125">Обучение в формате PDF, JPG, PNG общей стоимостью 50 МБ/500 pp.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-125">Train on PDF, JPG, PNG format, total 50 MB/500 pp.</span></span> | <span data-ttu-id="4eaf0-126">Обучение на 5–10 PDF-файлах, файлах Office или электронной почты, в том числе отрицательные примеры.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-126">Train on 5-10 PDF, Office, or email files, including negative examples.</span></span> |

<span data-ttu-id="4eaf0-127">Для более полного сравнения возможностей см. разницу между пониманием документов и [моделями обработки форм.](difference-between-document-understanding-and-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="4eaf0-127">For a more complete comparison of the capabilities, see [Difference between document understanding and form processing models](difference-between-document-understanding-and-form-processing-model.md).</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="4eaf0-128">Определение пилотных бизнес-сценариев для оптимизации</span><span class="sxs-lookup"><span data-stu-id="4eaf0-128">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="4eaf0-129">Чтобы подготовиться к использованию SharePoint Syntex в организации, сначала необходимо понять сценарии, в которых это будет полезно.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-129">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="4eaf0-130">"Почему" помогает определить, какая модель будет нужна, и как структурировать свою организацию на основе того, где модель будет применяться.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-130">The "why" helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="4eaf0-131">Вот несколько сценариев, в которых понимание документов может помочь организации:</span><span class="sxs-lookup"><span data-stu-id="4eaf0-131">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="4eaf0-132">**Обработка контента:** Обработка контрактов, отчетов о работе и других документов, похожих на форму.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-132">**Content processing:** Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="4eaf0-133">Включите формы, обучите модель понимать поля и сопобирать их, а затем запустите формы, чтобы автоматически собирать данные.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-133">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="4eaf0-134">Дополнительные сведения см. в [обзоре обработки форм.](form-processing-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4eaf0-134">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="4eaf0-135">**Анализ счетов:** Извлеките соответствующие сведения из счетов и убедитесь, что они соответствуют политике или обрабатываются надлежащим образом.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-135">**Invoice analysis:** Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="4eaf0-136">Подумайте, как SharePoint Syntex помочь организации:</span><span class="sxs-lookup"><span data-stu-id="4eaf0-136">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="4eaf0-137">Автоматизация бизнес-процессов</span><span class="sxs-lookup"><span data-stu-id="4eaf0-137">Automate business processes</span></span>
- <span data-ttu-id="4eaf0-138">Повышение точности поиска</span><span class="sxs-lookup"><span data-stu-id="4eaf0-138">Improve search accuracy</span></span>
- <span data-ttu-id="4eaf0-139">Управление рисками, связанными с соответствием требованиям</span><span class="sxs-lookup"><span data-stu-id="4eaf0-139">Manage compliance risk</span></span>

<span data-ttu-id="4eaf0-140">При рассмотрении бизнес-сценариев задайте себе следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="4eaf0-140">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="4eaf0-141">Решает ли это реальную проблему?</span><span class="sxs-lookup"><span data-stu-id="4eaf0-141">Does it solve a real problem?</span></span>
- <span data-ttu-id="4eaf0-142">Будет ли он широко использоваться или будет иметь широкое влияние?</span><span class="sxs-lookup"><span data-stu-id="4eaf0-142">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="4eaf0-143">Можно ли получить его?</span><span class="sxs-lookup"><span data-stu-id="4eaf0-143">Is it obtainable?</span></span>
- <span data-ttu-id="4eaf0-144">Можете ли вы измерить успех?</span><span class="sxs-lookup"><span data-stu-id="4eaf0-144">Can you measure success?</span></span>

<span data-ttu-id="4eaf0-145">Расставить приоритеты сценариев на основе влияния и простоты реализации.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-145">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="4eaf0-146">Сделайте начальную область фокуса более высокими сценариями воздействия, которые также можно легко реализовать.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-146">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="4eaf0-147">Расставить приоритеты при снижении приоритетов сценариев воздействия, которые трудно реализовать.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-147">De-prioritize lower impact scenarios that are hard to implement.</span></span>

<span data-ttu-id="4eaf0-148">Используйте примеры [сценариев и](adoption-scenarios.md) используйте примеры, чтобы подсказок о том, как можно использовать SharePoint Syntex в организации.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-148">Use the [example scenarios and use cases](adoption-scenarios.md) to prompt ideas about how you can use SharePoint Syntex in your organization.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="4eaf0-149">Определение ролей & обязанностей</span><span class="sxs-lookup"><span data-stu-id="4eaf0-149">Identify roles & responsibilities</span></span>

<span data-ttu-id="4eaf0-150">Определите, кто в организации будет создавать и управлять моделями?</span><span class="sxs-lookup"><span data-stu-id="4eaf0-150">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="4eaf0-151">Могут быть задействованы следующие роли:</span><span class="sxs-lookup"><span data-stu-id="4eaf0-151">The following roles might be involved:</span></span>

| <span data-ttu-id="4eaf0-152">SharePoint/Knowledge admin</span><span class="sxs-lookup"><span data-stu-id="4eaf0-152">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="4eaf0-153">Администратор Power Platform</span><span class="sxs-lookup"><span data-stu-id="4eaf0-153">Power Platform admin</span></span> | <span data-ttu-id="4eaf0-154">Управляющий базой знаний</span><span class="sxs-lookup"><span data-stu-id="4eaf0-154">Knowledge manager</span></span> | <span data-ttu-id="4eaf0-155">Владелец модели</span><span class="sxs-lookup"><span data-stu-id="4eaf0-155">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="4eaf0-156">Роль AAD</span><span class="sxs-lookup"><span data-stu-id="4eaf0-156">AAD role</span></span>| <span data-ttu-id="4eaf0-157">Роль AAD</span><span class="sxs-lookup"><span data-stu-id="4eaf0-157">AAD role</span></span> | <span data-ttu-id="4eaf0-158">Роль AAD</span><span class="sxs-lookup"><span data-stu-id="4eaf0-158">AAD role</span></span> | <span data-ttu-id="4eaf0-159">Лидеры</span><span class="sxs-lookup"><span data-stu-id="4eaf0-159">Champions</span></span> |
| <span data-ttu-id="4eaf0-160">Настройка обработки форм</span><span class="sxs-lookup"><span data-stu-id="4eaf0-160">Configure form processing</span></span> | <span data-ttu-id="4eaf0-161">Настройка среды общей службы данных для обработки форм</span><span class="sxs-lookup"><span data-stu-id="4eaf0-161">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="4eaf0-162">Сбор случаев использования</span><span class="sxs-lookup"><span data-stu-id="4eaf0-162">Gather use cases</span></span> | <span data-ttu-id="4eaf0-163">Сбор дел по использованию бизнеса</span><span class="sxs-lookup"><span data-stu-id="4eaf0-163">Gather business use cases</span></span> |
| <span data-ttu-id="4eaf0-164">Управление центрами контента и разрешениями</span><span class="sxs-lookup"><span data-stu-id="4eaf0-164">Manage content centers and permissions</span></span>| <span data-ttu-id="4eaf0-165">Покупка и выделение кредитов AIB</span><span class="sxs-lookup"><span data-stu-id="4eaf0-165">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="4eaf0-166">Создание наилучшей практики и анализ моделей обзоров</span><span class="sxs-lookup"><span data-stu-id="4eaf0-166">Establish best practices and review model analytics</span></span> | <span data-ttu-id="4eaf0-167">Создание и применение моделей</span><span class="sxs-lookup"><span data-stu-id="4eaf0-167">Create and apply models</span></span> |

<span data-ttu-id="4eaf0-168">Менеджер знаний, владелец бизнес-процессов и владелец модели контента создают примерные модели и утверждение чемпиона в организации.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-168">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="4eaf0-169">Другие, которые могут быть вовлечены: администратор соответствия требованиям, менеджеры таксономии.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-169">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="4eaf0-170">Где будут создаваться и применяться модели?</span><span class="sxs-lookup"><span data-stu-id="4eaf0-170">Where will they build and apply the models?</span></span> <span data-ttu-id="4eaf0-171">Существуют ли существующие процессы или репозитории, которые можно усовершенствовать?</span><span class="sxs-lookup"><span data-stu-id="4eaf0-171">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="4eaf0-172">Обработка форм. Определите, какие сайты получат действие обработки форм.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-172">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="4eaf0-173">Понимание документов. Можно создать несколько центров контента для различных бизнес-областей.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-173">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="4eaf0-174">Стратегическое позиционирование</span><span class="sxs-lookup"><span data-stu-id="4eaf0-174">Strategic positioning</span></span>

<span data-ttu-id="4eaf0-175">Работай с заинтересованными сторонами, чтобы убедиться, что они соответствуют стратегии использования SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-175">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="4eaf0-176">Исследование и предоставление следующих ресурсов, которые помогут в этом позиционировании:</span><span class="sxs-lookup"><span data-stu-id="4eaf0-176">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="4eaf0-177">Бизнес-результаты:</span><span class="sxs-lookup"><span data-stu-id="4eaf0-177">Business outcomes:</span></span>
  - <span data-ttu-id="4eaf0-178">Потенциальные финансовые результаты</span><span class="sxs-lookup"><span data-stu-id="4eaf0-178">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="4eaf0-179">Потенциальные результаты гибкости</span><span class="sxs-lookup"><span data-stu-id="4eaf0-179">Potential agility outcomes</span></span>
  - <span data-ttu-id="4eaf0-180">Шаблон бизнес-результатов</span><span class="sxs-lookup"><span data-stu-id="4eaf0-180">Business outcome template</span></span>
- <span data-ttu-id="4eaf0-181">Участие в покупке/согласовании спонсоров и спонсоров Exec</span><span class="sxs-lookup"><span data-stu-id="4eaf0-181">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="4eaf0-182">Колоды бизнес-кейсов</span><span class="sxs-lookup"><span data-stu-id="4eaf0-182">Business case decks</span></span>
  - <span data-ttu-id="4eaf0-183">Финансовые модели</span><span class="sxs-lookup"><span data-stu-id="4eaf0-183">Financial models</span></span>
  - <span data-ttu-id="4eaf0-184">Готовность компании — культура</span><span class="sxs-lookup"><span data-stu-id="4eaf0-184">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="4eaf0-185">Определение круга заинтересованных лиц</span><span class="sxs-lookup"><span data-stu-id="4eaf0-185">Identify stakeholders</span></span>

<span data-ttu-id="4eaf0-186">Определите заинтересованных лиц для проекта.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-186">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="4eaf0-187">Роль</span><span class="sxs-lookup"><span data-stu-id="4eaf0-187">Role</span></span> |<span data-ttu-id="4eaf0-188">Обязанности</span><span class="sxs-lookup"><span data-stu-id="4eaf0-188">Responsibilities</span></span> |<span data-ttu-id="4eaf0-189">Отдел</span><span class="sxs-lookup"><span data-stu-id="4eaf0-189">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="4eaf0-190">Исполнительный спонсор (s)</span><span class="sxs-lookup"><span data-stu-id="4eaf0-190">Executive sponsor(s)</span></span>   | <span data-ttu-id="4eaf0-191">Сообщение компании о видении и ценностях высокого уровня</span><span class="sxs-lookup"><span data-stu-id="4eaf0-191">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="4eaf0-192">Высшее руководство</span><span class="sxs-lookup"><span data-stu-id="4eaf0-192">Executive leadership</span></span>   |
| <span data-ttu-id="4eaf0-193">Project(ы)</span><span class="sxs-lookup"><span data-stu-id="4eaf0-193">Project lead(s)</span></span> | <span data-ttu-id="4eaf0-194">Наблюдение за всем процессом запуска и развертывания</span><span class="sxs-lookup"><span data-stu-id="4eaf0-194">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="4eaf0-195">Управление проектами</span><span class="sxs-lookup"><span data-stu-id="4eaf0-195">Project management</span></span> |
| <span data-ttu-id="4eaf0-196">Администраторы знаний</span><span class="sxs-lookup"><span data-stu-id="4eaf0-196">Knowledge administrators</span></span>| <span data-ttu-id="4eaf0-197">Создание и управление центрами контента</span><span class="sxs-lookup"><span data-stu-id="4eaf0-197">Create and manage the content centers</span></span> | <span data-ttu-id="4eaf0-198">ИТ-отдел или другой отдел</span><span class="sxs-lookup"><span data-stu-id="4eaf0-198">IT or other department</span></span>|
| <span data-ttu-id="4eaf0-199">Менеджеры контента и владельцы моделей</span><span class="sxs-lookup"><span data-stu-id="4eaf0-199">Content managers and model owners</span></span>| <span data-ttu-id="4eaf0-200">Сбор случаев использования и создание и применение моделей</span><span class="sxs-lookup"><span data-stu-id="4eaf0-200">Gather use cases and create and apply models</span></span> | <span data-ttu-id="4eaf0-201">Любой отдел</span><span class="sxs-lookup"><span data-stu-id="4eaf0-201">Any department</span></span>|
| <span data-ttu-id="4eaf0-202">Лидеры</span><span class="sxs-lookup"><span data-stu-id="4eaf0-202">Champions</span></span> | <span data-ttu-id="4eaf0-203">Помощь в работе с возражениями и управлении ими</span><span class="sxs-lookup"><span data-stu-id="4eaf0-203">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="4eaf0-204">Любой отдел (сотрудники)</span><span class="sxs-lookup"><span data-stu-id="4eaf0-204">Any department (staff)</span></span> |
| <span data-ttu-id="4eaf0-205">Администратор клиента</span><span class="sxs-lookup"><span data-stu-id="4eaf0-205">Tenant administrator</span></span> | <span data-ttu-id="4eaf0-206">Настройка параметров на уровне клиента</span><span class="sxs-lookup"><span data-stu-id="4eaf0-206">Configure tenant-level settings</span></span> | <span data-ttu-id="4eaf0-207">ИТ-отдел</span><span class="sxs-lookup"><span data-stu-id="4eaf0-207">IT department</span></span>|
| <span data-ttu-id="4eaf0-208">Администратор Power Platform</span><span class="sxs-lookup"><span data-stu-id="4eaf0-208">Power Platform administrator</span></span>| <span data-ttu-id="4eaf0-209">Настройка среды служб общих данных</span><span class="sxs-lookup"><span data-stu-id="4eaf0-209">Configure common data services environment</span></span> | <span data-ttu-id="4eaf0-210">ИТ-отдел</span><span class="sxs-lookup"><span data-stu-id="4eaf0-210">IT department</span></span>|

> [!Note]
> <span data-ttu-id="4eaf0-211">Хотя мы рекомендуем выполнять каждую из этих ролей на протяжении всего выполнения, вы можете обнаружить, что вам не требуется, чтобы все они начали работу с идентифицированным решением.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-211">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="4eaf0-212">Контрольный список готовности</span><span class="sxs-lookup"><span data-stu-id="4eaf0-212">Readiness checklist</span></span>

<span data-ttu-id="4eaf0-213">Чтобы быть готовым к реализации SharePoint Syntex, необходимо:</span><span class="sxs-lookup"><span data-stu-id="4eaf0-213">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![Готовность к пониманию контента](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="4eaf0-215">Планирование конечных состояния</span><span class="sxs-lookup"><span data-stu-id="4eaf0-215">Plan the end state</span></span>
    - <span data-ttu-id="4eaf0-216">Модели понимания документов — это средства, а не конец.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-216">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="4eaf0-217">Планирование использования значения извлеченных метаданных с помощью:</span><span class="sxs-lookup"><span data-stu-id="4eaf0-217">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="4eaf0-218">Поиск</span><span class="sxs-lookup"><span data-stu-id="4eaf0-218">Search</span></span>
      - <span data-ttu-id="4eaf0-219">Фильтрация и форматирование представлений</span><span class="sxs-lookup"><span data-stu-id="4eaf0-219">Filtering and view formatting</span></span>
      - <span data-ttu-id="4eaf0-220">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="4eaf0-220">Compliance</span></span>
      - <span data-ttu-id="4eaf0-221">Автоматизация</span><span class="sxs-lookup"><span data-stu-id="4eaf0-221">Automation</span></span>
2. <span data-ttu-id="4eaf0-222">Определение</span><span class="sxs-lookup"><span data-stu-id="4eaf0-222">Identify</span></span>
    - <span data-ttu-id="4eaf0-223">Сведения о существующей информационной архитектуре и использовании функций управления контентом.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-223">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="4eaf0-224">Являются ли существующие типы контента хорошими кандидатами для моделей?</span><span class="sxs-lookup"><span data-stu-id="4eaf0-224">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="4eaf0-225">Какие существующие процессы будут улучшены с помощью метаданных?</span><span class="sxs-lookup"><span data-stu-id="4eaf0-225">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="4eaf0-226">Разработка</span><span class="sxs-lookup"><span data-stu-id="4eaf0-226">Design</span></span>
    - <span data-ttu-id="4eaf0-227">Разработка подхода к информационной архитектуре, управляемым метаданным и типам контента.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-227">Design your approach to information architecture, managed metadata and content types.</span></span>
    - <span data-ttu-id="4eaf0-228">Разработка процесса определения, создания, управления.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-228">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="4eaf0-229">Вовлечение организации</span><span class="sxs-lookup"><span data-stu-id="4eaf0-229">Engage your organization</span></span>

1. <span data-ttu-id="4eaf0-230">Определите владельцев долей, подтвердим сценарии и разработайте план проекта.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-230">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="4eaf0-231">Настройка параметров и применение лицензий.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-231">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="4eaf0-232">Начало осведомленности и подготовки — набор чемпионов.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-232">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="4eaf0-233">Раскатывать поэтапно.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-233">Roll out in stages.</span></span>  
1. <span data-ttu-id="4eaf0-234">Сбор отзывов и итерации.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-234">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="4eaf0-235">По мере роста использования планируйте любые кредиты AI Builder по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="4eaf0-235">As usage grows plan for any AI Builder credits as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="4eaf0-236">См. также</span><span class="sxs-lookup"><span data-stu-id="4eaf0-236">See also</span></span>

[<span data-ttu-id="4eaf0-237">Сценарии и использование случаев для SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="4eaf0-237">Scenarios and use cases for SharePoint Syntex</span></span>](adoption-scenarios.md)
