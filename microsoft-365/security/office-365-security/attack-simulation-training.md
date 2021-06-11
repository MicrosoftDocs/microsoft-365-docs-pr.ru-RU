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
ms.openlocfilehash: d82e7544e6795e4514cf1949645107c53fc69c61
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878368"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="8728b-103">Имитация фишинговой атаки</span><span class="sxs-lookup"><span data-stu-id="8728b-103">Simulate a phishing attack</span></span>

<span data-ttu-id="8728b-104">**Применяется к** [Microsoft Defender для Office 365 плана 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="8728b-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="8728b-105">Обучение имитации атак в Microsoft Defender для Office 365 позволяет запускать в организации доброкачественные имитации кибератак для проверки политик и методов безопасности, а также обучения сотрудников повышению их осведомленности и снижению их восприимчивости к атакам.</span><span class="sxs-lookup"><span data-stu-id="8728b-105">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="8728b-106">В этой статье вы можете создать смоделированную фишинговую атаку с помощью обучения имитации атак.</span><span class="sxs-lookup"><span data-stu-id="8728b-106">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

<span data-ttu-id="8728b-107">Сведения о подготовке к имитации атаки см. в см. в игре [Get started using Attack simulation training.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="8728b-107">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="8728b-108">Чтобы запустить смоделированную фишинговую атаку, откройте портал Microsoft 365 Defender (), перейдите на обучение моделированию совместной & электронной почты и перейдите на вкладку <https://security.microsoft.com/>  \>  **[Simulations.](https://security.microsoft.com/attacksimulator?viewid=simulations)**</span><span class="sxs-lookup"><span data-stu-id="8728b-108">To launch a simulated phishing attack, open the Microsoft 365 Defender portal (<https://security.microsoft.com/>), go to **Email & collaboration** \> **Attack simulation training**, and switch to the **[Simulations](https://security.microsoft.com/attacksimulator?viewid=simulations)** tab.</span></span>

<span data-ttu-id="8728b-109">В **рамках моделирования** выберите **+ Запустите моделирование.**</span><span class="sxs-lookup"><span data-stu-id="8728b-109">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Запустите кнопку моделирования на портале Microsoft 365 Defender](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="8728b-111">В любой момент при создании моделирования можно сохранить и закрыть, чтобы продолжить настройку моделирования в более позднее время.</span><span class="sxs-lookup"><span data-stu-id="8728b-111">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="8728b-112">Выбор метода социальной инженерии</span><span class="sxs-lookup"><span data-stu-id="8728b-112">Selecting a social engineering technique</span></span>

<span data-ttu-id="8728b-113">Выберите из 4 различных методов, куратором из структуры [ATT MITRE&CK®](https://attack.mitre.org/techniques/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="8728b-113">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="8728b-114">Различные полезной нагрузки доступны для различных методов:</span><span class="sxs-lookup"><span data-stu-id="8728b-114">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="8728b-115">**Сбор учетных** данных пытается собрать учетные данные, относя пользователей к известному выглядящем веб-сайту с входными полями для отправки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="8728b-115">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="8728b-116">**Вложение вредоносных** программ добавляет вредоносное вложение в сообщение.</span><span class="sxs-lookup"><span data-stu-id="8728b-116">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="8728b-117">Когда пользователь открывает вложение, запустится произвольный код, который поможет злоумышленнику скомпрометировать устройство цели.</span><span class="sxs-lookup"><span data-stu-id="8728b-117">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="8728b-118">**Ссылка в приложении** — это тип гибрида сбора учетных данных.</span><span class="sxs-lookup"><span data-stu-id="8728b-118">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="8728b-119">Злоумышленник вставляет URL-адрес в вложение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8728b-119">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="8728b-120">URL-адрес в приложении следует той же методике, что и сбор учетных данных.</span><span class="sxs-lookup"><span data-stu-id="8728b-120">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="8728b-121">**Ссылка на вредоносные** программы будет запускать произвольный код из файла, хранимого в известной службе обмена файлами.</span><span class="sxs-lookup"><span data-stu-id="8728b-121">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="8728b-122">Сообщение, отправленное пользователю, будет содержать ссылку на этот вредоносный файл.</span><span class="sxs-lookup"><span data-stu-id="8728b-122">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="8728b-123">Открытие файла и помощь злоумышленнику в компрометации устройства цели.</span><span class="sxs-lookup"><span data-stu-id="8728b-123">Opening the file and help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="8728b-124">**URL-адрес drive-by** — это место, где вредоносный URL-адрес в сообщении отводит пользователя на знакомый веб-сайт, который бесшумно запускает и/или устанавливает код кода на устройстве пользователя.</span><span class="sxs-lookup"><span data-stu-id="8728b-124">**Drive-by URL** is where the malicious URL in the message takes the user to a familiar-looking website that silently runs and/or installs code code on the user's device.</span></span>

> [!TIP]
> <span data-ttu-id="8728b-125">Нажатие на **сведения Просмотра** в описании каждого метода отображает дополнительные сведения и шаги моделирования для метода.</span><span class="sxs-lookup"><span data-stu-id="8728b-125">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Этапы моделирования сбора учетных данных в рамках обучения моделированию атак на портале Microsoft 365 Defender](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="8728b-127">После выбора метода и нажатия на **кнопку Далее,** дайте вашему моделированию имя и необязательно описание.</span><span class="sxs-lookup"><span data-stu-id="8728b-127">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="8728b-128">Выбор полезной нагрузки</span><span class="sxs-lookup"><span data-stu-id="8728b-128">Selecting a payload</span></span>

<span data-ttu-id="8728b-129">Далее необходимо выбрать полезной нагрузки из уже существующего каталога полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="8728b-129">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="8728b-130">У полезной нагрузки есть несколько точек данных, которые помогут выбрать:</span><span class="sxs-lookup"><span data-stu-id="8728b-130">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="8728b-131">**Ставка мыши** подсчитывает, сколько людей нажали эту полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="8728b-131">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="8728b-132">**Прогнозируемая** скорость компромисса предсказывает процент людей, которые будут скомпрометироваться этой полезной нагрузкой на основе исторических данных для полезной нагрузки в Microsoft Defender для Office 365 клиентов.</span><span class="sxs-lookup"><span data-stu-id="8728b-132">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="8728b-133">**Запущенные имитации** подсчитывают количество раз, когда эта полезной нагрузки использовалась в других имитациях.</span><span class="sxs-lookup"><span data-stu-id="8728b-133">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="8728b-134">**Сложность,** **доступная** с помощью фильтров, рассчитывается на основе количества индикаторов в полезной нагрузке, которая подсказывает, что объекты на нем являются атакой.</span><span class="sxs-lookup"><span data-stu-id="8728b-134">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="8728b-135">Дополнительные показатели приводят к снижению сложности.</span><span class="sxs-lookup"><span data-stu-id="8728b-135">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="8728b-136">**Источник,** доступный через **фильтры,** указывает, была ли полезной нагрузки создана на вашем клиенте или является частью уже существующего каталога полезной нагрузки Майкрософт (глобальный).</span><span class="sxs-lookup"><span data-stu-id="8728b-136">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Выбор полезной нагрузки в рамках обучения моделированию атак на портале Microsoft 365 Defender](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="8728b-138">Выберите полезной нагрузки из списка, чтобы просмотреть полезной нагрузки с дополнительными сведениями об этом.</span><span class="sxs-lookup"><span data-stu-id="8728b-138">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="8728b-139">Если вы хотите создать собственную полезной нагрузки, ознакомьтесь с созданием полезной нагрузки [для обучения имитации атак.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="8728b-139">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="8728b-140">Выбор целевой аудитории</span><span class="sxs-lookup"><span data-stu-id="8728b-140">Audience targeting</span></span>

<span data-ttu-id="8728b-141">Теперь пришло время выбрать аудиторию этого моделирования.</span><span class="sxs-lookup"><span data-stu-id="8728b-141">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="8728b-142">Вы можете включить **всех пользователей в организацию** или **включить только определенных пользователей и группы.**</span><span class="sxs-lookup"><span data-stu-id="8728b-142">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="8728b-143">Если вы решите включить **только определенных пользователей и групп,** вы можете либо:</span><span class="sxs-lookup"><span data-stu-id="8728b-143">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="8728b-144">**Добавьте пользователей,** что позволяет использовать поиск для клиента, а также расширенные возможности поиска и фильтрации, например, ориентацию на пользователей, которые не были объектом моделирования в течение последних 3 месяцев.</span><span class="sxs-lookup"><span data-stu-id="8728b-144">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>

  ![Фильтрация пользователей при обучении моделированию атак на портале Microsoft 365 Defender](../../media/attack-sim-preview-user-targeting.png)

- <span data-ttu-id="8728b-146">**Импорт из CSV** позволяет импортировать заранее заранее заданной набор пользователей для этого моделирования.</span><span class="sxs-lookup"><span data-stu-id="8728b-146">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="8728b-147">Назначение обучения</span><span class="sxs-lookup"><span data-stu-id="8728b-147">Assigning training</span></span>

<span data-ttu-id="8728b-148">Рекомендуется назначать обучение для каждого моделирования, так как сотрудники, которые проходят обучение, менее подвержены подобным атакам.</span><span class="sxs-lookup"><span data-stu-id="8728b-148">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="8728b-149">Вы можете выбрать, чтобы обучение назначено для вас или выбрать учебные курсы и модули самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="8728b-149">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="8728b-150">Выберите дату **подготовки,** чтобы убедиться, что сотрудники своевременно завершат обучение.</span><span class="sxs-lookup"><span data-stu-id="8728b-150">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="8728b-151">Если выбрать курсы и модули самостоятельно, вы все равно сможете увидеть рекомендуемое содержимое, а также все доступные курсы и модули.</span><span class="sxs-lookup"><span data-stu-id="8728b-151">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Добавление рекомендуемой подготовки в рамках обучения моделированию атак на портале Microsoft 365 Defender](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="8728b-153">В следующих действиях необходимо  добавить тренинги, если вы решили выбрать его самостоятельно, и настроить страницу подготовки.</span><span class="sxs-lookup"><span data-stu-id="8728b-153">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="8728b-154">Вы сможете просмотреть страницу подготовки, а также изменить ее заголовка и тело.</span><span class="sxs-lookup"><span data-stu-id="8728b-154">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="8728b-155">Запуск сведений и обзор</span><span class="sxs-lookup"><span data-stu-id="8728b-155">Launch details and review</span></span>

<span data-ttu-id="8728b-156">Теперь, когда все настроено, вы можете запустить это моделирование немедленно или запланировать его на более поздний срок.</span><span class="sxs-lookup"><span data-stu-id="8728b-156">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="8728b-157">Кроме того, необходимо выбрать время окончания этого моделирования.</span><span class="sxs-lookup"><span data-stu-id="8728b-157">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="8728b-158">Мы перестанет захватывать взаимодействие с этим моделированием в течение выбранного времени.</span><span class="sxs-lookup"><span data-stu-id="8728b-158">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="8728b-159">**Включить доставку часовой пояса** в регионах для доставки смоделированных сообщений об атаке сотрудникам в рабочее время в зависимости от региона.</span><span class="sxs-lookup"><span data-stu-id="8728b-159">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="8728b-160">После этого нажмите кнопку **Далее** и просмотрите сведения об имитации.</span><span class="sxs-lookup"><span data-stu-id="8728b-160">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="8728b-161">Нажмите **кнопку Изменить** на любой из частей, чтобы вернуться и изменить все сведения, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="8728b-161">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="8728b-162">После этого щелкните **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="8728b-162">Once done, click **Submit**.</span></span>
