---
title: Имитация атаки с фишингом с помощью защитника Майкрософт для
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: В этой статье рассказывается, как имитировать фишинговые атаки и обучить пользователей в защите от фишинга с помощью обучающих курсов по атакам в защитнике Майкрософт для Office 365.
ms.openlocfilehash: b9b8a431fc28942f5e11bc7ce2e805ca082cf36b
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944571"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="f76cc-103">Имитация атаки фишинга</span><span class="sxs-lookup"><span data-stu-id="f76cc-103">Simulate a phishing attack</span></span>

<span data-ttu-id="f76cc-104">Учебные курсы по атакам через защитник Майкрософт для Office 365 позволяет выполнять в Организации неблагоприятные имитации атаки кибератак, чтобы протестировать политики и методики безопасности, а также обучить сотрудников Организации, чтобы повысить их осведомленность и снизить риск атак на сусцептибилити.</span><span class="sxs-lookup"><span data-stu-id="f76cc-104">Attack simulator training through Microsoft Defender for Office 365 lets you run benign cyber attack simulations on your organization to test your security policies and practices, as well as train the employees of your organization to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="f76cc-105">Ниже приведена пошаговое руководство по моделированию атаки с фишингом с помощью учебного захождения для симуляторов атак.</span><span class="sxs-lookup"><span data-stu-id="f76cc-105">The following walks you through simulating a phishing attack using attack simulator training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="f76cc-106">Чтобы запустить имитацию атаки фишинга, перейдите в [Центр безопасности Microsoft 365](https://security.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f76cc-106">To launch a simulated phishing attack, navigate to the [Microsoft 365 security center](https://security.microsoft.com/).</span></span> <span data-ttu-id="f76cc-107">В разделе **Электронная почта & совместная работа** щелкните **симулятор атак** и переключитесь на вкладку [**имитация**](https://security.microsoft.com/attacksimulator?viewid=simulations) .</span><span class="sxs-lookup"><span data-stu-id="f76cc-107">Under **Email & collaboration** click on **Attack simulator** and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="f76cc-108">В разделе **имитация** выберите **+ запустить имитацию**.</span><span class="sxs-lookup"><span data-stu-id="f76cc-108">Under **Simulations** select **+ Launch a simulation**.</span></span>

![Запуск кнопки моделирования в центре безопасности Microsoft 365](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="f76cc-110">В любой момент при создании модели можно сохранить и закрыть, чтобы продолжить настройку имитации позже.</span><span class="sxs-lookup"><span data-stu-id="f76cc-110">At any point during simulation creation you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="f76cc-111">Выбор метода социального проектирования</span><span class="sxs-lookup"><span data-stu-id="f76cc-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="f76cc-112">Выберите один из четырех различных способов, проверенных в [МИТРЕ ATT&а® Framework](https://attack.mitre.org/techniques/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="f76cc-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="f76cc-113">Разные полезные данные доступны для разных приемов.</span><span class="sxs-lookup"><span data-stu-id="f76cc-113">Different payloads are available for different techniques.</span></span>

- <span data-ttu-id="f76cc-114">Сбор **учетных данных** пытается собрать учетные данные сотрудников, отправляя их на известный веб-сайт с полями ввода для ввода имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="f76cc-114">**Credential harvest** attempts to collect credentials from employees by taking them to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="f76cc-115">**Вложение вредоносных программ** добавляет к сообщению вредоносное вложение.</span><span class="sxs-lookup"><span data-stu-id="f76cc-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="f76cc-116">При открытии этого вложения запустится произвольный код, который поможет злоумышленнику взвредить целевое устройство.</span><span class="sxs-lookup"><span data-stu-id="f76cc-116">When opened, this attachment will run some arbitrary code that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="f76cc-117">**Ссылка во вложении** — это тип гибридной системы сбора учетных данных.</span><span class="sxs-lookup"><span data-stu-id="f76cc-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="f76cc-118">Злоумышленник вставляет URL-адрес во вложение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f76cc-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="f76cc-119">URL-адрес внутри вложения соответствует тому же методу, что и сбор учетных данных.</span><span class="sxs-lookup"><span data-stu-id="f76cc-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="f76cc-120">**Ссылка на вредоносный** код запустит некоторый произвольный код из файла, размещенного на хорошо известном сайте совместного использования файлов.</span><span class="sxs-lookup"><span data-stu-id="f76cc-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file-sharing site.</span></span> <span data-ttu-id="f76cc-121">Ссылка на этот вредоносный файл добавляется в сообщение, отправляемое на целевой объект, и щелкает его, чтобы запустить файл и помочь злоумышленнику получить несанкционированный доступ к оконечному устройству.</span><span class="sxs-lookup"><span data-stu-id="f76cc-121">A link to this malicious file is added to the message sent to the target and clicking it will run the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="f76cc-122">При нажатии кнопки **Просмотр сведений** в описании каждого метода отображаются дополнительные сведения о приеме, а также действия по моделированию для этого метода.</span><span class="sxs-lookup"><span data-stu-id="f76cc-122">Clicking on **View details** within the description of each technique will display further information about the technique as well as the simulation steps for that technique.</span></span>
>
> ![Действия по моделированию учетных данных при моделировании атак в центре безопасности Майкрософт 365](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="f76cc-124">После выбора метода и нажатия кнопки **Далее** укажите имя и, при необходимости, описание модели.</span><span class="sxs-lookup"><span data-stu-id="f76cc-124">Once you've selected the technique and clicked on **Next** give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="f76cc-125">Выбор полезных данных</span><span class="sxs-lookup"><span data-stu-id="f76cc-125">Selecting a payload</span></span>

<span data-ttu-id="f76cc-126">Далее необходимо выбрать полезные данные из ранее существующего каталога полезных данных.</span><span class="sxs-lookup"><span data-stu-id="f76cc-126">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="f76cc-127">Полезные данные содержат ряд точек данных, которые помогут выбрать:</span><span class="sxs-lookup"><span data-stu-id="f76cc-127">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="f76cc-128">**Выберите** количество пользователей, которые щелкают эту полезную нагрузку.</span><span class="sxs-lookup"><span data-stu-id="f76cc-128">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="f76cc-129">**Предсказуемая частота угроз** прогнозирует процент людей, которые будут скомпрометированы на основе исторических данных для этих полезных данных в защитнике Майкрософт для пользователей Office 365.</span><span class="sxs-lookup"><span data-stu-id="f76cc-129">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historic data for this payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="f76cc-130">**Запущенных эмуляций** подсчитывает количество использований этих полезных данных в других эмуляциях.</span><span class="sxs-lookup"><span data-stu-id="f76cc-130">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="f76cc-131">**Сложность** , доступная через **фильтры** , вычисляется на основе количества индикаторов в полезных данных, которые могут быть нацелены на атаку.</span><span class="sxs-lookup"><span data-stu-id="f76cc-131">**Complexity** , available through **filters** , is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="f76cc-132">Дополнительные индикаторы понизьте сложность.</span><span class="sxs-lookup"><span data-stu-id="f76cc-132">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="f76cc-133">**Источник** , доступный через **фильтры** , указывает, были ли полезные данные созданы в вашем клиенте или является частью уже существующего каталога полезных данных корпорации Майкрософт (Global).</span><span class="sxs-lookup"><span data-stu-id="f76cc-133">**Source** , available through **filters** , indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Выбранные полезные данные в обучающем процессе моделирования атак в центре безопасности Майкрософт 365](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="f76cc-135">Выберите полезные данные в списке для предварительного просмотра полезных данных с дополнительными сведениями о ней.</span><span class="sxs-lookup"><span data-stu-id="f76cc-135">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="f76cc-136">Если вы хотите создать свои полезные данные, прочитайте статью [Создание полезных данных для обучения по моделированию атак](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="f76cc-136">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="f76cc-137">Выбор целевой аудитории</span><span class="sxs-lookup"><span data-stu-id="f76cc-137">Audience targeting</span></span>

<span data-ttu-id="f76cc-138">Теперь настало время выбрать аудиторию этого моделирования.</span><span class="sxs-lookup"><span data-stu-id="f76cc-138">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="f76cc-139">Можно выбрать **Включение всех пользователей в Организации** или **Включение только определенных пользователей и групп**.</span><span class="sxs-lookup"><span data-stu-id="f76cc-139">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span> 

<span data-ttu-id="f76cc-140">Если вы решили **включить только определенных пользователей и групп** , можно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f76cc-140">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="f76cc-141">**Добавление пользователей** , которое позволяет использовать поиск клиента, а также расширенные возможности поиска и фильтрации, например целевые пользователи, которым не назначена эмуляция в последние 3 месяца.</span><span class="sxs-lookup"><span data-stu-id="f76cc-141">**Add users** , which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="f76cc-142">![Фильтрация пользователей в учебном курсе "моделирование атак" в центре безопасности Майкрософт 365](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="f76cc-142">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="f76cc-143">**Импорт из CSV** позволяет импортировать предварительно определенный набор пользователей для этой имитации.</span><span class="sxs-lookup"><span data-stu-id="f76cc-143">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="f76cc-144">Назначение обучения</span><span class="sxs-lookup"><span data-stu-id="f76cc-144">Assigning training</span></span>

<span data-ttu-id="f76cc-145">Рекомендуется назначить обучение для каждой имитации, так как сотрудники, проходящих через обучение, менее подвержены воздействию подобных атак.</span><span class="sxs-lookup"><span data-stu-id="f76cc-145">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="f76cc-146">Вы можете выбрать обучение, назначенное Вам, либо самостоятельно выбрать учебные курсы и модули.</span><span class="sxs-lookup"><span data-stu-id="f76cc-146">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="f76cc-147">Выберите срок **обучения** , чтобы убедиться, что сотрудники своевременно завершают обучение.</span><span class="sxs-lookup"><span data-stu-id="f76cc-147">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="f76cc-148">Если вы решили выбрать курсы и модули самостоятельно, вы по-прежнему сможете просматривать рекомендуемый контент, а также все доступные курсы и модули.</span><span class="sxs-lookup"><span data-stu-id="f76cc-148">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Добавление рекомендуемого обучения в рамках обучения по моделированию атак в центре безопасности Майкрософт 365](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="f76cc-150">В следующих действиях необходимо **Добавить обучение** , если вы выбрали его самостоятельно и настроите начальную страницу обучения.</span><span class="sxs-lookup"><span data-stu-id="f76cc-150">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="f76cc-151">Вы сможете просмотреть учебную целевую страницу, а также изменить заголовок и основной текст.</span><span class="sxs-lookup"><span data-stu-id="f76cc-151">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="f76cc-152">Сведения о запуске и обзор</span><span class="sxs-lookup"><span data-stu-id="f76cc-152">Launch details and review</span></span>

<span data-ttu-id="f76cc-153">Теперь, когда все настроено, вы можете запустить эту имитацию немедленно или запланировать ее на более позднюю дату.</span><span class="sxs-lookup"><span data-stu-id="f76cc-153">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="f76cc-154">Кроме того, необходимо выбрать время окончания этой имитации.</span><span class="sxs-lookup"><span data-stu-id="f76cc-154">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="f76cc-155">Мы не будем перезаписывать взаимодействие с этим моделированием за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="f76cc-155">We will stop capturing interaction with this simulation past the selected time.</span></span> 

<span data-ttu-id="f76cc-156">**Включить поддержку часовых поясов для региона** для предоставления имитации сообщений о атаках сотрудникам в рабочее время в зависимости от их региона.</span><span class="sxs-lookup"><span data-stu-id="f76cc-156">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="f76cc-157">После завершения нажмите кнопку **Далее** и просмотрите сведения о модели.</span><span class="sxs-lookup"><span data-stu-id="f76cc-157">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="f76cc-158">Нажмите кнопку **Edit (изменить** ) в любой из частей, чтобы вернуться и изменить все нужные сведения.</span><span class="sxs-lookup"><span data-stu-id="f76cc-158">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="f76cc-159">После этого нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="f76cc-159">Once done, click **Submit**.</span></span>
