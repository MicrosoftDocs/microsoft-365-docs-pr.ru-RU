---
title: Использование готового классификатора (предварительная версия)
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: В Microsoft 365 имеется ряд готовых к использованию классификаторов машинного обучения, которые можно использовать для определения и маркировки содержимого в Организации. В этом разделе показано, как подготовиться к использованию этих средств для использования классификаторов.
ms.openlocfilehash: 3387d8fa91e88ec966e570e8eca339ebaa45fa27
ms.sourcegitcommit: 7c977771fc295ca1e4e9b16a6d05faee8edeadad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "38690874"
---
# <a name="using-a-ready-to-use-classifier-preview"></a><span data-ttu-id="9807a-104">Использование готового классификатора (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="9807a-104">Using a ready to use classifier (preview)</span></span>

<span data-ttu-id="9807a-105">Корпорация Майкрософт обученное и протестированное количество классификаторов, использующих очень большие наборы данных, поможет определить некоторые категории контента.</span><span class="sxs-lookup"><span data-stu-id="9807a-105">Microsoft has trained and tested number of classifiers using very large sample data sets can help to identify certain categories of content.</span></span> <span data-ttu-id="9807a-106">Ознакомьтесь [со статьей начало работы с обучением классификаторов (Предварительная версия)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="9807a-106">See [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span> <span data-ttu-id="9807a-107">Эти классификаторы отображаются в `Ready to use` группе по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9807a-107">These classifiers show up in the `Ready to use` group by default.</span></span>

- <span data-ttu-id="9807a-108">**Оскорбительный язык**: обнаружение текстовых элементов, которые содержат ненормативные (ненормативные), слурс, таунтс и замаскированные выражения (выражения, которые имеют такое же значение, что и более оскорбительный термин).</span><span class="sxs-lookup"><span data-stu-id="9807a-108">**Offensive Language**: detects text items which contain profanities, slurs, taunts, and disguised expressions (which are expressions that have the same meaning as a more offensive term).</span></span>
- <span data-ttu-id="9807a-109">**Resume**: обнаруживает элементы, являющиеся текстовыми учетными записями личного, учебного, профессионального квалификации, опыта работы и других персональных данных</span><span class="sxs-lookup"><span data-stu-id="9807a-109">**Resumes**: detects items which are textual accounts of an applicant's personal, educational, professional qualifications, work experience and other personally identifying information</span></span>
- <span data-ttu-id="9807a-110">**Саурцекоде**: обнаружение элементов, которые содержат набор инструкций и операторов, написанных на широко используемых языках программирования компьютеров.</span><span class="sxs-lookup"><span data-stu-id="9807a-110">**SourceCode**: detects items which contain a set of instructions and statements written in widely used computer programming languages.</span></span>
- <span data-ttu-id="9807a-111">**Преследования**: обнаруживает определенную категорию нежелательных текстовых элементов, относящихся к нежелательным действиям, предназначенным для одного или нескольких пользователей на основе следующих характеристик: состязание, этническость, религион, Национальный источник, пол, упоминание сексуального характера, возраст, инвалидность.</span><span class="sxs-lookup"><span data-stu-id="9807a-111">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="9807a-112">**Ненормативная лексика**: обнаруживает определенную категорию нежелательных текстовых элементов языка, содержащих выражения, которые считают большинство людей</span><span class="sxs-lookup"><span data-stu-id="9807a-112">**Profanity**: detects a specific category of offensive language text items which contain expressions that embarrass most people</span></span>
- <span data-ttu-id="9807a-113">**Угроза**: обнаружение конкретной категории нежелательных текстовых элементов, относящихся к угрозам для фиксации насилия или физического ущерба для пользователя или свойства</span><span class="sxs-lookup"><span data-stu-id="9807a-113">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

> [!NOTE]
> <span data-ttu-id="9807a-114">Прежде чем приступить к использованию классификаторов для классификации и маркировки рабочего процесса, необходимо протестировать его по образцу контента вашей организации, который вы будете подразделовать, чтобы убедиться в том, что прогноз классификации соответствует вашим ожиданиям.</span><span class="sxs-lookup"><span data-stu-id="9807a-114">Before using ready to use classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9807a-115">Обратите внимание на то, что оскорбительный язык, преследование, ненормативность и классификаторы угроз работают только с поисковым текстом, который не является исчерпывающим или полным.</span><span class="sxs-lookup"><span data-stu-id="9807a-115">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="9807a-116">Кроме того, язык и региональные стандарты постоянно меняются, и в свете этих реалитиес Корпорация Майкрософт оставляет за собой право на обновление этих классификаторов по собственному усмотрению.</span><span class="sxs-lookup"><span data-stu-id="9807a-116">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="9807a-117">В то время как классификаторы могут помочь вашей организации в мониторинге нежелательных и других используемых языков, классификаторы не устраняют последствия такого языка и не предоставили для Организации единственный способ отслеживания и реагирования на использование такой язык.</span><span class="sxs-lookup"><span data-stu-id="9807a-117">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization’s sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="9807a-118">Ваша организация, а не Майкрософт или ее дочерние компании, остается ответственной за все решения, связанные с мониторингом, принудительным выполнением, блокировкой, удалением и хранением любого контента, идентифицируемого предварительно подготовленным классификатором.</span><span class="sxs-lookup"><span data-stu-id="9807a-118">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-prepare-for-and-use-a-ready-to-use-classifier"></a><span data-ttu-id="9807a-119">Подготовка к использованию классификатора и его использование</span><span class="sxs-lookup"><span data-stu-id="9807a-119">How to prepare for and use a ready to use classifier</span></span>

1. <span data-ttu-id="9807a-120">Соберите неудаляемые тестовые элементы контента, которые вы относите в категорию "готово к использованию классификатора" (положительные совпадения) и те, которые не должны включаться (отрицательные совпадения) в тестируемой категории.</span><span class="sxs-lookup"><span data-stu-id="9807a-120">Collect disposable test content items that you feel belong in the category of the ready to use classifier (positive matches) and ones that should not be included (negative matches) in the category you are testing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9807a-121">Элементы примера не должны быть зашифрованы и должны быть на английском языке.</span><span class="sxs-lookup"><span data-stu-id="9807a-121">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="9807a-122">Создайте выделенную папку SharePoint Online, дождитесь добавления папки в индекс поиска по крайней мере в течение часа.</span><span class="sxs-lookup"><span data-stu-id="9807a-122">Create a dedicated SharePoint Online folder, wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="9807a-123">Запишите URL-адрес папки.</span><span class="sxs-lookup"><span data-stu-id="9807a-123">Make note of the folder URL.</span></span>

3. <span data-ttu-id="9807a-124">Войдите в центр соответствия требованиям Microsoft 365, используя доступ к роли администратора безопасности или администратора безопасности и откройте **центр соответствия требованиям Microsoft 365** или **Microsoft 365 центр** > безопасности**записей (Предварительная версия)** > \*\*\*\* .</span><span class="sxs-lookup"><span data-stu-id="9807a-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="9807a-125">Выберите `Auto-apply a label`.</span><span class="sxs-lookup"><span data-stu-id="9807a-125">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="9807a-126">Выберите `Choose a label to auto-apply`.</span><span class="sxs-lookup"><span data-stu-id="9807a-126">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="9807a-127">Выберите `Create new labels` и создайте метку для использования только с этим тестом.</span><span class="sxs-lookup"><span data-stu-id="9807a-127">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="9807a-128">При этом оставьте `Retention` параметр отключенным.</span><span class="sxs-lookup"><span data-stu-id="9807a-128">When you do this, leave `Retention` set to off.</span></span> <span data-ttu-id="9807a-129">Вы не хотите включать все функции хранения и другие действия.</span><span class="sxs-lookup"><span data-stu-id="9807a-129">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="9807a-130">В этом случае вы будете использовать метку хранения просто как текстовую метку без применения каких бы то ни было действий.</span><span class="sxs-lookup"><span data-stu-id="9807a-130">In this case, you'll be using using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="9807a-131">Например, вы можете создать метку хранения под названием "Саурцекоде классификаторный тест" без действий, а затем автоматически применять эту метку хранения к контенту с помощью классификатора исходного кода в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="9807a-131">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content with that has Source code classifier as a condition.</span></span> <span data-ttu-id="9807a-132">Чтобы узнать больше о создании меток хранения, ознакомьтесь [со статьей Обзор меток хранения](labels.md).</span><span class="sxs-lookup"><span data-stu-id="9807a-132">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="9807a-133">Выберите `Auto-apply a label` , а `Choose a label to auto-apply`затем.</span><span class="sxs-lookup"><span data-stu-id="9807a-133">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="9807a-134">Дополнительные сведения об использовании метки с автоматическим применением метки можно узнать в статье [Автоматическое применение метки хранения на основе условия](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span><span class="sxs-lookup"><span data-stu-id="9807a-134">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="9807a-135">Выберите метку теста из списка и нажмите кнопку `Next`.</span><span class="sxs-lookup"><span data-stu-id="9807a-135">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="9807a-136">Выберите `Apply label to content that matches a trainable classifier`.</span><span class="sxs-lookup"><span data-stu-id="9807a-136">Choose `Apply label to content that matches a trainable classifier`.</span></span>

![Выбор классификатора в качестве условия](media/classifier-pre-trained-apply-label-match-trainable-classifier.png)<span data-ttu-id="9807a-138">.</span><span class="sxs-lookup"><span data-stu-id="9807a-138"></span></span>

10. <span data-ttu-id="9807a-139">Выберите классификатор из списка, в данном случае`Source Code`</span><span class="sxs-lookup"><span data-stu-id="9807a-139">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="9807a-140">Назовите политику, например "исходный код готов к использованию проверки классификатора".</span><span class="sxs-lookup"><span data-stu-id="9807a-140">Name the policy, for example "Source code ready to use classifier test".</span></span>

12. <span data-ttu-id="9807a-141">Выберите `Let me choose specific locations`.</span><span class="sxs-lookup"><span data-stu-id="9807a-141">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="9807a-142">Отключите все расположения, кроме `SharePoint sites` и выберите `Choose sites`.</span><span class="sxs-lookup"><span data-stu-id="9807a-142">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="9807a-143">Введите URL-адрес сайта из шага 2.</span><span class="sxs-lookup"><span data-stu-id="9807a-143">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="9807a-144">Завершите работу мастера и выберите`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="9807a-144">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="9807a-145">Поместите тестовые элементы в выделенную папку SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9807a-145">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="9807a-146">Разрешает применение метки к часам.</span><span class="sxs-lookup"><span data-stu-id="9807a-146">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="9807a-147">Проверьте свойства документов для метки, чтобы убедиться, что классификатор включал и исключил тестовое содержимое, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="9807a-147">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="9807a-148">Просмотрите элементы, помеченные как отмеченные.</span><span class="sxs-lookup"><span data-stu-id="9807a-148">Review the items that were labeled .</span></span>

20. <span data-ttu-id="9807a-149">Удалите содержимое и политику меток, если вы завершили тестирование.</span><span class="sxs-lookup"><span data-stu-id="9807a-149">Delete the content, and the label policy if you are done with your testing.</span></span>

<span data-ttu-id="9807a-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="9807a-150">See also:</span></span>

- [<span data-ttu-id="9807a-151">Начало работы с обучаемыми классификаторами (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="9807a-151">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="9807a-152">Обзор меток хранения</span><span class="sxs-lookup"><span data-stu-id="9807a-152">Overview of retention labels</span></span>](labels.md)
- [<span data-ttu-id="9807a-153">Автоматическое применение политики меток хранения на основе условия</span><span class="sxs-lookup"><span data-stu-id="9807a-153">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)