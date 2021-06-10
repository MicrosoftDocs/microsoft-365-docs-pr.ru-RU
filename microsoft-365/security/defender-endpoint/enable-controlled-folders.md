---
title: Включить контролируемый доступ к папкам
keywords: Управляемый доступ к папкам, Windows 10, защитник Windows, вымогатели, защита, файлы, папки, включить, включить, использовать
description: Узнайте, как защитить важные файлы, включив доступ к управляемой папке
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 1d09eaf04999478a0cd0b4907667a522a23fb39f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841982"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="16917-104">Включить контролируемый доступ к папкам</span><span class="sxs-lookup"><span data-stu-id="16917-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="16917-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="16917-105">**Applies to:**</span></span>
- [<span data-ttu-id="16917-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="16917-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="16917-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16917-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="16917-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="16917-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="16917-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="16917-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="16917-110">[Управляемый доступ к папкам](controlled-folders.md) помогает защитить ценные данные от вредоносных приложений и угроз, таких как вымогателей.</span><span class="sxs-lookup"><span data-stu-id="16917-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="16917-111">Доступ к управляемой папке включен в Windows 10 и Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="16917-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="16917-112">Вы можете включить управляемый доступ к папкам с помощью любого из этих методов:</span><span class="sxs-lookup"><span data-stu-id="16917-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="16917-113">Безопасность Windows приложение</span><span class="sxs-lookup"><span data-stu-id="16917-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="16917-114">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="16917-114">Microsoft Intune</span></span>](#intune)
* [<span data-ttu-id="16917-115">Управление мобильными устройствами (MDM)</span><span class="sxs-lookup"><span data-stu-id="16917-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="16917-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="16917-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="16917-117">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="16917-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="16917-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="16917-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="16917-119">[Режим аудита](evaluate-controlled-folder-access.md) позволяет проверить, как эта функция будет работать (и проверять события), не влияя на нормальное использование устройства.</span><span class="sxs-lookup"><span data-stu-id="16917-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="16917-120">Параметры групповой политики, отключающие слияние списков локальных администраторов, переопределяют параметры доступа к управляемым папкам.</span><span class="sxs-lookup"><span data-stu-id="16917-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="16917-121">Кроме того, они переопределяют защищенные папки и разрешают приложения, установленные местным администратором, с помощью управляемого доступа к папкам.</span><span class="sxs-lookup"><span data-stu-id="16917-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="16917-122">Эти политики включают:</span><span class="sxs-lookup"><span data-stu-id="16917-122">These policies include:</span></span>

* <span data-ttu-id="16917-123">антивирусная программа в Microsoft Defender Настройка **поведения локального администратора для объединения списков**</span><span class="sxs-lookup"><span data-stu-id="16917-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="16917-124">System Center Endpoint Protection разрешить **пользователям добавлять исключения и переопределения**</span><span class="sxs-lookup"><span data-stu-id="16917-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="16917-125">Дополнительные сведения об отключении локального объединения списков см. в см. в twitter [Prevent или allow users to locally modify Microsoft Defender AV policy settings.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)</span><span class="sxs-lookup"><span data-stu-id="16917-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="16917-126">Безопасность Windows приложение</span><span class="sxs-lookup"><span data-stu-id="16917-126">Windows Security app</span></span>

1. <span data-ttu-id="16917-127">Откройте приложение Безопасность Windows, выбрав значок щита в панели задач.</span><span class="sxs-lookup"><span data-stu-id="16917-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="16917-128">Вы также можете искать меню пусков для **Defender**.</span><span class="sxs-lookup"><span data-stu-id="16917-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="16917-129">Выберите **плитку защиты &** вирусов (или значок щита в левой панели меню), а затем выберите защиту **вымогателей.**</span><span class="sxs-lookup"><span data-stu-id="16917-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="16917-130">Установите переключатель для **доступа к управляемой папке** **для On**.</span><span class="sxs-lookup"><span data-stu-id="16917-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="16917-131">Если управляемый доступ к папке настроен с помощью CSPs групповой политики, PowerShell или MDM, состояние изменится в приложении Безопасность Windows после перезапуска устройства.</span><span class="sxs-lookup"><span data-stu-id="16917-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="16917-132">Если функция настроена в **режиме аудита** с любым из этих средств, Безопасность Windows приложение покажет состояние **как Off**.</span><span class="sxs-lookup"><span data-stu-id="16917-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="16917-133">Если вы защищаете данные профилей пользователей, рекомендуется, чтобы профиль пользователя был на Windows установки.</span><span class="sxs-lookup"><span data-stu-id="16917-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="intune"></a><span data-ttu-id="16917-134">Intune</span><span class="sxs-lookup"><span data-stu-id="16917-134">Intune</span></span>

1. <span data-ttu-id="16917-135">Вопишитесь на портал [Azure и](https://portal.azure.com) откройте Intune.</span><span class="sxs-lookup"><span data-stu-id="16917-135">Sign in to the [Azure portal](https://portal.azure.com) and open Intune.</span></span>

2. <span data-ttu-id="16917-136">Перейдите к **профилям**  >  **конфигурации устройств**  >  **Создайте профиль**.</span><span class="sxs-lookup"><span data-stu-id="16917-136">Go to **Device configuration** > **Profiles** > **Create profile**.</span></span>

3. <span data-ttu-id="16917-137">Назови профиль, **выберите Windows 10 и более поздний и** **конечную точки защиты.**</span><span class="sxs-lookup"><span data-stu-id="16917-137">Name the profile, choose **Windows 10 and later** and **Endpoint protection**.</span></span> <br/> <span data-ttu-id="16917-138">![Создание профиля защиты конечных точек](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span><span class="sxs-lookup"><span data-stu-id="16917-138">![Create endpoint protection profile](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span></span> <br/>

4. <span data-ttu-id="16917-139">Перейдите **к настройке Защитник Windows** с  >  **управляемым** доступом к папке Exploit Guard  >    >  **Enable**.</span><span class="sxs-lookup"><span data-stu-id="16917-139">Go to **Configure** > **Windows Defender Exploit Guard** > **Controlled folder access** > **Enable**.</span></span>

5. <span data-ttu-id="16917-140">Введите путь к каждому приложению, которое имеет доступ к защищенным папкам, и путь к любой дополнительной папке, которая нуждается в защите.</span><span class="sxs-lookup"><span data-stu-id="16917-140">Type the path to each application that has access to protected folders and the path to any additional folder that needs protection.</span></span> <span data-ttu-id="16917-141">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="16917-141">Select **Add**.</span></span><br/> <span data-ttu-id="16917-142">![Включить управляемый доступ к папкам в Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span><span class="sxs-lookup"><span data-stu-id="16917-142">![Enable controlled folder access in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span></span><br/>

   > [!NOTE]
   > <span data-ttu-id="16917-143">Wilcard поддерживается для приложений, но не для папок.</span><span class="sxs-lookup"><span data-stu-id="16917-143">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="16917-144">Подмостки не защищены.</span><span class="sxs-lookup"><span data-stu-id="16917-144">Subfolders are not protected.</span></span> <span data-ttu-id="16917-145">Разрешенные приложения будут продолжать запускать события, пока они не будут перезапущены.</span><span class="sxs-lookup"><span data-stu-id="16917-145">Allowed apps will continue to trigger events until they are restarted.</span></span>

6. <span data-ttu-id="16917-146">Выберите **ОК,** чтобы сохранить каждое открытое лезвие и **создать**.</span><span class="sxs-lookup"><span data-stu-id="16917-146">Select **OK** to save each open blade and **Create**.</span></span>

7. <span data-ttu-id="16917-147">Выберите назначения **профилей,** назначьте всем **пользователям & все устройства** и **сохраните**.</span><span class="sxs-lookup"><span data-stu-id="16917-147">Select the profile **Assignments**, assign to **All Users & All Devices**, and **Save**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="16917-148">Управление мобильными устройствами (MDM)</span><span class="sxs-lookup"><span data-stu-id="16917-148">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="16917-149">Используйте [поставщик услуг конфигурации ./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) (CSP), чтобы разрешить приложениям вносить изменения в защищенные папки.</span><span class="sxs-lookup"><span data-stu-id="16917-149">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="16917-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="16917-150">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="16917-151">В Microsoft Endpoint Configuration Manager перейдите в **службу Assets and Compliance**  >  **Endpoint Protection** Защитник Windows  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="16917-151">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="16917-152">Выберите   >  **домашнее создание политики защиты от эксплойтов**.</span><span class="sxs-lookup"><span data-stu-id="16917-152">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="16917-153">Введите имя и описание, выберите доступ к управляемой **папке** и выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="16917-153">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="16917-154">Выберите блок или аудит изменений, разрешить другие приложения или добавить другие папки и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="16917-154">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="16917-155">Wilcard поддерживается для приложений, но не для папок.</span><span class="sxs-lookup"><span data-stu-id="16917-155">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="16917-156">Подмостки не защищены.</span><span class="sxs-lookup"><span data-stu-id="16917-156">Subfolders are not protected.</span></span> <span data-ttu-id="16917-157">Разрешенные приложения будут продолжать запускать события, пока они не будут перезапущены.</span><span class="sxs-lookup"><span data-stu-id="16917-157">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="16917-158">Просмотрите параметры и выберите **Далее,** чтобы создать политику.</span><span class="sxs-lookup"><span data-stu-id="16917-158">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="16917-159">После создания политики **закрой**.</span><span class="sxs-lookup"><span data-stu-id="16917-159">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="16917-160">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="16917-160">Group Policy</span></span>

1. <span data-ttu-id="16917-161">На устройстве управления групповой политикой откройте консоль управления групповой политикой [правой](https://technet.microsoft.com/library/cc731212.aspx)кнопкой мыши объект групповой политики, который необходимо настроить, и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="16917-161">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="16917-162">В **редакторе управления групповыми политиками** перейдите к **конфигурации компьютера** и выберите **Административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="16917-162">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="16917-163">Расширь дерево до **Windows компонентов > антивирусная программа в Microsoft Defender > Защитник Windows exploit Guard > управляемой папке.**</span><span class="sxs-lookup"><span data-stu-id="16917-163">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="16917-164">Дважды нажмите **кнопку Настройка управляемого доступа к папке** и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="16917-164">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="16917-165">В разделе Параметры необходимо указать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="16917-165">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="16917-166">**Включить** . Вредоносные и подозрительные приложения не смогут вносить изменения в файлы в защищенных папках.</span><span class="sxs-lookup"><span data-stu-id="16917-166">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="16917-167">Уведомление будет предоставлено в журнале Windows событий.</span><span class="sxs-lookup"><span data-stu-id="16917-167">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="16917-168">**Отключение (по умолчанию)** — функция доступа к управляемой папке не будет работать.</span><span class="sxs-lookup"><span data-stu-id="16917-168">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="16917-169">Все приложения могут вносить изменения в файлы в защищенных папках.</span><span class="sxs-lookup"><span data-stu-id="16917-169">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="16917-170">**Режим аудита** . Изменения будут разрешены, если вредоносное или подозрительное приложение пытается внести изменения в файл в защищенной папке.</span><span class="sxs-lookup"><span data-stu-id="16917-170">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="16917-171">Однако он будет записан в журнале событий Windows, где можно оценить влияние на организацию.</span><span class="sxs-lookup"><span data-stu-id="16917-171">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="16917-172">**Блокировка только** изменения диска . Попытки неоправдавляемого приложения для записи в дисковые сектора будут регистрироваться в журнале Windows событий.</span><span class="sxs-lookup"><span data-stu-id="16917-172">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="16917-173">Эти журналы можно  найти в журналах приложений и служб > Microsoft > Windows > Защитник Windows > операционных > ID 1123.</span><span class="sxs-lookup"><span data-stu-id="16917-173">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="16917-174">**Только изменение** диска аудита — только попытки записи в защищенные дисковые сектора будут записываться в журнале событий Windows (в журнале приложений и служб Microsoft Windows Защитник Windows Operational  >    >    >    >    >  **ID 1124).**</span><span class="sxs-lookup"><span data-stu-id="16917-174">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="16917-175">Попытки изменить или удалить файлы в защищенных папках не будут записываться.</span><span class="sxs-lookup"><span data-stu-id="16917-175">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![Снимок экрана параметра групповой политики Включен и режим аудита, выбранный в отсеве](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="16917-177">Чтобы полностью включить управляемый доступ к папкам,  необходимо настроить параметр Групповой политики для включения и выбрать **Блок** в выпадаемом меню параметров.</span><span class="sxs-lookup"><span data-stu-id="16917-177">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="16917-178">PowerShell</span><span class="sxs-lookup"><span data-stu-id="16917-178">PowerShell</span></span>

1. <span data-ttu-id="16917-179">Введите **powershell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**.</span><span class="sxs-lookup"><span data-stu-id="16917-179">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="16917-180">Введите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="16917-180">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="16917-181">Вы можете включить функцию в режиме аудита, указав `AuditMode` вместо `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="16917-181">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="16917-182">Используйте `Disabled` для отключения функции.</span><span class="sxs-lookup"><span data-stu-id="16917-182">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="16917-183">См. также</span><span class="sxs-lookup"><span data-stu-id="16917-183">See also</span></span>

* [<span data-ttu-id="16917-184">Защита важных папок с управляемым доступом к папкам</span><span class="sxs-lookup"><span data-stu-id="16917-184">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="16917-185">Настройка контролируемого доступа к папкам</span><span class="sxs-lookup"><span data-stu-id="16917-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="16917-186">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="16917-186">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
