---
title: Тестирование встроенных классификаторов с использованием меток хранения (Предварительная версия)
f1.keywords:
- NOCSH
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
description: Microsoft 365 поставляется с несколькими встроенными классификаторами, которые можно использовать для определения и маркировки контента в Организации. В этом разделе показано, как подготовиться к использованию этих классификаторов.
ms.openlocfilehash: 2652df8d79b06d6614e2478843195e67de0a8ebb
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371411"
---
# <a name="testing-built-in-classifiers-using-retention-labels-preview"></a><span data-ttu-id="d6f9c-104">Тестирование встроенных классификаторов с использованием меток хранения (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="d6f9c-104">Testing built-in classifiers using retention labels (preview)</span></span>

<span data-ttu-id="d6f9c-105">Корпорация Майкрософт протестировала и проверила пять классификаторов, которые помогут определить определенные категории контента.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-105">Microsoft has trained and tested five classifiers which can help to identify certain categories of content.</span></span> <span data-ttu-id="d6f9c-106">Эти классификаторы отображаются в `Ready to use` группе по умолчанию и обучены с помощью очень больших наборов данных.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-106">These classifiers show up in the `Ready to use` group by default and were trained using very large sample data sets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6f9c-107">Перед использованием встроенных классификаторов в классификации и маркировке в рабочем процессе необходимо протестировать его по образцу контента вашей организации, который вы будете подразделовать, чтобы убедиться в том, что прогноз классификации соответствует вашим ожиданиям.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-107">Before using built-in classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

<span data-ttu-id="d6f9c-108">Более подробную информацию о классификаторах можно узнать в статье [Начало работы с поездными классификаторами (Предварительная версия)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="d6f9c-108">For more information on trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="d6f9c-109">Microsoft 365 поставляется с пятью рекомендуемыми встроенными классификаторами:</span><span class="sxs-lookup"><span data-stu-id="d6f9c-109">Microsoft 365 comes with five recommended built-in classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="d6f9c-110">Мы не рекомендуем использовать встроенный классификатор **Оскорбительная лексика**, так как он генерировал большое количество ложных срабатываний.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-110">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="d6f9c-111">Не используйте его и, если вы используете его в настоящее время, следует переместить бизнес-процессы из нее.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-111">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="d6f9c-112">Вместо этого рекомендуется **использовать встроенные** классификаторы **угроз**, **ненормативных и ненормативных слов**.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-112">We recommend using the **Threat**, **Profanity**, and **Harassment** built-in classifiers instead.</span></span>

- <span data-ttu-id="d6f9c-113">**Resume**: обнаружение элементов, которые являются текстовыми учетными записями персональных, образовательных, профессиональных квалификации, опыта работы и других личных сведений</span><span class="sxs-lookup"><span data-stu-id="d6f9c-113">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="d6f9c-114">**Исходный код**: обнаружение элементов, которые содержат набор инструкций и операторов, написанных на 25 самых распространенных языковых компьютерных языках на сайте GitHub</span><span class="sxs-lookup"><span data-stu-id="d6f9c-114">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>

  |<span data-ttu-id="d6f9c-115">имя языка</span><span class="sxs-lookup"><span data-stu-id="d6f9c-115">language name</span></span>|||||
  |---------|---------|---------|---------|---------|
  |<span data-ttu-id="d6f9c-116">Используем</span><span class="sxs-lookup"><span data-stu-id="d6f9c-116">ActionScript</span></span>|<span data-ttu-id="d6f9c-117">C</span><span class="sxs-lookup"><span data-stu-id="d6f9c-117">C</span></span>        |<span data-ttu-id="d6f9c-118">Диска #</span><span class="sxs-lookup"><span data-stu-id="d6f9c-118">C#</span></span>       |<span data-ttu-id="d6f9c-119">Языка</span><span class="sxs-lookup"><span data-stu-id="d6f9c-119">C++</span></span>     |<span data-ttu-id="d6f9c-120">кложуре</span><span class="sxs-lookup"><span data-stu-id="d6f9c-120">Clojure</span></span>  |
  |<span data-ttu-id="d6f9c-121">коффискрипт</span><span class="sxs-lookup"><span data-stu-id="d6f9c-121">CoffeeScript</span></span>|<span data-ttu-id="d6f9c-122">CSS</span><span class="sxs-lookup"><span data-stu-id="d6f9c-122">CSS</span></span>     |<span data-ttu-id="d6f9c-123">Перейти</span><span class="sxs-lookup"><span data-stu-id="d6f9c-123">Go</span></span>       |<span data-ttu-id="d6f9c-124">хаскелл</span><span class="sxs-lookup"><span data-stu-id="d6f9c-124">Haskell</span></span> |<span data-ttu-id="d6f9c-125">HTML</span><span class="sxs-lookup"><span data-stu-id="d6f9c-125">HTML</span></span>     |
  |<span data-ttu-id="d6f9c-126">Java</span><span class="sxs-lookup"><span data-stu-id="d6f9c-126">Java</span></span>     |<span data-ttu-id="d6f9c-127">JavaScript</span><span class="sxs-lookup"><span data-stu-id="d6f9c-127">JavaScript</span></span>|<span data-ttu-id="d6f9c-128">Ограничен</span><span class="sxs-lookup"><span data-stu-id="d6f9c-128">Lua</span></span>      |<span data-ttu-id="d6f9c-129">MATLAB</span><span class="sxs-lookup"><span data-stu-id="d6f9c-129">MATLAB</span></span>   |<span data-ttu-id="d6f9c-130">Objective-C</span><span class="sxs-lookup"><span data-stu-id="d6f9c-130">Objective-C</span></span>|
  |<span data-ttu-id="d6f9c-131">Perl</span><span class="sxs-lookup"><span data-stu-id="d6f9c-131">Perl</span></span>     |<span data-ttu-id="d6f9c-132">PHP</span><span class="sxs-lookup"><span data-stu-id="d6f9c-132">PHP</span></span>      |<span data-ttu-id="d6f9c-133">Python</span><span class="sxs-lookup"><span data-stu-id="d6f9c-133">Python</span></span>   |<span data-ttu-id="d6f9c-134">R</span><span class="sxs-lookup"><span data-stu-id="d6f9c-134">R</span></span>        |<span data-ttu-id="d6f9c-135">Ruby</span><span class="sxs-lookup"><span data-stu-id="d6f9c-135">Ruby</span></span>     |
  |<span data-ttu-id="d6f9c-136">скала</span><span class="sxs-lookup"><span data-stu-id="d6f9c-136">Scala</span></span>    |<span data-ttu-id="d6f9c-137">Командная консоль</span><span class="sxs-lookup"><span data-stu-id="d6f9c-137">Shell</span></span>    |<span data-ttu-id="d6f9c-138">SWIFT</span><span class="sxs-lookup"><span data-stu-id="d6f9c-138">Swift</span></span>    |<span data-ttu-id="d6f9c-139">текс</span><span class="sxs-lookup"><span data-stu-id="d6f9c-139">Tex</span></span>      |<span data-ttu-id="d6f9c-140">Сценарий Вим</span><span class="sxs-lookup"><span data-stu-id="d6f9c-140">Vim Script</span></span>|

> [!NOTE]
> <span data-ttu-id="d6f9c-141">Исходный код обучен для определения, когда основная часть текста является исходным кодом.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-141">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="d6f9c-142">Он не определяет текст исходного кода, который называется обычным текстом.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-142">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="d6f9c-143">**Преследования**: обнаруживает определенную категорию оскорбительных элементов текста, относящихся к нежелательным действиям, предназначенным для одного или нескольких пользователей, на основе следующих характеристик: состязание, этническость, религион, Национальный источник, пол, подвижность, возраст, инвалидность</span><span class="sxs-lookup"><span data-stu-id="d6f9c-143">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="d6f9c-144">**Ненормативная лексика**: обнаруживает определенную категорию нежелательных текстовых элементов языка, содержащих выражения, которые считают большинство людей</span><span class="sxs-lookup"><span data-stu-id="d6f9c-144">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="d6f9c-145">**Угроза**: обнаружение конкретной категории нежелательных текстовых элементов, относящихся к угрозам для фиксации насилия или физического ущерба для пользователя или свойства</span><span class="sxs-lookup"><span data-stu-id="d6f9c-145">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6f9c-146">Обратите внимание на то, что оскорбительный язык, преследование, ненормативность и классификаторы угроз работают только с поисковым текстом, который не является исчерпывающим или полным.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-146">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span> <span data-ttu-id="d6f9c-147">Кроме того, язык и региональные стандарты постоянно меняются, и в свете этих реалитиес Корпорация Майкрософт оставляет за собой право на обновление этих классификаторов по собственному усмотрению.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-147">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="d6f9c-148">В то время как классификаторы могут помочь вашей организации в мониторинге нежелательных и других используемых языков, классификаторы не устраняют последствия такого языка и не предоставили для Организации единственный способ отслеживания и реагирования на использование такого языка.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-148">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="d6f9c-149">Ваша организация, а не Майкрософт или ее дочерние компании, остается ответственной за все решения, связанные с мониторингом, принудительным выполнением, блокировкой, удалением и хранением любого контента, идентифицируемого предварительно подготовленным классификатором.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-149">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-verify-that-a-built-in-classifier-will-meet-your-needs"></a><span data-ttu-id="d6f9c-150">Как убедиться, что встроенный классификатор отвечает вашим потребностям</span><span class="sxs-lookup"><span data-stu-id="d6f9c-150">How to verify that a built-in classifier will meet your needs</span></span>

1. <span data-ttu-id="d6f9c-151">Соберите неудаляемые тестовые элементы контента, которые вы в категории встроенного классификатора (положительные совпадения) и те из них, которые не должны быть включены (отрицательные совпадения) в тестируемой категории.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-151">Collect disposable test content items that you feel belong in the category of the built-in classifier (positive matches) and ones that shouldn't be included (negative matches) in the category you're testing.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="d6f9c-152">Элементы примера не должны быть зашифрованы и должны быть на английском языке.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-152">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="d6f9c-153">Создайте выделенную папку SharePoint Online; Подождите не менее часа, чтобы добавить папку в индекс поиска.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-153">Create a dedicated SharePoint Online folder; wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="d6f9c-154">Запишите URL-адрес папки.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-154">Make note of the folder URL.</span></span>

3. <span data-ttu-id="d6f9c-155">Войдите в центр соответствия требованиям Microsoft 365 с помощью учетной записи администратора или роли администратора безопасности и откройте **центр соответствия требованиям Microsoft 365**  >  **(Предварительная версия)**  >  **Label policies** .</span><span class="sxs-lookup"><span data-stu-id="d6f9c-155">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="d6f9c-156">Выберите `Auto-apply a label` .</span><span class="sxs-lookup"><span data-stu-id="d6f9c-156">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="d6f9c-157">Выберите `Choose a label to auto-apply` .</span><span class="sxs-lookup"><span data-stu-id="d6f9c-157">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="d6f9c-158">Выберите `Create new labels` и создайте метку для использования только с этим тестом.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-158">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="d6f9c-159">В этом случае оставьте `Retention` значение `off` .</span><span class="sxs-lookup"><span data-stu-id="d6f9c-159">When you do this, leave `Retention` set to `off`.</span></span> <span data-ttu-id="d6f9c-160">Вы не хотите включать все функции хранения и другие действия.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-160">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="d6f9c-161">В этом случае метка хранения будет использоваться просто как текстовая метка без применения каких бы то ни было действий.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-161">In this case, you'll be using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="d6f9c-162">Например, вы можете создать метку хранения под названием "Саурцекоде классификаторный тест" без действий, а затем автоматически применять эту метку хранения к контенту, который имеет классификатор исходного кода в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-162">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content that has Source code classifier as a condition.</span></span> <span data-ttu-id="d6f9c-163">Чтобы узнать больше о создании меток хранения, ознакомьтесь [со статьей Обзор меток хранения](labels.md).</span><span class="sxs-lookup"><span data-stu-id="d6f9c-163">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="d6f9c-164">Выберите `Auto-apply a label` , а затем `Choose a label to auto-apply` .</span><span class="sxs-lookup"><span data-stu-id="d6f9c-164">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="d6f9c-165">Дополнительные сведения об использовании метки с автоматическим применением метки можно узнать в статье [Автоматическое применение метки хранения на основе условия](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span><span class="sxs-lookup"><span data-stu-id="d6f9c-165">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="d6f9c-166">Выберите метку теста из списка и нажмите кнопку `Next` .</span><span class="sxs-lookup"><span data-stu-id="d6f9c-166">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="d6f9c-167">Выберите `Apply label to content that matches a trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="d6f9c-167">Choose `Apply label to content that matches a trainable classifier`.</span></span>

   ![Выбор классификатора в качестве условия](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

10. <span data-ttu-id="d6f9c-169">Выберите классификатор из списка, в данном случае`Source Code`</span><span class="sxs-lookup"><span data-stu-id="d6f9c-169">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="d6f9c-170">Назовите политику, например "исходный код, встроенный в проверку классификатора".</span><span class="sxs-lookup"><span data-stu-id="d6f9c-170">Name the policy, for example "Source code built-in classifier test".</span></span>

12. <span data-ttu-id="d6f9c-171">Выберите `Let me choose specific locations` .</span><span class="sxs-lookup"><span data-stu-id="d6f9c-171">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="d6f9c-172">Отключите все расположения, кроме `SharePoint sites` и выберите `Choose sites` .</span><span class="sxs-lookup"><span data-stu-id="d6f9c-172">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="d6f9c-173">Введите URL-адрес сайта из шага 2.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-173">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="d6f9c-174">Завершите работу мастера и выберите`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="d6f9c-174">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="d6f9c-175">Поместите тестовые элементы в выделенную папку SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-175">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="d6f9c-176">Разрешает применение метки к часам.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-176">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="d6f9c-177">Проверьте свойства документов для метки, чтобы убедиться, что классификатор включал и исключил тестовое содержимое, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-177">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="d6f9c-178">Просмотрите элементы, помеченные как отмеченные.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-178">Review the items that were labeled.</span></span>

20. <span data-ttu-id="d6f9c-179">Удалите содержимое и политику меток, если вы завершили тестирование.</span><span class="sxs-lookup"><span data-stu-id="d6f9c-179">Delete the content and the label policy if you're done with your testing.</span></span>

<span data-ttu-id="d6f9c-180">См. также:</span><span class="sxs-lookup"><span data-stu-id="d6f9c-180">See also:</span></span>

- [<span data-ttu-id="d6f9c-181">Начало работы с обучаемыми классификаторами (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="d6f9c-181">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="d6f9c-182">Обзор меток хранения</span><span class="sxs-lookup"><span data-stu-id="d6f9c-182">Overview of retention labels</span></span>](labels.md)
- [<span data-ttu-id="d6f9c-183">Автоматическое применение политики меток хранения на основе условия</span><span class="sxs-lookup"><span data-stu-id="d6f9c-183">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)
