---
title: Включить контролируемый доступ к папкам
keywords: Управляемый доступ к папкам, Windows 10, защитник Windows, вымогатели, защита, файлы, папки, включить, включить, использовать
description: Узнайте, как защитить важные файлы, включив доступ к управляемой папке
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.topic: article
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
ms.openlocfilehash: 5a90a12457597fa38c648fd44bf194d2322a26af
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861228"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="4e0c7-104">Включить контролируемый доступ к папкам</span><span class="sxs-lookup"><span data-stu-id="4e0c7-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4e0c7-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4e0c7-105">**Applies to:**</span></span>
- [<span data-ttu-id="4e0c7-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="4e0c7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4e0c7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e0c7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="4e0c7-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="4e0c7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4e0c7-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="4e0c7-110">[Управляемый доступ к папкам](controlled-folders.md) помогает защитить ценные данные от вредоносных приложений и угроз, таких как вымогателей.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="4e0c7-111">Доступ к управляемой папке включен в Windows 10 и Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="4e0c7-112">Вы можете включить управляемый доступ к папкам с помощью любого из этих методов:</span><span class="sxs-lookup"><span data-stu-id="4e0c7-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="4e0c7-113">Безопасность Windows приложение</span><span class="sxs-lookup"><span data-stu-id="4e0c7-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="4e0c7-114">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4e0c7-114">Microsoft Endpoint Manager</span></span>](#endpoint-manager)
* [<span data-ttu-id="4e0c7-115">Управление мобильными устройствами (MDM)</span><span class="sxs-lookup"><span data-stu-id="4e0c7-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="4e0c7-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4e0c7-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="4e0c7-117">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="4e0c7-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="4e0c7-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e0c7-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="4e0c7-119">[Режим аудита](evaluate-controlled-folder-access.md) позволяет проверить, как эта функция будет работать (и проверять события), не влияя на нормальное использование устройства.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="4e0c7-120">Параметры групповой политики, отключающие слияние списков локальных администраторов, переопределяют параметры доступа к управляемым папкам.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="4e0c7-121">Кроме того, они переопределяют защищенные папки и разрешают приложения, установленные местным администратором, с помощью управляемого доступа к папкам.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="4e0c7-122">Эти политики включают:</span><span class="sxs-lookup"><span data-stu-id="4e0c7-122">These policies include:</span></span>

* <span data-ttu-id="4e0c7-123">антивирусная программа в Microsoft Defender Настройка **поведения локального администратора для объединения списков**</span><span class="sxs-lookup"><span data-stu-id="4e0c7-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="4e0c7-124">System Center Endpoint Protection разрешить **пользователям добавлять исключения и переопределения**</span><span class="sxs-lookup"><span data-stu-id="4e0c7-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="4e0c7-125">Дополнительные сведения об отключении локального объединения списков см. в см. в twitter [Prevent или allow users to locally modify Microsoft Defender AV policy settings.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)</span><span class="sxs-lookup"><span data-stu-id="4e0c7-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="4e0c7-126">Безопасность Windows приложение</span><span class="sxs-lookup"><span data-stu-id="4e0c7-126">Windows Security app</span></span>

1. <span data-ttu-id="4e0c7-127">Откройте приложение Безопасность Windows, выбрав значок щита в панели задач.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="4e0c7-128">Вы также можете искать меню пусков для **Defender**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="4e0c7-129">Выберите **плитку защиты &** вирусов (или значок щита в левой панели меню), а затем выберите защиту **вымогателей.**</span><span class="sxs-lookup"><span data-stu-id="4e0c7-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="4e0c7-130">Установите переключатель для **доступа к управляемой папке** **для On**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="4e0c7-131">Если управляемый доступ к папке настроен с помощью CSPs групповой политики, PowerShell или MDM, состояние изменится в приложении Безопасность Windows после перезапуска устройства.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="4e0c7-132">Если функция настроена в **режиме аудита** с любым из этих средств, Безопасность Windows приложение покажет состояние **как Off**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="4e0c7-133">Если вы защищаете данные профилей пользователей, рекомендуется, чтобы профиль пользователя был на Windows установки.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="endpoint-manager"></a><span data-ttu-id="4e0c7-134">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4e0c7-134">Endpoint Manager</span></span>

1. <span data-ttu-id="4e0c7-135">Во входе в [Endpoint Manager](https://endpoint.microsoft.com) и откройте **конечную точку безопасности**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-135">Sign in to the [Endpoint Manager](https://endpoint.microsoft.com) and open **Endpoint Security**.</span></span>

2. <span data-ttu-id="4e0c7-136">Перейдите к **политике уменьшения**  >  **поверхности атаки**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-136">Go to **Attack Surface Reduction** > **Policy**.</span></span>

3. <span data-ttu-id="4e0c7-137">Выберите **платформу,** **выберите Windows 10 и** более позднее, а также выберите правила уменьшения поверхности   >  **профилей Создать**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-137">Select **Platform**, choose **Windows 10 and later**, and select the profile **Attack Surface Reduction rules** > **Create**.</span></span>

4.  <span data-ttu-id="4e0c7-138">Назови политику и добавьте описание.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-138">Name the policy and add a description.</span></span> <span data-ttu-id="4e0c7-139">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-139">Select **Next**.</span></span>

5.  <span data-ttu-id="4e0c7-140">Прокрутите вниз вниз, выберите каплю **Enable Folder Protection** и выберите **Включить**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-140">Scroll down to the bottom, select the **Enable Folder Protection** drop-down, and choose **Enable**.</span></span>

6.  <span data-ttu-id="4e0c7-141">Выберите **список дополнительных папок,** которые необходимо защитить, и добавьте папки, которые необходимо защитить.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-141">Select **List of additional folders that need to be protected** and add the folders that need to be protected.</span></span>

7.  <span data-ttu-id="4e0c7-142">Выберите **Список приложений, которые имеют доступ** к защищенным папкам, и добавьте приложения, которые имеют доступ к защищенным папок.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-142">Select **List of apps that have access to protected folders** and add the apps that have access to protected folders.</span></span>

8.  <span data-ttu-id="4e0c7-143">Выберите **Исключение файлов и путей из** правил уменьшения поверхности атаки и добавьте файлы и пути, которые необходимо исключить из правил уменьшения поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-143">Select **Exclude files and paths from attack surface reduction rules** and add the files and paths that need to be excluded from attack surface reduction rules.</span></span>

9.  <span data-ttu-id="4e0c7-144">Выберите назначения **профилей,** назначьте всем **пользователям & всех** устройств и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-144">Select the profile **Assignments**, assign to **All Users & All Devices**, and select **Save**.</span></span>

10.  <span data-ttu-id="4e0c7-145">Выберите **Далее,** чтобы сохранить каждое открытое лезвие и **создать**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-145">Select **Next** to save each open blade and then **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4e0c7-146">Поддиальды поддерживаются для приложений, но не для папок.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-146">Wildcards are supported for applications, but not for folders.</span></span> <span data-ttu-id="4e0c7-147">Подмостки не защищены.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-147">Subfolders are not protected.</span></span> <span data-ttu-id="4e0c7-148">Разрешенные приложения будут продолжать запускать события, пока они не будут перезапущены.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-148">Allowed apps will continue to trigger events until they are restarted.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="4e0c7-149">Управление мобильными устройствами (MDM)</span><span class="sxs-lookup"><span data-stu-id="4e0c7-149">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="4e0c7-150">Используйте [поставщик услуг конфигурации ./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) (CSP), чтобы разрешить приложениям вносить изменения в защищенные папки.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-150">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="4e0c7-151">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4e0c7-151">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="4e0c7-152">В Microsoft Endpoint Configuration Manager перейдите в **службу Assets and Compliance**  >  **Endpoint Protection** Защитник Windows  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-152">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="4e0c7-153">Выберите   >  **домашнее создание политики защиты от эксплойтов**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-153">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="4e0c7-154">Введите имя и описание, выберите доступ к управляемой **папке** и выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="4e0c7-154">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="4e0c7-155">Выберите блок или аудит изменений, разрешить другие приложения или добавить другие папки и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-155">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="4e0c7-156">Wilcard поддерживается для приложений, но не для папок.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-156">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="4e0c7-157">Подмостки не защищены.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-157">Subfolders are not protected.</span></span> <span data-ttu-id="4e0c7-158">Разрешенные приложения будут продолжать запускать события, пока они не будут перезапущены.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-158">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="4e0c7-159">Просмотрите параметры и выберите **Далее,** чтобы создать политику.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-159">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="4e0c7-160">После создания политики **закрой**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-160">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="4e0c7-161">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="4e0c7-161">Group Policy</span></span>

1. <span data-ttu-id="4e0c7-162">На устройстве управления групповой политикой откройте консоль управления групповой политикой [правой](https://technet.microsoft.com/library/cc731212.aspx)кнопкой мыши объект групповой политики, который необходимо настроить, и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-162">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="4e0c7-163">В **редакторе управления групповыми политиками** перейдите к **конфигурации компьютера** и выберите **Административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-163">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="4e0c7-164">Расширь дерево до **Windows компонентов > антивирусная программа в Microsoft Defender > Защитник Windows exploit Guard > управляемой папке.**</span><span class="sxs-lookup"><span data-stu-id="4e0c7-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="4e0c7-165">Дважды нажмите **кнопку Настройка управляемого доступа к папке** и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-165">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="4e0c7-166">В разделе Параметры необходимо указать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="4e0c7-166">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="4e0c7-167">**Включить** . Вредоносные и подозрительные приложения не смогут вносить изменения в файлы в защищенных папках.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-167">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="4e0c7-168">Уведомление будет предоставлено в журнале Windows событий.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-168">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="4e0c7-169">**Отключение (по умолчанию)** — функция доступа к управляемой папке не будет работать.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-169">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="4e0c7-170">Все приложения могут вносить изменения в файлы в защищенных папках.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-170">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="4e0c7-171">**Режим аудита** . Изменения будут разрешены, если вредоносное или подозрительное приложение пытается внести изменения в файл в защищенной папке.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-171">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="4e0c7-172">Однако он будет записан в журнале событий Windows, где можно оценить влияние на организацию.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-172">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="4e0c7-173">**Блокировка только** изменения диска . Попытки неоправдавляемого приложения для записи в дисковые сектора будут регистрироваться в журнале Windows событий.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-173">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="4e0c7-174">Эти журналы можно  найти в журналах приложений и служб > Microsoft > Windows > Защитник Windows > операционных > ID 1123.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-174">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="4e0c7-175">**Только изменение** диска аудита — только попытки записи в защищенные дисковые сектора будут записываться в журнале событий Windows (в журнале приложений и служб Microsoft Windows Защитник Windows Operational  >    >    >    >    >  **ID 1124).**</span><span class="sxs-lookup"><span data-stu-id="4e0c7-175">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="4e0c7-176">Попытки изменить или удалить файлы в защищенных папках не будут записываться.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-176">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![Снимок экрана параметра групповой политики Включен и режим аудита, выбранный в отсеве](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="4e0c7-178">Чтобы полностью включить управляемый доступ к папкам,  необходимо настроить параметр Групповой политики для включения и выбрать **Блок** в выпадаемом меню параметров.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-178">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="4e0c7-179">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e0c7-179">PowerShell</span></span>

1. <span data-ttu-id="4e0c7-180">Введите **powershell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-180">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="4e0c7-181">Введите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4e0c7-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="4e0c7-182">Вы можете включить функцию в режиме аудита, указав `AuditMode` вместо `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="4e0c7-182">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="4e0c7-183">Используйте `Disabled` для отключения функции.</span><span class="sxs-lookup"><span data-stu-id="4e0c7-183">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e0c7-184">См. также</span><span class="sxs-lookup"><span data-stu-id="4e0c7-184">See also</span></span>

* [<span data-ttu-id="4e0c7-185">Защита важных папок с управляемым доступом к папкам</span><span class="sxs-lookup"><span data-stu-id="4e0c7-185">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="4e0c7-186">Настройка контролируемого доступа к папкам</span><span class="sxs-lookup"><span data-stu-id="4e0c7-186">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="4e0c7-187">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="4e0c7-187">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
