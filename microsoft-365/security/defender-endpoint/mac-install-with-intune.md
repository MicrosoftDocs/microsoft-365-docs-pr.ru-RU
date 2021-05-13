---
title: Развертывание на основе intune для Microsoft Defender для конечной точки на Mac
description: Установите Microsoft Defender для конечной точки на Mac с Microsoft Intune.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: da82b24b8a6bb6aa22028615bb3dd0c9d45acfa1
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346032"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="0cbee-104">Развертывание на основе intune для Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="0cbee-104">Intune-based deployment for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0cbee-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0cbee-105">**Applies to:**</span></span>

- [<span data-ttu-id="0cbee-106">Microsoft Defender для конечной точки в macOS</span><span class="sxs-lookup"><span data-stu-id="0cbee-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="0cbee-107">В этом разделе описывается развертывание Microsoft Defender для конечной точки на macOS через Intune.</span><span class="sxs-lookup"><span data-stu-id="0cbee-107">This topic describes how to deploy Microsoft Defender for Endpoint on macOS through Intune.</span></span> <span data-ttu-id="0cbee-108">Успешное развертывание требует выполнения всех следующих действий:</span><span class="sxs-lookup"><span data-stu-id="0cbee-108">A successful deployment requires the completion of all of the following steps:</span></span>

1. [<span data-ttu-id="0cbee-109">Скачайте пакет onboarding</span><span class="sxs-lookup"><span data-stu-id="0cbee-109">Download the onboarding package</span></span>](#download-the-onboarding-package)
1. [<span data-ttu-id="0cbee-110">Установка клиентских устройств</span><span class="sxs-lookup"><span data-stu-id="0cbee-110">Client device setup</span></span>](#client-device-setup)
1. [<span data-ttu-id="0cbee-111">Утверждение расширений системы</span><span class="sxs-lookup"><span data-stu-id="0cbee-111">Approve system extensions</span></span>](#approve-system-extensions)
1. [<span data-ttu-id="0cbee-112">Создание профилей конфигурации системы</span><span class="sxs-lookup"><span data-stu-id="0cbee-112">Create System Configuration profiles</span></span>](#create-system-configuration-profiles)
1. [<span data-ttu-id="0cbee-113">Публикация приложения</span><span class="sxs-lookup"><span data-stu-id="0cbee-113">Publish application</span></span>](#publish-application)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="0cbee-114">Необходимые условия и требования к системе</span><span class="sxs-lookup"><span data-stu-id="0cbee-114">Prerequisites and system requirements</span></span>

<span data-ttu-id="0cbee-115">Перед началом работы см. в главной странице [Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md) на странице macOS описание необходимых условий и системных требований к текущей версии программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="0cbee-115">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="overview"></a><span data-ttu-id="0cbee-116">Обзор</span><span class="sxs-lookup"><span data-stu-id="0cbee-116">Overview</span></span>

<span data-ttu-id="0cbee-117">В следующей таблице подводятся итоги действий, которые необходимо предпринять для развертывания и управления Microsoft Defender для конечной точки на Mac с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="0cbee-117">The following table summarizes the steps you would need to take to deploy and manage Microsoft Defender for Endpoint on Macs, via Intune.</span></span> <span data-ttu-id="0cbee-118">Более подробные действия доступны ниже.</span><span class="sxs-lookup"><span data-stu-id="0cbee-118">More detailed steps are available below.</span></span>

| <span data-ttu-id="0cbee-119">Шаг</span><span class="sxs-lookup"><span data-stu-id="0cbee-119">Step</span></span> | <span data-ttu-id="0cbee-120">Примеры имен файлов</span><span class="sxs-lookup"><span data-stu-id="0cbee-120">Sample file names</span></span> | <span data-ttu-id="0cbee-121">BundleIdentifier</span><span class="sxs-lookup"><span data-stu-id="0cbee-121">BundleIdentifier</span></span> |
|-|-|-|
| [<span data-ttu-id="0cbee-122">Скачайте пакет onboarding</span><span class="sxs-lookup"><span data-stu-id="0cbee-122">Download the onboarding package</span></span>](#download-the-onboarding-package) | <span data-ttu-id="0cbee-123">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span><span class="sxs-lookup"><span data-stu-id="0cbee-123">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span></span> | <span data-ttu-id="0cbee-124">com.microsoft.wdav.atp</span><span class="sxs-lookup"><span data-stu-id="0cbee-124">com.microsoft.wdav.atp</span></span> |
| [<span data-ttu-id="0cbee-125">Утверждение расширения системы для Защитника Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0cbee-125">Approve System Extension for Microsoft Defender for Endpoint</span></span>](#approve-system-extensions) | <span data-ttu-id="0cbee-126">MDATP_SysExt.xml</span><span class="sxs-lookup"><span data-stu-id="0cbee-126">MDATP_SysExt.xml</span></span> | <span data-ttu-id="0cbee-127">Н/Д</span><span class="sxs-lookup"><span data-stu-id="0cbee-127">N/A</span></span> |
| [<span data-ttu-id="0cbee-128">Утверждение расширения ядра для Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0cbee-128">Approve Kernel Extension for Microsoft Defender for Endpoint</span></span>](#download-the-onboarding-package) | <span data-ttu-id="0cbee-129">MDATP_KExt.xml</span><span class="sxs-lookup"><span data-stu-id="0cbee-129">MDATP_KExt.xml</span></span> | <span data-ttu-id="0cbee-130">Н/Д</span><span class="sxs-lookup"><span data-stu-id="0cbee-130">N/A</span></span> |
| [<span data-ttu-id="0cbee-131">Предоставление полного доступа к диску Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0cbee-131">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#full-disk-access) | <span data-ttu-id="0cbee-132">MDATP_tcc_Catalina_or_newer.xml</span><span class="sxs-lookup"><span data-stu-id="0cbee-132">MDATP_tcc_Catalina_or_newer.xml</span></span> | <span data-ttu-id="0cbee-133">com.microsoft.wdav.tcc</span><span class="sxs-lookup"><span data-stu-id="0cbee-133">com.microsoft.wdav.tcc</span></span> |
| [<span data-ttu-id="0cbee-134">Политика расширения сети</span><span class="sxs-lookup"><span data-stu-id="0cbee-134">Network Extension policy</span></span>](#network-filter) | <span data-ttu-id="0cbee-135">MDATP_NetExt.xml</span><span class="sxs-lookup"><span data-stu-id="0cbee-135">MDATP_NetExt.xml</span></span> | <span data-ttu-id="0cbee-136">Н/Д</span><span class="sxs-lookup"><span data-stu-id="0cbee-136">N/A</span></span> |
| [<span data-ttu-id="0cbee-137">Настройка Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="0cbee-137">Configure Microsoft AutoUpdate (MAU)</span></span>](mac-updates.md#intune) | <span data-ttu-id="0cbee-138">MDATP_Microsoft_AutoUpdate.xml</span><span class="sxs-lookup"><span data-stu-id="0cbee-138">MDATP_Microsoft_AutoUpdate.xml</span></span> | <span data-ttu-id="0cbee-139">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="0cbee-139">com.microsoft.autoupdate2</span></span> |
| [<span data-ttu-id="0cbee-140">Microsoft Defender для параметров конфигурации конечной точки</span><span class="sxs-lookup"><span data-stu-id="0cbee-140">Microsoft Defender for Endpoint configuration settings</span></span>](mac-preferences.md#intune-profile-1)<br/><br/> <span data-ttu-id="0cbee-141">**Примечание:** Если вы планируете запустить сторонний AV для macOS, задай `passiveMode` . `true`</span><span class="sxs-lookup"><span data-stu-id="0cbee-141">**Note:** If you're planning to run a third-party AV for macOS, set `passiveMode` to `true`.</span></span> | <span data-ttu-id="0cbee-142">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span><span class="sxs-lookup"><span data-stu-id="0cbee-142">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span></span> | <span data-ttu-id="0cbee-143">com.microsoft.wdav</span><span class="sxs-lookup"><span data-stu-id="0cbee-143">com.microsoft.wdav</span></span> |
| [<span data-ttu-id="0cbee-144">Настройка уведомлений Microsoft Defender для конечной точки и ms AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="0cbee-144">Configure Microsoft Defender for Endpoint and MS AutoUpdate (MAU) notifications</span></span>](mac-updates.md) | <span data-ttu-id="0cbee-145">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span><span class="sxs-lookup"><span data-stu-id="0cbee-145">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span></span> | <span data-ttu-id="0cbee-146">com.microsoft.autoupdate2 или com.microsoft.wdav.tray</span><span class="sxs-lookup"><span data-stu-id="0cbee-146">com.microsoft.autoupdate2 or com.microsoft.wdav.tray</span></span> |


## <a name="download-the-onboarding-package"></a><span data-ttu-id="0cbee-147">Скачайте пакет onboarding</span><span class="sxs-lookup"><span data-stu-id="0cbee-147">Download the onboarding package</span></span>

<span data-ttu-id="0cbee-148">Скачайте бортовые пакеты из Центр безопасности в Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="0cbee-148">Download the onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="0cbee-149">В Центр безопасности в Microsoft Defender перейдите **к Параметры**  >  **управления**  >  **устройствами.**</span><span class="sxs-lookup"><span data-stu-id="0cbee-149">In Microsoft Defender Security Center, go to **Settings** > **Device Management** > **Onboarding**.</span></span>

2. <span data-ttu-id="0cbee-150">Установите операционную систему **для macOS** и метод развертывания для управления мобильными устройствами **и Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="0cbee-150">Set the operating system to **macOS** and the deployment method to **Mobile Device Management / Microsoft Intune**.</span></span>

    ![Скриншот параметров onboarding](images/atp-mac-install.png)

3. <span data-ttu-id="0cbee-152">Выберите **пакет загрузки.**</span><span class="sxs-lookup"><span data-stu-id="0cbee-152">Select **Download onboarding package**.</span></span> <span data-ttu-id="0cbee-153">Сохраните его _WindowsDefenderATPOnboardingPackage.zip_ в том же каталоге.</span><span class="sxs-lookup"><span data-stu-id="0cbee-153">Save it as _WindowsDefenderATPOnboardingPackage.zip_ to the same directory.</span></span>

4. <span data-ttu-id="0cbee-154">Извлечение содержимого .zip файла:</span><span class="sxs-lookup"><span data-stu-id="0cbee-154">Extract the contents of the .zip file:</span></span>

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    warning:  WindowsDefenderATPOnboardingPackage.zip appears to use backslashes as path separators
      inflating: intune/kext.xml
      inflating: intune/WindowsDefenderATPOnboarding.xml
      inflating: jamf/WindowsDefenderATPOnboarding.plist
    ```

## <a name="create-system-configuration-profiles"></a><span data-ttu-id="0cbee-155">Создание профилей конфигурации системы</span><span class="sxs-lookup"><span data-stu-id="0cbee-155">Create System Configuration profiles</span></span>

<span data-ttu-id="0cbee-156">Следующий шаг — создание профилей конфигурации системы, необходимых Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0cbee-156">The next step is to create system configuration profiles that Microsoft Defender for Endpoint needs.</span></span>
<span data-ttu-id="0cbee-157">В центре [администрирования Microsoft Endpoint Manager](https://endpoint.microsoft.com/) **открытые** профили  >  **конфигурации устройств.**</span><span class="sxs-lookup"><span data-stu-id="0cbee-157">In the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/), open **Devices** > **Configuration profiles**.</span></span>

### <a name="onboarding-blob"></a><span data-ttu-id="0cbee-158">Вметь blob</span><span class="sxs-lookup"><span data-stu-id="0cbee-158">Onboarding blob</span></span>

<span data-ttu-id="0cbee-159">Этот профиль содержит сведения о лицензии для Microsoft Defender для конечной точки, без нее он будет сообщать, что она не лицензирована.</span><span class="sxs-lookup"><span data-stu-id="0cbee-159">This profile contains a license information for Microsoft Defender for Endpoint, without it it will report that it is not licensed.</span></span>

1. <span data-ttu-id="0cbee-160">Выберите **Создание профиля в** **профилях конфигурации.**</span><span class="sxs-lookup"><span data-stu-id="0cbee-160">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="0cbee-161">Выберите  = **шаблоны типов** **профилей Platform** macOS = .</span><span class="sxs-lookup"><span data-stu-id="0cbee-161">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="0cbee-162">**Имя шаблона** = **Настраиваемый**.</span><span class="sxs-lookup"><span data-stu-id="0cbee-162">**Template name**=**Custom**.</span></span> <span data-ttu-id="0cbee-163">Щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0cbee-163">Click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0cbee-164">![Создание настраиваемой конфигурации профиля](images/mdatp-6-systemconfigurationprofiles-1.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-164">![Custom Configuration Profile creation](images/mdatp-6-systemconfigurationprofiles-1.png)</span></span>

1. <span data-ttu-id="0cbee-165">Выберите имя для профиля, например "MDATP для macOS".</span><span class="sxs-lookup"><span data-stu-id="0cbee-165">Choose a name for the profile, e.g., "MDATP onboarding for macOS".</span></span> <span data-ttu-id="0cbee-166">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbee-166">Click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0cbee-167">![Настраиваемый профиль конфигурации — имя](images/mdatp-6-systemconfigurationprofiles-2.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-167">![Custom Configuration Profile - name](images/mdatp-6-systemconfigurationprofiles-2.png)</span></span>

1. <span data-ttu-id="0cbee-168">Выберите имя имени профиля конфигурации, например "MDATP для macOS".</span><span class="sxs-lookup"><span data-stu-id="0cbee-168">Choose a name for the configuration profile name, e.g., "MDATP onboarding for macOS".</span></span>
1. <span data-ttu-id="0cbee-169">Выберите intune/WindowsDefenderATPOnboarding.xml, извлеченный из пакета onboarding выше, в качестве файла профиля конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0cbee-169">Select intune/WindowsDefenderATPOnboarding.xml that you extracted from the onboarding package above as configuration profile file.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0cbee-170">![Импорт конфигурации из файла для настраиваемого профиля конфигурации](images/mdatp-6-systemconfigurationprofiles.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-170">![Import a configuration from a file for Custom Configuration Profile](images/mdatp-6-systemconfigurationprofiles.png)</span></span>

1. <span data-ttu-id="0cbee-171">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbee-171">Click **Next**.</span></span>
1. <span data-ttu-id="0cbee-172">Назначение устройств на **вкладке Назначение.** Нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbee-172">Assign devices on the **Assignment** tab. Click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0cbee-173">![Настраиваемый профиль конфигурации — назначение](images/mdatp-6-systemconfigurationprofiles-2.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-173">![Custom Configuration Profile - assignment](images/mdatp-6-systemconfigurationprofiles-2.png)</span></span>

1. <span data-ttu-id="0cbee-174">Обзор и **создание**.</span><span class="sxs-lookup"><span data-stu-id="0cbee-174">Review and **Create**.</span></span>
1. <span data-ttu-id="0cbee-175">Откройте   >  **профили конфигурации устройств**, вы можете увидеть созданный профиль там.</span><span class="sxs-lookup"><span data-stu-id="0cbee-175">Open **Devices** > **Configuration profiles**, you can see your created profile there.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0cbee-176">![Настраиваемый профиль конфигурации — сделано](images/mdatp-6-systemconfigurationprofiles-3.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-176">![Custom Configuration Profile - done](images/mdatp-6-systemconfigurationprofiles-3.png)</span></span>

### <a name="approve-system-extensions"></a><span data-ttu-id="0cbee-177">Утверждение расширений системы</span><span class="sxs-lookup"><span data-stu-id="0cbee-177">Approve System Extensions</span></span>

<span data-ttu-id="0cbee-178">Этот профиль необходим для macOS 10.15 (Catalina) или более нового.</span><span class="sxs-lookup"><span data-stu-id="0cbee-178">This profile is needed for macOS 10.15 (Catalina) or newer.</span></span> <span data-ttu-id="0cbee-179">Он будет игнорироваться на более старых macOS.</span><span class="sxs-lookup"><span data-stu-id="0cbee-179">It will be ignored on older macOS.</span></span>

1. <span data-ttu-id="0cbee-180">Выберите **Создание профиля в** **профилях конфигурации.**</span><span class="sxs-lookup"><span data-stu-id="0cbee-180">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="0cbee-181">Выберите  = **шаблоны типов** **профилей Platform** macOS = .</span><span class="sxs-lookup"><span data-stu-id="0cbee-181">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="0cbee-182">**Имя шаблона** = **Расширения**.</span><span class="sxs-lookup"><span data-stu-id="0cbee-182">**Template name**=**Extensions**.</span></span> <span data-ttu-id="0cbee-183">Щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0cbee-183">Click **Create**.</span></span>
1. <span data-ttu-id="0cbee-184">На **вкладке Basics** назови имя этому новому профилю.</span><span class="sxs-lookup"><span data-stu-id="0cbee-184">In the **Basics** tab, give a name to this new profile.</span></span>
1. <span data-ttu-id="0cbee-185">На **вкладке Параметры конфигурации** расширяйте **расширения системы,** добавьте следующие записи в разделе **Разрешенные расширения** системы:</span><span class="sxs-lookup"><span data-stu-id="0cbee-185">In the **Configuration settings** tab, expand **System Extensions** add the following entries in the **Allowed system extensions** section:</span></span>

    <span data-ttu-id="0cbee-186">Идентификатор bundle</span><span class="sxs-lookup"><span data-stu-id="0cbee-186">Bundle identifier</span></span>         | <span data-ttu-id="0cbee-187">Идентификатор группы</span><span class="sxs-lookup"><span data-stu-id="0cbee-187">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="0cbee-188">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="0cbee-188">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="0cbee-189">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="0cbee-189">UBF8T346G9</span></span>
    <span data-ttu-id="0cbee-190">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="0cbee-190">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="0cbee-191">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="0cbee-191">UBF8T346G9</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0cbee-192">![Параметры расширения системы](images/mac-system-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-192">![System extension settings](images/mac-system-extension-intune2.png)</span></span>

1. <span data-ttu-id="0cbee-193">На **вкладке Назначения** назначьте этот профиль всем пользователям **& всем устройствам.**</span><span class="sxs-lookup"><span data-stu-id="0cbee-193">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>
1. <span data-ttu-id="0cbee-194">Просмотрите и создайте этот профиль конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0cbee-194">Review and create this configuration profile.</span></span>

### <a name="kernel-extensions"></a><span data-ttu-id="0cbee-195">Расширения ядра</span><span class="sxs-lookup"><span data-stu-id="0cbee-195">Kernel Extensions</span></span>

<span data-ttu-id="0cbee-196">Этот профиль необходим для macOS 10.15 (Catalina) или старше.</span><span class="sxs-lookup"><span data-stu-id="0cbee-196">This profile is needed for macOS 10.15 (Catalina) or older.</span></span> <span data-ttu-id="0cbee-197">Он будет игнорироваться на более новых macOS.</span><span class="sxs-lookup"><span data-stu-id="0cbee-197">It will be ignored on newer macOS.</span></span>

> [!CAUTION]
> <span data-ttu-id="0cbee-198">Устройства Apple Silicon (M1) не поддерживают KEXT.</span><span class="sxs-lookup"><span data-stu-id="0cbee-198">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="0cbee-199">Установка профиля конфигурации, состоящего из политик KEXT, не будет работать на этих устройствах.</span><span class="sxs-lookup"><span data-stu-id="0cbee-199">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="0cbee-200">Выберите **Создание профиля в** **профилях конфигурации.**</span><span class="sxs-lookup"><span data-stu-id="0cbee-200">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="0cbee-201">Выберите  = **шаблоны типов** **профилей Platform** macOS = .</span><span class="sxs-lookup"><span data-stu-id="0cbee-201">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="0cbee-202">**Имя шаблона** = **Расширения**.</span><span class="sxs-lookup"><span data-stu-id="0cbee-202">**Template name**=**Extensions**.</span></span> <span data-ttu-id="0cbee-203">Щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0cbee-203">Click **Create**.</span></span>
1. <span data-ttu-id="0cbee-204">На **вкладке Basics** назови имя этому новому профилю.</span><span class="sxs-lookup"><span data-stu-id="0cbee-204">In the **Basics** tab, give a name to this new profile.</span></span>
1. <span data-ttu-id="0cbee-205">На **вкладке Параметры конфигурации** разоширим **расширения ядра.**</span><span class="sxs-lookup"><span data-stu-id="0cbee-205">In the **Configuration settings** tab, expand **Kernel Extensions**.</span></span>
1. <span data-ttu-id="0cbee-206">Установите **идентификатор команды в** **UBF8T346G9** и нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbee-206">Set **Team identifier** to **UBF8T346G9** and click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0cbee-207">![Параметры расширения ядра](images/mac-kernel-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-207">![Kernel extension settings](images/mac-kernel-extension-intune2.png)</span></span>

1. <span data-ttu-id="0cbee-208">На **вкладке Назначения** назначьте этот профиль всем пользователям **& всем устройствам.**</span><span class="sxs-lookup"><span data-stu-id="0cbee-208">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>
1. <span data-ttu-id="0cbee-209">Просмотрите и создайте этот профиль конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0cbee-209">Review and create this configuration profile.</span></span>

### <a name="full-disk-access"></a><span data-ttu-id="0cbee-210">Полный доступ к диску</span><span class="sxs-lookup"><span data-stu-id="0cbee-210">Full Disk Access</span></span>

   > [!CAUTION]
   > <span data-ttu-id="0cbee-211">MacOS 10.15 (Catalina) содержит новые улучшения безопасности и конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="0cbee-211">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="0cbee-212">Начиная с этой версии, по умолчанию приложения не могут получить доступ к определенным расположениям на диске (например, документы, скачивания, настольные компьютеры и т.д.) без явного согласия.</span><span class="sxs-lookup"><span data-stu-id="0cbee-212">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="0cbee-213">При отсутствии такого согласия Microsoft Defender для конечной точки не может полностью защитить ваше устройство.</span><span class="sxs-lookup"><span data-stu-id="0cbee-213">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
   >
   > <span data-ttu-id="0cbee-214">Этот профиль конфигурации предоставляет полный дисковый доступ к Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0cbee-214">This configuration profile grants Full Disk Access to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="0cbee-215">Если вы ранее настраивали Microsoft Defender для конечной точки через Intune, рекомендуем обновить развертывание с помощью этого профиля конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0cbee-215">If you previously configured Microsoft Defender for Endpoint through Intune, we recommend you update the deployment with this configuration profile.</span></span>

<span data-ttu-id="0cbee-216">Скачайте [**fulldisk.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/kext.mobileconfig) из [нашего GitHub репозиторий](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span><span class="sxs-lookup"><span data-stu-id="0cbee-216">Download [**fulldisk.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/kext.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="0cbee-217">Выполните инструкции по использованию [blob onboarding](#onboarding-blob) сверху, используя "MDATP полный доступ к диску" в качестве имени профиля и скачав **имя профиля конфигурации fulldisk.mobileconfig.**</span><span class="sxs-lookup"><span data-stu-id="0cbee-217">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "MDATP Full Disk Access" as profile name, and downloaded **fulldisk.mobileconfig** as Configuration profile name.</span></span>

### <a name="network-filter"></a><span data-ttu-id="0cbee-218">Фильтр сети</span><span class="sxs-lookup"><span data-stu-id="0cbee-218">Network Filter</span></span>

<span data-ttu-id="0cbee-219">В рамках возможностей обнаружения конечных точек и ответов Microsoft Defender для конечной точки на macOS проверяет трафик розетки и передает эти сведения на Центр безопасности в Microsoft Defender портал.</span><span class="sxs-lookup"><span data-stu-id="0cbee-219">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="0cbee-220">Следующая политика позволяет сетевому расширению выполнять эту функцию.</span><span class="sxs-lookup"><span data-stu-id="0cbee-220">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="0cbee-221">Скачайте [**netfilter.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/kext.mobileconfig) из [нашего GitHub репозиторий](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span><span class="sxs-lookup"><span data-stu-id="0cbee-221">Download [**netfilter.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/kext.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="0cbee-222">Выполните инструкции по использованию [blob onboarding](#onboarding-blob) сверху, используя "фильтр сети MDATP" в качестве имени профиля и скачав **имя профиля конфигурации netfilter.mobileconfig.**</span><span class="sxs-lookup"><span data-stu-id="0cbee-222">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "MDATP Network Filter" as profile name, and downloaded **netfilter.mobileconfig** as Configuration profile name.</span></span>

### <a name="notifications"></a><span data-ttu-id="0cbee-223">Уведомления</span><span class="sxs-lookup"><span data-stu-id="0cbee-223">Notifications</span></span>

<span data-ttu-id="0cbee-224">Этот профиль используется для того, чтобы позволить Microsoft Defender для конечной точки на macOS и Microsoft Auto Update отображать уведомления в пользовательском интерфейсе на macOS 10.15 (Catalina) или более новых.</span><span class="sxs-lookup"><span data-stu-id="0cbee-224">This profile is used to allow Microsoft Defender for Endpoint on macOS and Microsoft Auto Update to display notifications in UI on macOS 10.15 (Catalina) or newer.</span></span>

<span data-ttu-id="0cbee-225">Скачайте [**notif.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/kext.mobileconfig) из [нашего GitHub репозиторий](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span><span class="sxs-lookup"><span data-stu-id="0cbee-225">Download [**notif.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/kext.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="0cbee-226">Следуйте инструкциям по использованию [blob onboarding](#onboarding-blob) сверху, используя "фильтр сети MDATP" в качестве имени профиля, а также загрузите **notif.mobileconfig** в качестве имени профиля конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0cbee-226">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "MDATP Network Filter" as profile name, and downloaded **notif.mobileconfig** as Configuration profile name.</span></span>

### <a name="view-status"></a><span data-ttu-id="0cbee-227">Просмотр состояния</span><span class="sxs-lookup"><span data-stu-id="0cbee-227">View Status</span></span>

<span data-ttu-id="0cbee-228">После распространения изменений Intune на зарегистрированные устройства вы можете увидеть их, перечисленные в состоянии **Monitor**  >  **Device:**</span><span class="sxs-lookup"><span data-stu-id="0cbee-228">Once the Intune changes are propagated to the enrolled devices, you can see them listed under **Monitor** > **Device status**:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0cbee-229">![Просмотр состояния устройства в мониторе](images/mdatp-7-devicestatusblade.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-229">![View of Device Status in Monitor](images/mdatp-7-devicestatusblade.png)</span></span>

## <a name="publish-application"></a><span data-ttu-id="0cbee-230">Публикация приложения</span><span class="sxs-lookup"><span data-stu-id="0cbee-230">Publish application</span></span>

<span data-ttu-id="0cbee-231">Этот шаг позволяет развертывать Microsoft Defender для конечной точки на зарегистрированных машинах.</span><span class="sxs-lookup"><span data-stu-id="0cbee-231">This step enables deploying Microsoft Defender for Endpoint to enrolled machines.</span></span>

1. <span data-ttu-id="0cbee-232">В центре [администрирования Microsoft Endpoint Manager](https://endpoint.microsoft.com/)откройте **приложения.**</span><span class="sxs-lookup"><span data-stu-id="0cbee-232">In the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/), open **Apps**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0cbee-233">![Готовый к созданию приложения](images/mdatp-8-app-before.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-233">![Ready to create application](images/mdatp-8-app-before.png)</span></span>

1. <span data-ttu-id="0cbee-234">Выберите по платформе > macOS > Добавить.</span><span class="sxs-lookup"><span data-stu-id="0cbee-234">Select By platform > macOS > Add.</span></span>
1. <span data-ttu-id="0cbee-235">Выберите  = **macOS типа приложения,** нажмите **кнопку Выберите**.</span><span class="sxs-lookup"><span data-stu-id="0cbee-235">Choose **App type**=**macOS**, click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0cbee-236">![Укажите тип приложения](images/mdatp-9-app-type.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-236">![Specify application type](images/mdatp-9-app-type.png)</span></span>

1. <span data-ttu-id="0cbee-237">Сохранить значения по умолчанию, нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbee-237">Keep default values, click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0cbee-238">![Свойства приложения](images/mdatp-10-properties.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-238">![Application properties](images/mdatp-10-properties.png)</span></span>

1. <span data-ttu-id="0cbee-239">Добавление назначений, нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbee-239">Add assignments, click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0cbee-240">![Снимок экрана информации о назначениях Intune](images/mdatp-11-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-240">![Intune assignments info screenshot](images/mdatp-11-assignments.png)</span></span>

1. <span data-ttu-id="0cbee-241">Обзор и **создание**.</span><span class="sxs-lookup"><span data-stu-id="0cbee-241">Review and **Create**.</span></span>
1. <span data-ttu-id="0cbee-242">Вы можете **посетить MacOS платформы Apps** By, чтобы увидеть его  >    >   в списке всех приложений.</span><span class="sxs-lookup"><span data-stu-id="0cbee-242">You can visit **Apps** > **By platform** > **macOS** to see it on the list of all applications.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0cbee-243">![Список приложений](images/mdatp-12-applications.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-243">![Applications list](images/mdatp-12-applications.png)</span></span>

<span data-ttu-id="0cbee-244">(Подробные сведения можно найти на странице [Intune](/mem/intune/apps/apps-advanced-threat-protection-macos)для развертывания Defender.)</span><span class="sxs-lookup"><span data-stu-id="0cbee-244">(You can find detailed information on the [Intune's page for Defender deployment](/mem/intune/apps/apps-advanced-threat-protection-macos).)</span></span>

   > [!CAUTION]
   > <span data-ttu-id="0cbee-245">Необходимо создать все необходимые профили конфигурации и нажать их на все машины, как было объяснено выше.</span><span class="sxs-lookup"><span data-stu-id="0cbee-245">You have to create all required configuration profiles and push them to all machines, as explained above.</span></span>

## <a name="client-device-setup"></a><span data-ttu-id="0cbee-246">Установка клиентских устройств</span><span class="sxs-lookup"><span data-stu-id="0cbee-246">Client device setup</span></span>

<span data-ttu-id="0cbee-247">Вам не требуется специальная подготовка для устройства Mac за пределами стандартной Корпоративный портал [установки.](/intune-user-help/enroll-your-device-in-intune-macos-cp)</span><span class="sxs-lookup"><span data-stu-id="0cbee-247">You don't need any special provisioning for a Mac device beyond a standard [Company Portal installation](/intune-user-help/enroll-your-device-in-intune-macos-cp).</span></span>

1. <span data-ttu-id="0cbee-248">Подтверждение управления устройствами.</span><span class="sxs-lookup"><span data-stu-id="0cbee-248">Confirm device management.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0cbee-249">![Подтверждение экрана управления устройствами](images/mdatp-3-confirmdevicemgmt.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-249">![Confirm device management screenshot](images/mdatp-3-confirmdevicemgmt.png)</span></span>

    <span data-ttu-id="0cbee-250">Выберите **параметры Open System Preferences,** найдите **профиль** управления в списке и выберите **Утверждение...**. Ваш профиль управления будет отображаться как **Проверенный:**</span><span class="sxs-lookup"><span data-stu-id="0cbee-250">Select **Open System Preferences**, locate **Management Profile** on the list, and select **Approve...**. Your Management Profile would be displayed as **Verified**:</span></span>

    ![Снимок экрана профиля управления](images/mdatp-4-managementprofile.png)

2. <span data-ttu-id="0cbee-252">Выберите **Продолжить** и завершить регистрацию.</span><span class="sxs-lookup"><span data-stu-id="0cbee-252">Select **Continue** and complete the enrollment.</span></span>

   <span data-ttu-id="0cbee-253">Теперь вы можете записать больше устройств.</span><span class="sxs-lookup"><span data-stu-id="0cbee-253">You may now enroll more devices.</span></span> <span data-ttu-id="0cbee-254">Вы также можете записать их позже, после завершения настройки системы и пакетов приложений.</span><span class="sxs-lookup"><span data-stu-id="0cbee-254">You can also enroll them later, after you have finished provisioning system configuration and application packages.</span></span>

3. <span data-ttu-id="0cbee-255">В Intune откройте **управление**  >  **устройствами**  >  **все устройства.**</span><span class="sxs-lookup"><span data-stu-id="0cbee-255">In Intune, open **Manage** > **Devices** > **All devices**.</span></span> <span data-ttu-id="0cbee-256">Здесь вы можете увидеть ваше устройство среди перечисленных ниже.</span><span class="sxs-lookup"><span data-stu-id="0cbee-256">Here you can see your device among those listed:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0cbee-257">![Добавление экрана устройства](images/mdatp-5-alldevices.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-257">![Add Devices screenshot](images/mdatp-5-alldevices.png)</span></span>

## <a name="verify-client-device-state"></a><span data-ttu-id="0cbee-258">Проверка состояния клиентского устройства</span><span class="sxs-lookup"><span data-stu-id="0cbee-258">Verify client device state</span></span>

1. <span data-ttu-id="0cbee-259">После развертывания профилей конфигурации на устройствах откройте **профили** системных  >  **предпочтений** на устройстве Mac.</span><span class="sxs-lookup"><span data-stu-id="0cbee-259">After the configuration profiles are deployed to your devices, open **System Preferences** > **Profiles** on your Mac device.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0cbee-260">![Снимок экрана "Параметры системы"](images/mdatp-13-systempreferences.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-260">![System Preferences screenshot](images/mdatp-13-systempreferences.png)</span></span>

    ![Снимок экрана профилей системных предпочтений](images/mdatp-14-systempreferencesprofiles.png)

2. <span data-ttu-id="0cbee-262">Убедитесь, что следующие профили конфигурации присутствуют и устанавливаются.</span><span class="sxs-lookup"><span data-stu-id="0cbee-262">Verify that the following configuration profiles are present and installed.</span></span> <span data-ttu-id="0cbee-263">Профиль **управления должен** быть профилем системы Intune.</span><span class="sxs-lookup"><span data-stu-id="0cbee-263">The **Management Profile** should be the Intune system profile.</span></span> <span data-ttu-id="0cbee-264">_Wdav-config_ и _wdav-kext_ — это профили конфигурации системы, добавленные в Intune:</span><span class="sxs-lookup"><span data-stu-id="0cbee-264">_Wdav-config_ and _wdav-kext_ are system configuration profiles that were added in Intune:</span></span>

    ![Снимок экрана профилей](images/mdatp-15-managementprofileconfig.png)

3. <span data-ttu-id="0cbee-266">В правом верхнем углу также следует увидеть значок Microsoft Defender для конечных точек:</span><span class="sxs-lookup"><span data-stu-id="0cbee-266">You should also see the Microsoft Defender for Endpoint icon in the top-right corner:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0cbee-267">![Значок Microsoft Defender для конечной точки в скриншоте панели состояния](images/mdatp-icon-bar.png)</span><span class="sxs-lookup"><span data-stu-id="0cbee-267">![Microsoft Defender for Endpoint icon in status bar screenshot](images/mdatp-icon-bar.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0cbee-268">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="0cbee-268">Troubleshooting</span></span>

<span data-ttu-id="0cbee-269">Проблема. Лицензия не найдена.</span><span class="sxs-lookup"><span data-stu-id="0cbee-269">Issue: No license found.</span></span>

<span data-ttu-id="0cbee-270">Решение. Выполните следующие действия, чтобы создать профиль устройства с WindowsDefenderATPOnboarding.xml.</span><span class="sxs-lookup"><span data-stu-id="0cbee-270">Solution: Follow the steps above to create a device profile using WindowsDefenderATPOnboarding.xml.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="0cbee-271">Проблемы с установкой журнала</span><span class="sxs-lookup"><span data-stu-id="0cbee-271">Logging installation issues</span></span>

<span data-ttu-id="0cbee-272">Дополнительные сведения о том, как найти автоматически созданный журнал, созданный установщиком при ошибке, см. в примере проблемы с [установкой журнала.](mac-resources.md#logging-installation-issues)</span><span class="sxs-lookup"><span data-stu-id="0cbee-272">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Logging installation issues](mac-resources.md#logging-installation-issues).</span></span>

## <a name="uninstallation"></a><span data-ttu-id="0cbee-273">Uninstallation</span><span class="sxs-lookup"><span data-stu-id="0cbee-273">Uninstallation</span></span>

<span data-ttu-id="0cbee-274">Сведения о том, как удалить Microsoft Defender для конечной точки на macOS с клиентских устройств, см. в материале [Uninstalling.](mac-resources.md#uninstalling)</span><span class="sxs-lookup"><span data-stu-id="0cbee-274">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint on macOS from client devices.</span></span>
