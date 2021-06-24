---
title: На борту Windows 10 в Microsoft Defender для конечной точки с помощью групповой политики
description: Используйте групповую политику для развертывания пакета конфигурации на Windows 10 устройствах, чтобы они были размещены в службе.
keywords: настройка устройств с помощью групповой политики, управления устройствами, настройка Microsoft Defender для устройств конечных точек, на борту устройств Microsoft Defender для конечных точек, групповой политики
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 80794a9d5e4da0d2da74fc714ffd1e0ceab34c8f
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105690"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="5781e-104">Onboard Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="5781e-104">Onboard Windows 10 devices using Group Policy</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5781e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5781e-105">**Applies to:**</span></span>

- <span data-ttu-id="5781e-106">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="5781e-106">Group Policy</span></span>
- [<span data-ttu-id="5781e-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5781e-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5781e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5781e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5781e-109">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="5781e-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5781e-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="5781e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="5781e-111">Чтобы использовать обновления групповой политики (GP) для развертывания пакета, необходимо быть на Windows Server 2008 R2 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="5781e-111">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>
> 
> <span data-ttu-id="5781e-112">Для Windows Server 2019 может потребоваться заменить NT AUTHORITY\Well-Known-System-Account на NT AUTHORITY\SYSTEM XML-файла, который создается в предпочтениях групповой политики.</span><span class="sxs-lookup"><span data-stu-id="5781e-112">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="5781e-113">Подключение устройств с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="5781e-113">Onboard devices using Group Policy</span></span>

<span data-ttu-id="5781e-114">[![Изображение PDF, показывающая различные пути развертывания](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5781e-114">[![Image of the PDF showing the various deployment paths](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span></span>

<span data-ttu-id="5781e-115">Ознакомьтесь с [PDF или Visio,](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) чтобы увидеть различные пути развертывания Defender для конечной точки. [](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="5781e-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 



1. <span data-ttu-id="5781e-116">Откройте пакет конфигурации GP .zip *(WindowsDefenderATPOnboardingPackage.zip),* который вы скачали из мастера бортового обслуживания.</span><span class="sxs-lookup"><span data-stu-id="5781e-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="5781e-117">Вы также можете получить пакет из [Центр безопасности в Microsoft Defender:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="5781e-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>
 
    1. <span data-ttu-id="5781e-118">В области навигации выберите **Параметры**  >  **onboarding**.</span><span class="sxs-lookup"><span data-stu-id="5781e-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="5781e-119">Выберите Windows 10 в качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="5781e-119">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="5781e-120">В поле **Метод развертывания** выберите **групповую политику.**</span><span class="sxs-lookup"><span data-stu-id="5781e-120">In the **Deployment method** field, select **Group policy**.</span></span>
    
    1. <span data-ttu-id="5781e-121">Нажмите **кнопку Загрузка** пакета и сохраните .zip файл.</span><span class="sxs-lookup"><span data-stu-id="5781e-121">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="5781e-122">Извлечение содержимого файла .zip в общее, только для чтения расположение, которое можно получить на устройстве.</span><span class="sxs-lookup"><span data-stu-id="5781e-122">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="5781e-123">У вас должна быть папка *OptionalParamsPolicy* и файл *WindowsDefenderATPOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="5781e-123">You should have a folder called *OptionalParamsPolicy* and the file *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="5781e-124">Откройте консоль [управления групповой](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) политикой (GPMC), щелкните правой кнопкой мыши объект групповой политики (GPO), который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5781e-124">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="5781e-125">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера,** затем **параметры**"Предпочтения", а затем **параметры панели управления.**</span><span class="sxs-lookup"><span data-stu-id="5781e-125">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="5781e-126">Щелкните правой кнопкой мыши **Запланированные задачи,** указать **на Новое,** а затем нажмите кнопку Немедленная задача **(по крайней мере Windows 7).**</span><span class="sxs-lookup"><span data-stu-id="5781e-126">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

6. <span data-ttu-id="5781e-127">В **открываемом** окне Задача перейдите на **вкладку General.** В **параметрах Безопасности** нажмите **кнопку Изменить пользователя или группу** и введите SYSTEM, а затем нажмите **кнопку Check Names** then **OK**.</span><span class="sxs-lookup"><span data-stu-id="5781e-127">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="5781e-128">NT AUTHORITY\SYSTEM отображается в качестве учетной записи пользователя, как будет работать задача.</span><span class="sxs-lookup"><span data-stu-id="5781e-128">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

7. <span data-ttu-id="5781e-129">Выберите **Выполнить, вошел** ли пользователь или нет, и проверьте поле Выполнить с **самыми** высокими привилегиями.</span><span class="sxs-lookup"><span data-stu-id="5781e-129">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

8. <span data-ttu-id="5781e-130">Перейдите на **вкладку Действия** и нажмите **кнопку New...** **Убедитесь, что программа Start** выбрана в поле **Действия.**</span><span class="sxs-lookup"><span data-stu-id="5781e-130">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="5781e-131">Введите имя файла и расположение общего *файла WindowsDefenderATPOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="5781e-131">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

9. <span data-ttu-id="5781e-132">Нажмите **кнопку ОК** и закрой все открытые окна GPMC.</span><span class="sxs-lookup"><span data-stu-id="5781e-132">Click **OK** and close any open GPMC windows.</span></span>

>[!TIP]
> <span data-ttu-id="5781e-133">После работы на устройстве можно выполнить тест обнаружения, чтобы убедиться, что устройство правильно вошел в службу.</span><span class="sxs-lookup"><span data-stu-id="5781e-133">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="5781e-134">Дополнительные сведения см. в таблице [Run a detection test on a newly onboarded Defender for Endpoint device.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="5781e-134">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>

## <a name="additional-defender-for-endpoint-configuration-settings"></a><span data-ttu-id="5781e-135">Дополнительные параметры конфигурации Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5781e-135">Additional Defender for Endpoint configuration settings</span></span>
<span data-ttu-id="5781e-136">Для каждого устройства можно указать, можно ли собирать образцы с устройства при Центр безопасности в Microsoft Defender отправки файла для глубокого анализа.</span><span class="sxs-lookup"><span data-stu-id="5781e-136">For each device, you can state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="5781e-137">Можно использовать групповую политику (GP) для настройки параметров, например параметров для общего доступа к примеру, используемого в функции глубокого анализа.</span><span class="sxs-lookup"><span data-stu-id="5781e-137">You can use Group Policy (GP) to configure settings, such as settings for the sample sharing used in the deep analysis feature.</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="5781e-138">Настройка параметров коллекции образцов</span><span class="sxs-lookup"><span data-stu-id="5781e-138">Configure sample collection settings</span></span>
1.  <span data-ttu-id="5781e-139">На устройстве управления GP скопируйте следующие файлы из пакета конфигурации:</span><span class="sxs-lookup"><span data-stu-id="5781e-139">On your GP management device, copy the following files from the configuration package:</span></span>

    - <span data-ttu-id="5781e-140">_Скопируйте AtpConfiguration.admx_ в _C: \\ Windows \\ PolicyDefinitions_</span><span class="sxs-lookup"><span data-stu-id="5781e-140">Copy _AtpConfiguration.admx_ into _C:\\Windows\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="5781e-141">_Скопируйте AtpConfiguration.adml_ в _C: \\ Windows \\ PolicyDefinitions \\ en-US_</span><span class="sxs-lookup"><span data-stu-id="5781e-141">Copy _AtpConfiguration.adml_ into _C:\\Windows\\PolicyDefinitions\\en-US_</span></span>

    <span data-ttu-id="5781e-142">Если вы используете административные шаблоны [центра хранения групповой](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)политики, скопируйте следующие файлы из пакета конфигурации:</span><span class="sxs-lookup"><span data-stu-id="5781e-142">If you are using a [Central Store for Group Policy Administrative Templates](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra), copy the following files from the configuration package:</span></span>
    
    - <span data-ttu-id="5781e-143">_Скопируйте AtpConfiguration.admx в_ _\\ \\ \<forest.root\> \\ политики SysVol \\ \<forest.root\> \\ \\ PoliciesDefinitions_</span><span class="sxs-lookup"><span data-stu-id="5781e-143">Copy _AtpConfiguration.admx_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="5781e-144">Copy _AtpConfiguration.adml_ into _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ \\ Policies PolicyDefinitions \\ en-US_</span><span class="sxs-lookup"><span data-stu-id="5781e-144">Copy _AtpConfiguration.adml_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions\\en-US_</span></span>

2.  <span data-ttu-id="5781e-145">Откройте консоль [управления групповой политикой](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), щелкните правой кнопкой мыши GPO, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5781e-145">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), right-click the GPO you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="5781e-146">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="5781e-146">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="5781e-147">Щелкните **Политики,** а затем **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="5781e-147">Click **Policies**, then **Administrative templates**.</span></span>

5.  <span data-ttu-id="5781e-148">Щелкните **Windows компоненты** и **Защитник Windows SmartScreen**.</span><span class="sxs-lookup"><span data-stu-id="5781e-148">Click **Windows components** and then **Windows Defender SmartScreen**.</span></span>

6.  <span data-ttu-id="5781e-149">Выберите, чтобы включить или отключить общий доступ к примеру с устройств.</span><span class="sxs-lookup"><span data-stu-id="5781e-149">Choose to enable or disable sample sharing from your devices.</span></span>

>[!NOTE]
> <span data-ttu-id="5781e-150">Если значение не установлено, по умолчанию необходимо включить коллекцию образцов.</span><span class="sxs-lookup"><span data-stu-id="5781e-150">If you don't set a value, the default value is to enable sample collection.</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="5781e-151">Другие рекомендуемые параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="5781e-151">Other recommended configuration settings</span></span>

### <a name="update-endpoint-protection-configuration"></a><span data-ttu-id="5781e-152">Обновление конфигурации защиты конечной точки</span><span class="sxs-lookup"><span data-stu-id="5781e-152">Update endpoint protection configuration</span></span>

<span data-ttu-id="5781e-153">После настройки сценария бортовой настройки продолжайте редактирование той же групповой политики, чтобы добавить конфигурации защиты конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5781e-153">After configuring the onboarding script, continue editing the same group policy to add endpoint protection configurations.</span></span> <span data-ttu-id="5781e-154">Выполните изменения групповой политики из системы Windows 10 или Server 2019, чтобы убедиться, что у вас есть все необходимые антивирусная программа в Microsoft Defender возможности.</span><span class="sxs-lookup"><span data-stu-id="5781e-154">Perform group policy edits from a system running Windows 10 or Server 2019 to ensure you have all of the required Microsoft Defender Antivirus capabilities.</span></span> <span data-ttu-id="5781e-155">Может потребоваться закрыть и открыть объект групповой политики для регистрации параметров конфигурации ATP Defender.</span><span class="sxs-lookup"><span data-stu-id="5781e-155">You may need to close and reopen the group policy object to register the Defender ATP configuration settings.</span></span>

<span data-ttu-id="5781e-156">Все политики находятся под `Computer Configuration\Policies\Administrative Templates` .</span><span class="sxs-lookup"><span data-stu-id="5781e-156">All policies are located under `Computer Configuration\Policies\Administrative Templates`.</span></span>

<span data-ttu-id="5781e-157">**Расположение политики:** \Windows компоненты\Защитник Windows ATP</span><span class="sxs-lookup"><span data-stu-id="5781e-157">**Policy location:** \Windows Components\Windows Defender ATP</span></span>

<span data-ttu-id="5781e-158">Политика</span><span class="sxs-lookup"><span data-stu-id="5781e-158">Policy</span></span> | <span data-ttu-id="5781e-159">Setting</span><span class="sxs-lookup"><span data-stu-id="5781e-159">Setting</span></span> 
:---|:---
<span data-ttu-id="5781e-160">Enable\Disable Sample collection</span><span class="sxs-lookup"><span data-stu-id="5781e-160">Enable\Disable Sample collection</span></span>|   <span data-ttu-id="5781e-161">Включено - "Включить коллекцию образцов на машинах" проверено</span><span class="sxs-lookup"><span data-stu-id="5781e-161">Enabled - "Enable sample collection on machines" checked</span></span>

<br/>

<span data-ttu-id="5781e-162">**Расположение политики:** \Windows компоненты\антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5781e-162">**Policy location:**  \Windows Components\Microsoft Defender Antivirus</span></span>

<span data-ttu-id="5781e-163">Политика</span><span class="sxs-lookup"><span data-stu-id="5781e-163">Policy</span></span> | <span data-ttu-id="5781e-164">Setting</span><span class="sxs-lookup"><span data-stu-id="5781e-164">Setting</span></span> 
:---|:---
<span data-ttu-id="5781e-165">Настройка обнаружения для потенциально нежелательных приложений</span><span class="sxs-lookup"><span data-stu-id="5781e-165">Configure detection for potentially unwanted applications</span></span> | <span data-ttu-id="5781e-166">Включено, блок</span><span class="sxs-lookup"><span data-stu-id="5781e-166">Enabled, Block</span></span>

<br/>

<span data-ttu-id="5781e-167">**Расположение политики:** \Windows компоненты\антивирусная программа в Microsoft Defender\MAPS</span><span class="sxs-lookup"><span data-stu-id="5781e-167">**Policy location:** \Windows Components\Microsoft Defender Antivirus\MAPS</span></span>

<span data-ttu-id="5781e-168">Политика</span><span class="sxs-lookup"><span data-stu-id="5781e-168">Policy</span></span> | <span data-ttu-id="5781e-169">Setting</span><span class="sxs-lookup"><span data-stu-id="5781e-169">Setting</span></span> 
:---|:---
<span data-ttu-id="5781e-170">Присоединяйтесь к Microsoft MAPS</span><span class="sxs-lookup"><span data-stu-id="5781e-170">Join Microsoft MAPS</span></span> | <span data-ttu-id="5781e-171">Включено, расширенные КАРТЫ</span><span class="sxs-lookup"><span data-stu-id="5781e-171">Enabled, Advanced MAPS</span></span>
<span data-ttu-id="5781e-172">Отправка образцов файлов при необходимости дополнительного анализа</span><span class="sxs-lookup"><span data-stu-id="5781e-172">Send file samples when further analysis is required</span></span> | <span data-ttu-id="5781e-173">Включено, отправка безопасных образцов</span><span class="sxs-lookup"><span data-stu-id="5781e-173">Enabled, Send safe samples</span></span>

<br/>

<span data-ttu-id="5781e-174">**Расположение политики:** \Windows компоненты\антивирусная программа в Microsoft Defender\Защита в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="5781e-174">**Policy location:** \Windows Components\Microsoft Defender Antivirus\Real-time Protection</span></span>

<span data-ttu-id="5781e-175">Политика</span><span class="sxs-lookup"><span data-stu-id="5781e-175">Policy</span></span> | <span data-ttu-id="5781e-176">Setting</span><span class="sxs-lookup"><span data-stu-id="5781e-176">Setting</span></span> 
:---|:---
<span data-ttu-id="5781e-177">Отключение защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="5781e-177">Turn off real-time protection</span></span>|<span data-ttu-id="5781e-178">Отключено</span><span class="sxs-lookup"><span data-stu-id="5781e-178">Disabled</span></span>
<span data-ttu-id="5781e-179">Включив мониторинг поведения</span><span class="sxs-lookup"><span data-stu-id="5781e-179">Turn on behavior monitoring</span></span>|<span data-ttu-id="5781e-180">Включено</span><span class="sxs-lookup"><span data-stu-id="5781e-180">Enabled</span></span>
<span data-ttu-id="5781e-181">Сканирование всех загруженных файлов и вложений</span><span class="sxs-lookup"><span data-stu-id="5781e-181">Scan all downloaded files and attachments</span></span>|<span data-ttu-id="5781e-182">Включено</span><span class="sxs-lookup"><span data-stu-id="5781e-182">Enabled</span></span>
<span data-ttu-id="5781e-183">Мониторинг активности файлов и программ на компьютере</span><span class="sxs-lookup"><span data-stu-id="5781e-183">Monitor file and program activity on your computer</span></span>|<span data-ttu-id="5781e-184">Включено</span><span class="sxs-lookup"><span data-stu-id="5781e-184">Enabled</span></span>

<br/>

<span data-ttu-id="5781e-185">**Расположение политики:** \Windows компоненты\антивирусная программа в Microsoft Defender\Scan</span><span class="sxs-lookup"><span data-stu-id="5781e-185">**Policy location:**  \Windows Components\Microsoft Defender Antivirus\Scan</span></span>

<span data-ttu-id="5781e-186">Эти параметры настраивают периодическое сканирование конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5781e-186">These settings configure periodic scans of the endpoint.</span></span> <span data-ttu-id="5781e-187">Рекомендуется выполнять еженедельное быстрое сканирование с разрешением производительности.</span><span class="sxs-lookup"><span data-stu-id="5781e-187">We recommend performing a weekly quick scan, performance permitting.</span></span>

<span data-ttu-id="5781e-188">Политика</span><span class="sxs-lookup"><span data-stu-id="5781e-188">Policy</span></span> | <span data-ttu-id="5781e-189">Setting</span><span class="sxs-lookup"><span data-stu-id="5781e-189">Setting</span></span> 
:---|:---
<span data-ttu-id="5781e-190">Проверьте последнюю информацию о безопасности вирусов и шпионских программ перед запуском запланированного сканирования</span><span class="sxs-lookup"><span data-stu-id="5781e-190">Check for the latest virus and spyware security intelligence before running a scheduled scan</span></span> |<span data-ttu-id="5781e-191">Включено</span><span class="sxs-lookup"><span data-stu-id="5781e-191">Enabled</span></span>


<br/>

<span data-ttu-id="5781e-192">**Расположение политики:** \Windows компоненты\антивирусная программа в Microsoft Defender\Exploit Guard в Microsoft Defender\Уменьшение поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="5781e-192">**Policy location:** \Windows Components\Microsoft Defender Antivirus\Microsoft Defender Exploit Guard\Attack Surface Reduction</span></span>

<span data-ttu-id="5781e-193">Получите текущий список GUID-интерфейсов уменьшения поверхности атаки из настройки правил уменьшения [поверхности атаки](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="5781e-193">Get the current list of attack surface reduction GUIDs from [Customize attack surface reduction rules](customize-attack-surface-reduction.md)</span></span>

1. <span data-ttu-id="5781e-194">Откройте политику **настройки политики уменьшения поверхности атаки.**</span><span class="sxs-lookup"><span data-stu-id="5781e-194">Open the **Configure Attack Surface Reduction** policy.</span></span>

1. <span data-ttu-id="5781e-195">Щелкните **Включено**.</span><span class="sxs-lookup"><span data-stu-id="5781e-195">Select **Enabled**.</span></span>

1. <span data-ttu-id="5781e-196">Выберите **кнопку Показать.**</span><span class="sxs-lookup"><span data-stu-id="5781e-196">Select the **Show** button.</span></span>

1. <span data-ttu-id="5781e-197">Добавьте каждый GUID в **поле Имя** значения со значением 2.</span><span class="sxs-lookup"><span data-stu-id="5781e-197">Add each GUID in the **Value Name** field with a Value of 2.</span></span>

   <span data-ttu-id="5781e-198">Это будет настроить каждый только для аудита.</span><span class="sxs-lookup"><span data-stu-id="5781e-198">This will set each up for audit only.</span></span>

   ![Изображение конфигурации уменьшения поверхности атаки](images/asr-guid.png)



<span data-ttu-id="5781e-200">Политика</span><span class="sxs-lookup"><span data-stu-id="5781e-200">Policy</span></span> | <span data-ttu-id="5781e-201">Setting</span><span class="sxs-lookup"><span data-stu-id="5781e-201">Setting</span></span> 
:---|:---
<span data-ttu-id="5781e-202">Настройка доступа к управляемой папке</span><span class="sxs-lookup"><span data-stu-id="5781e-202">Configure Controlled folder access</span></span>| <span data-ttu-id="5781e-203">Включен режим аудита</span><span class="sxs-lookup"><span data-stu-id="5781e-203">Enabled, Audit Mode</span></span>



## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="5781e-204">Offboard devices using Group Policy</span><span class="sxs-lookup"><span data-stu-id="5781e-204">Offboard devices using Group Policy</span></span>
<span data-ttu-id="5781e-205">По соображениям безопасности срок действия пакета, используемой для устройств Offboard, истекает через 30 дней после даты его загрузки.</span><span class="sxs-lookup"><span data-stu-id="5781e-205">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="5781e-206">Просроченные пакеты offboarding, отправленные на устройство, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="5781e-206">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="5781e-207">При загрузке пакета offboarding вы будете уведомлены о дате истечения срока действия пакетов и он также будет включен в имя пакета.</span><span class="sxs-lookup"><span data-stu-id="5781e-207">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="5781e-208">На одном устройстве одновременно не следует развертывать политики бортового и оффбординга, в противном случае это приведет к непредсказуемым столкновениям.</span><span class="sxs-lookup"><span data-stu-id="5781e-208">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="5781e-209">Получите пакет offboarding из [Центр безопасности в Microsoft Defender:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="5781e-209">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="5781e-210">В области навигации выберите **Параметры**  >  **Offboarding**.</span><span class="sxs-lookup"><span data-stu-id="5781e-210">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="5781e-211">Выберите Windows 10 в качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="5781e-211">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="5781e-212">В поле **Метод развертывания** выберите **групповую политику.**</span><span class="sxs-lookup"><span data-stu-id="5781e-212">In the **Deployment method** field, select **Group policy**.</span></span>

    1. <span data-ttu-id="5781e-213">Нажмите **кнопку Загрузка** пакета и сохраните .zip файл.</span><span class="sxs-lookup"><span data-stu-id="5781e-213">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="5781e-214">Извлечение содержимого файла .zip в общее, только для чтения расположение, которое можно получить на устройстве.</span><span class="sxs-lookup"><span data-stu-id="5781e-214">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="5781e-215">У вас должен быть *файл с именем WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="5781e-215">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="5781e-216">Откройте консоль [управления групповой](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) политикой (GPMC), щелкните правой кнопкой мыши объект групповой политики (GPO), который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5781e-216">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="5781e-217">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера,** затем **параметры**"Предпочтения", а затем **параметры панели управления.**</span><span class="sxs-lookup"><span data-stu-id="5781e-217">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="5781e-218">Щелкните правой кнопкой мыши **Запланированные задачи,** указать **на Новое,** а затем нажмите **кнопку Немедленное задание**.</span><span class="sxs-lookup"><span data-stu-id="5781e-218">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

6. <span data-ttu-id="5781e-219">В **открываемом** окне Задача перейдите на **вкладку General.** Выберите учетную запись локального пользователя SYSTEM (BUILTIN\SYSTEM) в **параметрах Безопасности.**</span><span class="sxs-lookup"><span data-stu-id="5781e-219">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

7. <span data-ttu-id="5781e-220">Выберите **Выполнить, вошел** ли пользователь в систему или нет, и проверьте поле **Выполнить** с самыми высокими привилегиями.</span><span class="sxs-lookup"><span data-stu-id="5781e-220">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

8. <span data-ttu-id="5781e-221">Перейдите на **вкладку Действия** и нажмите **кнопку New...**. **Убедитесь, что программа Start** выбрана в поле **Действия.**</span><span class="sxs-lookup"><span data-stu-id="5781e-221">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="5781e-222">Введите имя файла и расположение *общего WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd.*</span><span class="sxs-lookup"><span data-stu-id="5781e-222">Enter the file name and location of the shared  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

9. <span data-ttu-id="5781e-223">Нажмите **кнопку ОК** и закрой все открытые окна GPMC.</span><span class="sxs-lookup"><span data-stu-id="5781e-223">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5781e-224">Отключение приводит к тому, что устройство перестает отправлять данные датчиков на портал, но данные с устройства, включая ссылки на все оповещения, которые у него были, будут храниться до 6 месяцев.</span><span class="sxs-lookup"><span data-stu-id="5781e-224">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="5781e-225">Мониторинг конфигурации устройства</span><span class="sxs-lookup"><span data-stu-id="5781e-225">Monitor device configuration</span></span>
<span data-ttu-id="5781e-226">В групповой политике нет возможности отслеживать развертывание политик на устройствах.</span><span class="sxs-lookup"><span data-stu-id="5781e-226">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="5781e-227">Мониторинг можно сделать непосредственно на портале или с помощью различных средств развертывания.</span><span class="sxs-lookup"><span data-stu-id="5781e-227">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="5781e-228">Мониторинг устройств с помощью портала</span><span class="sxs-lookup"><span data-stu-id="5781e-228">Monitor devices using the portal</span></span>
1. <span data-ttu-id="5781e-229">Перейдите [в Центр безопасности в Microsoft Defender](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="5781e-229">Go to [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span>
2. <span data-ttu-id="5781e-230">Щелкните **список Устройств**.</span><span class="sxs-lookup"><span data-stu-id="5781e-230">Click **Devices list**.</span></span>
3. <span data-ttu-id="5781e-231">Убедитесь, что устройства отображаются.</span><span class="sxs-lookup"><span data-stu-id="5781e-231">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="5781e-232">Для начала показа устройств в списке Устройств может занять несколько **дней.**</span><span class="sxs-lookup"><span data-stu-id="5781e-232">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="5781e-233">Это включает время, необходимое для распространения политик на устройство, время, необходимое для входа пользователя, и время, необходимое для начала отчетов конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="5781e-233">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="5781e-234">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="5781e-234">Related topics</span></span>
- [<span data-ttu-id="5781e-235">На борту Windows 10 устройства с Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5781e-235">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="5781e-236">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="5781e-236">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="5781e-237">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="5781e-237">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="5781e-238">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="5781e-238">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="5781e-239">Запустите тест обнаружения на недавно висячем устройствах Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="5781e-239">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](run-detection-test.md)
- [<span data-ttu-id="5781e-240">Устранение неполадок в Microsoft Defender для проблем с бортовой точкой конечной точки</span><span class="sxs-lookup"><span data-stu-id="5781e-240">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
