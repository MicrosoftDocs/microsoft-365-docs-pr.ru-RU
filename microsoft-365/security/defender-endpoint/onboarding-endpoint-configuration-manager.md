---
title: Onboarding using Microsoft Endpoint Configuration Manager
description: Узнайте, как учиться в Microsoft Defender для конечной точки с помощью Microsoft Endpoint Configuration Manager
keywords: onboarding, configuration, deploy, deployment, endpoint configuration manager, mdatp, advanced threat protection, collection creation, endpoint detection response, next generation protection, attack surface reduction, Microsoft endpoint configuration manager
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
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 31c946ccad84aca3b2fc86c95655cea9e66e182f
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186405"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="42b00-104">Onboarding using Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="42b00-104">Onboarding using Microsoft Endpoint Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="42b00-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="42b00-105">**Applies to:**</span></span>
- [<span data-ttu-id="42b00-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="42b00-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="42b00-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42b00-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="42b00-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="42b00-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="42b00-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="42b00-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="42b00-110">Эта статья является частью руководства по развертыванию и выступает в качестве примера бортового метода.</span><span class="sxs-lookup"><span data-stu-id="42b00-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="42b00-111">В разделе [Планирование](deployment-strategy.md) для бортовых устройств для службы было предоставлено несколько методов.</span><span class="sxs-lookup"><span data-stu-id="42b00-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="42b00-112">В этом разделе описывается архитектура совместного управления.</span><span class="sxs-lookup"><span data-stu-id="42b00-112">This topic covers the co-management architecture.</span></span> 

<span data-ttu-id="42b00-113">![Изображение облачной архитектуры ](images/co-management-architecture.png)
 *Схема архитектуры среды*</span><span class="sxs-lookup"><span data-stu-id="42b00-113">![Image of cloud-native architecture](images/co-management-architecture.png)
*Diagram of environment architectures*</span></span>


<span data-ttu-id="42b00-114">Несмотря на то, что Defender для конечной точки поддерживает вовсю различные конечные точки и средства, эта статья не охватывает их.</span><span class="sxs-lookup"><span data-stu-id="42b00-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="42b00-115">Сведения об общей онбордации с помощью других поддерживаемых средств развертывания и методов см. в [обзоре onboarding.](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="42b00-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>



<span data-ttu-id="42b00-116">В этом разделе данная тема направляет пользователей в:</span><span class="sxs-lookup"><span data-stu-id="42b00-116">This topic guides users in:</span></span>
- <span data-ttu-id="42b00-117">Шаг 1. Привнося устройства Windows в службу</span><span class="sxs-lookup"><span data-stu-id="42b00-117">Step 1: Onboarding Windows devices to the service</span></span> 
- <span data-ttu-id="42b00-118">Шаг 2. Настройка функций Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="42b00-118">Step 2: Configuring Defender for Endpoint capabilities</span></span>

<span data-ttu-id="42b00-119">В этом руководстве по бортовой настройке вы сможете пройти следующие основные действия, которые необходимо предпринять при использовании Microsoft Endpoint Configuration Manager:</span><span class="sxs-lookup"><span data-stu-id="42b00-119">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Configuration Manager:</span></span>
- <span data-ttu-id="42b00-120">**Создание коллекции в Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="42b00-120">**Creating a collection in Microsoft Endpoint Configuration Manager**</span></span>
- <span data-ttu-id="42b00-121">**Настройка возможностей Microsoft Defender для конечных точек с помощью Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="42b00-121">**Configuring Microsoft Defender for Endpoint capabilities using Microsoft Endpoint Configuration Manager**</span></span>

>[!NOTE]
><span data-ttu-id="42b00-122">В этом примере развертывание охватывается только устройствами Windows.</span><span class="sxs-lookup"><span data-stu-id="42b00-122">Only Windows devices are covered in this example deployment.</span></span> 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="42b00-123">Шаг 1. На борту устройств Windows с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="42b00-123">Step 1: Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>

### <a name="collection-creation"></a><span data-ttu-id="42b00-124">Создание коллекции</span><span class="sxs-lookup"><span data-stu-id="42b00-124">Collection creation</span></span>
<span data-ttu-id="42b00-125">На бортовых устройствах Windows 10 с помощью Microsoft Endpoint Configuration Manager развертывание может быть ориентировано на существующую коллекцию, а для тестирования может быть создана новая коллекция.</span><span class="sxs-lookup"><span data-stu-id="42b00-125">To onboard Windows 10 devices with Microsoft Endpoint Configuration Manager, the deployment can target an existing collection or a new collection can be created for testing.</span></span> 

<span data-ttu-id="42b00-126">При использовании таких средств, как групповой политики или ручного метода, в системе не устанавливается агент.</span><span class="sxs-lookup"><span data-stu-id="42b00-126">Onboarding using tools such as Group policy or manual method does not install any agent on the system.</span></span> 

<span data-ttu-id="42b00-127">В консоли Microsoft Endpoint Configuration Manager процесс вставки будет настроен как часть параметров соответствия требованиям в консоли.</span><span class="sxs-lookup"><span data-stu-id="42b00-127">Within the Microsoft Endpoint Configuration Manager console the onboarding process will be configured as part of the compliance settings within the console.</span></span>

<span data-ttu-id="42b00-128">Любая система, которая получает эту необходимую конфигурацию, будет поддерживать эту конфигурацию до тех пор, пока клиент Configuration Manager продолжает получать эту политику из точки управления.</span><span class="sxs-lookup"><span data-stu-id="42b00-128">Any system that receives this required configuration will maintain that configuration for as long as the Configuration Manager client continues to receive this policy from the management point.</span></span> 

<span data-ttu-id="42b00-129">Следуйте ниже шагам к конечным точкам на борту с помощью Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="42b00-129">Follow the steps below to onboard endpoints using Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="42b00-130">В консоли Microsoft Endpoint Configuration Manager перейдите к **коллекциям устройств Assets и \> Compliance Overview Device \> Collections.**</span><span class="sxs-lookup"><span data-stu-id="42b00-130">In Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Device Collections**.</span></span>            

    ![Изображение мастера конфигурации конечных точек Майкрософт1](images/configmgr-device-collections.png)

2. <span data-ttu-id="42b00-132">Щелкните **правой кнопкой мыши коллекцию устройств** и выберите Создать **коллекцию устройств.**</span><span class="sxs-lookup"><span data-stu-id="42b00-132">Right Click **Device Collection** and select **Create Device Collection**.</span></span>

    ![Изображение мастера конфигурации конечных точек Майкрософт2](images/configmgr-create-device-collection.png)

3. <span data-ttu-id="42b00-134">Предоставление имени **и** **ограничение коллекции**, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="42b00-134">Provide a **Name** and **Limiting Collection**, then select **Next**.</span></span>

    ![Изображение мастера конфигурации конечных точек Майкрософт3](images/configmgr-limiting-collection.png)

4. <span data-ttu-id="42b00-136">Выберите **правило Добавить** и выберите правило **запроса**.</span><span class="sxs-lookup"><span data-stu-id="42b00-136">Select **Add Rule** and choose **Query Rule**.</span></span>

    ![Изображение мастера конфигурации конечных точек Майкрософт4](images/configmgr-query-rule.png)

5.  <span data-ttu-id="42b00-138">Нажмите **кнопку Далее** по **мастеру прямого членства** и нажмите кнопку **Изменить заявление запроса**.</span><span class="sxs-lookup"><span data-stu-id="42b00-138">Click **Next** on the **Direct Membership Wizard** and click on **Edit Query Statement**.</span></span>

     ![Изображение мастера конфигурации конечных точек Майкрософт5](images/configmgr-direct-membership.png)

6. <span data-ttu-id="42b00-140">Выберите **Критерии** и выберите значок звезды.</span><span class="sxs-lookup"><span data-stu-id="42b00-140">Select **Criteria** and then choose the star icon.</span></span>

     ![Изображение мастера конфигурации конечных точек Майкрософт6](images/configmgr-criteria.png)

7. <span data-ttu-id="42b00-142">Сохраняйте тип критерия как простое **значение,**  выберите, где в качестве операционной системы **—** номер сборки, оператор больше или равен и значение **14393** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="42b00-142">Keep criterion type as **simple value**, choose where as **Operating System - build number**, operator as **is greater than or equal to** and value **14393** and click on **OK**.</span></span>

    ![Изображение мастера конфигурации конечных точек Майкрософт7](images/configmgr-simple-value.png)

8. <span data-ttu-id="42b00-144">Выберите **Далее** и **закрой**.</span><span class="sxs-lookup"><span data-stu-id="42b00-144">Select **Next** and **Close**.</span></span>

    ![Изображение мастера конфигурации конечных точек Майкрософт8](images/configmgr-membership-rules.png)

9. <span data-ttu-id="42b00-146">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="42b00-146">Select **Next**.</span></span>

    ![Изображение мастера конфигурации конечных точек Майкрософт9](images/configmgr-confirm.png)


<span data-ttu-id="42b00-148">После выполнения этой задачи у вас теперь есть коллекция устройств со всеми конечными точками Windows 10 в среде.</span><span class="sxs-lookup"><span data-stu-id="42b00-148">After completing this task, you now have a device collection with all the Windows 10 endpoints in the environment.</span></span> 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="42b00-149">Шаг 2. Настройка microsoft Defender для возможностей конечных точек</span><span class="sxs-lookup"><span data-stu-id="42b00-149">Step 2: Configure Microsoft Defender for Endpoint capabilities</span></span> 
<span data-ttu-id="42b00-150">В этом разделе приводится руководство по настройке следующих возможностей с помощью Microsoft Endpoint Configuration Manager на устройствах Windows:</span><span class="sxs-lookup"><span data-stu-id="42b00-150">This section guides you in configuring the following capabilities using Microsoft Endpoint Configuration Manager on Windows devices:</span></span>

- [<span data-ttu-id="42b00-151">**Обнаружение и устранение угроз на конечных точках**</span><span class="sxs-lookup"><span data-stu-id="42b00-151">**Endpoint detection and response**</span></span>](#endpoint-detection-and-response)
- [<span data-ttu-id="42b00-152">**Защита следующего поколения**</span><span class="sxs-lookup"><span data-stu-id="42b00-152">**Next-generation protection**</span></span>](#next-generation-protection)
- [<span data-ttu-id="42b00-153">**Сокращение направлений атак**</span><span class="sxs-lookup"><span data-stu-id="42b00-153">**Attack surface reduction**</span></span>](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a><span data-ttu-id="42b00-154">Обнаружение и устранение угроз на конечных точках</span><span class="sxs-lookup"><span data-stu-id="42b00-154">Endpoint detection and response</span></span>
#### <a name="windows-10"></a><span data-ttu-id="42b00-155">Windows 10</span><span class="sxs-lookup"><span data-stu-id="42b00-155">Windows 10</span></span>
<span data-ttu-id="42b00-156">В центре безопасности Microsoft Defender можно скачать политику ".onboarding", которая может быть использована для создания политики в system Center Configuration Manager и развертывания этой политики на устройствах Windows 10.</span><span class="sxs-lookup"><span data-stu-id="42b00-156">From within the Microsoft Defender Security Center it is possible to download the '.onboarding' policy that can be used to create the policy in System Center Configuration Manager and deploy that policy to Windows 10 devices.</span></span>

1. <span data-ttu-id="42b00-157">На портале Центра безопасности Защитника Майкрософт выберите [параметры и затем входящего](https://securitycenter.windows.com/preferences2/onboarding)в него.</span><span class="sxs-lookup"><span data-stu-id="42b00-157">From a Microsoft Defender Security Center Portal, select [Settings and then Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span></span>



2. <span data-ttu-id="42b00-158">В методе Развертывания выберите поддерживаемую версию **Microsoft Endpoint Configuration Manager.**</span><span class="sxs-lookup"><span data-stu-id="42b00-158">Under Deployment method select the supported version of **Microsoft Endpoint Configuration Manager**.</span></span>

    ![Изображение мастера бортовой точки Microsoft Defender для конечной точки10](images/mdatp-onboarding-wizard.png)

3. <span data-ttu-id="42b00-160">Выберите **пакет Загрузка**.</span><span class="sxs-lookup"><span data-stu-id="42b00-160">Select **Download package**.</span></span>

    ![Изображение мастера бортовой точки Microsoft Defender для конечной точки11](images/mdatp-download-package.png)

4. <span data-ttu-id="42b00-162">Сохраните пакет в доступном расположении.</span><span class="sxs-lookup"><span data-stu-id="42b00-162">Save the package to an accessible location.</span></span>
5. <span data-ttu-id="42b00-163">В Microsoft Endpoint Configuration Manager перейдите к: Assets and Compliance > Обзор > защиты конечных точек > **политики ATP защитника Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="42b00-163">In  Microsoft Endpoint Configuration Manager, navigate to: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span></span>

6. <span data-ttu-id="42b00-164">Щелкните правой **кнопкой мыши политики ATP Защитника Майкрософт** и выберите **Создать политику ATP защитника Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="42b00-164">Right-click **Microsoft Defender ATP Policies** and select **Create Microsoft Defender ATP Policy**.</span></span>

    ![Изображение мастера конфигурации конечной точки Майкрософт12](images/configmgr-create-policy.png)

7. <span data-ttu-id="42b00-166">Введите имя и описание, убедитесь, что выбрана **onboarding,** а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="42b00-166">Enter the name and description, verify **Onboarding** is selected, then select **Next**.</span></span>

    ![Изображение мастера конфигурации конечных точек Майкрософт13](images/configmgr-policy-name.png)


8. <span data-ttu-id="42b00-168">Нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="42b00-168">Click **Browse**.</span></span>

9. <span data-ttu-id="42b00-169">Перейдите к расположению скачаного файла на шаге 4 выше.</span><span class="sxs-lookup"><span data-stu-id="42b00-169">Navigate to the location of the downloaded file from step 4 above.</span></span>

10. <span data-ttu-id="42b00-170">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="42b00-170">Click **Next**.</span></span>
11. <span data-ttu-id="42b00-171">Настройка агента с соответствующими примерами **(None** or **All file types).**</span><span class="sxs-lookup"><span data-stu-id="42b00-171">Configure the Agent with the appropriate samples (**None** or **All file types**).</span></span>

    ![Изображение параметров конфигурации1](images/configmgr-config-settings.png)

12. <span data-ttu-id="42b00-173">Выберите соответствующую телеметрию **(обычная или** **ускоренная),** а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="42b00-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span></span>

    ![Изображение параметров конфигурации2](images/configmgr-telemetry.png)

14. <span data-ttu-id="42b00-175">Проверьте конфигурацию, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="42b00-175">Verify the configuration, then click **Next**.</span></span>

     ![Изображение параметров конфигурации3](images/configmgr-verify-configuration.png)

15. <span data-ttu-id="42b00-177">Нажмите **кнопку Закрыть,** когда мастер завершится.</span><span class="sxs-lookup"><span data-stu-id="42b00-177">Click **Close** when the Wizard completes.</span></span>

16.  <span data-ttu-id="42b00-178">В консоли Microsoft Endpoint Configuration Manager щелкните правой кнопкой мыши политику Defender для конечных точек, созданную только что, и выберите **Развертывание.**</span><span class="sxs-lookup"><span data-stu-id="42b00-178">In the Microsoft Endpoint Configuration Manager console, right-click the Defender for Endpoint policy you just created and select **Deploy**.</span></span>

     ![Изображение параметров конфигурации4](images/configmgr-deploy.png)

17. <span data-ttu-id="42b00-180">На правой панели выберите ранее созданную коллекцию и нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="42b00-180">On the right panel, select the previously created collection and click **OK**.</span></span>

    ![Изображение параметров конфигурации5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a><span data-ttu-id="42b00-182">Предыдущие версии Windows Client (Windows 7 и Windows 8.1)</span><span class="sxs-lookup"><span data-stu-id="42b00-182">Previous versions of Windows Client (Windows 7 and Windows 8.1)</span></span>
<span data-ttu-id="42b00-183">Следуйте ниже шагам, чтобы определить ИД защитника для конечного рабочего пространства и ключ рабочего пространства, которые потребуются для вовсю предыдущих версий Windows.</span><span class="sxs-lookup"><span data-stu-id="42b00-183">Follow the steps below to identify the Defender for Endpoint Workspace ID and Workspace Key, that will be required for the onboarding of previous versions of Windows.</span></span>

1. <span data-ttu-id="42b00-184">На портале Центра безопасности Защитника Майкрософт выберите параметры > **onboarding.**</span><span class="sxs-lookup"><span data-stu-id="42b00-184">From a Microsoft Defender Security Center Portal, select **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="42b00-185">В операционной системе выберите **Windows 7 SP1 и 8.1**.</span><span class="sxs-lookup"><span data-stu-id="42b00-185">Under operating system choose **Windows 7 SP1 and 8.1**.</span></span>

3. <span data-ttu-id="42b00-186">**Скопируйте ID рабочего пространства и** **клавишу Рабочей области и** сохраните их.</span><span class="sxs-lookup"><span data-stu-id="42b00-186">Copy the **Workspace ID** and **Workspace Key** and save them.</span></span> <span data-ttu-id="42b00-187">Они будут использоваться позже в процессе.</span><span class="sxs-lookup"><span data-stu-id="42b00-187">They will be used later in the process.</span></span>

    ![Изображение бортового](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. <span data-ttu-id="42b00-189">Установка агента мониторинга Майкрософт (MMA).</span><span class="sxs-lookup"><span data-stu-id="42b00-189">Install the Microsoft Monitoring Agent (MMA).</span></span> <br>
    <span data-ttu-id="42b00-190">MMA в настоящее время (по данным на январь 2019 г.) поддерживается в следующих операционных системах Windows:</span><span class="sxs-lookup"><span data-stu-id="42b00-190">MMA is currently (as of January 2019) supported on the following Windows Operating Systems:</span></span>

    -   <span data-ttu-id="42b00-191">Сервер skUs: Windows Server 2008 SP1 или Newer</span><span class="sxs-lookup"><span data-stu-id="42b00-191">Server SKUs: Windows Server 2008 SP1 or Newer</span></span>

    -   <span data-ttu-id="42b00-192">Клиентские skUs: Windows 7 SP1 и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="42b00-192">Client SKUs: Windows 7 SP1 and later</span></span>

    <span data-ttu-id="42b00-193">Агент MMA должен быть установлен на устройствах Windows.</span><span class="sxs-lookup"><span data-stu-id="42b00-193">The MMA agent will need to be installed on Windows devices.</span></span> <span data-ttu-id="42b00-194">Чтобы установить агента, некоторым системам [](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) необходимо скачать обновление для работы с клиентами и диагностическую телеметрию для сбора данных с помощью MMA.</span><span class="sxs-lookup"><span data-stu-id="42b00-194">To install the agent, some systems will need to download the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) in order to collect the data with MMA.</span></span> <span data-ttu-id="42b00-195">Эти системные версии включают, но не могут ограничиваться:</span><span class="sxs-lookup"><span data-stu-id="42b00-195">These system versions include but may not be limited to:</span></span>

    -   <span data-ttu-id="42b00-196">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="42b00-196">Windows 8.1</span></span>

    -   <span data-ttu-id="42b00-197">Windows 7</span><span class="sxs-lookup"><span data-stu-id="42b00-197">Windows 7</span></span>

    -   <span data-ttu-id="42b00-198">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="42b00-198">Windows Server 2016</span></span>

    -   <span data-ttu-id="42b00-199">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="42b00-199">Windows Server 2012 R2</span></span>

    -   <span data-ttu-id="42b00-200">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="42b00-200">Windows Server 2008 R2</span></span>

    <span data-ttu-id="42b00-201">В частности, для Windows 7 SP1 необходимо установить следующие исправления:</span><span class="sxs-lookup"><span data-stu-id="42b00-201">Specifically, for Windows 7 SP1, the following patches must be installed:</span></span>

    -   <span data-ttu-id="42b00-202">Установка [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="42b00-202">Install [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>

    -   <span data-ttu-id="42b00-203">Установка платформа .NET Framework [4.5](https://www.microsoft.com/download/details.aspx?id=30653) (или более **поздней)** или 
         [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span><span class="sxs-lookup"><span data-stu-id="42b00-203">Install either [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) **or**
        [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span></span>
        <span data-ttu-id="42b00-204">Не устанавливайте обе системы в одной и той же системе.</span><span class="sxs-lookup"><span data-stu-id="42b00-204">Do not install both on the same system.</span></span>

5. <span data-ttu-id="42b00-205">Если вы используете прокси для подключения к Интернету, см. раздел Настройка параметров прокси.</span><span class="sxs-lookup"><span data-stu-id="42b00-205">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="42b00-206">После завершения работы в течение часа на портале должны быть понастройки конечных точек.</span><span class="sxs-lookup"><span data-stu-id="42b00-206">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="42b00-207">Защита нового поколения</span><span class="sxs-lookup"><span data-stu-id="42b00-207">Next generation protection</span></span> 
<span data-ttu-id="42b00-208">Антивирусная программа в Microsoft Defender — это встроенное антивредоносное решение, которое предоставляет защиту нового поколения для настольных компьютеров, портативных компьютеров и серверов.</span><span class="sxs-lookup"><span data-stu-id="42b00-208">Microsoft Defender Antivirus is a built-in antimalware solution that provides next generation protection for desktops, portable computers, and servers.</span></span>

1. <span data-ttu-id="42b00-209">В консоли Microsoft Endpoint Configuration Manager перейдите к службам защиты от конечной точки и обзору соответствия требованиям, а также выберите **Политику создания антимарактерной политики.** **\> \> \>**</span><span class="sxs-lookup"><span data-stu-id="42b00-209">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** and choose **Create Antimalware Policy**.</span></span>

    ![Изображение политики противомалярийных программ](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. <span data-ttu-id="42b00-211">Выберите запланированные проверки, параметры сканирования, действия по умолчанию, защита в режиме реального **времени,** параметры исключения, расширенные, переопределения угрозы, облачные службы защиты и обновления аналитики безопасности и выберите **ОК**.        </span><span class="sxs-lookup"><span data-stu-id="42b00-211">Select **Scheduled scans**, **Scan settings**, **Default actions**, **Real-time protection**, **Exclusion settings**, **Advanced**, **Threat overrides**, **Cloud Protection Service** and **Security intelligence   updates** and choose **OK**.</span></span>

    ![Изображение области защиты следующего поколения1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    <span data-ttu-id="42b00-213">В определенных отраслях или некоторых отдельных корпоративных клиентах могут возникнуть определенные потребности в настройке антивируса.</span><span class="sxs-lookup"><span data-stu-id="42b00-213">In certain industries or some select enterprise customers might have specific needs on how Antivirus is configured.</span></span>

  
    [<span data-ttu-id="42b00-214">Быстрое сканирование по сравнению с полным сканированием и пользовательским сканированием</span><span class="sxs-lookup"><span data-stu-id="42b00-214">Quick scan versus full scan and custom scan</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    <span data-ttu-id="42b00-215">Дополнительные сведения см. в [материале Windows Security configuration framework](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span><span class="sxs-lookup"><span data-stu-id="42b00-215">For more details, see [Windows Security configuration framework](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span></span>
  
    ![Изображение области защиты следующего поколения2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Изображение области защиты следующего поколения3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Изображение области защиты следующего поколения4](images/a28afc02c1940d5220b233640364970c.png)

    ![Изображение области защиты следующего поколения5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Изображение области защиты следующего поколения6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Изображение области защиты следующего поколения7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Изображение области защиты следующего поколения8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Изображение области защиты следующего поколения9](images/3876ca687391bfc0ce215d221c683970.png)

3. <span data-ttu-id="42b00-224">Щелкните правой кнопкой мыши по недавно созданной политике антивирусного обеспечения и выберите **Развертывание.**</span><span class="sxs-lookup"><span data-stu-id="42b00-224">Right-click on the newly created antimalware policy and select **Deploy**.</span></span>

    ![Изображение области защиты следующего поколения10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. <span data-ttu-id="42b00-226">Найдите новую политику противомалярийных программ в вашей коллекции Windows 10 и нажмите **кнопку ОК.**</span><span class="sxs-lookup"><span data-stu-id="42b00-226">Target the new antimalware policy to your Windows 10 collection and click **OK**.</span></span>

     ![Изображение области защиты следующего поколения11](images/configmgr-select-collection.png)

<span data-ttu-id="42b00-228">После выполнения этой задачи вы успешно настроили Защитник Windows антивируса.</span><span class="sxs-lookup"><span data-stu-id="42b00-228">After completing this task, you now have successfully configured Windows Defender Antivirus.</span></span>

### <a name="attack-surface-reduction"></a><span data-ttu-id="42b00-229">Сокращение направлений атак</span><span class="sxs-lookup"><span data-stu-id="42b00-229">Attack surface reduction</span></span>
<span data-ttu-id="42b00-230">Столб сокращения поверхности атаки Defender для конечной точки включает набор функций, доступный в статье Exploit Guard.</span><span class="sxs-lookup"><span data-stu-id="42b00-230">The attack surface reduction pillar of Defender for Endpoint includes the feature set that is available under Exploit Guard.</span></span> <span data-ttu-id="42b00-231">Правила уменьшения поверхности атаки, управляемый доступ к папкам, защита сети и защита от эксплойтов.</span><span class="sxs-lookup"><span data-stu-id="42b00-231">Attack surface reduction (ASR) rules, Controlled Folder Access, Network Protection and Exploit Protection.</span></span> 

<span data-ttu-id="42b00-232">Все эти функции обеспечивают режим аудита и режим блокировки.</span><span class="sxs-lookup"><span data-stu-id="42b00-232">All these features provide an audit mode and a block mode.</span></span> <span data-ttu-id="42b00-233">В режиме аудита не влияет на конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="42b00-233">In audit mode there is no end-user impact.</span></span> <span data-ttu-id="42b00-234">Все, что он делает, это собирает дополнительную телеметрию и делает ее доступной в Центре безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="42b00-234">All it does is collect additional telemetry and make it available in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="42b00-235">Цель развертывания — пошаговые перемещения элементов управления безопасностью в режим блокировки.</span><span class="sxs-lookup"><span data-stu-id="42b00-235">The goal with a deployment is to step-by-step move security controls into block mode.</span></span>

<span data-ttu-id="42b00-236">Чтобы установить правила ASR в режиме аудита:</span><span class="sxs-lookup"><span data-stu-id="42b00-236">To set ASR rules in Audit mode:</span></span>

1. <span data-ttu-id="42b00-237">В консоли Microsoft Endpoint Configuration Manager перейдите в службу защиты конечных точек и обзор соответствия требованиям Защитник Windows **\> Exploit Guard \> \> и** выберите Политику защиты от **эксплуатации.**</span><span class="sxs-lookup"><span data-stu-id="42b00-237">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

   ![Изображение консоли Microsoft Endpoint Configuration Manager0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  <span data-ttu-id="42b00-239">Выберите **уменьшение поверхности атаки.**</span><span class="sxs-lookup"><span data-stu-id="42b00-239">Select **Attack Surface Reduction**.</span></span>
   

3. <span data-ttu-id="42b00-240">Установите правила **аудита и** нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="42b00-240">Set rules to **Audit** and click **Next**.</span></span>


    ![Изображение консоли Microsoft Endpoint Configuration Manager1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. <span data-ttu-id="42b00-242">Подтвердит новую политику Exploit Guard, нажав кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="42b00-242">Confirm the new Exploit Guard policy by clicking on **Next**.</span></span>

    ![Изображение консоли Microsoft Endpoint Configuration Manager2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. <span data-ttu-id="42b00-244">После создания политики нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="42b00-244">Once the policy is created click **Close**.</span></span>

    ![Изображение консоли Microsoft Endpoint Configuration Manager3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Изображение консоли Microsoft Endpoint Manager1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  <span data-ttu-id="42b00-247">Щелкните правой кнопкой мыши по вновь созданной политике и выберите **Развертывание.**</span><span class="sxs-lookup"><span data-stu-id="42b00-247">Right-click on the newly created policy and choose **Deploy**.</span></span>
    
    ![Изображение консоли Microsoft Endpoint Configuration Manager4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="42b00-249">Нацелить политику на недавно созданную коллекцию Windows 10 и нажмите **кнопку ОК.**</span><span class="sxs-lookup"><span data-stu-id="42b00-249">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Изображение консоли Microsoft Endpoint Configuration Manager5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="42b00-251">После выполнения этой задачи вы успешно настроили правила ASR в режиме аудита.</span><span class="sxs-lookup"><span data-stu-id="42b00-251">After completing this task, you now have successfully configured ASR rules in audit mode.</span></span>  
  
<span data-ttu-id="42b00-252">Ниже приведены дополнительные действия, чтобы убедиться, правильно ли правила ASR применяются к конечным точкам.</span><span class="sxs-lookup"><span data-stu-id="42b00-252">Below are additional steps to verify whether ASR rules are correctly applied to endpoints.</span></span> <span data-ttu-id="42b00-253">(Это может занять несколько минут)</span><span class="sxs-lookup"><span data-stu-id="42b00-253">(This may take few minutes)</span></span>


1. <span data-ttu-id="42b00-254">Из веб-браузера перейдите на <https://securitycenter.windows.com> .</span><span class="sxs-lookup"><span data-stu-id="42b00-254">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

2.  <span data-ttu-id="42b00-255">Выберите **управление конфигурацией** из левого бокового меню.</span><span class="sxs-lookup"><span data-stu-id="42b00-255">Select **Configuration management** from left side menu.</span></span>

3. <span data-ttu-id="42b00-256">Нажмите **кнопку Перейти к управлению поверхностью** атаки в панели управления поверхностью атаки.</span><span class="sxs-lookup"><span data-stu-id="42b00-256">Click **Go to attack surface management** in the Attack surface management panel.</span></span> 
    
    ![Изображение управления поверхностью атаки](images/security-center-attack-surface-mgnt-tile.png)

4. <span data-ttu-id="42b00-258">Щелкните **вкладку Configuration** в отчетах о снижении поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="42b00-258">Click **Configuration** tab in Attack surface reduction rules reports.</span></span> <span data-ttu-id="42b00-259">В нем показан обзор конфигурации правил ASR и состояние правил ASR на каждом устройстве.</span><span class="sxs-lookup"><span data-stu-id="42b00-259">It shows ASR rules configuration overview and ASR rules status on each devices.</span></span>

    ![Скриншот отчетов о правилах уменьшения поверхности атаки1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. <span data-ttu-id="42b00-261">Щелкните каждое устройство, отображающее сведения о конфигурации правил ASR.</span><span class="sxs-lookup"><span data-stu-id="42b00-261">Click each device shows configuration details of ASR rules.</span></span>

    ![Снимок экрана отчетов о снижении поверхности атаки2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

<span data-ttu-id="42b00-263">Дополнительные сведения см. в материале Оптимизируйте развертывание и обнаружение правил [ASR.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)</span><span class="sxs-lookup"><span data-stu-id="42b00-263">See [Optimize ASR rule deployment and detections](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   for more details.</span></span>  


#### <a name="set-network-protection-rules-in-audit-mode"></a><span data-ttu-id="42b00-264">Установите правила защиты сети в режиме аудита:</span><span class="sxs-lookup"><span data-stu-id="42b00-264">Set Network Protection rules in Audit mode:</span></span>
1. <span data-ttu-id="42b00-265">В консоли Microsoft Endpoint Configuration Manager перейдите в службу защиты конечных точек и обзор соответствия требованиям Защитник Windows **\> Exploit Guard \> \> и** выберите Политику защиты от **эксплуатации.**</span><span class="sxs-lookup"><span data-stu-id="42b00-265">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and  Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![A screenshot System Center Configuration Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="42b00-267">Выберите **защиту сети.**</span><span class="sxs-lookup"><span data-stu-id="42b00-267">Select **Network protection**.</span></span>

3. <span data-ttu-id="42b00-268">Установите параметр Аудит **и нажмите** кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="42b00-268">Set the setting to **Audit** and click **Next**.</span></span> 

    ![Скриншот System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. <span data-ttu-id="42b00-270">Подтвердит новую политику защиты эксплойтов, нажав **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="42b00-270">Confirm the new Exploit Guard Policy by clicking **Next**.</span></span>
    
    ![Снимок экрана Exploit GUard policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="42b00-272">После создания политики нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="42b00-272">Once the policy is created click on **Close**.</span></span>

    ![Снимок экрана Exploit GUard policy2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="42b00-274">Щелкните правой кнопкой мыши по вновь созданной политике и выберите **Развертывание.**</span><span class="sxs-lookup"><span data-stu-id="42b00-274">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Снимок экрана Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="42b00-276">Выберите политику в недавно созданной коллекции Windows 10 и выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="42b00-276">Select the policy to the newly created Windows 10 collection and choose **OK**.</span></span>

    ![Снимок экрана Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



<span data-ttu-id="42b00-278">После выполнения этой задачи успешно настроена защита сети в режиме аудита.</span><span class="sxs-lookup"><span data-stu-id="42b00-278">After completing this task, you now have successfully configured Network Protection in audit mode.</span></span>

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a><span data-ttu-id="42b00-279">Настройка правил доступа к управляемым папкам в режиме аудита:</span><span class="sxs-lookup"><span data-stu-id="42b00-279">To set Controlled Folder Access rules in Audit mode:</span></span>

1. <span data-ttu-id="42b00-280">В консоли Microsoft Endpoint Configuration Manager перейдите в службу защиты конечных точек и обзор соответствия требованиям Защитник Windows **\> Exploit Guard \> \> и** выберите Политику защиты от **эксплуатации.**</span><span class="sxs-lookup"><span data-stu-id="42b00-280">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Снимок экрана Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="42b00-282">Выберите **управляемый доступ к папке.**</span><span class="sxs-lookup"><span data-stu-id="42b00-282">Select **Controlled folder access**.</span></span>
    
3. <span data-ttu-id="42b00-283">Установите конфигурацию для **аудита и** нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="42b00-283">Set the configuration to **Audit** and click **Next**.</span></span>

    ![Снимок экрана microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. <span data-ttu-id="42b00-285">Подтвердит новую политику защиты эксплойтов, нажав кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="42b00-285">Confirm the new Exploit Guard Policy by clicking on **Next**.</span></span>

    ![Снимок экрана Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="42b00-287">После создания политики нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="42b00-287">Once the policy is created click on **Close**.</span></span>

    ![Снимок экрана microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="42b00-289">Щелкните правой кнопкой мыши по вновь созданной политике и выберите **Развертывание.**</span><span class="sxs-lookup"><span data-stu-id="42b00-289">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Снимок экрана Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  <span data-ttu-id="42b00-291">Нацелить политику на недавно созданную коллекцию Windows 10 и нажмите **кнопку ОК.**</span><span class="sxs-lookup"><span data-stu-id="42b00-291">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Снимок экрана Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="42b00-293">Теперь вы успешно настраивали управляемый доступ к папкам в режиме аудита.</span><span class="sxs-lookup"><span data-stu-id="42b00-293">You have now successfully configured Controlled folder access in audit mode.</span></span>

## <a name="related-topic"></a><span data-ttu-id="42b00-294">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="42b00-294">Related topic</span></span>
- [<span data-ttu-id="42b00-295">Onboarding using Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="42b00-295">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
