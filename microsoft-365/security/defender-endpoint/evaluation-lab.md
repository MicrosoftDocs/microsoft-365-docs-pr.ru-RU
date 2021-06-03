---
title: Лаборатория оценки Microsoft Defender для конечной точки
description: Узнайте о возможностях Microsoft Defender для конечных точек, запустите имитацию атак и узнайте, как он предотвращает, обнаруживает и устраняет угрозы.
keywords: оценка Microsoft Defender для конечной точки, оценка, лаборатория, моделирование, Windows 10, windows server 2019, лаборатория оценки
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f6ef1d3dbc111e5d10bf4d3c42dfd08e5e9d63e3
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730629"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a><span data-ttu-id="7ce07-104">Лаборатория оценки Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7ce07-104">Microsoft Defender for Endpoint evaluation lab</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7ce07-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7ce07-105">**Applies to:**</span></span>
- [<span data-ttu-id="7ce07-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7ce07-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7ce07-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ce07-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="7ce07-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="7ce07-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7ce07-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="7ce07-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="7ce07-110">Проведение комплексной оценки продукта безопасности может быть сложным процессом, требующим громоздких условий и конфигурации устройств, прежде чем может быть фактически сделано комплексное моделирование атаки.</span><span class="sxs-lookup"><span data-stu-id="7ce07-110">Conducting a comprehensive security product evaluation can be a complex process requiring cumbersome environment and device configuration before an end-to-end attack simulation can actually be done.</span></span> <span data-ttu-id="7ce07-111">Сложность заключается в отслеживании того, где во время оценки отражаются действия моделирования, оповещения и результаты.</span><span class="sxs-lookup"><span data-stu-id="7ce07-111">Adding to the complexity is the challenge of tracking where the simulation activities, alerts, and results are reflected during the evaluation.</span></span>

<span data-ttu-id="7ce07-112">Лаборатория оценки Microsoft Defender для конечной точки предназначена для устранения сложностей конфигурации устройства и среды, чтобы вы могли сосредоточиться на оценке возможностей платформы, запуске имитаций и обнаружении функций предотвращения, обнаружения и восстановления в действии.</span><span class="sxs-lookup"><span data-stu-id="7ce07-112">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can  focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

<span data-ttu-id="7ce07-113">С помощью упрощенной системы можно сосредоточиться на выполнении собственных тестовых сценариев и заранее сделанных имитаций, чтобы узнать, как работает Defender для endpoint.</span><span class="sxs-lookup"><span data-stu-id="7ce07-113">With the simplified set-up experience, you can focus on running your own test scenarios and the pre-made simulations to see how Defender for Endpoint performs.</span></span> 

<span data-ttu-id="7ce07-114">У вас будет полный доступ к мощным возможностям платформы, таким как автоматизированные расследования, расширенные поиски и аналитика угроз, что позволит протестировать комплексный стек защиты, который предлагает Defender для Endpoint.</span><span class="sxs-lookup"><span data-stu-id="7ce07-114">You'll have full access to the powerful capabilities of the platform such as automated investigations, advanced hunting, and threat analytics, allowing you to test the comprehensive protection stack that Defender for Endpoint offers.</span></span> 

<span data-ttu-id="7ce07-115">Можно добавить Windows 10 или Windows Server 2019, которые предварительно настроены для установки последних версий ОС и нужных компонентов безопасности, а также Office стандарта 2019 г.</span><span class="sxs-lookup"><span data-stu-id="7ce07-115">You can add Windows 10 or Windows Server 2019 devices that come pre-configured to have the latest OS versions and the right security components in place as well as Office 2019 Standard installed.</span></span>

<span data-ttu-id="7ce07-116">Вы также можете установить симуляторы угроз.</span><span class="sxs-lookup"><span data-stu-id="7ce07-116">You can also install threat simulators.</span></span> <span data-ttu-id="7ce07-117">Defender for Endpoint имеет партнерские отношения с ведущими отраслевыми платформами моделирования угроз, чтобы помочь вам проверить возможности Defender для конечной точки, не покидая портал.</span><span class="sxs-lookup"><span data-stu-id="7ce07-117">Defender for Endpoint has partnered with industry leading threat simulation platforms to help you test out the Defender for Endpoint capabilities without having to leave the portal.</span></span>

 <span data-ttu-id="7ce07-118">Установите предпочтительный симулятор, запустите сценарии в лаборатории оценки и сразу же посмотрите, как выполняется платформа — все удобно доступно без дополнительных затрат для вас.</span><span class="sxs-lookup"><span data-stu-id="7ce07-118">Install your preferred simulator, run scenarios within the evaluation lab, and instantly see how the platform performs - all conveniently available at no extra cost to you.</span></span> <span data-ttu-id="7ce07-119">Вы также будете иметь удобный доступ к широкому спектру имитаций, к которым можно получить доступ и запустить из каталога моделирования.</span><span class="sxs-lookup"><span data-stu-id="7ce07-119">You'll also have convenient access to wide array of simulations which you can access and run from the simulations catalog.</span></span>
    

## <a name="before-you-begin"></a><span data-ttu-id="7ce07-120">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="7ce07-120">Before you begin</span></span>
<span data-ttu-id="7ce07-121">Чтобы получить доступ к [](minimum-requirements.md#licensing-requirements) лаборатории оценки, необходимо выполнить требования лицензирования или получить пробный доступ к Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="7ce07-121">You'll need to fulfill the [licensing requirements](minimum-requirements.md#licensing-requirements) or have trial access to Microsoft Defender for Endpoint to access the evaluation lab.</span></span>

<span data-ttu-id="7ce07-122">Необходимо иметь разрешения на управление **настройками** безопасности, чтобы:</span><span class="sxs-lookup"><span data-stu-id="7ce07-122">You must have **Manage security settings** permissions to:</span></span>
- <span data-ttu-id="7ce07-123">Создание лаборатории</span><span class="sxs-lookup"><span data-stu-id="7ce07-123">Create the lab</span></span>
- <span data-ttu-id="7ce07-124">Создание устройств</span><span class="sxs-lookup"><span data-stu-id="7ce07-124">Create devices</span></span>
- <span data-ttu-id="7ce07-125">Сброс пароля</span><span class="sxs-lookup"><span data-stu-id="7ce07-125">Reset password</span></span>
- <span data-ttu-id="7ce07-126">Создание имитаций</span><span class="sxs-lookup"><span data-stu-id="7ce07-126">Create simulations</span></span> 
 
<span data-ttu-id="7ce07-127">Если вы включили управление доступом на основе ролей (RBAC) и создали по крайней мере одну группу машин, пользователи должны иметь доступ ко всем группам машин.</span><span class="sxs-lookup"><span data-stu-id="7ce07-127">If you enabled role-based access control (RBAC) and created at least a one machine group, users must have access to All machine groups.</span></span>

<span data-ttu-id="7ce07-128">Дополнительные сведения см. в [дополнительных сведениях о создании и управлении ролями.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="7ce07-128">For more information, see [Create and manage roles](user-roles.md).</span></span>

<span data-ttu-id="7ce07-129">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="7ce07-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7ce07-130">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="7ce07-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a><span data-ttu-id="7ce07-131">Начало работы с лабораторией</span><span class="sxs-lookup"><span data-stu-id="7ce07-131">Get started with the lab</span></span>
<span data-ttu-id="7ce07-132">Вы можете получить доступ к лаборатории из меню.</span><span class="sxs-lookup"><span data-stu-id="7ce07-132">You can access the lab from the menu.</span></span> <span data-ttu-id="7ce07-133">В меню навигации выберите оценку и **учебники > оценки.**</span><span class="sxs-lookup"><span data-stu-id="7ce07-133">In the navigation menu, select **Evaluation and tutorials > Evaluation lab**.</span></span>

![Изображение лаборатории оценки в меню](images/evaluation-lab-menu.png)

>[!NOTE]
>- <span data-ttu-id="7ce07-135">В зависимости от выбранной структуры среды устройства будут доступны в течение указанного количества часов со дня активации.</span><span class="sxs-lookup"><span data-stu-id="7ce07-135">Depending the type of environment structure you select, devices will be available for the specified number of hours from the day of activation.</span></span>
>- <span data-ttu-id="7ce07-136">Каждая среда содержит ограниченный набор тестовых устройств.</span><span class="sxs-lookup"><span data-stu-id="7ce07-136">Each environment is provisioned with a limited set of test devices.</span></span> <span data-ttu-id="7ce07-137">Если вы использовали устройства с предварительной провизией и удалили их, можно запросить дополнительные устройства.</span><span class="sxs-lookup"><span data-stu-id="7ce07-137">When you've used up the provisioned devices and have deleted them, you can request for more devices.</span></span> 
>- <span data-ttu-id="7ce07-138">Вы можете запрашивать ресурсы лаборатории раз в месяц.</span><span class="sxs-lookup"><span data-stu-id="7ce07-138">You can request for lab resources once a month.</span></span> 

<span data-ttu-id="7ce07-139">Уже есть лаборатория?</span><span class="sxs-lookup"><span data-stu-id="7ce07-139">Already have a lab?</span></span> <span data-ttu-id="7ce07-140">Убедитесь в том, чтобы включить новые симуляторы угроз и иметь активные устройства.</span><span class="sxs-lookup"><span data-stu-id="7ce07-140">Make sure to enable the new threat simulators and have active devices.</span></span>

## <a name="setup-the-evaluation-lab"></a><span data-ttu-id="7ce07-141">Настройка лаборатории оценки</span><span class="sxs-lookup"><span data-stu-id="7ce07-141">Setup the evaluation lab</span></span>

1. <span data-ttu-id="7ce07-142">В области навигации выберите **лабораторию оценки** и оценки учебных пособий,  >  а затем выберите **лабораторию установки.**</span><span class="sxs-lookup"><span data-stu-id="7ce07-142">In the navigation pane, select **Evaluation and tutorials** > **Evaluation lab**, then select **Setup lab**.</span></span>

    ![Изображение страницы приветствия лаборатории оценки](images/evaluation-lab-setup.png)

2. <span data-ttu-id="7ce07-144">В зависимости от потребностей в оценке можно настроить среду с большим или большим количеством устройств на более короткий период.</span><span class="sxs-lookup"><span data-stu-id="7ce07-144">Depending on your evaluation needs, you can choose to setup an environment with fewer devices for a longer period or more devices for a shorter period.</span></span> <span data-ttu-id="7ce07-145">Выберите предпочитаемую конфигурацию лаборатории, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7ce07-145">Select your preferred lab configuration then select **Next**.</span></span>

    ![Изображение параметров конфигурации лаборатории](images/lab-creation-page.png) 


3. <span data-ttu-id="7ce07-147">(Необязательный) Вы можете установить симуляторы угроз в лаборатории.</span><span class="sxs-lookup"><span data-stu-id="7ce07-147">(Optional) You can choose to install threat simulators in the lab.</span></span> 

    ![Изображение агента симуляторов установки](images/install-agent.png)

    >[!IMPORTANT]
    ><span data-ttu-id="7ce07-149">Сначала необходимо принять и предоставить согласие на условия и заявления о совместном использовании информации.</span><span class="sxs-lookup"><span data-stu-id="7ce07-149">You'll first need to accept and provide consent to the terms and information sharing statements.</span></span> 

4. <span data-ttu-id="7ce07-150">Выберите агент моделирования угроз, который вы хотите использовать, и введите сведения.</span><span class="sxs-lookup"><span data-stu-id="7ce07-150">Select the threat simulation agent you'd like to use and enter your details.</span></span> <span data-ttu-id="7ce07-151">Вы также можете выбрать установку симуляторов угроз в более позднее время.</span><span class="sxs-lookup"><span data-stu-id="7ce07-151">You can also choose to install threat simulators at a later time.</span></span> <span data-ttu-id="7ce07-152">Если вы решите установить агенты моделирования угроз во время установки лаборатории, вы сможете удобно установить их на добавленных устройствах.</span><span class="sxs-lookup"><span data-stu-id="7ce07-152">If you choose to install threat simulation agents during the lab setup, you'll enjoy the benefit of having them conveniently installed on the devices you add.</span></span>  
    
    ![Изображение страницы сводки](images/lab-setup-summary.png)

5.  <span data-ttu-id="7ce07-154">Просмотрите сводку и выберите **лабораторию установки.**</span><span class="sxs-lookup"><span data-stu-id="7ce07-154">Review the summary and select **Setup lab**.</span></span>  

<span data-ttu-id="7ce07-155">После завершения процесса установки лаборатории можно добавить устройства и запустить моделирование.</span><span class="sxs-lookup"><span data-stu-id="7ce07-155">After the lab setup process is complete, you can add devices and run simulations.</span></span> 


## <a name="add-devices"></a><span data-ttu-id="7ce07-156">Добавление устройств</span><span class="sxs-lookup"><span data-stu-id="7ce07-156">Add devices</span></span>
<span data-ttu-id="7ce07-157">При добавлении устройства в среду Defender for Endpoint настраивает хорошо настроенное устройство с сведениями о подключении.</span><span class="sxs-lookup"><span data-stu-id="7ce07-157">When you add a device to your environment, Defender for Endpoint sets up a well-configured device with connection details.</span></span> <span data-ttu-id="7ce07-158">Можно добавить устройства Windows 10 или Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7ce07-158">You can add Windows 10 or Windows Server 2019 devices.</span></span>

<span data-ttu-id="7ce07-159">Устройство будет настроено с самой новой версией оси и стандарта Office 2019 г., а также с другими приложениями, такими как Java, Python и SysIntenals.</span><span class="sxs-lookup"><span data-stu-id="7ce07-159">The device will be configured with the most up-to-date version of the OS and Office 2019 Standard as well as other apps such as Java, Python, and SysIntenals.</span></span> 

<span data-ttu-id="7ce07-160">Если вы решили добавить симулятор угроз во время установки лаборатории, на всех устройствах будет установлен агент симулятора угроз, установленный на добавленных устройствах.</span><span class="sxs-lookup"><span data-stu-id="7ce07-160">If you chose to add a threat simulator during the lab setup, all devices will have the threat simulator agent installed in the devices that you add.</span></span>

<span data-ttu-id="7ce07-161">Устройство автоматически будет включено для клиента с рекомендуемой Windows включена и в режиме аудита без каких-либо усилий на вашей стороне.</span><span class="sxs-lookup"><span data-stu-id="7ce07-161">The device will automatically be onboarded to your tenant with the recommended Windows security components turned on and in audit mode - with no effort on your side.</span></span> 

<span data-ttu-id="7ce07-162">На тестовых устройствах предварительно настроены следующие компоненты безопасности:</span><span class="sxs-lookup"><span data-stu-id="7ce07-162">The following security components are pre-configured in the test devices:</span></span>

- [<span data-ttu-id="7ce07-163">Сокращение направлений атак</span><span class="sxs-lookup"><span data-stu-id="7ce07-163">Attack surface reduction</span></span>](attack-surface-reduction.md)
- [<span data-ttu-id="7ce07-164">Блок с первого взгляда</span><span class="sxs-lookup"><span data-stu-id="7ce07-164">Block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7ce07-165">Контролируемый доступ к папкам</span><span class="sxs-lookup"><span data-stu-id="7ce07-165">Controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="7ce07-166">Защита от эксплойтов</span><span class="sxs-lookup"><span data-stu-id="7ce07-166">Exploit protection</span></span>](enable-exploit-protection.md)
- [<span data-ttu-id="7ce07-167">Защита сети</span><span class="sxs-lookup"><span data-stu-id="7ce07-167">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="7ce07-168">Обнаружение потенциально нежелательных приложений</span><span class="sxs-lookup"><span data-stu-id="7ce07-168">Potentially unwanted application detection</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7ce07-169">Защита с облачным доставкой</span><span class="sxs-lookup"><span data-stu-id="7ce07-169">Cloud-delivered protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7ce07-170">фильтр SmartScreen в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7ce07-170">Microsoft Defender SmartScreen</span></span>](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

>[!NOTE]
> <span data-ttu-id="7ce07-171">антивирусная программа в Microsoft Defender будет (не в режиме аудита).</span><span class="sxs-lookup"><span data-stu-id="7ce07-171">Microsoft Defender Antivirus will be on (not in audit mode).</span></span> <span data-ttu-id="7ce07-172">Если антивирусная программа в Microsoft Defender не позволяет запускать моделирование, вы можете отключить защиту в режиме реального времени на устройстве Безопасность Windows.</span><span class="sxs-lookup"><span data-stu-id="7ce07-172">If Microsoft Defender Antivirus blocks you from running your simulation, you can turn off real-time protection on the device through Windows Security.</span></span> <span data-ttu-id="7ce07-173">Дополнительные сведения см. [в перенастройке всегда на защиту.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="7ce07-173">For more information, see [Configure always-on protection](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="7ce07-174">Параметры автоматического расследования будут зависеть от параметров клиента.</span><span class="sxs-lookup"><span data-stu-id="7ce07-174">Automated investigation settings will be dependent on tenant settings.</span></span> <span data-ttu-id="7ce07-175">Он будет настроен на полуавтоматизированный по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7ce07-175">It will be configured to be semi-automated by default.</span></span> <span data-ttu-id="7ce07-176">Дополнительные сведения см. [в обзоре автоматизированных расследований.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="7ce07-176">For more information, see [Overview of Automated investigations](automated-investigations.md).</span></span>

>[!NOTE]
><span data-ttu-id="7ce07-177">Подключение к тест-устройствам делается с помощью RDP.</span><span class="sxs-lookup"><span data-stu-id="7ce07-177">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="7ce07-178">Убедитесь, что параметры брандмауэра позволяют подключения RDP.</span><span class="sxs-lookup"><span data-stu-id="7ce07-178">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="7ce07-179">На панели мониторинга выберите **устройство Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7ce07-179">From the dashboard, select **Add device**.</span></span> 

2. <span data-ttu-id="7ce07-180">Выберите тип устройства для добавления.</span><span class="sxs-lookup"><span data-stu-id="7ce07-180">Choose the type of device to add.</span></span> <span data-ttu-id="7ce07-181">Вы можете добавить Windows 10 или Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7ce07-181">You can choose to add Windows 10 or Windows Server 2019.</span></span>

    ![Изображение лабораторной установки с вариантами устройств](images/add-machine-options.png)


    >[!NOTE]
    ><span data-ttu-id="7ce07-183">Если что-то не справится с процессом создания устройства, вы будете уведомлены и вам потребуется отправить новый запрос.</span><span class="sxs-lookup"><span data-stu-id="7ce07-183">If something goes wrong with the device creation process, you'll be notified and you'll need to submit a new request.</span></span> <span data-ttu-id="7ce07-184">Если создание устройства не удается, он не будет засчитываться по общей разрешенной квоте.</span><span class="sxs-lookup"><span data-stu-id="7ce07-184">If the device creation fails, it will not be counted against the overall allowed quota.</span></span> 

3. <span data-ttu-id="7ce07-185">Отображаются сведения о подключении.</span><span class="sxs-lookup"><span data-stu-id="7ce07-185">The connection details are displayed.</span></span> <span data-ttu-id="7ce07-186">Выберите **Копию,** чтобы сохранить пароль для устройства.</span><span class="sxs-lookup"><span data-stu-id="7ce07-186">Select **Copy** to save the password for the device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="7ce07-187">Пароль отображается только один раз.</span><span class="sxs-lookup"><span data-stu-id="7ce07-187">The password is only displayed once.</span></span> <span data-ttu-id="7ce07-188">Обязательно сохраните его для более позднего использования.</span><span class="sxs-lookup"><span data-stu-id="7ce07-188">Be sure to save it for later use.</span></span>

    ![Изображение устройства, добавленного с сведениями о подключении](images/add-machine-eval-lab.png)

4. <span data-ttu-id="7ce07-190">Начинается настройка устройства.</span><span class="sxs-lookup"><span data-stu-id="7ce07-190">Device set up begins.</span></span> <span data-ttu-id="7ce07-191">Это может занять около 30 минут.</span><span class="sxs-lookup"><span data-stu-id="7ce07-191">This can take up to approximately 30 minutes.</span></span> 

5. <span data-ttu-id="7ce07-192">Узнайте о состоянии тестовых устройств, уровнях риска и экспозиции, а также о состоянии установок симулятора, выбрав вкладку **Devices.**</span><span class="sxs-lookup"><span data-stu-id="7ce07-192">See the status of test devices, the risk and exposure levels, and the status of simulator installations by selecting the **Devices** tab.</span></span> 

    ![Изображение вкладки устройств](images/machines-tab.png)
    

    > [!TIP]
    > <span data-ttu-id="7ce07-194">В **столбце Состояние Симулятор** можно нависать над значком информации, чтобы узнать состояние установки агента.</span><span class="sxs-lookup"><span data-stu-id="7ce07-194">In the **Simulator status** column, you can hover over the information icon to know the installation status of an agent.</span></span>

## <a name="request-for-more-devices"></a><span data-ttu-id="7ce07-195">Запрос на дополнительные устройства</span><span class="sxs-lookup"><span data-stu-id="7ce07-195">Request for more devices</span></span>
<span data-ttu-id="7ce07-196">Если все существующие устройства используются и удаляются, можно запросить дополнительные устройства.</span><span class="sxs-lookup"><span data-stu-id="7ce07-196">When all existing devices are used and deleted, you can request for more devices.</span></span> <span data-ttu-id="7ce07-197">Вы можете запрашивать ресурсы лаборатории раз в месяц.</span><span class="sxs-lookup"><span data-stu-id="7ce07-197">You can request for lab resources once a month.</span></span> 


1. <span data-ttu-id="7ce07-198">На панели мониторинга лаборатории оценки выберите **Запрос для дополнительных устройств.**</span><span class="sxs-lookup"><span data-stu-id="7ce07-198">From the evaluation lab dashboard, select **Request for more devices**.</span></span>

   ![Изображение запроса для большего количество устройств](images/request-more-devices.png)

2. <span data-ttu-id="7ce07-200">Выберите конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="7ce07-200">Choose your configuration.</span></span> 
3. <span data-ttu-id="7ce07-201">Отправка запроса.</span><span class="sxs-lookup"><span data-stu-id="7ce07-201">Submit the request.</span></span> 

<span data-ttu-id="7ce07-202">После успешного отправки запроса вы увидите зеленый баннер подтверждения и дату последней отправки.</span><span class="sxs-lookup"><span data-stu-id="7ce07-202">When the request is submitted successfully you'll see a green confirmation banner and the date of the last submission.</span></span>
 
<span data-ttu-id="7ce07-203">Состояние запроса можно найти на вкладке **Действия** пользователя, которая будет утверждена в течение нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="7ce07-203">You can find the status of your request in the **User Actions** tab, which will be approved in a matter of hours.</span></span>

<span data-ttu-id="7ce07-204">После утверждения запрашиваемые устройства будут добавлены в вашу лабораторию, и вы сможете создавать больше устройств.</span><span class="sxs-lookup"><span data-stu-id="7ce07-204">When approved, the requested devices will be added to your lab set up and you’ll be able to create more devices.</span></span> 


> [!TIP]
> <span data-ttu-id="7ce07-205">Чтобы получить больше из лаборатории, не забудьте проверить нашу библиотеку моделирования.</span><span class="sxs-lookup"><span data-stu-id="7ce07-205">To get more out of your lab, don’t forget to check out our simulations library.</span></span>

## <a name="simulate-attack-scenarios"></a><span data-ttu-id="7ce07-206">Имитация сценариев атак</span><span class="sxs-lookup"><span data-stu-id="7ce07-206">Simulate attack scenarios</span></span>
<span data-ttu-id="7ce07-207">Используйте тестовые устройства для запуска собственных имитаций атак, подключившись к ним.</span><span class="sxs-lookup"><span data-stu-id="7ce07-207">Use the test devices to run your own attack simulations by connecting to them.</span></span> 

<span data-ttu-id="7ce07-208">Вы можете имитировать сценарии атак с помощью:</span><span class="sxs-lookup"><span data-stu-id="7ce07-208">You can simulate attack scenarios using:</span></span>
- <span data-ttu-id="7ce07-209">Сценарии [атаки "Do It Yourself"](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="7ce07-209">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="7ce07-210">Симуляторы угроз</span><span class="sxs-lookup"><span data-stu-id="7ce07-210">Threat simulators</span></span>

<span data-ttu-id="7ce07-211">Вы также можете использовать [расширенный](advanced-hunting-overview.md) [](threat-analytics.md) поиск для запроса данных и аналитики угроз для просмотра отчетов о возникающих угрозах.</span><span class="sxs-lookup"><span data-stu-id="7ce07-211">You can also use [Advanced hunting](advanced-hunting-overview.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="7ce07-212">Сценарии атак do-it-yourself</span><span class="sxs-lookup"><span data-stu-id="7ce07-212">Do-it-yourself attack scenarios</span></span>
<span data-ttu-id="7ce07-213">Если вы ищете предварительное моделирование, вы можете использовать сценарии атак ["Do It Yourself".](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="7ce07-213">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="7ce07-214">Эти скрипты безопасны, документированы и просты в использовании.</span><span class="sxs-lookup"><span data-stu-id="7ce07-214">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="7ce07-215">Эти сценарии будут отражать возможности Defender для конечных точек и ходить по опыту исследования.</span><span class="sxs-lookup"><span data-stu-id="7ce07-215">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>


>[!NOTE]
><span data-ttu-id="7ce07-216">Подключение к тест-устройствам делается с помощью RDP.</span><span class="sxs-lookup"><span data-stu-id="7ce07-216">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="7ce07-217">Убедитесь, что параметры брандмауэра позволяют подключения RDP.</span><span class="sxs-lookup"><span data-stu-id="7ce07-217">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="7ce07-218">Подключение на устройство и запустите имитацию атаки, выбрав **Подключение**.</span><span class="sxs-lookup"><span data-stu-id="7ce07-218">Connect to your device and run an attack simulation by selecting **Connect**.</span></span> 

    ![Изображение кнопки подключения для тестовых устройств](images/test-machine-table.png)

2. <span data-ttu-id="7ce07-220">Сохраните файл RDP и запустите его, выбрав **Подключение**.</span><span class="sxs-lookup"><span data-stu-id="7ce07-220">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![Изображение удаленного подключения к рабочему столу](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="7ce07-222">Если у вас нет копии пароля, сохраненного во время начальной установки, вы можете сбросить пароль, выбрав пароль **Reset** из меню: Изображение пароля ![ сброса.](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="7ce07-222">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span><br>
    > <span data-ttu-id="7ce07-223">Устройство изменит его состояние на "Выполнение сброса пароля", после чего через несколько минут вам будет представлен новый пароль.</span><span class="sxs-lookup"><span data-stu-id="7ce07-223">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="7ce07-224">Введите пароль, отображаемый во время шага создания устройства.</span><span class="sxs-lookup"><span data-stu-id="7ce07-224">Enter the password that was displayed during the device creation step.</span></span> 

   ![Изображение окна для ввода учетных данных](images/enter-password.png)

4. <span data-ttu-id="7ce07-226">Запустите имитацию атак do-it-yourself на устройстве.</span><span class="sxs-lookup"><span data-stu-id="7ce07-226">Run Do-it-yourself attack simulations on the device.</span></span> 


### <a name="threat-simulator-scenarios"></a><span data-ttu-id="7ce07-227">Сценарии симулятора угроз</span><span class="sxs-lookup"><span data-stu-id="7ce07-227">Threat simulator scenarios</span></span>
<span data-ttu-id="7ce07-228">Если вы решили установить любой из поддерживаемых имитаторов угроз во время установки лаборатории, вы можете запустить встроенные имитации на устройствах лаборатории оценки.</span><span class="sxs-lookup"><span data-stu-id="7ce07-228">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span> 


<span data-ttu-id="7ce07-229">Запуск имитации угроз с использованием сторонних платформ — это хороший способ оценить возможности Microsoft Defender для конечных точек в пределах лабораторной среды.</span><span class="sxs-lookup"><span data-stu-id="7ce07-229">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
><span data-ttu-id="7ce07-230">Прежде чем запускать моделирование, убедитесь, что следующие требования будут выполнены:</span><span class="sxs-lookup"><span data-stu-id="7ce07-230">Before you can run simulations, ensure the following requirements are met:</span></span>
>- <span data-ttu-id="7ce07-231">Устройства должны быть добавлены в лабораторию оценки</span><span class="sxs-lookup"><span data-stu-id="7ce07-231">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="7ce07-232">Симуляторы угроз должны быть установлены в лаборатории оценки</span><span class="sxs-lookup"><span data-stu-id="7ce07-232">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="7ce07-233">На портале выберите **Создание моделирования.**</span><span class="sxs-lookup"><span data-stu-id="7ce07-233">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="7ce07-234">Выберите симулятор угрозы.</span><span class="sxs-lookup"><span data-stu-id="7ce07-234">Select a threat simulator.</span></span>

    ![Изображение выбора симулятора угроз](images/select-simulator.png)

3. <span data-ttu-id="7ce07-236">Выберите имитацию или просмотрите галерею моделирования, чтобы просмотреть доступные модели.</span><span class="sxs-lookup"><span data-stu-id="7ce07-236">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span> 

    <span data-ttu-id="7ce07-237">Вы можете попасть в галерею моделирования из:</span><span class="sxs-lookup"><span data-stu-id="7ce07-237">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="7ce07-238">Основная панель мониторинга оценки в плитке **обзоров simulations** или</span><span class="sxs-lookup"><span data-stu-id="7ce07-238">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="7ce07-239">Путем навигации из области навигации **Оценка** и учебники Моделирование & учебники, а затем  >  выберите **каталог моделирования**.</span><span class="sxs-lookup"><span data-stu-id="7ce07-239">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="7ce07-240">Выберите устройства, на которых необходимо выполнить моделирование.</span><span class="sxs-lookup"><span data-stu-id="7ce07-240">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="7ce07-241">Выберите **Создание моделирования**.</span><span class="sxs-lookup"><span data-stu-id="7ce07-241">Select **Create simulation**.</span></span>

6. <span data-ttu-id="7ce07-242">Просмотреть ход моделирования, выбрав вкладку **Simulations.** Просмотр состояния моделирования, активных оповещений и других сведений.</span><span class="sxs-lookup"><span data-stu-id="7ce07-242">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span> 

    ![Изображение вкладки моделирования](images/simulations-tab.png)
    
<span data-ttu-id="7ce07-244">После выполнения имитации мы рекомендуем вам пройти через планку прогресса лаборатории и изучить Microsoft Defender для конечной точки инициировать автоматическое расследование и **исправление.**</span><span class="sxs-lookup"><span data-stu-id="7ce07-244">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="7ce07-245">Ознакомьтесь с доказательствами, собранными и проанализироваными этой функцией.</span><span class="sxs-lookup"><span data-stu-id="7ce07-245">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="7ce07-246">Поиск доказательств атаки с помощью продвинутой охоты с помощью богатого языка запросов и сырой телеметрии и проверить некоторые угрозы во всем мире, задокументированные в аналитике угроз.</span><span class="sxs-lookup"><span data-stu-id="7ce07-246">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>


## <a name="simulation-gallery"></a><span data-ttu-id="7ce07-247">Галерея моделирования</span><span class="sxs-lookup"><span data-stu-id="7ce07-247">Simulation gallery</span></span>
<span data-ttu-id="7ce07-248">Microsoft Defender для конечной точки имеет партнерские отношения с различными платформами моделирования угроз, чтобы предоставить вам удобный доступ для проверки возможностей платформы прямо из портала.</span><span class="sxs-lookup"><span data-stu-id="7ce07-248">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span> 

<span data-ttu-id="7ce07-249">Просмотр всех доступных имитаций, переехав в каталог **моделирования** и учебных пособий из  >   меню.</span><span class="sxs-lookup"><span data-stu-id="7ce07-249">View all the available simulations by going to  **Simulations and tutorials** > **Simulations catalog**  from the menu.</span></span> 

<span data-ttu-id="7ce07-250">В каталоге перечислены поддерживаемые сторонние агенты моделирования угроз, а в каталоге перечислены определенные типы имитаций, а также подробные описания.</span><span class="sxs-lookup"><span data-stu-id="7ce07-250">A list of supported third-party threat simulation agents are listed, and specific types of simulations along with detailed descriptions are provided on the catalog.</span></span> 

<span data-ttu-id="7ce07-251">Вы можете удобно выполнить любое доступное моделирование прямо из каталога.</span><span class="sxs-lookup"><span data-stu-id="7ce07-251">You can conveniently run any available simulation right from the catalog.</span></span>  


![Изображение каталога моделирования](images/simulations-catalog.png)

<span data-ttu-id="7ce07-253">Каждое моделирование поставляется с подробным описанием сценария атаки и ссылками, такими как методы атаки MITRE, используемые и примеры расширенных запросов охоты, которые вы запустите.</span><span class="sxs-lookup"><span data-stu-id="7ce07-253">Each simulation comes with an in-depth description of the attack scenario and references such as the MITRE attack techniques used and sample Advanced hunting queries you run.</span></span>

<span data-ttu-id="7ce07-254">**Примеры:** 
 ![ Изображение деталей описания моделирования1](images/simulation-details-aiq.png)</span><span class="sxs-lookup"><span data-stu-id="7ce07-254">**Examples:**
![Image of simulation description details1](images/simulation-details-aiq.png)</span></span>


![Изображение сведений о описании моделирования2](images/simulation-details-sb.png)


## <a name="evaluation-report"></a><span data-ttu-id="7ce07-256">Отчет об оценке</span><span class="sxs-lookup"><span data-stu-id="7ce07-256">Evaluation report</span></span>
<span data-ttu-id="7ce07-257">В лабораторных отчетах подводятся итоги моделирования, проведенного на устройствах.</span><span class="sxs-lookup"><span data-stu-id="7ce07-257">The lab reports summarize the results of the simulations conducted on the devices.</span></span>

![Изображение отчета об оценке](images/eval-report.png)

<span data-ttu-id="7ce07-259">С первого взгляда вы быстро сможете увидеть:</span><span class="sxs-lookup"><span data-stu-id="7ce07-259">At a glance, you'll quickly be able to see:</span></span>
- <span data-ttu-id="7ce07-260">Инциденты, которые были вызваны</span><span class="sxs-lookup"><span data-stu-id="7ce07-260">Incidents that were triggered</span></span>
- <span data-ttu-id="7ce07-261">Сгенерированная оповещений</span><span class="sxs-lookup"><span data-stu-id="7ce07-261">Generated alerts</span></span>
- <span data-ttu-id="7ce07-262">Оценки уровня экспозиции</span><span class="sxs-lookup"><span data-stu-id="7ce07-262">Assessments on exposure level</span></span> 
- <span data-ttu-id="7ce07-263">Наблюдаемые категории угроз</span><span class="sxs-lookup"><span data-stu-id="7ce07-263">Threat categories observed</span></span>
- <span data-ttu-id="7ce07-264">Источники обнаружения</span><span class="sxs-lookup"><span data-stu-id="7ce07-264">Detection sources</span></span>
- <span data-ttu-id="7ce07-265">Автоматические исследования</span><span class="sxs-lookup"><span data-stu-id="7ce07-265">Automated investigations</span></span>


## <a name="provide-feedback"></a><span data-ttu-id="7ce07-266">Предоставление отзывов</span><span class="sxs-lookup"><span data-stu-id="7ce07-266">Provide feedback</span></span>
<span data-ttu-id="7ce07-267">Ваши отзывы помогают нам лучше защищать вашу среду от расширенных атак.</span><span class="sxs-lookup"><span data-stu-id="7ce07-267">Your feedback helps us get better in protecting your environment from advanced attacks.</span></span> <span data-ttu-id="7ce07-268">Поделитесь своим опытом и впечатлениями от возможностей продукта и результатов оценки.</span><span class="sxs-lookup"><span data-stu-id="7ce07-268">Share your experience and impressions from product capabilities and evaluation results.</span></span>

<span data-ttu-id="7ce07-269">Дайте нам знать, что вы думаете, выбрав **Обеспечить обратную связь**.</span><span class="sxs-lookup"><span data-stu-id="7ce07-269">Let us know what you think, by selecting **Provide feedback**.</span></span>

![Изображение предоставления обратной связи](images/send-us-feedback-eval-lab.png)
