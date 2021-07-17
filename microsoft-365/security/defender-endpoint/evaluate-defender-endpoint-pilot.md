---
title: Опыт Microsoft Defender для конечной точки (MDE) с помощью имитации атак
description: Пилотная Microsoft 365 Defender пробная лаборатория или пилотная среда.
keywords: Microsoft 365 Defender пробной версии попробуйте Microsoft 365 Defender, оцените Microsoft 365 Defender, Microsoft 365 Defender лаборатории оценки, пилот Microsoft 365 Defender, кибербезопасность, расширенные постоянные угрозы, безопасность предприятия, устройства, устройства, удостоверения, пользователей, данные, приложения, инциденты, автоматическое расследование и исправление, продвинутая охота
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 131a048e806976afa3bffbd3f3bce2d61a370225
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458611"
---
# <a name="experience-microsoft-defender-for-endpoint-mde-through-simulated-attacks"></a><span data-ttu-id="acd3a-104">Опыт Microsoft Defender для конечной точки (MDE) с помощью имитации атак</span><span class="sxs-lookup"><span data-stu-id="acd3a-104">Experience Microsoft Defender for Endpoint (MDE) through simulated attacks</span></span>

>[!TIP]
>
>- <span data-ttu-id="acd3a-105">Узнайте о последних улучшениях в Microsoft Defender для конечной точки: что нового в [Defender для конечной точки?.](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="acd3a-105">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="acd3a-106">Defender for Endpoint в недавней оценке MITRE продемонстрировал ведущие в отрасли возможности оптики и обнаружения.</span><span class="sxs-lookup"><span data-stu-id="acd3a-106">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="acd3a-107">Read: Аналитика из оценки [ATT MITRE&на](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)основе CK .</span><span class="sxs-lookup"><span data-stu-id="acd3a-107">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="acd3a-108">Может потребоваться испытать Defender для конечной точки, прежде чем вы на борту более нескольких устройств в службу.</span><span class="sxs-lookup"><span data-stu-id="acd3a-108">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="acd3a-109">Для этого можно выполнить управляемые имитации атак на нескольких тестовых устройствах.</span><span class="sxs-lookup"><span data-stu-id="acd3a-109">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="acd3a-110">После запуска смоделированных атак вы можете просмотреть, как Defender для конечной точки просматривает вредоносную активность и изучите, как она позволяет эффективно отвечать.</span><span class="sxs-lookup"><span data-stu-id="acd3a-110">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="acd3a-111">Подготовка</span><span class="sxs-lookup"><span data-stu-id="acd3a-111">Before you begin</span></span>

<span data-ttu-id="acd3a-112">Для запуска любого из предоставленных симуляций необходимо по крайней мере [одно бортовом устройстве.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="acd3a-112">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span>

<span data-ttu-id="acd3a-113">Ознакомьтесь с документом по погона, который содержит каждый сценарий атаки.</span><span class="sxs-lookup"><span data-stu-id="acd3a-113">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="acd3a-114">Каждый документ содержит требования к ОС и приложениям, а также подробные инструкции, которые относятся к сценарию атаки.</span><span class="sxs-lookup"><span data-stu-id="acd3a-114">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="acd3a-115">Запуск моделирования</span><span class="sxs-lookup"><span data-stu-id="acd3a-115">Run a simulation</span></span>

1. <span data-ttu-id="acd3a-116">В   >  **справке & руководства**, выберите, какой из доступных сценариев атак вы хотите имитировать:</span><span class="sxs-lookup"><span data-stu-id="acd3a-116">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="acd3a-117">**Сценарий 1. Отбрасыватель** документа — имитирует доставку социально разработанного документа-приманки.</span><span class="sxs-lookup"><span data-stu-id="acd3a-117">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="acd3a-118">В документе запускается специально созданный backdoor, который дает злоумышленникам контроль.</span><span class="sxs-lookup"><span data-stu-id="acd3a-118">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="acd3a-119">**Сценарий 2. Сценарий PowerShell** в без файловой атаке — имитирует без файловую атаку, которая опирается на PowerShell, демонстрацию уменьшения поверхности атаки и обнаружение вредоносных действий памяти на устройстве.</span><span class="sxs-lookup"><span data-stu-id="acd3a-119">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>

   - <span data-ttu-id="acd3a-120">**Сценарий 3.** Автоматизированная реакция на инциденты — запускает автоматическое расследование, которое автоматически охотится за артефактами нарушений и устраняет их для масштабирования емкости реагирования на инциденты.</span><span class="sxs-lookup"><span data-stu-id="acd3a-120">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="acd3a-121">Скачайте и прочитайте соответствующий документ по погонам, предоставленный в выбранном сценарии.</span><span class="sxs-lookup"><span data-stu-id="acd3a-121">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="acd3a-122">Скачайте файл моделирования или скопируйте сценарий моделирования, перенавигав для **справки**&  >  **руководства.**</span><span class="sxs-lookup"><span data-stu-id="acd3a-122">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="acd3a-123">Вы можете скачать файл или скрипт на тестовом устройстве, но это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="acd3a-123">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="acd3a-124">Запустите файл или сценарий моделирования на тестовом устройстве, как поручено в документе по поручению.</span><span class="sxs-lookup"><span data-stu-id="acd3a-124">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="acd3a-125">Файлы или сценарии моделирования имитируют действия атаки, но на самом деле являются доброкачественными и не наносят вреда тестовом устройству.</span><span class="sxs-lookup"><span data-stu-id="acd3a-125">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
>

## <a name="alternate-topic-text"></a><span data-ttu-id="acd3a-126">АЛЬТЕРНАТИВНЫЙ ТЕКСТ ТЕМЫ</span><span class="sxs-lookup"><span data-stu-id="acd3a-126">ALTERNATE TOPIC TEXT</span></span>

## <a name="simulate-attack-scenarios"></a><span data-ttu-id="acd3a-127">Имитация сценариев атак</span><span class="sxs-lookup"><span data-stu-id="acd3a-127">Simulate attack scenarios</span></span>

<span data-ttu-id="acd3a-128">Используйте тестовые устройства для запуска собственных имитаций атак, подключившись к ним.</span><span class="sxs-lookup"><span data-stu-id="acd3a-128">Use the test devices to run your own attack simulations by connecting to them.</span></span>

<span data-ttu-id="acd3a-129">Вы можете имитировать сценарии атак с помощью:</span><span class="sxs-lookup"><span data-stu-id="acd3a-129">You can simulate attack scenarios using:</span></span>

- <span data-ttu-id="acd3a-130">Сценарии [атаки "Do It Yourself"](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="acd3a-130">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="acd3a-131">Симуляторы угроз</span><span class="sxs-lookup"><span data-stu-id="acd3a-131">Threat simulators</span></span>

<span data-ttu-id="acd3a-132">Вы также можете использовать [расширенный](advanced-hunting-overview.md) [](threat-analytics.md) поиск для запроса данных и аналитики угроз для просмотра отчетов о возникающих угрозах.</span><span class="sxs-lookup"><span data-stu-id="acd3a-132">You can also use [Advanced hunting](advanced-hunting-overview.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="acd3a-133">Сценарии атак do-it-yourself</span><span class="sxs-lookup"><span data-stu-id="acd3a-133">Do-it-yourself attack scenarios</span></span>

<span data-ttu-id="acd3a-134">Если вы ищете предварительное моделирование, вы можете использовать сценарии атак ["Do It Yourself".](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="acd3a-134">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="acd3a-135">Эти скрипты безопасны, документированы и просты в использовании.</span><span class="sxs-lookup"><span data-stu-id="acd3a-135">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="acd3a-136">Эти сценарии будут отражать возможности Defender для конечных точек и ходить по опыту исследования.</span><span class="sxs-lookup"><span data-stu-id="acd3a-136">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>

>[!NOTE]
><span data-ttu-id="acd3a-137">Подключение к тест-устройствам делается с помощью RDP.</span><span class="sxs-lookup"><span data-stu-id="acd3a-137">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="acd3a-138">Убедитесь, что параметры брандмауэра позволяют подключения RDP.</span><span class="sxs-lookup"><span data-stu-id="acd3a-138">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="acd3a-139">Подключение на устройство и запустите имитацию атаки, выбрав **Подключение**.</span><span class="sxs-lookup"><span data-stu-id="acd3a-139">Connect to your device and run an attack simulation by selecting **Connect**.</span></span>

    ![Изображение кнопки подключения для тестовых устройств](images/test-machine-table.png)

2. <span data-ttu-id="acd3a-141">Сохраните файл RDP и запустите его, выбрав **Подключение**.</span><span class="sxs-lookup"><span data-stu-id="acd3a-141">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![Изображение удаленного подключения к рабочему столу](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="acd3a-143">Если у вас нет копии пароля, сохраненного во время начальной установки, вы можете сбросить пароль, выбрав пароль **Reset** из меню: Изображение пароля ![ сброса.](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="acd3a-143">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span>
    >
    > <span data-ttu-id="acd3a-144">Устройство изменит его состояние на "Выполнение сброса пароля", после чего через несколько минут вам будет представлен новый пароль.</span><span class="sxs-lookup"><span data-stu-id="acd3a-144">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="acd3a-145">Введите пароль, отображаемый во время шага создания устройства.</span><span class="sxs-lookup"><span data-stu-id="acd3a-145">Enter the password that was displayed during the device creation step.</span></span>

   ![Изображение окна для ввода учетных данных](images/enter-password.png)

4. <span data-ttu-id="acd3a-147">Запустите имитацию атак do-it-yourself на устройстве.</span><span class="sxs-lookup"><span data-stu-id="acd3a-147">Run Do-it-yourself attack simulations on the device.</span></span>

### <a name="threat-simulator-scenarios"></a><span data-ttu-id="acd3a-148">Сценарии имитатора угроз</span><span class="sxs-lookup"><span data-stu-id="acd3a-148">Threat simulator scenarios</span></span>

<span data-ttu-id="acd3a-149">Если вы решили установить любой из поддерживаемых имитаторов угроз во время установки лаборатории, вы можете запустить встроенные имитации на устройствах лаборатории оценки.</span><span class="sxs-lookup"><span data-stu-id="acd3a-149">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span>

<span data-ttu-id="acd3a-150">Запуск имитации угроз с использованием сторонних платформ — это хороший способ оценить возможности Microsoft Defender для конечных точек в пределах лабораторной среды.</span><span class="sxs-lookup"><span data-stu-id="acd3a-150">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
>
><span data-ttu-id="acd3a-151">Прежде чем запускать моделирование, убедитесь, что следующие требования будут выполнены:</span><span class="sxs-lookup"><span data-stu-id="acd3a-151">Before you can run simulations, ensure the following requirements are met:</span></span>

>- <span data-ttu-id="acd3a-152">Устройства должны быть добавлены в лабораторию оценки</span><span class="sxs-lookup"><span data-stu-id="acd3a-152">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="acd3a-153">Симуляторы угроз должны быть установлены в лаборатории оценки</span><span class="sxs-lookup"><span data-stu-id="acd3a-153">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="acd3a-154">На портале выберите **Создание моделирования.**</span><span class="sxs-lookup"><span data-stu-id="acd3a-154">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="acd3a-155">Выберите симулятор угрозы.</span><span class="sxs-lookup"><span data-stu-id="acd3a-155">Select a threat simulator.</span></span>

    ![Изображение выбора симулятора угроз](images/select-simulator.png)

3. <span data-ttu-id="acd3a-157">Выберите имитацию или просмотрите галерею моделирования, чтобы просмотреть доступные модели.</span><span class="sxs-lookup"><span data-stu-id="acd3a-157">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span>

    <span data-ttu-id="acd3a-158">Вы можете попасть в галерею моделирования из:</span><span class="sxs-lookup"><span data-stu-id="acd3a-158">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="acd3a-159">Основная панель мониторинга оценки в плитке **обзоров simulations** или</span><span class="sxs-lookup"><span data-stu-id="acd3a-159">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="acd3a-160">Путем навигации из области навигации **Оценка** и учебники Моделирование & учебники, а затем  >  выберите **каталог моделирования**.</span><span class="sxs-lookup"><span data-stu-id="acd3a-160">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="acd3a-161">Выберите устройства, на которых необходимо выполнить моделирование.</span><span class="sxs-lookup"><span data-stu-id="acd3a-161">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="acd3a-162">Выберите **Создание моделирования**.</span><span class="sxs-lookup"><span data-stu-id="acd3a-162">Select **Create simulation**.</span></span>

6. <span data-ttu-id="acd3a-163">Просмотреть ход моделирования, выбрав вкладку **Simulations.** Просмотр состояния моделирования, активных оповещений и других сведений.</span><span class="sxs-lookup"><span data-stu-id="acd3a-163">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span>

    <span data-ttu-id="acd3a-164">![Изображение вкладки моделирования](images/simulations-tab.png)
</span><span class="sxs-lookup"><span data-stu-id="acd3a-164">![Image of simulations tab](images/simulations-tab.png)
</span></span><br>

<span data-ttu-id="acd3a-165">После выполнения имитации мы рекомендуем вам пройти через планку прогресса лаборатории и изучить Microsoft Defender для конечной точки инициировать автоматическое расследование и **исправление.**</span><span class="sxs-lookup"><span data-stu-id="acd3a-165">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="acd3a-166">Ознакомьтесь с доказательствами, собранными и проанализироваными этой функцией.</span><span class="sxs-lookup"><span data-stu-id="acd3a-166">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="acd3a-167">Поиск доказательств атаки с помощью продвинутой охоты с помощью богатого языка запросов и сырой телеметрии и проверить некоторые угрозы во всем мире, задокументированные в аналитике угроз.</span><span class="sxs-lookup"><span data-stu-id="acd3a-167">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>
