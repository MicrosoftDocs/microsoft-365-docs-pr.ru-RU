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
ms.openlocfilehash: ed2165c0102170256f50964180a550d8eccbce8c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932791"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a><span data-ttu-id="7a1c4-104">Лаборатория оценки Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7a1c4-104">Microsoft Defender for Endpoint evaluation lab</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7a1c4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7a1c4-105">**Applies to:**</span></span>
- [<span data-ttu-id="7a1c4-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7a1c4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7a1c4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7a1c4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="7a1c4-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="7a1c4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7a1c4-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="7a1c4-110">Проведение комплексной оценки продукта безопасности может быть сложным процессом, требующим громоздких условий и конфигурации устройств, прежде чем может быть фактически сделано комплексное моделирование атаки.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-110">Conducting a comprehensive security product evaluation can be a complex process requiring cumbersome environment and device configuration before an end-to-end attack simulation can actually be done.</span></span> <span data-ttu-id="7a1c4-111">Сложность заключается в отслеживании того, где во время оценки отражаются действия моделирования, оповещения и результаты.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-111">Adding to the complexity is the challenge of tracking where the simulation activities, alerts, and results are reflected during the evaluation.</span></span>

<span data-ttu-id="7a1c4-112">Лаборатория оценки Microsoft Defender для конечной точки предназначена для устранения сложностей конфигурации устройства и среды, чтобы вы могли сосредоточиться на оценке возможностей платформы, запуске имитаций и обнаружении функций предотвращения, обнаружения и восстановления в действии.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-112">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can  focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

<span data-ttu-id="7a1c4-113">С помощью упрощенной системы можно сосредоточиться на выполнении собственных тестовых сценариев и заранее сделанных имитаций, чтобы узнать, как работает Defender для endpoint.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-113">With the simplified set-up experience, you can focus on running your own test scenarios and the pre-made simulations to see how Defender for Endpoint performs.</span></span> 

<span data-ttu-id="7a1c4-114">У вас будет полный доступ к мощным возможностям платформы, таким как автоматизированные расследования, расширенные поиски и аналитика угроз, что позволит протестировать комплексный стек защиты, который предлагает Defender для Endpoint.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-114">You'll have full access to the powerful capabilities of the platform such as automated investigations, advanced hunting, and threat analytics, allowing you to test the comprehensive protection stack that Defender for Endpoint offers.</span></span> 

<span data-ttu-id="7a1c4-115">Вы можете добавить устройства Windows 10 или Windows Server 2019, которые предварительно настроены для установки последних версий ОС и нужных компонентов безопасности, а также для установки стандарта Office 2019.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-115">You can add Windows 10 or Windows Server 2019 devices that come pre-configured to have the latest OS versions and the right security components in place as well as Office 2019 Standard installed.</span></span>

<span data-ttu-id="7a1c4-116">Вы также можете установить симуляторы угроз.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-116">You can also install threat simulators.</span></span> <span data-ttu-id="7a1c4-117">Defender for Endpoint имеет партнерские отношения с ведущими отраслевыми платформами моделирования угроз, чтобы помочь вам проверить возможности Defender для конечной точки, не покидая портал.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-117">Defender for Endpoint has partnered with industry leading threat simulation platforms to help you test out the Defender for Endpoint capabilities without having to leave the portal.</span></span>

 <span data-ttu-id="7a1c4-118">Установите предпочтительный симулятор, запустите сценарии в лаборатории оценки и сразу же посмотрите, как выполняется платформа — все удобно доступно без дополнительных затрат для вас.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-118">Install your preferred simulator, run scenarios within the evaluation lab, and instantly see how the platform performs - all conveniently available at no extra cost to you.</span></span> <span data-ttu-id="7a1c4-119">Вы также будете иметь удобный доступ к широкому спектру имитаций, к которым можно получить доступ и запустить из каталога моделирования.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-119">You'll also have convenient access to wide array of simulations which you can access and run from the simulations catalog.</span></span>
    

## <a name="before-you-begin"></a><span data-ttu-id="7a1c4-120">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="7a1c4-120">Before you begin</span></span>
<span data-ttu-id="7a1c4-121">Чтобы получить доступ к [](minimum-requirements.md#licensing-requirements) лаборатории оценки, необходимо выполнить требования лицензирования или получить пробный доступ к Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-121">You'll need to fulfill the [licensing requirements](minimum-requirements.md#licensing-requirements) or have trial access to Microsoft Defender for Endpoint to access the evaluation lab.</span></span>

<span data-ttu-id="7a1c4-122">Необходимо иметь разрешения на управление **настройками** безопасности, чтобы:</span><span class="sxs-lookup"><span data-stu-id="7a1c4-122">You must have **Manage security settings** permissions to:</span></span>
- <span data-ttu-id="7a1c4-123">Создание лаборатории</span><span class="sxs-lookup"><span data-stu-id="7a1c4-123">Create the lab</span></span>
- <span data-ttu-id="7a1c4-124">Создание устройств</span><span class="sxs-lookup"><span data-stu-id="7a1c4-124">Create devices</span></span>
- <span data-ttu-id="7a1c4-125">Сброс пароля</span><span class="sxs-lookup"><span data-stu-id="7a1c4-125">Reset password</span></span>
- <span data-ttu-id="7a1c4-126">Создание имитаций</span><span class="sxs-lookup"><span data-stu-id="7a1c4-126">Create simulations</span></span> 
 
<span data-ttu-id="7a1c4-127">Если вы включили управление доступом на основе ролей (RBAC) и создали по крайней мере одну группу машин, пользователи должны иметь доступ ко всем группам машин.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-127">If you enabled role-based access control (RBAC) and created at least a one machine group, users must have access to All machine groups.</span></span>

<span data-ttu-id="7a1c4-128">Дополнительные сведения см. в [дополнительных сведениях о создании и управлении ролями.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="7a1c4-128">For more information, see [Create and manage roles](user-roles.md).</span></span>

<span data-ttu-id="7a1c4-129">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="7a1c4-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7a1c4-130">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a><span data-ttu-id="7a1c4-131">Начало работы с лабораторией</span><span class="sxs-lookup"><span data-stu-id="7a1c4-131">Get started with the lab</span></span>
<span data-ttu-id="7a1c4-132">Вы можете получить доступ к лаборатории из меню.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-132">You can access the lab from the menu.</span></span> <span data-ttu-id="7a1c4-133">В меню навигации выберите оценку и **учебники > оценки.**</span><span class="sxs-lookup"><span data-stu-id="7a1c4-133">In the navigation menu, select **Evaluation and tutorials > Evaluation lab**.</span></span>

![Изображение лаборатории оценки в меню](images/evaluation-lab-menu.png)

>[!NOTE]
>- <span data-ttu-id="7a1c4-135">В зависимости от выбранной структуры среды устройства будут доступны в течение указанного количества часов со дня активации.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-135">Depending the type of environment structure you select, devices will be available for the specified number of hours from the day of activation.</span></span>
>- <span data-ttu-id="7a1c4-136">Каждая среда содержит ограниченный набор тестовых устройств.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-136">Each environment is provisioned with a limited set of test devices.</span></span> <span data-ttu-id="7a1c4-137">Когда вы использовали готовые устройства, новые устройства не предоставляются.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-137">When you've used up the provisioned devices, no new devices are provided.</span></span> <span data-ttu-id="7a1c4-138">Удаленное устройство не обновляет доступное количество тестовых устройств.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-138">A deleted device does not refresh the available test device count.</span></span>
>- <span data-ttu-id="7a1c4-139">Вы больше не можете использовать лабораторию при использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-139">You can no longer use the lab when the resources have been used up.</span></span> <span data-ttu-id="7a1c4-140">Он не сбрасывается и не обновляется.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-140">It does not reset nor refresh.</span></span>
>- <span data-ttu-id="7a1c4-141">Рекомендуется тщательно использовать ресурсы. Ресурсы лаборатории ограничены.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-141">It is advisable to use the resources carefully.The lab resources are limited.</span></span> <span data-ttu-id="7a1c4-142">Они не сброшены и не обновляются.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-142">They will not reset nor refresh.</span></span> 

<span data-ttu-id="7a1c4-143">Уже есть лаборатория?</span><span class="sxs-lookup"><span data-stu-id="7a1c4-143">Already have a lab?</span></span> <span data-ttu-id="7a1c4-144">Убедитесь в том, чтобы включить новые симуляторы угроз и иметь активные устройства.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-144">Make sure to enable the new threat simulators and have active devices.</span></span>

## <a name="setup-the-evaluation-lab"></a><span data-ttu-id="7a1c4-145">Настройка лаборатории оценки</span><span class="sxs-lookup"><span data-stu-id="7a1c4-145">Setup the evaluation lab</span></span>

1. <span data-ttu-id="7a1c4-146">В области навигации выберите **лабораторию оценки** и оценки учебных пособий,  >  а затем выберите **лабораторию установки.**</span><span class="sxs-lookup"><span data-stu-id="7a1c4-146">In the navigation pane, select **Evaluation and tutorials** > **Evaluation lab**, then select **Setup lab**.</span></span>

    ![Изображение страницы приветствия лаборатории оценки](images/evaluation-lab-setup.png)

2. <span data-ttu-id="7a1c4-148">В зависимости от потребностей в оценке можно настроить среду с большим или большим количеством устройств на более короткий период.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-148">Depending on your evaluation needs, you can choose to setup an environment with fewer devices for a longer period or more devices for a shorter period.</span></span> <span data-ttu-id="7a1c4-149">Выберите предпочитаемую конфигурацию лаборатории, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-149">Select your preferred lab configuration then select **Next**.</span></span>

    ![Изображение параметров конфигурации лаборатории](images/lab-creation-page.png) 


3. <span data-ttu-id="7a1c4-151">(Необязательный) Вы можете установить симуляторы угроз в лаборатории.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-151">(Optional) You can choose to install threat simulators in the lab.</span></span> 

    ![Изображение агента симуляторов установки](images/install-agent.png)

    >[!IMPORTANT]
    ><span data-ttu-id="7a1c4-153">Сначала необходимо принять и предоставить согласие на условия и заявления о совместном использовании информации.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-153">You'll first need to accept and provide consent to the terms and information sharing statements.</span></span> 

4. <span data-ttu-id="7a1c4-154">Выберите агент моделирования угроз, который вы хотите использовать, и введите сведения.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-154">Select the threat simulation agent you'd like to use and enter your details.</span></span> <span data-ttu-id="7a1c4-155">Вы также можете выбрать установку симуляторов угроз в более позднее время.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-155">You can also choose to install threat simulators at a later time.</span></span> <span data-ttu-id="7a1c4-156">Если вы решите установить агенты моделирования угроз во время установки лаборатории, вы сможете удобно установить их на добавленных устройствах.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-156">If you choose to install threat simulation agents during the lab setup, you'll enjoy the benefit of having them conveniently installed on the devices you add.</span></span>  
    
    ![Изображение страницы сводки](images/lab-setup-summary.png)

5.  <span data-ttu-id="7a1c4-158">Просмотрите сводку и выберите **лабораторию установки.**</span><span class="sxs-lookup"><span data-stu-id="7a1c4-158">Review the summary and select **Setup lab**.</span></span>  

<span data-ttu-id="7a1c4-159">После завершения процесса установки лаборатории можно добавить устройства и запустить моделирование.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-159">After the lab setup process is complete, you can add devices and run simulations.</span></span> 


## <a name="add-devices"></a><span data-ttu-id="7a1c4-160">Добавление устройств</span><span class="sxs-lookup"><span data-stu-id="7a1c4-160">Add devices</span></span>
<span data-ttu-id="7a1c4-161">При добавлении устройства в среду Defender for Endpoint настраивает хорошо настроенное устройство с сведениями о подключении.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-161">When you add a device to your environment, Defender for Endpoint sets up a well-configured device with connection details.</span></span> <span data-ttu-id="7a1c4-162">Можно добавить устройства с Windows 10 или Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-162">You can add Windows 10 or Windows Server 2019 devices.</span></span>

<span data-ttu-id="7a1c4-163">Устройство будет настроено с самой новой версией ОС и Office 2019 Standard, а также с другими приложениями, такими как Java, Python и SysIntenals.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-163">The device will be configured with the most up-to-date version of the OS and Office 2019 Standard as well as other apps such as Java, Python, and SysIntenals.</span></span> 

   >[!TIP]
   > <span data-ttu-id="7a1c4-164">Нужны дополнительные устройства в лаборатории?</span><span class="sxs-lookup"><span data-stu-id="7a1c4-164">Need more devices in your lab?</span></span> <span data-ttu-id="7a1c4-165">Отправьте билет поддержки, чтобы ваш запрос был рассмотрен командой Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-165">Submit a support ticket to have your request reviewed by the Defender for Endpoint team.</span></span> 

<span data-ttu-id="7a1c4-166">Если вы решили добавить симулятор угроз во время установки лаборатории, на всех устройствах будет установлен агент симулятора угроз, установленный на добавленных устройствах.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-166">If you chose to add a threat simulator during the lab setup, all devices will have the threat simulator agent installed in the devices that you add.</span></span>

<span data-ttu-id="7a1c4-167">Устройство автоматически будет включено для клиента с рекомендованными компонентами безопасности Windows и в режиме аудита без каких-либо усилий на вашей стороне.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-167">The device will automatically be onboarded to your tenant with the recommended Windows security components turned on and in audit mode - with no effort on your side.</span></span> 

<span data-ttu-id="7a1c4-168">На тестовых устройствах предварительно настроены следующие компоненты безопасности:</span><span class="sxs-lookup"><span data-stu-id="7a1c4-168">The following security components are pre-configured in the test devices:</span></span>

- [<span data-ttu-id="7a1c4-169">Сокращение направлений атак</span><span class="sxs-lookup"><span data-stu-id="7a1c4-169">Attack surface reduction</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)
- [<span data-ttu-id="7a1c4-170">Блок с первого взгляда</span><span class="sxs-lookup"><span data-stu-id="7a1c4-170">Block at first sight</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
- [<span data-ttu-id="7a1c4-171">Контролируемый доступ к папкам</span><span class="sxs-lookup"><span data-stu-id="7a1c4-171">Controlled folder access</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)
- [<span data-ttu-id="7a1c4-172">Защита от эксплойтов</span><span class="sxs-lookup"><span data-stu-id="7a1c4-172">Exploit protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/enable-exploit-protection)
- [<span data-ttu-id="7a1c4-173">Защита сети</span><span class="sxs-lookup"><span data-stu-id="7a1c4-173">Network protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
- [<span data-ttu-id="7a1c4-174">Обнаружение потенциально нежелательных приложений</span><span class="sxs-lookup"><span data-stu-id="7a1c4-174">Potentially unwanted application detection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="7a1c4-175">Облачная защита</span><span class="sxs-lookup"><span data-stu-id="7a1c4-175">Cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="7a1c4-176">SmartScreen защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7a1c4-176">Microsoft Defender SmartScreen</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)

>[!NOTE]
> <span data-ttu-id="7a1c4-177">Антивирус Microsoft Defender будет работать (не в режиме аудита).</span><span class="sxs-lookup"><span data-stu-id="7a1c4-177">Microsoft Defender Antivirus will be on (not in audit mode).</span></span> <span data-ttu-id="7a1c4-178">Если антивирус Microsoft Defender блокирует работу моделирования, вы можете отключить защиту в режиме реального времени на устройстве с помощью Windows Security.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-178">If Microsoft Defender Antivirus blocks you from running your simulation, you can turn off real-time protection on the device through Windows Security.</span></span> <span data-ttu-id="7a1c4-179">Дополнительные сведения см. [в перенастройке всегда на защиту.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="7a1c4-179">For more information, see [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="7a1c4-180">Параметры автоматического расследования будут зависеть от параметров клиента.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-180">Automated investigation settings will be dependent on tenant settings.</span></span> <span data-ttu-id="7a1c4-181">Он будет настроен на полуавтоматизированный по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-181">It will be configured to be semi-automated by default.</span></span> <span data-ttu-id="7a1c4-182">Дополнительные сведения см. [в обзоре автоматизированных расследований.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="7a1c4-182">For more information, see [Overview of Automated investigations](automated-investigations.md).</span></span>

>[!NOTE]
><span data-ttu-id="7a1c4-183">Подключение к тест-устройствам делается с помощью RDP.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-183">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="7a1c4-184">Убедитесь, что параметры брандмауэра позволяют подключения RDP.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-184">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="7a1c4-185">На панели мониторинга выберите **устройство Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-185">From the dashboard, select **Add device**.</span></span> 

2. <span data-ttu-id="7a1c4-186">Выберите тип устройства для добавления.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-186">Choose the type of device to add.</span></span> <span data-ttu-id="7a1c4-187">Вы можете добавить Windows 10 или Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-187">You can choose to add Windows 10 or Windows Server 2019.</span></span>

    ![Изображение лабораторной установки с вариантами устройств](images/add-machine-options.png)


    >[!NOTE]
    ><span data-ttu-id="7a1c4-189">Если что-то не справится с процессом создания устройства, вы будете уведомлены и вам потребуется отправить новый запрос.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-189">If something goes wrong with the device creation process, you'll be notified and you'll need to submit a new request.</span></span> <span data-ttu-id="7a1c4-190">Если создание устройства не удается, он не будет засчитываться по общей разрешенной квоте.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-190">If the device creation fails, it will not be counted against the overall allowed quota.</span></span> 

3. <span data-ttu-id="7a1c4-191">Отображаются сведения о подключении.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-191">The connection details are displayed.</span></span> <span data-ttu-id="7a1c4-192">Выберите **Копию,** чтобы сохранить пароль для устройства.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-192">Select **Copy** to save the password for the device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="7a1c4-193">Пароль отображается только один раз.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-193">The password is only displayed once.</span></span> <span data-ttu-id="7a1c4-194">Обязательно сохраните его для более позднего использования.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-194">Be sure to save it for later use.</span></span>

    ![Изображение устройства, добавленного с сведениями о подключении](images/add-machine-eval-lab.png)

4. <span data-ttu-id="7a1c4-196">Начинается настройка устройства.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-196">Device set up begins.</span></span> <span data-ttu-id="7a1c4-197">Это может занять около 30 минут.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-197">This can take up to approximately 30 minutes.</span></span> 

5. <span data-ttu-id="7a1c4-198">Узнайте о состоянии тестовых устройств, уровнях риска и экспозиции, а также о состоянии установок симулятора, выбрав вкладку **Devices.**</span><span class="sxs-lookup"><span data-stu-id="7a1c4-198">See the status of test devices, the risk and exposure levels, and the status of simulator installations by selecting the **Devices** tab.</span></span> 

    ![Изображение вкладки устройств](images/machines-tab.png)
    

    >[!TIP]
    ><span data-ttu-id="7a1c4-200">В **столбце Состояние Симулятор** можно нависать над значком информации, чтобы узнать состояние установки агента.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-200">In the **Simulator status** column, you can hover over the information icon to know the installation status of an agent.</span></span>



## <a name="simulate-attack-scenarios"></a><span data-ttu-id="7a1c4-201">Имитация сценариев атак</span><span class="sxs-lookup"><span data-stu-id="7a1c4-201">Simulate attack scenarios</span></span>
<span data-ttu-id="7a1c4-202">Используйте тестовые устройства для запуска собственных имитаций атак, подключившись к ним.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-202">Use the test devices to run your own attack simulations by connecting to them.</span></span> 

<span data-ttu-id="7a1c4-203">Вы можете имитировать сценарии атак с помощью:</span><span class="sxs-lookup"><span data-stu-id="7a1c4-203">You can simulate attack scenarios using:</span></span>
- <span data-ttu-id="7a1c4-204">Сценарии [атаки "Do It Yourself"](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="7a1c4-204">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="7a1c4-205">Симуляторы угроз</span><span class="sxs-lookup"><span data-stu-id="7a1c4-205">Threat simulators</span></span>

<span data-ttu-id="7a1c4-206">Вы также можете использовать [расширенный](advanced-hunting-query-language.md) [](threat-analytics.md) поиск для запроса данных и аналитики угроз для просмотра отчетов о возникающих угрозах.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-206">You can also use [Advanced hunting](advanced-hunting-query-language.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="7a1c4-207">Сценарии атак do-it-yourself</span><span class="sxs-lookup"><span data-stu-id="7a1c4-207">Do-it-yourself attack scenarios</span></span>
<span data-ttu-id="7a1c4-208">Если вы ищете предварительное моделирование, вы можете использовать сценарии атак ["Do It Yourself".](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="7a1c4-208">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="7a1c4-209">Эти скрипты безопасны, документированы и просты в использовании.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-209">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="7a1c4-210">Эти сценарии будут отражать возможности Defender для конечных точек и ходить по опыту исследования.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-210">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>


>[!NOTE]
><span data-ttu-id="7a1c4-211">Подключение к тест-устройствам делается с помощью RDP.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-211">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="7a1c4-212">Убедитесь, что параметры брандмауэра позволяют подключения RDP.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-212">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="7a1c4-213">Подключись к устройству и запустите имитацию атаки, выбрав **Подключение.**</span><span class="sxs-lookup"><span data-stu-id="7a1c4-213">Connect to your device and run an attack simulation by selecting **Connect**.</span></span> 

    ![Изображение кнопки подключения для тестовых устройств](images/test-machine-table.png)

2. <span data-ttu-id="7a1c4-215">Сохраните файл RDP и запустите его, выбрав **Подключение.**</span><span class="sxs-lookup"><span data-stu-id="7a1c4-215">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![Изображение удаленного подключения к рабочему столу](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="7a1c4-217">Если у вас нет копии пароля, сохраненного во время начальной установки, вы можете сбросить пароль, выбрав пароль **Reset** из меню: Изображение пароля ![ сброса.](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="7a1c4-217">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span><br>
    > <span data-ttu-id="7a1c4-218">Устройство изменит его состояние на "Выполнение сброса пароля", после чего через несколько минут вам будет представлен новый пароль.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-218">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="7a1c4-219">Введите пароль, отображаемый во время шага создания устройства.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-219">Enter the password that was displayed during the device creation step.</span></span> 

   ![Изображение окна для ввода учетных данных](images/enter-password.png)

4. <span data-ttu-id="7a1c4-221">Запустите имитацию атак do-it-yourself на устройстве.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-221">Run Do-it-yourself attack simulations on the device.</span></span> 


### <a name="threat-simulator-scenarios"></a><span data-ttu-id="7a1c4-222">Сценарии симулятора угроз</span><span class="sxs-lookup"><span data-stu-id="7a1c4-222">Threat simulator scenarios</span></span>
<span data-ttu-id="7a1c4-223">Если вы решили установить любой из поддерживаемых имитаторов угроз во время установки лаборатории, вы можете запустить встроенные имитации на устройствах лаборатории оценки.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-223">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span> 


<span data-ttu-id="7a1c4-224">Запуск имитации угроз с использованием сторонних платформ — это хороший способ оценить возможности Microsoft Defender для конечных точек в пределах лабораторной среды.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-224">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
><span data-ttu-id="7a1c4-225">Прежде чем запускать моделирование, убедитесь, что следующие требования будут выполнены:</span><span class="sxs-lookup"><span data-stu-id="7a1c4-225">Before you can run simulations, ensure the following requirements are met:</span></span>
>- <span data-ttu-id="7a1c4-226">Устройства должны быть добавлены в лабораторию оценки</span><span class="sxs-lookup"><span data-stu-id="7a1c4-226">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="7a1c4-227">Симуляторы угроз должны быть установлены в лаборатории оценки</span><span class="sxs-lookup"><span data-stu-id="7a1c4-227">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="7a1c4-228">На портале выберите **Создание моделирования.**</span><span class="sxs-lookup"><span data-stu-id="7a1c4-228">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="7a1c4-229">Выберите симулятор угрозы.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-229">Select a threat simulator.</span></span>

    ![Изображение выбора симулятора угроз](images/select-simulator.png)

3. <span data-ttu-id="7a1c4-231">Выберите имитацию или просмотрите галерею моделирования, чтобы просмотреть доступные модели.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-231">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span> 

    <span data-ttu-id="7a1c4-232">Вы можете попасть в галерею моделирования из:</span><span class="sxs-lookup"><span data-stu-id="7a1c4-232">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="7a1c4-233">Основная панель мониторинга оценки в плитке **обзоров simulations** или</span><span class="sxs-lookup"><span data-stu-id="7a1c4-233">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="7a1c4-234">Путем навигации из области навигации **Оценка** и учебники Моделирование & учебники, а затем  >  выберите **каталог моделирования**.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-234">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="7a1c4-235">Выберите устройства, на которых необходимо выполнить моделирование.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-235">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="7a1c4-236">Выберите **Создание моделирования**.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-236">Select **Create simulation**.</span></span>

6. <span data-ttu-id="7a1c4-237">Просмотреть ход моделирования, выбрав вкладку **Simulations.** Просмотр состояния моделирования, активных оповещений и других сведений.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-237">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span> 

    ![Изображение вкладки моделирования](images/simulations-tab.png)
    
<span data-ttu-id="7a1c4-239">После выполнения имитации мы рекомендуем вам пройти через планку прогресса лаборатории и изучить Microsoft Defender для конечной точки инициировать автоматическое расследование и **исправление.**</span><span class="sxs-lookup"><span data-stu-id="7a1c4-239">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="7a1c4-240">Ознакомьтесь с доказательствами, собранными и проанализироваными этой функцией.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-240">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="7a1c4-241">Поиск доказательств атаки с помощью продвинутой охоты с помощью богатого языка запросов и сырой телеметрии и проверить некоторые угрозы во всем мире, задокументированные в аналитике угроз.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-241">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>


## <a name="simulation-gallery"></a><span data-ttu-id="7a1c4-242">Галерея моделирования</span><span class="sxs-lookup"><span data-stu-id="7a1c4-242">Simulation gallery</span></span>
<span data-ttu-id="7a1c4-243">Microsoft Defender для конечной точки имеет партнерские отношения с различными платформами моделирования угроз, чтобы предоставить вам удобный доступ для проверки возможностей платформы прямо из портала.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-243">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span> 

<span data-ttu-id="7a1c4-244">Просмотр всех доступных имитаций, переехав в каталог **моделирования** и учебных пособий из  >   меню.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-244">View all the available simulations by going to  **Simulations and tutorials** > **Simulations catalog**  from the menu.</span></span> 

<span data-ttu-id="7a1c4-245">В каталоге перечислены поддерживаемые сторонние агенты моделирования угроз, а в каталоге перечислены определенные типы имитаций, а также подробные описания.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-245">A list of supported third-party threat simulation agents are listed, and specific types of simulations along with detailed descriptions are provided on the catalog.</span></span> 

<span data-ttu-id="7a1c4-246">Вы можете удобно выполнить любое доступное моделирование прямо из каталога.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-246">You can conveniently run any available simulation right from the catalog.</span></span>  


![Изображение каталога моделирования](images/simulations-catalog.png)

<span data-ttu-id="7a1c4-248">Каждое моделирование поставляется с подробным описанием сценария атаки и ссылками, такими как методы атаки MITRE, используемые и примеры расширенных запросов охоты, которые вы запустите.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-248">Each simulation comes with an in-depth description of the attack scenario and references such as the MITRE attack techniques used and sample Advanced hunting queries you run.</span></span>

<span data-ttu-id="7a1c4-249">**Примеры:** 
 ![ Изображение деталей описания моделирования1](images/simulation-details-aiq.png)</span><span class="sxs-lookup"><span data-stu-id="7a1c4-249">**Examples:**
![Image of simulation description details1](images/simulation-details-aiq.png)</span></span>


![Изображение сведений о описании моделирования2](images/simulation-details-sb.png)


## <a name="evaluation-report"></a><span data-ttu-id="7a1c4-251">Отчет об оценке</span><span class="sxs-lookup"><span data-stu-id="7a1c4-251">Evaluation report</span></span>
<span data-ttu-id="7a1c4-252">В лабораторных отчетах подводятся итоги моделирования, проведенного на устройствах.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-252">The lab reports summarize the results of the simulations conducted on the devices.</span></span>

![Изображение отчета об оценке](images/eval-report.png)

<span data-ttu-id="7a1c4-254">С первого взгляда вы быстро сможете увидеть:</span><span class="sxs-lookup"><span data-stu-id="7a1c4-254">At a glance, you'll quickly be able to see:</span></span>
- <span data-ttu-id="7a1c4-255">Инциденты, которые были вызваны</span><span class="sxs-lookup"><span data-stu-id="7a1c4-255">Incidents that were triggered</span></span>
- <span data-ttu-id="7a1c4-256">Сгенерированная оповещений</span><span class="sxs-lookup"><span data-stu-id="7a1c4-256">Generated alerts</span></span>
- <span data-ttu-id="7a1c4-257">Оценки уровня экспозиции</span><span class="sxs-lookup"><span data-stu-id="7a1c4-257">Assessments on exposure level</span></span> 
- <span data-ttu-id="7a1c4-258">Наблюдаемые категории угроз</span><span class="sxs-lookup"><span data-stu-id="7a1c4-258">Threat categories observed</span></span>
- <span data-ttu-id="7a1c4-259">Источники обнаружения</span><span class="sxs-lookup"><span data-stu-id="7a1c4-259">Detection sources</span></span>
- <span data-ttu-id="7a1c4-260">Автоматические исследования</span><span class="sxs-lookup"><span data-stu-id="7a1c4-260">Automated investigations</span></span>


## <a name="provide-feedback"></a><span data-ttu-id="7a1c4-261">Предоставление отзывов</span><span class="sxs-lookup"><span data-stu-id="7a1c4-261">Provide feedback</span></span>
<span data-ttu-id="7a1c4-262">Ваши отзывы помогают нам лучше защищать вашу среду от расширенных атак.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-262">Your feedback helps us get better in protecting your environment from advanced attacks.</span></span> <span data-ttu-id="7a1c4-263">Поделитесь своим опытом и впечатлениями от возможностей продукта и результатов оценки.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-263">Share your experience and impressions from product capabilities and evaluation results.</span></span>

<span data-ttu-id="7a1c4-264">Дайте нам знать, что вы думаете, выбрав **Обеспечить обратную связь**.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-264">Let us know what you think, by selecting **Provide feedback**.</span></span>

![Изображение предоставления обратной связи](images/send-us-feedback-eval-lab.png)
