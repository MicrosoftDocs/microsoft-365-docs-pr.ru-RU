---
title: Имитация фишинговой атаки с помощью Microsoft Defender для Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Администраторы могут научиться имитировать фишинговые атаки и обучать пользователей предотвращению фишинга с помощью обучения имитации атаки в Microsoft Defender для Office 365.
ms.technology: mdo
ms.openlocfilehash: 27279f927a15ea94ae84112ffdc23d88ea42d2ff
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073517"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="890e0-103">Имитация фишинговой атаки</span><span class="sxs-lookup"><span data-stu-id="890e0-103">Simulate a phishing attack</span></span>

<span data-ttu-id="890e0-104">Обучение имитации атак в Microsoft Defender для Office 365 позволяет запускать в организации доброкачественные имитации кибератак для проверки политик и практик безопасности, а также обучения сотрудников повышению их осведомленности и снижению их восприимчивости к атакам.</span><span class="sxs-lookup"><span data-stu-id="890e0-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="890e0-105">В этой статье вы можете создать смоделированную фишинговую атаку с помощью обучения имитации атак.</span><span class="sxs-lookup"><span data-stu-id="890e0-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

<span data-ttu-id="890e0-106">Сведения о подготовке к имитации атаки см. в см. в игре [Get started using Attack simulation training.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="890e0-106">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="890e0-107">Чтобы запустить смоделированную фишинговую атаку, откройте центр  безопасности [Microsoft 365,](https://security.microsoft.com/)перейдите на обучение моделированию совместной & электронной почты и переключиться на вкладку \>  [**Simulations.**](https://security.microsoft.com/attacksimulator?viewid=simulations)</span><span class="sxs-lookup"><span data-stu-id="890e0-107">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="890e0-108">В **рамках моделирования** выберите **+ Запустите моделирование.**</span><span class="sxs-lookup"><span data-stu-id="890e0-108">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Запустите кнопку моделирования в центре безопасности Microsoft 365](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="890e0-110">В любой момент при создании моделирования можно сохранить и закрыть, чтобы продолжить настройку моделирования в более позднее время.</span><span class="sxs-lookup"><span data-stu-id="890e0-110">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="890e0-111">Выбор метода социальной инженерии</span><span class="sxs-lookup"><span data-stu-id="890e0-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="890e0-112">Выберите из 4 различных методов, куратором из структуры [ATT MITRE&CK®](https://attack.mitre.org/techniques/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="890e0-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="890e0-113">Различные полезной нагрузки доступны для различных методов:</span><span class="sxs-lookup"><span data-stu-id="890e0-113">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="890e0-114">**Сбор учетных** данных пытается собрать учетные данные, относя пользователей к известному выглядящем веб-сайту с входными полями для отправки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="890e0-114">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="890e0-115">**Вложение вредоносных** программ добавляет вредоносное вложение в сообщение.</span><span class="sxs-lookup"><span data-stu-id="890e0-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="890e0-116">Когда пользователь открывает вложение, запустится произвольный код, который поможет злоумышленнику скомпрометировать устройство цели.</span><span class="sxs-lookup"><span data-stu-id="890e0-116">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="890e0-117">**Ссылка в приложении** — это тип гибрида сбора учетных данных.</span><span class="sxs-lookup"><span data-stu-id="890e0-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="890e0-118">Злоумышленник вставляет URL-адрес в вложение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="890e0-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="890e0-119">URL-адрес в приложении следует той же методике, что и сбор учетных данных.</span><span class="sxs-lookup"><span data-stu-id="890e0-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="890e0-120">**Ссылка на вредоносные** программы будет запускать произвольный код из файла, хранимого в известной службе обмена файлами.</span><span class="sxs-lookup"><span data-stu-id="890e0-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="890e0-121">Сообщение, отправленное пользователю, будет содержать ссылку на этот вредоносный файл.</span><span class="sxs-lookup"><span data-stu-id="890e0-121">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="890e0-122">Открытие файла и помощь злоумышленнику в компрометации устройства цели.</span><span class="sxs-lookup"><span data-stu-id="890e0-122">Opening the file and help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="890e0-123">**URL-адрес drive-by** — это место, где вредоносный URL-адрес в сообщении отводит пользователя на знакомый веб-сайт, который бесшумно запускает и/или устанавливает код кода на устройстве пользователя.</span><span class="sxs-lookup"><span data-stu-id="890e0-123">**Drive-by URL** is where the malicious URL in the message takes the user to a familiar-looking website that silently runs and/or installs code code on the user's device.</span></span>

> [!TIP]
> <span data-ttu-id="890e0-124">Нажатие на **сведения Просмотра** в описании каждого метода отображает дополнительные сведения и шаги моделирования для метода.</span><span class="sxs-lookup"><span data-stu-id="890e0-124">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Этапы моделирования сбора учетных данных в рамках обучения моделированию атак в центре безопасности Microsoft 365](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="890e0-126">После выбора метода и нажатия на **кнопку Далее,** дайте вашему моделированию имя и необязательно описание.</span><span class="sxs-lookup"><span data-stu-id="890e0-126">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="890e0-127">Выбор полезной нагрузки</span><span class="sxs-lookup"><span data-stu-id="890e0-127">Selecting a payload</span></span>

<span data-ttu-id="890e0-128">Далее необходимо выбрать полезной нагрузки из уже существующего каталога полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="890e0-128">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="890e0-129">У полезной нагрузки есть несколько точек данных, которые помогут выбрать:</span><span class="sxs-lookup"><span data-stu-id="890e0-129">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="890e0-130">**Ставка мыши** подсчитывает, сколько людей нажали эту полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="890e0-130">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="890e0-131">**Прогнозируемая скорость** компромисса предсказывает процент людей, которые будут скомпрометироваться этой полезной нагрузкой на основе исторических данных для полезной нагрузки в Microsoft Defender для клиентов Office 365.</span><span class="sxs-lookup"><span data-stu-id="890e0-131">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="890e0-132">**Запущенные имитации** подсчитывают количество раз, когда эта полезной нагрузки использовалась в других имитациях.</span><span class="sxs-lookup"><span data-stu-id="890e0-132">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="890e0-133">**Сложность,** **доступная** с помощью фильтров, рассчитывается на основе количества индикаторов в полезной нагрузке, которая подсказывает, что объекты на нем являются атакой.</span><span class="sxs-lookup"><span data-stu-id="890e0-133">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="890e0-134">Дополнительные показатели приводят к снижению сложности.</span><span class="sxs-lookup"><span data-stu-id="890e0-134">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="890e0-135">**Источник,** доступный через **фильтры,** указывает, была ли полезной нагрузки создана на вашем клиенте или является частью уже существующего каталога полезной нагрузки Майкрософт (глобальный).</span><span class="sxs-lookup"><span data-stu-id="890e0-135">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Выбор полезной нагрузки в рамках обучения моделированию атак в центре безопасности Microsoft 365](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="890e0-137">Выберите полезной нагрузки из списка, чтобы просмотреть полезной нагрузки с дополнительными сведениями об этом.</span><span class="sxs-lookup"><span data-stu-id="890e0-137">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="890e0-138">Если вы хотите создать собственную полезной нагрузки, ознакомьтесь с созданием полезной нагрузки [для обучения имитации атак.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="890e0-138">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="890e0-139">Выбор целевой аудитории</span><span class="sxs-lookup"><span data-stu-id="890e0-139">Audience targeting</span></span>

<span data-ttu-id="890e0-140">Теперь пришло время выбрать аудиторию этого моделирования.</span><span class="sxs-lookup"><span data-stu-id="890e0-140">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="890e0-141">Вы можете включить **всех пользователей в организацию** или **включить только определенных пользователей и группы.**</span><span class="sxs-lookup"><span data-stu-id="890e0-141">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="890e0-142">Если вы решите включить **только определенных пользователей и групп,** вы можете либо:</span><span class="sxs-lookup"><span data-stu-id="890e0-142">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="890e0-143">**Добавьте пользователей,** что позволяет использовать поиск для клиента, а также расширенные возможности поиска и фильтрации, например, ориентацию на пользователей, которые не были объектом моделирования в течение последних 3 месяцев.</span><span class="sxs-lookup"><span data-stu-id="890e0-143">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="890e0-144">![Фильтрация пользователей при обучении моделированию атак в центре безопасности Microsoft 365](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="890e0-144">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="890e0-145">**Импорт из CSV** позволяет импортировать заранее заранее заданной набор пользователей для этого моделирования.</span><span class="sxs-lookup"><span data-stu-id="890e0-145">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="890e0-146">Назначение обучения</span><span class="sxs-lookup"><span data-stu-id="890e0-146">Assigning training</span></span>

<span data-ttu-id="890e0-147">Рекомендуется назначать обучение для каждого моделирования, так как сотрудники, которые проходят обучение, менее подвержены подобным атакам.</span><span class="sxs-lookup"><span data-stu-id="890e0-147">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="890e0-148">Вы можете выбрать, чтобы обучение назначено для вас или выбрать учебные курсы и модули самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="890e0-148">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="890e0-149">Выберите дату **подготовки,** чтобы убедиться, что сотрудники своевременно завершат обучение.</span><span class="sxs-lookup"><span data-stu-id="890e0-149">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="890e0-150">Если выбрать курсы и модули самостоятельно, вы все равно сможете увидеть рекомендуемое содержимое, а также все доступные курсы и модули.</span><span class="sxs-lookup"><span data-stu-id="890e0-150">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Добавление рекомендуемой подготовки в центре безопасности Microsoft 365 в рамках подготовки по моделированию атак](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="890e0-152">В следующих действиях необходимо  добавить тренинги, если вы решили выбрать его самостоятельно, и настроить страницу подготовки.</span><span class="sxs-lookup"><span data-stu-id="890e0-152">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="890e0-153">Вы сможете просмотреть страницу подготовки, а также изменить ее заголовка и тело.</span><span class="sxs-lookup"><span data-stu-id="890e0-153">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="890e0-154">Запуск сведений и обзор</span><span class="sxs-lookup"><span data-stu-id="890e0-154">Launch details and review</span></span>

<span data-ttu-id="890e0-155">Теперь, когда все настроено, вы можете запустить это моделирование немедленно или запланировать его на более поздний срок.</span><span class="sxs-lookup"><span data-stu-id="890e0-155">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="890e0-156">Кроме того, необходимо выбрать время окончания этого моделирования.</span><span class="sxs-lookup"><span data-stu-id="890e0-156">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="890e0-157">Мы перестанет захватывать взаимодействие с этим моделированием в течение выбранного времени.</span><span class="sxs-lookup"><span data-stu-id="890e0-157">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="890e0-158">**Включить доставку часовой пояса** в регионах для доставки смоделированных сообщений об атаке сотрудникам в рабочее время в зависимости от региона.</span><span class="sxs-lookup"><span data-stu-id="890e0-158">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="890e0-159">После этого нажмите кнопку **Далее** и просмотрите сведения об имитации.</span><span class="sxs-lookup"><span data-stu-id="890e0-159">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="890e0-160">Нажмите **кнопку Изменить** на любой из частей, чтобы вернуться и изменить все сведения, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="890e0-160">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="890e0-161">После этого щелкните **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="890e0-161">Once done, click **Submit**.</span></span>
