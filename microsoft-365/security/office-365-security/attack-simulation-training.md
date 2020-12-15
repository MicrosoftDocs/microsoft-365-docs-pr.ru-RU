---
title: Имитация фишинговой атаки с помощью Microsoft Defender для Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Администраторы могут научиться имитировать фишинговые атаки и обучить пользователей предотвращению фишинга с помощью обучения имитации атак в Microsoft Defender для Office 365.
ms.openlocfilehash: 3707041067fd76ee9535d0dccf5cdfcb9d74fbd7
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667581"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="f3fe8-103">Имитация фишинговой атаки</span><span class="sxs-lookup"><span data-stu-id="f3fe8-103">Simulate a phishing attack</span></span>

<span data-ttu-id="f3fe8-104">Обучение имитатору атак в Microsoft Defender для Office 365 позволяет запускать в организации имитации кибератак для тестирования политик и методик безопасности, а также обучение сотрудников повышению осведомленности сотрудников и снижению их подверженности атакам.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-104">Attack simulator training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="f3fe8-105">В этой статье вы можете создать имитацию фишинговой атаки с помощью обучения имитатору атак.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-105">This article walks you through creating  a simulated phishing attack using attack simulator training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="f3fe8-106">Чтобы запустить имитацию фишинговой атаки, откройте Центр безопасности [Microsoft 365,](https://security.microsoft.com/)перейдите в эмулятор атак & электронной почты и перейдите на вкладку  \>  [**"Имитации".**](https://security.microsoft.com/attacksimulator?viewid=simulations)</span><span class="sxs-lookup"><span data-stu-id="f3fe8-106">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulator**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="f3fe8-107">В **области "Имитации"** выберите **+Запустить имитацию.**</span><span class="sxs-lookup"><span data-stu-id="f3fe8-107">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Запуск кнопки имитации в Центре безопасности Microsoft 365](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="f3fe8-109">В любой момент во время создания имитации можно сохранить и закрыть, чтобы продолжить настройку имитации в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-109">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="f3fe8-110">Выбор метода социальной инженерии</span><span class="sxs-lookup"><span data-stu-id="f3fe8-110">Selecting a social engineering technique</span></span>

<span data-ttu-id="f3fe8-111">Выберите один из 4 различных методов, на основе структуры [MITRE ATT&CK®](https://attack.mitre.org/techniques/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="f3fe8-111">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="f3fe8-112">Различные полезной нагрузки доступны для различных методов:</span><span class="sxs-lookup"><span data-stu-id="f3fe8-112">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="f3fe8-113">**При сборе** учетных данных пользователи пытаются получить учетные данные на известном веб-сайте с полями ввода для отправки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-113">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="f3fe8-114">**Вредоносное вложение** добавляет вредоносное вложение в сообщение.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-114">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="f3fe8-115">Когда пользователь открывает вложение, запустится произвольный код, который поможет злоумышленнику скомпрометировать устройство цели.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-115">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="f3fe8-116">**Ссылка во вложении** — это тип гибридного сбора учетных данных.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-116">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="f3fe8-117">Злоумышленник вставляет URL-адрес в вложение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-117">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="f3fe8-118">URL-адрес во вложении следует той же методике, что и сбор учетных данных.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-118">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="f3fe8-119">**Ссылка на вредоносные** программы будет запускать произвольный код из файла, который имеется в известной службе общего доступа к файлам.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-119">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="f3fe8-120">Сообщение, отправленное пользователю, будет содержать ссылку на этот вредоносный файл.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-120">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="f3fe8-121">Открытие файла и помощь злоумышленнику в компрометации устройства цели.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-121">Opening the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="f3fe8-122">Если **щелкнуть "Просмотреть сведения"** в описании каждого метода, отобразит дополнительную информацию и шаги моделирования для этого метода.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-122">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Этапы моделирования сбора учетных данных в рамках обучения моделированию атак в Центре безопасности Microsoft 365](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="f3fe8-124">После выбора метода и нажатия кнопки "Далее" придайте имитации имя и описание (при желании).</span><span class="sxs-lookup"><span data-stu-id="f3fe8-124">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="f3fe8-125">Выбор полезной нагрузки</span><span class="sxs-lookup"><span data-stu-id="f3fe8-125">Selecting a payload</span></span>

<span data-ttu-id="f3fe8-126">Затем необходимо выбрать полезное данные из существующего каталога полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-126">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="f3fe8-127">У полезной нагрузки есть несколько точек данных, которые помогут выбрать:</span><span class="sxs-lookup"><span data-stu-id="f3fe8-127">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="f3fe8-128">**Скорость щелчка** рассчитывает, сколько людей щелкнули эту нагрузку.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-128">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="f3fe8-129">**Прогнозируемая коэффициент** компрометации прогнозирования процента людей, которые будут скомпрометированы этой полезной нагрузкой на основе исторических данных для полезной нагрузки в Microsoft Defender для клиентов Office 365.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-129">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="f3fe8-130">**Запущенные имитации** подсчитывают, сколько раз эти полезной нагрузки использовались в других моделированиях.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-130">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="f3fe8-131">**Сложность,** доступная с помощью **фильтров,** рассчитывается на основе количества индикаторов в полезной нагрузке, которые подсказывают, что в ней нацелена атака.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-131">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="f3fe8-132">Чем больше индикаторов, тем сложнее.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-132">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="f3fe8-133">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is part of Microsoft's pre-existing payload catalog (global).</span><span class="sxs-lookup"><span data-stu-id="f3fe8-133">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Выбранные полезной нагрузки в рамках обучения моделированию атак в Центре безопасности Microsoft 365](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="f3fe8-135">Выберите в списке полезной нагрузки, чтобы просмотреть их с дополнительными сведениями о них.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-135">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="f3fe8-136">Если вы хотите создать собственные полезной нагрузки, ознакомьтесь с созданием полезной нагрузки для [обучения моделированию атак.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="f3fe8-136">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="f3fe8-137">Выбор целевой аудитории</span><span class="sxs-lookup"><span data-stu-id="f3fe8-137">Audience targeting</span></span>

<span data-ttu-id="f3fe8-138">Теперь пора выбрать аудиторию имитации.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-138">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="f3fe8-139">Вы можете включить **всех пользователей** в организации или включить только **определенных пользователей и группы.**</span><span class="sxs-lookup"><span data-stu-id="f3fe8-139">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="f3fe8-140">Если вы решите включить **только определенных пользователей и группы,** вы можете:</span><span class="sxs-lookup"><span data-stu-id="f3fe8-140">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="f3fe8-141">Добавьте **пользователей,** что позволяет использовать поиск для клиента, а также расширенные возможности поиска и фильтрации, например для пользователей, которые не были нацелены на моделирование за последние 3 месяца.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-141">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="f3fe8-142">![Фильтрация пользователей при моделировании атак в Центре безопасности Microsoft 365](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="f3fe8-142">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="f3fe8-143">**Импорт из CSV-данных** позволяет импортировать предопределяемую набор пользователей для этого моделирования.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-143">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="f3fe8-144">Назначение обучения</span><span class="sxs-lookup"><span data-stu-id="f3fe8-144">Assigning training</span></span>

<span data-ttu-id="f3fe8-145">Рекомендуется назначать обучение для каждого моделирования, так как сотрудники, которые проходят обучение, менее подвержены аналогичным атакам.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-145">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="f3fe8-146">Вы можете выбрать обучение, назначенное вам, или выбрать учебные курсы и модули самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-146">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="f3fe8-147">Выберите дату **окончания обучения,** чтобы убедиться, что сотрудники завершили обучение своевременно.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-147">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="f3fe8-148">Если выбрать курсы и модули самостоятельно, вы по-прежнему сможете увидеть рекомендуемое содержимое, а также все доступные курсы и модули.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-148">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Добавление рекомендованного обучения в рамках обучения моделированию атак в Центре безопасности Microsoft 365](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="f3fe8-150">На следующих шагах вам  потребуется добавить учебные курсы, если вы решили выбрать его самостоятельно и настроить свою следующую страницу обучения.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-150">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="f3fe8-151">Вы сможете просмотреть страницу обучения, а также изменить заголовщик и ее тело.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-151">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="f3fe8-152">Сведения о запуске и проверка</span><span class="sxs-lookup"><span data-stu-id="f3fe8-152">Launch details and review</span></span>

<span data-ttu-id="f3fe8-153">Теперь, когда все настроено, вы можете запустить это моделирование немедленно или запланировать его на более позднее время.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-153">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="f3fe8-154">Вам также потребуется выбрать время окончания моделирования.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-154">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="f3fe8-155">Мы перестанет захватывать взаимодействие с этим моделированием после выбранного времени.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-155">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="f3fe8-156">**Включить доставку в часовом** поясе с учетом региона для доставки имитированных сообщений о атаках сотрудникам в рабочее время в зависимости от региона.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-156">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="f3fe8-157">После этого нажмите кнопку  "Далее" и просмотрите сведения о моделировании.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-157">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="f3fe8-158">Нажмите **кнопку "Изменить"** на любом из частей, чтобы вернуться и изменить все сведения, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="f3fe8-158">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="f3fe8-159">После этого нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="f3fe8-159">Once done, click **Submit**.</span></span>
