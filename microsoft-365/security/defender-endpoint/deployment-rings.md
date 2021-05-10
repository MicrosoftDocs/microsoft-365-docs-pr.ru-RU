---
title: Развертывание Microsoft Defender для конечной точки в кольцах
description: Узнайте, как развернуть Microsoft Defender для конечной точки в кольцах
keywords: развертывание, кольца, оценка, пилот, инсайдерская быстро, инсайдерская медленная, установка, бортовая, фаза, развертывание, развертывание, развертывание, принятие, настройка
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
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5aeaa51e5ab8974c8ca26453534396dac14b5853
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297214"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a><span data-ttu-id="82b66-104">Развертывание Microsoft Defender для конечной точки в кольцах</span><span class="sxs-lookup"><span data-stu-id="82b66-104">Deploy Microsoft Defender for Endpoint in rings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="82b66-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="82b66-105">**Applies to:**</span></span>
- [<span data-ttu-id="82b66-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="82b66-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="82b66-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82b66-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="82b66-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="82b66-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="82b66-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="82b66-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="82b66-110">Развертывание Microsoft Defender для конечной точки можно сделать с помощью подхода к развертыванию на основе кольца.</span><span class="sxs-lookup"><span data-stu-id="82b66-110">Deploying Microsoft Defender for Endpoint can be done using a ring-based deployment approach.</span></span> 

<span data-ttu-id="82b66-111">Кольца развертывания можно применить в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="82b66-111">The deployment rings can be applied in the following scenarios:</span></span>
- [<span data-ttu-id="82b66-112">Новые развертывания</span><span class="sxs-lookup"><span data-stu-id="82b66-112">New deployments</span></span>](#new-deployments)
- [<span data-ttu-id="82b66-113">Существующие развертывания</span><span class="sxs-lookup"><span data-stu-id="82b66-113">Existing deployments</span></span>](#existing-deployments)

## <a name="new-deployments"></a><span data-ttu-id="82b66-114">Новые развертывания</span><span class="sxs-lookup"><span data-stu-id="82b66-114">New deployments</span></span>

![Изображение колец развертывания](images/deployment-rings.png)


<span data-ttu-id="82b66-116">Метод на основе кольца — это метод определения набора конечных точек для бортового устройства и проверки соответствия определенным критериям перед началом развертывания службы на более широком наборе устройств.</span><span class="sxs-lookup"><span data-stu-id="82b66-116">A ring-based approach is a method of identifying a set of endpoints to onboard and verifying that certain criteria is met before proceeding to deploy the service to a larger set of devices.</span></span> <span data-ttu-id="82b66-117">Вы можете определить критерии выхода для каждого кольца и убедиться, что они удовлетворены перед переходом на следующее кольцо.</span><span class="sxs-lookup"><span data-stu-id="82b66-117">You can define the exit criteria for each ring and ensure that they are satisfied before moving on to the next ring.</span></span>

<span data-ttu-id="82b66-118">Внедрение развертывания на основе кольца помогает уменьшить возможные проблемы, которые могут возникнуть при развертывании службы.</span><span class="sxs-lookup"><span data-stu-id="82b66-118">Adopting a ring-based deployment helps reduce potential issues that could arise while rolling out the service.</span></span> <span data-ttu-id="82b66-119">Сначала с помощью пилотного пилотирования определенного числа устройств можно определить потенциальные проблемы и снизить возможные риски, которые могут возникнуть.</span><span class="sxs-lookup"><span data-stu-id="82b66-119">By piloting a certain number of devices first, you can identify potential issues and mitigate potential risks that might arise.</span></span> 


<span data-ttu-id="82b66-120">В таблице 1 приводится пример колец развертывания, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="82b66-120">Table 1 provides an example of the deployment rings you might use.</span></span> 

<span data-ttu-id="82b66-121">**Таблица 1**</span><span class="sxs-lookup"><span data-stu-id="82b66-121">**Table 1**</span></span>

|<span data-ttu-id="82b66-122">**Круг развертывания**</span><span class="sxs-lookup"><span data-stu-id="82b66-122">**Deployment ring**</span></span>|<span data-ttu-id="82b66-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="82b66-123">**Description**</span></span>|
|:-----|:-----|
<span data-ttu-id="82b66-124">Оценка</span><span class="sxs-lookup"><span data-stu-id="82b66-124">Evaluate</span></span> | <span data-ttu-id="82b66-125">Кольцо 1. Определение 50 систем для пилотного тестирования</span><span class="sxs-lookup"><span data-stu-id="82b66-125">Ring 1: Identify 50 systems for pilot testing</span></span> 
<span data-ttu-id="82b66-126">Пилотное развертывание</span><span class="sxs-lookup"><span data-stu-id="82b66-126">Pilot</span></span> | <span data-ttu-id="82b66-127">Кольцо 2. Определение следующих конечных точек 50-100 в производственной среде</span><span class="sxs-lookup"><span data-stu-id="82b66-127">Ring 2: Identify the next 50-100  endpoints in production environment</span></span> <br>  
<span data-ttu-id="82b66-128">Полное развертывание</span><span class="sxs-lookup"><span data-stu-id="82b66-128">Full deployment</span></span> | <span data-ttu-id="82b66-129">Кольцо 3. Выкатка службы для остальной среды с большими приращениями</span><span class="sxs-lookup"><span data-stu-id="82b66-129">Ring 3: Roll out service to the rest of environment in larger increments</span></span>



### <a name="exit-criteria"></a><span data-ttu-id="82b66-130">Критерии выхода</span><span class="sxs-lookup"><span data-stu-id="82b66-130">Exit criteria</span></span>
<span data-ttu-id="82b66-131">Пример набора критериев выхода для этих колец может включать в себя:</span><span class="sxs-lookup"><span data-stu-id="82b66-131">An example set of exit criteria for these rings can include:</span></span>
- <span data-ttu-id="82b66-132">Устройства показываются в списке инвентаризации устройств</span><span class="sxs-lookup"><span data-stu-id="82b66-132">Devices show up in the device inventory list</span></span>
- <span data-ttu-id="82b66-133">Оповещения отображаются на панели мониторинга</span><span class="sxs-lookup"><span data-stu-id="82b66-133">Alerts appear in dashboard</span></span>
- [<span data-ttu-id="82b66-134">Выполнить тест обнаружения</span><span class="sxs-lookup"><span data-stu-id="82b66-134">Run a detection test</span></span>](run-detection-test.md)
- [<span data-ttu-id="82b66-135">Запуск смоделированной атаки на устройство</span><span class="sxs-lookup"><span data-stu-id="82b66-135">Run a simulated attack on a device</span></span>](attack-simulations.md)

### <a name="evaluate"></a><span data-ttu-id="82b66-136">Оценка</span><span class="sxs-lookup"><span data-stu-id="82b66-136">Evaluate</span></span>
<span data-ttu-id="82b66-137">Определите небольшое количество тестовых машин в вашей среде, чтобы они были на борту службы.</span><span class="sxs-lookup"><span data-stu-id="82b66-137">Identify a small number of test machines in your environment to onboard to the service.</span></span> <span data-ttu-id="82b66-138">В идеале эти машины будут иметь менее 50 конечных точек.</span><span class="sxs-lookup"><span data-stu-id="82b66-138">Ideally, these machines would be fewer than 50 endpoints.</span></span> 


### <a name="pilot"></a><span data-ttu-id="82b66-139">Пилотное развертывание</span><span class="sxs-lookup"><span data-stu-id="82b66-139">Pilot</span></span>
<span data-ttu-id="82b66-140">Microsoft Defender для конечной точки поддерживает различные конечные точки, которые можно использовать в службе.</span><span class="sxs-lookup"><span data-stu-id="82b66-140">Microsoft Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> <span data-ttu-id="82b66-141">В этом кольце определите несколько устройств на борту и на основе определяемого вами критерия выхода решите перейти к следующему кольцу развертывания.</span><span class="sxs-lookup"><span data-stu-id="82b66-141">In this ring, identify several devices to onboard and based on the exit criteria you define, decide to proceed to the next deployment ring.</span></span>

<span data-ttu-id="82b66-142">В следующей таблице показаны поддерживаемые конечные точки и соответствующий инструмент, который можно использовать на бортовых устройствах службы.</span><span class="sxs-lookup"><span data-stu-id="82b66-142">The following table shows the supported endpoints and the corresponding tool you can use to onboard devices to the service.</span></span> 

| <span data-ttu-id="82b66-143">Endpoint</span><span class="sxs-lookup"><span data-stu-id="82b66-143">Endpoint</span></span>     | <span data-ttu-id="82b66-144">Средство развертывания</span><span class="sxs-lookup"><span data-stu-id="82b66-144">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="82b66-145">**Windows**</span><span class="sxs-lookup"><span data-stu-id="82b66-145">**Windows**</span></span>  |  [<span data-ttu-id="82b66-146">Локальный скрипт (до 10 устройств)</span><span class="sxs-lookup"><span data-stu-id="82b66-146">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br> <span data-ttu-id="82b66-147">ПРИМЕЧАНИЕ. Если вы хотите развернуть более 10 устройств в рабочей среде, используйте метод групповой политики или другие поддерживаемые ниже средства.</span><span class="sxs-lookup"><span data-stu-id="82b66-147">NOTE: If you want to deploy more than 10 devices in a production environment, use the Group Policy method instead or the other supported tools listed below.</span></span><br>  [<span data-ttu-id="82b66-148">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="82b66-148">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="82b66-149">Microsoft Endpoint Manager/ Диспетчер мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="82b66-149">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="82b66-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="82b66-150">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="82b66-151">Скрипты VDI</span><span class="sxs-lookup"><span data-stu-id="82b66-151">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="82b66-152">**macOS**</span><span class="sxs-lookup"><span data-stu-id="82b66-152">**macOS**</span></span>    | [<span data-ttu-id="82b66-153">Локальный скрипт</span><span class="sxs-lookup"><span data-stu-id="82b66-153">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="82b66-154">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="82b66-154">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="82b66-155">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="82b66-155">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="82b66-156">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="82b66-156">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="82b66-157">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="82b66-157">**Linux Server**</span></span> | [<span data-ttu-id="82b66-158">Локальный скрипт</span><span class="sxs-lookup"><span data-stu-id="82b66-158">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="82b66-159">Puppet</span><span class="sxs-lookup"><span data-stu-id="82b66-159">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="82b66-160">Ansible</span><span class="sxs-lookup"><span data-stu-id="82b66-160">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="82b66-161">**iOS**</span><span class="sxs-lookup"><span data-stu-id="82b66-161">**iOS**</span></span>      | [<span data-ttu-id="82b66-162">На основе приложения</span><span class="sxs-lookup"><span data-stu-id="82b66-162">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="82b66-163">**Android**</span><span class="sxs-lookup"><span data-stu-id="82b66-163">**Android**</span></span>  | [<span data-ttu-id="82b66-164">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="82b66-164">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




### <a name="full-deployment"></a><span data-ttu-id="82b66-165">Полное развертывание</span><span class="sxs-lookup"><span data-stu-id="82b66-165">Full deployment</span></span>
<span data-ttu-id="82b66-166">На данном этапе вы можете использовать материал [развертывания Plan](deployment-strategy.md) для планирования развертывания.</span><span class="sxs-lookup"><span data-stu-id="82b66-166">At this stage, you can use the [Plan deployment](deployment-strategy.md) material to help you plan your deployment.</span></span> 


<span data-ttu-id="82b66-167">Используйте следующий материал, чтобы выбрать соответствующую архитектуру Microsoft Defender для конечной точки, которая лучше всего подходит для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="82b66-167">Use the following material to select the appropriate Microsoft Defender for Endpoint architecture that best suites your organization.</span></span>

|<span data-ttu-id="82b66-168">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="82b66-168">**Item**</span></span>|<span data-ttu-id="82b66-169">**Описание**</span><span class="sxs-lookup"><span data-stu-id="82b66-169">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="82b66-170">[![Изображение большого пальца для стратегии развертывания Конечных точек Microsoft Defender для конечной точки](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="82b66-170">[![Thumb image for Microsoft Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="82b66-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="82b66-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="82b66-172">Материалы по архитектуре помогут вам спланировать развертывание для следующих архитектур:</span><span class="sxs-lookup"><span data-stu-id="82b66-172">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="82b66-173">Облачное развертывание</span><span class="sxs-lookup"><span data-stu-id="82b66-173">Cloud-native</span></span> </li><li> <span data-ttu-id="82b66-174">Совместное управление</span><span class="sxs-lookup"><span data-stu-id="82b66-174">Co-management</span></span> </li><li> <span data-ttu-id="82b66-175">Локальное развертывание</span><span class="sxs-lookup"><span data-stu-id="82b66-175">On-premise</span></span></li><li><span data-ttu-id="82b66-176">Оценка и локальное внедрение</span><span class="sxs-lookup"><span data-stu-id="82b66-176">Evaluation and local onboarding</span></span></li>




## <a name="existing-deployments"></a><span data-ttu-id="82b66-177">Существующие развертывания</span><span class="sxs-lookup"><span data-stu-id="82b66-177">Existing deployments</span></span>

### <a name="windows-endpoints"></a><span data-ttu-id="82b66-178">Windows конечных точек</span><span class="sxs-lookup"><span data-stu-id="82b66-178">Windows endpoints</span></span>
<span data-ttu-id="82b66-179">Для Windows и/или Windows серверов вы выбираете несколько машин для досрочного тестирования (перед обновлением во вторник) с помощью программы проверки обновления безопасности **(SUVP).**</span><span class="sxs-lookup"><span data-stu-id="82b66-179">For Windows and/or Windows Servers, you select several machines to test ahead of time (before patch Tuesday) by using the **Security Update Validation program (SUVP)**.</span></span>

<span data-ttu-id="82b66-180">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="82b66-180">For more information, see:</span></span>
- [<span data-ttu-id="82b66-181">Что такое программа проверки обновления безопасности</span><span class="sxs-lookup"><span data-stu-id="82b66-181">What is the Security Update Validation Program</span></span>](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [<span data-ttu-id="82b66-182">Программа проверки обновления программного обеспечения и Центр Майкрософт по защите от вредоносных программ создания — TwC Interactive Timeline Part 4</span><span class="sxs-lookup"><span data-stu-id="82b66-182">Software Update Validation Program and Microsoft Malware Protection Center Establishment - TwC Interactive Timeline Part 4</span></span>](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)


### <a name="non-windows-endpoints"></a><span data-ttu-id="82b66-183">Конечные точки Windows</span><span class="sxs-lookup"><span data-stu-id="82b66-183">Non-Windows endpoints</span></span>
<span data-ttu-id="82b66-184">С macOS и Linux можно взять несколько систем и запустить в бета-канале.</span><span class="sxs-lookup"><span data-stu-id="82b66-184">With macOS and Linux, you could take a couple of systems and run in the Beta channel.</span></span>

>[!NOTE]
><span data-ttu-id="82b66-185">В идеале не менее одного администратора безопасности и одного разработчика, чтобы вы могли находить проблемы совместимости, производительности и надежности до того, как сборка будет перенастройка в текущий канал.</span><span class="sxs-lookup"><span data-stu-id="82b66-185">Ideally at least one security admin and one developer so that you are able to find compatibility, performance and reliability issues before the build makes it into the Current channel.</span></span>

<span data-ttu-id="82b66-186">Выбор канала определяет тип и частоту обновлений, предлагаемых вашему устройству.</span><span class="sxs-lookup"><span data-stu-id="82b66-186">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="82b66-187">Устройства в бета-версии первыми получают обновления и новые функции, а затем предварительный просмотр и, наконец, Current.</span><span class="sxs-lookup"><span data-stu-id="82b66-187">Devices in Beta are the first ones to receive updates and new features, followed later by Preview and lastly by Current.</span></span>

![Изображение инсайдерской колец](images/insider-rings.png)

<span data-ttu-id="82b66-189">Для предварительного просмотра новых функций и предоставления ранних отзывов рекомендуется настроить некоторые устройства на предприятии для использования бета-версии или предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="82b66-189">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either Beta or Preview.</span></span>

>[!WARNING]
><span data-ttu-id="82b66-190">Переключение канала после начальной установки требует повторной установки продукта.</span><span class="sxs-lookup"><span data-stu-id="82b66-190">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="82b66-191">Чтобы переключить канал продукта: удалить существующий пакет, перенастройте устройство для использования нового канала и выполните действия в этом документе, чтобы установить пакет из нового расположения.</span><span class="sxs-lookup"><span data-stu-id="82b66-191">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>
