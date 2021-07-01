---
title: Настройка конечной точки Microsoft Defender для политик macOS в Jamf Pro
description: Узнайте, как настроить конечную точку Microsoft Defender для политики macOS в Jamf Pro
keywords: политики, Microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 577eea6e678b6a5d60e5bb8f2fbaaae25d239577
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230071"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a><span data-ttu-id="9714a-104">Настройка конечной точки Microsoft Defender для политик macOS в Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="9714a-104">Set up the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9714a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9714a-105">**Applies to:**</span></span>

- [<span data-ttu-id="9714a-106">Защитник для конечной точки на Mac</span><span class="sxs-lookup"><span data-stu-id="9714a-106">Defender for Endpoint on Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="9714a-107">На этой странице вы сможете найти необходимые действия, чтобы настроить политики macOS в Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="9714a-107">This page will guide you through the steps you need to take to set up macOS policies in Jamf Pro.</span></span>

<span data-ttu-id="9714a-108">Необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9714a-108">You'll need to take the following steps:</span></span>

1. [<span data-ttu-id="9714a-109">Получите пакет onboarding Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9714a-109">Get the Microsoft Defender for Endpoint onboarding package</span></span>](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [<span data-ttu-id="9714a-110">Создание профиля конфигурации в Jamf Pro с помощью пакета onboarding</span><span class="sxs-lookup"><span data-stu-id="9714a-110">Create a configuration profile in Jamf Pro using the onboarding package</span></span>](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [<span data-ttu-id="9714a-111">Настройка параметров конечных точек Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9714a-111">Configure Microsoft Defender for Endpoint settings</span></span>](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [<span data-ttu-id="9714a-112">Настройка параметров уведомлений Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9714a-112">Configure Microsoft Defender for Endpoint notification settings</span></span>](#step-4-configure-notifications-settings)

5. [<span data-ttu-id="9714a-113">Настройка Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="9714a-113">Configure Microsoft AutoUpdate (MAU)</span></span>](#step-5-configure-microsoft-autoupdate-mau)

6. [<span data-ttu-id="9714a-114">Предоставление полного доступа к диску Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9714a-114">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [<span data-ttu-id="9714a-115">Утверждение расширения ядра для Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9714a-115">Approve Kernel extension for Microsoft Defender for Endpoint</span></span>](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [<span data-ttu-id="9714a-116">Утверждение расширений системы для Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9714a-116">Approve System extensions for Microsoft Defender for Endpoint</span></span>](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [<span data-ttu-id="9714a-117">Настройка расширения сети</span><span class="sxs-lookup"><span data-stu-id="9714a-117">Configure Network Extension</span></span>](#step-9-configure-network-extension)

10. [<span data-ttu-id="9714a-118">Расписание сканирования с помощью Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="9714a-118">Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [<span data-ttu-id="9714a-119">Развертывание Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="9714a-119">Deploy Microsoft Defender for Endpoint on macOS</span></span>](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a><span data-ttu-id="9714a-120">Шаг 1. Получить пакет onboarding Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9714a-120">Step 1: Get the Microsoft Defender for Endpoint onboarding package</span></span>

1. <span data-ttu-id="9714a-121">В [Центр безопасности в Microsoft Defender](https://securitycenter.microsoft.com)перейдите **к Параметры > onboarding**.</span><span class="sxs-lookup"><span data-stu-id="9714a-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com), navigate to **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="9714a-122">Выберите macOS в качестве операционной системы и метод управления мобильными устройствами Microsoft Intune в качестве метода развертывания.</span><span class="sxs-lookup"><span data-stu-id="9714a-122">Select macOS as the operating system and Mobile Device Management / Microsoft Intune as the deployment method.</span></span>

    ![Изображение Центр безопасности в Microsoft Defender](images/onboarding-macos.png)

3. <span data-ttu-id="9714a-124">Выберите **пакет загрузки** (WindowsDefenderATPOnboardingPackage.zip).</span><span class="sxs-lookup"><span data-stu-id="9714a-124">Select **Download onboarding package** (WindowsDefenderATPOnboardingPackage.zip).</span></span>

4. <span data-ttu-id="9714a-125">`WindowsDefenderATPOnboardingPackage.zip`Извлечение .</span><span class="sxs-lookup"><span data-stu-id="9714a-125">Extract `WindowsDefenderATPOnboardingPackage.zip`.</span></span>

5. <span data-ttu-id="9714a-126">Скопируйте файл в предпочтительное расположение.</span><span class="sxs-lookup"><span data-stu-id="9714a-126">Copy the file to your preferred location.</span></span> <span data-ttu-id="9714a-127">Пример: `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span><span class="sxs-lookup"><span data-stu-id="9714a-127">For example,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span></span>


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a><span data-ttu-id="9714a-128">Шаг 2. Создание профиля конфигурации в Jamf Pro с помощью бортового пакета</span><span class="sxs-lookup"><span data-stu-id="9714a-128">Step 2: Create a configuration profile in Jamf Pro using the onboarding package</span></span>

1. <span data-ttu-id="9714a-129">Найдите файл `WindowsDefenderATPOnboarding.plist` из предыдущего раздела.</span><span class="sxs-lookup"><span data-stu-id="9714a-129">Locate the file `WindowsDefenderATPOnboarding.plist` from the previous section.</span></span>

   ![Изображение файла WindowsDefenderATPOnboarding](images/plist-onboarding-file.png)


2. <span data-ttu-id="9714a-131">В панели мониторинга Jamf Pro выберите **New**.</span><span class="sxs-lookup"><span data-stu-id="9714a-131">In the Jamf Pro dashboard, select **New**.</span></span>

    ![Изображение создания новой панели мониторинга Pro Jamf](images/jamf-pro-configure-profile.png)

3. <span data-ttu-id="9714a-133">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9714a-133">Enter the following details:</span></span>

   <span data-ttu-id="9714a-134">**Общие**</span><span class="sxs-lookup"><span data-stu-id="9714a-134">**General**</span></span>
   - <span data-ttu-id="9714a-135">Имя: бортовая система MDATP для macOS</span><span class="sxs-lookup"><span data-stu-id="9714a-135">Name: MDATP onboarding for macOS</span></span>
   - <span data-ttu-id="9714a-136">Описание: MDATP EDR для macOS</span><span class="sxs-lookup"><span data-stu-id="9714a-136">Description: MDATP EDR onboarding for macOS</span></span>
   - <span data-ttu-id="9714a-137">Категории: None (нет)</span><span class="sxs-lookup"><span data-stu-id="9714a-137">Category: None</span></span>
   - <span data-ttu-id="9714a-138">Метод рассылки: установка автоматически</span><span class="sxs-lookup"><span data-stu-id="9714a-138">Distribution Method: Install Automatically</span></span>
   - <span data-ttu-id="9714a-139">Уровень: уровень компьютера</span><span class="sxs-lookup"><span data-stu-id="9714a-139">Level: Computer Level</span></span>

4. <span data-ttu-id="9714a-140">В **приложении & настраиваемые Параметры** выберите **Configure**.</span><span class="sxs-lookup"><span data-stu-id="9714a-140">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Изображение настройки приложения и настраиваемых параметров](images/jamfpro-mac-profile.png)

5. <span data-ttu-id="9714a-142">Выберите **Upload файл (PLIST-файл),** а затем **введите параметр Preference Domain:** `com.microsoft.wdav.atp` .</span><span class="sxs-lookup"><span data-stu-id="9714a-142">Select **Upload File (PLIST file)** then in **Preference Domain** enter: `com.microsoft.wdav.atp`.</span></span>

    ![Изображение файла загрузки списка jamfpro](images/jamfpro-plist-upload.png)

    ![Изображение файла списка свойств upload file](images/jamfpro-plist-file.png)

6. <span data-ttu-id="9714a-145">Выберите **Открыть** и выбрать файл вмеяния.</span><span class="sxs-lookup"><span data-stu-id="9714a-145">Select **Open** and select the onboarding file.</span></span>

    ![Изображение бортового файла](images/jamfpro-plist-file-onboard.png)

7. <span data-ttu-id="9714a-147">Выберите **Upload**.</span><span class="sxs-lookup"><span data-stu-id="9714a-147">Select **Upload**.</span></span>

    ![Изображение загрузки файла plist](images/jamfpro-upload-plist.png)

8. <span data-ttu-id="9714a-149">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="9714a-149">Select the **Scope** tab.</span></span>

    ![Изображение вкладки области](images/jamfpro-scope-tab.png)

9. <span data-ttu-id="9714a-151">Выберите целевые компьютеры.</span><span class="sxs-lookup"><span data-stu-id="9714a-151">Select the target computers.</span></span>

    ![Изображение целевых компьютеров](images/jamfpro-target-computer.png)

    ![Изображение целей](images/jamfpro-targets.png)

10. <span data-ttu-id="9714a-154">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-154">Select **Save**.</span></span>

    ![Изображение целевых компьютеров развертывания](images/jamfpro-deployment-target.png)

    ![Изображение выбранных целевых компьютеров](images/jamfpro-target-selected.png)

11. <span data-ttu-id="9714a-157">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9714a-157">Select **Done**.</span></span>

    ![Изображение компьютеров целевой группы](images/jamfpro-target-group.png)

    ![Список профилей конфигурации](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a><span data-ttu-id="9714a-160">Шаг 3. Настройка защитника Майкрософт для параметров конечной точки</span><span class="sxs-lookup"><span data-stu-id="9714a-160">Step 3: Configure Microsoft Defender for Endpoint settings</span></span>

<span data-ttu-id="9714a-161">Вы можете использовать интерфейс JAMF Pro для редактирования отдельных параметров конфигурации Microsoft Defender или использовать устаревший метод, создав Plist конфигурации в текстовом редакторе и загрузив его в JAMF Pro.</span><span class="sxs-lookup"><span data-stu-id="9714a-161">You can either use JAMF Pro GUI to edit individual settings of the Microsoft Defender configuration, or use the legacy method by creating a configuration Plist in a text editor, and uploading it to JAMF Pro.</span></span>

<span data-ttu-id="9714a-162">Обратите внимание, что вы должны использовать точные параметры в качестве домена preference, Microsoft Defender использует только это имя и `com.microsoft.wdav`  `com.microsoft.wdav.ext` загружает управляемые параметры!</span><span class="sxs-lookup"><span data-stu-id="9714a-162">Note that you must use exact `com.microsoft.wdav` as the **Preference Domain**, Microsoft Defender uses only this name and `com.microsoft.wdav.ext` to load its managed settings!</span></span>

<span data-ttu-id="9714a-163">(Версия может использоваться в редких случаях, когда вы предпочитаете использовать метод GUI, но также необходимо настроить параметр, который еще не был добавлен в `com.microsoft.wdav.ext` схему.)</span><span class="sxs-lookup"><span data-stu-id="9714a-163">(The `com.microsoft.wdav.ext` version may be used in rare cases when you prefer to use GUI method, but also need to configure a setting that has not been added to the schema yet.)</span></span>

### <a name="gui-method"></a><span data-ttu-id="9714a-164">Метод GUI</span><span class="sxs-lookup"><span data-stu-id="9714a-164">GUI method</span></span>

1. <span data-ttu-id="9714a-165">Скачайте schema.jsфайл из GitHub Defender и [сохраните](https://github.com/microsoft/mdatp-xplat/tree/master/macos/schema) его в локальном файле:</span><span class="sxs-lookup"><span data-stu-id="9714a-165">Download schema.json file from [Defender's GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/schema) and save it to a local file:</span></span>

    ```bash
    curl -o ~/Documents/schema.json https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/schema/schema.json
    ```

2. <span data-ttu-id="9714a-166">Создайте новый профиль конфигурации в профиле компьютеров > конфигурации, введите следующие сведения на вкладке **General:**</span><span class="sxs-lookup"><span data-stu-id="9714a-166">Create a new Configuration Profile under Computers -> Configuration Profiles, enter the following details on the **General** tab:</span></span>

    ![New profile](images/644e0f3af40c29e80ca1443535b2fe32.png)

    - <span data-ttu-id="9714a-168">Имя: параметры конфигурации MDATP MDAV</span><span class="sxs-lookup"><span data-stu-id="9714a-168">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="9714a-169">Описание:\<blank\></span><span class="sxs-lookup"><span data-stu-id="9714a-169">Description:\<blank\></span></span>
    - <span data-ttu-id="9714a-170">Категория: Нет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9714a-170">Category: None (default)</span></span>
    - <span data-ttu-id="9714a-171">Уровень: уровень компьютера (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9714a-171">Level: Computer Level (default)</span></span>
    - <span data-ttu-id="9714a-172">Метод рассылки: установка автоматически (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9714a-172">Distribution Method: Install Automatically (default)</span></span>

3. <span data-ttu-id="9714a-173">Прокрутите вниз до **вкладки Application & custom Параметры,** выберите внешние **приложения,** нажмите кнопку **Добавить** и использовать настраиваемую схему в качестве источника для использования для домена предпочтений. </span><span class="sxs-lookup"><span data-stu-id="9714a-173">Scroll down to the **Application & Custom Settings** tab, select **External Applications**, click **Add** and use **Custom Schema** as Source to use for the preference domain.</span></span>

    ![Добавление настраиваемой схемы](images/4137189bc3204bb09eed3aabc41afd78.png)

4. <span data-ttu-id="9714a-175">Введите в качестве домена настройки нажмите кнопку Добавить схему и Upload schema.jsфайл, `com.microsoft.wdav` загруженный на шаге  1. </span><span class="sxs-lookup"><span data-stu-id="9714a-175">Enter `com.microsoft.wdav` as the Preference Domain, click on **Add Schema** and **Upload** the schema.json file downloaded on Step 1.</span></span> <span data-ttu-id="9714a-176">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-176">Click **Save**.</span></span>

    ![Upload схемы](images/a6f9f556037c42fabcfdcb1b697244cf.png)

5. <span data-ttu-id="9714a-178">Все поддерживаемые параметры конфигурации Microsoft Defender можно увидеть ниже в **статье Preference Domain Properties.**</span><span class="sxs-lookup"><span data-stu-id="9714a-178">You can see all supported Microsoft Defender configuration settings below, under **Preference Domain Properties**.</span></span> <span data-ttu-id="9714a-179">Нажмите **кнопку Добавить или Удалить свойства,** чтобы выбрать параметры, которыми вы хотите управлять, и нажмите **кнопку Ок,** чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="9714a-179">Click **Add/Remove properties** to select the settings that you want to be managed, and click **Ok** to save your changes.</span></span> <span data-ttu-id="9714a-180">(Параметры невыбранный не будет включен в управляемой конфигурации, конечный пользователь сможет настроить эти параметры на своих машинах.)</span><span class="sxs-lookup"><span data-stu-id="9714a-180">(Settings left unselected will not be included into the managed configuration, an end user will be able to configure those settings on their machines.)</span></span>

    ![Выбор управляемых параметров](images/817b3b760d11467abe9bdd519513f54f.png)

6. <span data-ttu-id="9714a-182">Изменение значений параметров на нужные значения.</span><span class="sxs-lookup"><span data-stu-id="9714a-182">Change values of the settings to desired values.</span></span> <span data-ttu-id="9714a-183">Дополнительные сведения **можно нажать,** чтобы получить документацию для определенного параметра.</span><span class="sxs-lookup"><span data-stu-id="9714a-183">You can click **More information** to get documentation for a particular setting.</span></span> <span data-ttu-id="9714a-184">(Вы можете щелкнуть предварительный просмотр **списка Plist,** чтобы проверить, как будет выглядеть plist конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9714a-184">(You may click **Plist preview** to inspect what the configuration plist will look like.</span></span> <span data-ttu-id="9714a-185">Щелкните **редактор формы,** чтобы вернуться к визуальному редактору.)</span><span class="sxs-lookup"><span data-stu-id="9714a-185">Click **Form editor** to return to the visual editor.)</span></span>

    ![Изменение значений параметров](images/a14a79efd5c041bb8974cb5b12b3a9b6.png)

7. <span data-ttu-id="9714a-187">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="9714a-187">Select the **Scope** tab.</span></span>

    ![Область профилей конфигурации](images/9fc17529e5577eefd773c658ec576a7d.png)

8. <span data-ttu-id="9714a-189">Выберите **машинную группу Contoso.**</span><span class="sxs-lookup"><span data-stu-id="9714a-189">Select **Contoso's Machine Group**.</span></span>

9. <span data-ttu-id="9714a-190">Выберите **Добавить,** а затем **выберите Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-190">Select **Add**, then select **Save**.</span></span>

    ![Параметры конфигурации — добавьте](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Параметры конфигурации — сохранение](images/6f093e42856753a3955cab7ee14f12d9.png)

10. <span data-ttu-id="9714a-193">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9714a-193">Select **Done**.</span></span> <span data-ttu-id="9714a-194">Вы увидите новый профиль **Конфигурация**.</span><span class="sxs-lookup"><span data-stu-id="9714a-194">You'll see the new **Configuration profile**.</span></span>

    ![Параметры конфигурации — сделано](images/dd55405106da0dfc2f50f8d4525b01c8.png)

<span data-ttu-id="9714a-196">Microsoft Defender со временем добавляет новые параметры.</span><span class="sxs-lookup"><span data-stu-id="9714a-196">Microsoft Defender adds new settings over time.</span></span> <span data-ttu-id="9714a-197">Эти новые параметры будут добавлены в схему, а новая версия будет опубликована в Github.</span><span class="sxs-lookup"><span data-stu-id="9714a-197">These new settings will be added to the schema, and a new version will be published to Github.</span></span>
<span data-ttu-id="9714a-198">Для обновления необходимо скачать обновленную схему, изменить существующий профиль конфигурации и изменить схему на вкладке **Application & Custom Параметры.** </span><span class="sxs-lookup"><span data-stu-id="9714a-198">All you need to do to have updates is to download an updated schema, edit existing configuration profile, and **Edit schema** at the **Application & Custom Settings** tab.</span></span>

### <a name="legacy-method"></a><span data-ttu-id="9714a-199">Устаревший метод</span><span class="sxs-lookup"><span data-stu-id="9714a-199">Legacy method</span></span>

1. <span data-ttu-id="9714a-200">Используйте следующие параметры конфигурации Microsoft Defender для конечных точек:</span><span class="sxs-lookup"><span data-stu-id="9714a-200">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

    - <span data-ttu-id="9714a-201">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="9714a-201">enableRealTimeProtection</span></span>
    - <span data-ttu-id="9714a-202">passiveMode</span><span class="sxs-lookup"><span data-stu-id="9714a-202">passiveMode</span></span>

    >[!NOTE]
    ><span data-ttu-id="9714a-203">Не включено по умолчанию, если вы планируете запустить сторонний AV для macOS, установите `true` его.</span><span class="sxs-lookup"><span data-stu-id="9714a-203">Not turned on by default, if you are planning to run a third-party AV for macOS, set it to `true`.</span></span>

    - <span data-ttu-id="9714a-204">исключения</span><span class="sxs-lookup"><span data-stu-id="9714a-204">exclusions</span></span>
    - <span data-ttu-id="9714a-205">excludedPath</span><span class="sxs-lookup"><span data-stu-id="9714a-205">excludedPath</span></span>
    - <span data-ttu-id="9714a-206">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="9714a-206">excludedFileExtension</span></span>
    - <span data-ttu-id="9714a-207">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="9714a-207">excludedFileName</span></span>
    - <span data-ttu-id="9714a-208">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="9714a-208">exclusionsMergePolicy</span></span>
    - <span data-ttu-id="9714a-209">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="9714a-209">allowedThreats</span></span>

    >[!NOTE]
    ><span data-ttu-id="9714a-210">EICAR находится в примере, если вы проходите проверку концепции, удалите ее, особенно если вы тестируете EICAR.</span><span class="sxs-lookup"><span data-stu-id="9714a-210">EICAR is on the sample, if you are going through a proof-of-concept, remove it especially if you are testing EICAR.</span></span>

    - <span data-ttu-id="9714a-211">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="9714a-211">disallowedThreatActions</span></span>
    - <span data-ttu-id="9714a-212">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="9714a-212">potentially_unwanted_application</span></span>
    - <span data-ttu-id="9714a-213">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="9714a-213">archive_bomb</span></span>
    - <span data-ttu-id="9714a-214">cloudService</span><span class="sxs-lookup"><span data-stu-id="9714a-214">cloudService</span></span>
    - <span data-ttu-id="9714a-215">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="9714a-215">automaticSampleSubmission</span></span>
    - <span data-ttu-id="9714a-216">tags</span><span class="sxs-lookup"><span data-stu-id="9714a-216">tags</span></span>
    - <span data-ttu-id="9714a-217">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="9714a-217">hideStatusMenuIcon</span></span>

     <span data-ttu-id="9714a-218">Сведения см. в [списке свойств для профиля конфигурации Jamf.](mac-preferences.md#property-list-for-jamf-configuration-profile)</span><span class="sxs-lookup"><span data-stu-id="9714a-218">For information, see [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).</span></span>

     ```XML
     <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
     <plist version="1.0">
     <dict>
         <key>antivirusEngine</key>
         <dict>
             <key>enableRealTimeProtection</key>
             <true/>
             <key>passiveMode</key>
             <false/>
             <key>exclusions</key>
             <array>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <false/>
                     <key>path</key>
                     <string>/var/log/system.log</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <true/>
                     <key>path</key>
                     <string>/home</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileExtension</string>
                     <key>extension</key>
                     <string>pdf</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileName</string>
                     <key>name</key>
                     <string>cat</string>
                 </dict>
             </array>
             <key>exclusionsMergePolicy</key>
             <string>merge</string>
             <key>allowedThreats</key>
             <array>
                 <string>EICAR-Test-File (not a virus)</string>
             </array>
             <key>disallowedThreatActions</key>
             <array>
                 <string>allow</string>
                 <string>restore</string>
             </array>
             <key>threatTypeSettings</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>potentially_unwanted_application</string>
                     <key>value</key>
                     <string>block</string>
                 </dict>
                 <dict>
                     <key>key</key>
                     <string>archive_bomb</string>
                     <key>value</key>
                     <string>audit</string>
                 </dict>
             </array>
             <key>threatTypeSettingsMergePolicy</key>
             <string>merge</string>
         </dict>
         <key>cloudService</key>
         <dict>
             <key>enabled</key>
             <true/>
             <key>diagnosticLevel</key>
             <string>optional</string>
             <key>automaticSampleSubmission</key>
             <true/>
         </dict>
         <key>edr</key>
         <dict>
             <key>tags</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>GROUP</string>
                     <key>value</key>
                     <string>ExampleTag</string>
                 </dict>
             </array>
         </dict>
         <key>userInterface</key>
         <dict>
             <key>hideStatusMenuIcon</key>
             <false/>
         </dict>
     </dict>
     </plist>
     ```

2. <span data-ttu-id="9714a-219">Сохраните файл как `MDATP_MDAV_configuration_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="9714a-219">Save the file as `MDATP_MDAV_configuration_settings.plist`.</span></span>

3. <span data-ttu-id="9714a-220">В панели мониторинга Jamf Pro откройте **компьютеры,** а также там **профили конфигурации.**</span><span class="sxs-lookup"><span data-stu-id="9714a-220">In the Jamf Pro dashboard, open **Computers**, and there **Configuration Profiles**.</span></span> <span data-ttu-id="9714a-221">Нажмите *кнопку* \* New (и перейдите на **вкладку General.**</span><span class="sxs-lookup"><span data-stu-id="9714a-221">Click \**New(* and switch to the **General** tab.</span></span>

    ![New profile](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. <span data-ttu-id="9714a-223">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9714a-223">Enter the following details:</span></span>

    <span data-ttu-id="9714a-224">**Общие**</span><span class="sxs-lookup"><span data-stu-id="9714a-224">**General**</span></span>

    - <span data-ttu-id="9714a-225">Имя: параметры конфигурации MDATP MDAV</span><span class="sxs-lookup"><span data-stu-id="9714a-225">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="9714a-226">Описание:\<blank\></span><span class="sxs-lookup"><span data-stu-id="9714a-226">Description:\<blank\></span></span>
    - <span data-ttu-id="9714a-227">Категория: Нет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9714a-227">Category: None (default)</span></span>
    - <span data-ttu-id="9714a-228">Метод рассылки: установка автоматически (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9714a-228">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="9714a-229">Уровень: уровень компьютера (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9714a-229">Level: Computer Level(default)</span></span>

    ![Изображение параметров конфигурации MDATP MDAV](images/3160906404bc5a2edf84d1d015894e3b.png)

5. <span data-ttu-id="9714a-231">В **приложении & настраиваемые Параметры** выберите **Configure**.</span><span class="sxs-lookup"><span data-stu-id="9714a-231">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Изображение параметров приложения и настраиваемого](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. <span data-ttu-id="9714a-233">Выберите **Upload файл (PLIST-файл).**</span><span class="sxs-lookup"><span data-stu-id="9714a-233">Select **Upload File (PLIST file)**.</span></span>

    ![Изображение файла plist параметров конфигурации](images/6f85269276b2278eca4bce84f935f87b.png)

7. <span data-ttu-id="9714a-235">В **домене Preferences** введите, а затем `com.microsoft.wdav` выберите Upload **PLIST File**.</span><span class="sxs-lookup"><span data-stu-id="9714a-235">In **Preferences Domain**, enter `com.microsoft.wdav`, then select  **Upload PLIST File**.</span></span>

    ![Изображение домена настроек конфигурации](images/db15f147dd959e872a044184711d7d46.png)

8. <span data-ttu-id="9714a-237">Выберите **выберите файл**.</span><span class="sxs-lookup"><span data-stu-id="9714a-237">Select **Choose File**.</span></span>

    ![Изображение параметров конфигурации выберите файл](images/526e978761fc571cca06907da7b01fd6.png)

9. <span data-ttu-id="9714a-239">Выберите **список MDATP_MDAV_configuration_settings.plist,** а затем **откройте**.</span><span class="sxs-lookup"><span data-stu-id="9714a-239">Select the **MDATP_MDAV_configuration_settings.plist**, then select **Open**.</span></span>

    ![Изображение параметров конфигурации mdatpmdav](images/98acea3750113b8dbab334296e833003.png)

10. <span data-ttu-id="9714a-241">Выберите **Upload**.</span><span class="sxs-lookup"><span data-stu-id="9714a-241">Select **Upload**.</span></span>

    ![Изображение загрузки параметра конфигурации](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Изображение параметров настройки загрузки изображения](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    ><span data-ttu-id="9714a-244">Если вы загрузите файл Intune, вы получите следующую ошибку:</span><span class="sxs-lookup"><span data-stu-id="9714a-244">If you happen to upload the Intune file, you'll get the following error:</span></span><br>
    ><span data-ttu-id="9714a-245">![Изображение загрузки файлов intune параметров конфигурации](images/8e69f867664668796a3b2904896f0436.png)</span><span class="sxs-lookup"><span data-stu-id="9714a-245">![Image of configuration settings intune file upload](images/8e69f867664668796a3b2904896f0436.png)</span></span>


11. <span data-ttu-id="9714a-246">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-246">Select **Save**.</span></span>

    ![Изображение параметров конфигурации Сохранить изображение](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. <span data-ttu-id="9714a-248">Файл загружен.</span><span class="sxs-lookup"><span data-stu-id="9714a-248">The file is uploaded.</span></span>

    ![Изображение загруженного изображения файла параметров конфигурации](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Изображение загруженного файла параметров конфигурации](images/a422e57fe8d45689227e784443e51bd1.png)

13. <span data-ttu-id="9714a-251">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="9714a-251">Select the **Scope** tab.</span></span>

    ![Изображение области параметров конфигурации](images/9fc17529e5577eefd773c658ec576a7d.png)

14. <span data-ttu-id="9714a-253">Выберите **машинную группу Contoso.**</span><span class="sxs-lookup"><span data-stu-id="9714a-253">Select **Contoso's Machine Group**.</span></span>

15. <span data-ttu-id="9714a-254">Выберите **Добавить,** а затем **выберите Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-254">Select **Add**, then select **Save**.</span></span>

    ![Изображение параметров конфигурации addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Изображение параметров конфигурации сохранить добавить](images/6f093e42856753a3955cab7ee14f12d9.png)

16. <span data-ttu-id="9714a-257">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9714a-257">Select **Done**.</span></span> <span data-ttu-id="9714a-258">Вы увидите новый профиль **Конфигурация**.</span><span class="sxs-lookup"><span data-stu-id="9714a-258">You'll see the new **Configuration profile**.</span></span>

    ![Изображение конфигурации параметров конфигурировать изображение профиля](images/dd55405106da0dfc2f50f8d4525b01c8.png)

## <a name="step-4-configure-notifications-settings"></a><span data-ttu-id="9714a-260">Шаг 4. Настройка параметров уведомлений</span><span class="sxs-lookup"><span data-stu-id="9714a-260">Step 4: Configure notifications settings</span></span>

<span data-ttu-id="9714a-261">Эти действия применимы к macOS 10.15 (Catalina) или более новым.</span><span class="sxs-lookup"><span data-stu-id="9714a-261">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="9714a-262">В панели мониторинга Jamf Pro выберите **компьютеры,** а затем **профили конфигурации.**</span><span class="sxs-lookup"><span data-stu-id="9714a-262">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="9714a-263">Нажмите **кнопку New** и введите следующие сведения для **Параметры**:</span><span class="sxs-lookup"><span data-stu-id="9714a-263">Click **New**, and enter the following details for **Options**:</span></span>

    - <span data-ttu-id="9714a-264">Tab **General:**</span><span class="sxs-lookup"><span data-stu-id="9714a-264">Tab **General**:</span></span>
        - <span data-ttu-id="9714a-265">**Имя:** параметры MDATP MDAV Notification</span><span class="sxs-lookup"><span data-stu-id="9714a-265">**Name**: MDATP MDAV Notification settings</span></span>
        - <span data-ttu-id="9714a-266">**Описание:** macOS 10.15 (Catalina) или более новый</span><span class="sxs-lookup"><span data-stu-id="9714a-266">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="9714a-267">**Категория:** Нет *(по умолчанию)*</span><span class="sxs-lookup"><span data-stu-id="9714a-267">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="9714a-268">**Метод рассылки:** Установка автоматически *(по умолчанию)*</span><span class="sxs-lookup"><span data-stu-id="9714a-268">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="9714a-269">**Уровень**: Уровень компьютера *(по умолчанию)*</span><span class="sxs-lookup"><span data-stu-id="9714a-269">**Level**: Computer Level *(default)*</span></span>

        ![Изображение нового экрана профиля конфигурации macOS](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - <span data-ttu-id="9714a-271">Tab **Notifications,** **нажмите кнопку Добавить** и введите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="9714a-271">Tab **Notifications**, click **Add**, and enter the following values:</span></span>
        - <span data-ttu-id="9714a-272">**Bundle ID:**`com.microsoft.wdav.tray`</span><span class="sxs-lookup"><span data-stu-id="9714a-272">**Bundle ID**: `com.microsoft.wdav.tray`</span></span>
        - <span data-ttu-id="9714a-273">**Критические оповещения:** нажмите **кнопку Отключение**</span><span class="sxs-lookup"><span data-stu-id="9714a-273">**Critical Alerts**: Click **Disable**</span></span>
        - <span data-ttu-id="9714a-274">**Уведомления:** щелкните **Включить**</span><span class="sxs-lookup"><span data-stu-id="9714a-274">**Notifications**: Click **Enable**</span></span>
        - <span data-ttu-id="9714a-275">**Тип оповещения баннера:** **Выберите включить и** временно **(по** *умолчанию)*</span><span class="sxs-lookup"><span data-stu-id="9714a-275">**Banner alert type**: Select **Include** and **Temporary** *(default)*</span></span>
        - <span data-ttu-id="9714a-276">**Уведомления на экране блокировки:** нажмите кнопку **Скрыть**</span><span class="sxs-lookup"><span data-stu-id="9714a-276">**Notifications on lock screen**: Click **Hide**</span></span>
        - <span data-ttu-id="9714a-277">**Уведомления в Центре уведомлений:** щелкните **отображение**</span><span class="sxs-lookup"><span data-stu-id="9714a-277">**Notifications in Notification Center**: Click **Display**</span></span>
        - <span data-ttu-id="9714a-278">**Значок приложения Badge:** Щелкните **Дисплей**</span><span class="sxs-lookup"><span data-stu-id="9714a-278">**Badge app icon**: Click **Display**</span></span>

        ![Изображение лотка уведомлений mdatpmdav параметров конфигурации](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - <span data-ttu-id="9714a-280">Tab **Notifications**, **щелкните Добавить** еще раз, прокрутите вниз, чтобы **новые уведомления Параметры**</span><span class="sxs-lookup"><span data-stu-id="9714a-280">Tab **Notifications**, click **Add** one more time, scroll down to **New Notifications Settings**</span></span>
        - <span data-ttu-id="9714a-281">**Bundle ID:**`com.microsoft.autoupdate2`</span><span class="sxs-lookup"><span data-stu-id="9714a-281">**Bundle ID**: `com.microsoft.autoupdate2`</span></span>
        - <span data-ttu-id="9714a-282">Настройка остальных параметров на те же значения, что и выше</span><span class="sxs-lookup"><span data-stu-id="9714a-282">Configure the rest of the settings to the same values as above</span></span>

        ![Изображение параметров конфигурации mdatpmdav notifications mau](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        <span data-ttu-id="9714a-284">Обратите внимание, что теперь у вас есть две "таблицы" с конфигурациями уведомлений, одна для bundle **ID: com.microsoft.wdav.tray** и другая для **Bundle ID: com.microsoft.autoupdate2**.</span><span class="sxs-lookup"><span data-stu-id="9714a-284">Note that now you have two 'tables' with notification configurations, one for **Bundle ID: com.microsoft.wdav.tray**, and another for **Bundle ID: com.microsoft.autoupdate2**.</span></span> <span data-ttu-id="9714a-285">Хотя вы можете настроить параметры оповещения в зависимости от ваших требований, набор ID должен быть точно таким же, как описано ранее, и **включить** переключатель должен быть **включен** для **уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="9714a-285">While you can configure alert settings per your requirements, Bundle IDs must be exactly the same as described before, and **Include** switch must be **On** for **Notifications**.</span></span>

3. <span data-ttu-id="9714a-286">Выберите **вкладку Область,** а **затем** добавьте .</span><span class="sxs-lookup"><span data-stu-id="9714a-286">Select the **Scope** tab, then select **Add**.</span></span>

    ![Добавлено изображение области параметров конфигурации](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. <span data-ttu-id="9714a-288">Выберите **машинную группу Contoso.**</span><span class="sxs-lookup"><span data-stu-id="9714a-288">Select **Contoso's Machine Group**.</span></span>

5. <span data-ttu-id="9714a-289">Выберите **Добавить,** а затем **выберите Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-289">Select **Add**, then select **Save**.</span></span>

    ![Image of configuration settings contoso machine grp save](images/09a275e321268e5e3ac0c0865d3e2db5.png)

    ![Изображение параметров конфигурации добавить сохранить](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. <span data-ttu-id="9714a-292">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9714a-292">Select **Done**.</span></span> <span data-ttu-id="9714a-293">Вы увидите новый профиль **Конфигурация**.</span><span class="sxs-lookup"><span data-stu-id="9714a-293">You'll see the new **Configuration profile**.</span></span>
    <span data-ttu-id="9714a-294">![Изображение параметра конфигурации сделано img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span><span class="sxs-lookup"><span data-stu-id="9714a-294">![Image of configuration setting done img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span></span>

## <a name="step-5-configure-microsoft-autoupdate-mau"></a><span data-ttu-id="9714a-295">Шаг 5. Настройка Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="9714a-295">Step 5: Configure Microsoft AutoUpdate (MAU)</span></span>

1. <span data-ttu-id="9714a-296">Используйте следующие параметры конфигурации Microsoft Defender для конечных точек:</span><span class="sxs-lookup"><span data-stu-id="9714a-296">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

      ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
   <plist version="1.0">
   <dict>
    <key>ChannelName</key>
    <string>Current</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
   </dict>
   </plist>
   ```

2. <span data-ttu-id="9714a-297">Сохраните его как `MDATP_MDAV_MAU_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="9714a-297">Save it as `MDATP_MDAV_MAU_settings.plist`.</span></span>

3. <span data-ttu-id="9714a-298">В панели мониторинга Jamf Pro выберите **General**.</span><span class="sxs-lookup"><span data-stu-id="9714a-298">In the Jamf Pro dashboard, select **General**.</span></span>

    ![Изображение общего образа настройки конфигурации](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. <span data-ttu-id="9714a-300">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9714a-300">Enter the following details:</span></span>

    <span data-ttu-id="9714a-301">**Общие**</span><span class="sxs-lookup"><span data-stu-id="9714a-301">**General**</span></span>

    - <span data-ttu-id="9714a-302">Имя: параметры MDATP MDAV MAU</span><span class="sxs-lookup"><span data-stu-id="9714a-302">Name: MDATP MDAV MAU settings</span></span>
    - <span data-ttu-id="9714a-303">Описание. Параметры Microsoft AutoUpdate для MDATP для macOS</span><span class="sxs-lookup"><span data-stu-id="9714a-303">Description: Microsoft AutoUpdate settings for MDATP for macOS</span></span>
    - <span data-ttu-id="9714a-304">Категория: Нет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9714a-304">Category: None (default)</span></span>
    - <span data-ttu-id="9714a-305">Метод рассылки: установка автоматически (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9714a-305">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="9714a-306">Уровень: уровень компьютера (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9714a-306">Level: Computer Level(default)</span></span>

5. <span data-ttu-id="9714a-307">В **приложении & настраиваемые Параметры** выберите **Configure**.</span><span class="sxs-lookup"><span data-stu-id="9714a-307">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Изображение приложения настройки конфигурации и настраиваемые параметры](images/1f72e9c15eaafcabf1504397e99be311.png)

6. <span data-ttu-id="9714a-309">Выберите **Upload файл (PLIST-файл).**</span><span class="sxs-lookup"><span data-stu-id="9714a-309">Select **Upload File (PLIST file)**.</span></span>

    ![Изображение plist настройки конфигурации](images/1213872db5833aa8be535da57653219f.png)

7. <span data-ttu-id="9714a-311">В **домене Preference** введите: `com.microsoft.autoupdate2` затем выберите Upload **PLIST File**.</span><span class="sxs-lookup"><span data-stu-id="9714a-311">In **Preference Domain** enter: `com.microsoft.autoupdate2`, then select **Upload PLIST File**.</span></span>

    ![Изображение предварительного домена настройки настройки](images/1213872db5833aa8be535da57653219f.png)

8. <span data-ttu-id="9714a-313">Выберите **выберите файл**.</span><span class="sxs-lookup"><span data-stu-id="9714a-313">Select **Choose File**.</span></span>

    ![Изображение параметра конфигурации choosefile](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. <span data-ttu-id="9714a-315">Выберите **MDATP_MDAV_MAU_settings.plist**.</span><span class="sxs-lookup"><span data-stu-id="9714a-315">Select **MDATP_MDAV_MAU_settings.plist**.</span></span>

    ![Изображение параметров настройки mdatpmdavmau](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. <span data-ttu-id="9714a-317">Выберите **Upload**.</span><span class="sxs-lookup"><span data-stu-id="9714a-317">Select **Upload**.</span></span>
    <span data-ttu-id="9714a-318">![Изображение настройки настройки uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span><span class="sxs-lookup"><span data-stu-id="9714a-318">![Image of configuration setting uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span></span>

    ![Изображение настройки настройки uplimg](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. <span data-ttu-id="9714a-320">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-320">Select **Save**.</span></span>

    ![Изображение параметра конфигурации saveimg](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. <span data-ttu-id="9714a-322">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="9714a-322">Select the **Scope** tab.</span></span>

     ![Изображение scopetab настройки конфигурации](images/10ab98358b2d602f3f67618735fa82fb.png)

13. <span data-ttu-id="9714a-324">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-324">Select **Add**.</span></span>

    ![Изображение параметра конфигурации addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Изображение параметра конфигурации addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Изображение параметра конфигурации addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. <span data-ttu-id="9714a-328">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9714a-328">Select **Done**.</span></span>

    ![Image of configuration setting doneimage](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="9714a-330">Шаг 6. Предоставление полного доступа к диску Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9714a-330">Step 6: Grant full disk access to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="9714a-331">В панели мониторинга Jamf Pro выберите **профили конфигурации.**</span><span class="sxs-lookup"><span data-stu-id="9714a-331">In the Jamf Pro dashboard, select **Configuration Profiles**.</span></span>

    ![Изображение профиля конфигурации настройки конфигурации](images/264493cd01e62c7085659d6fdc26dc91.png)

2. <span data-ttu-id="9714a-333">Выберите **+ Новый**.</span><span class="sxs-lookup"><span data-stu-id="9714a-333">Select **+ New**.</span></span>

3. <span data-ttu-id="9714a-334">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9714a-334">Enter the following details:</span></span>

    <span data-ttu-id="9714a-335">**Общие**</span><span class="sxs-lookup"><span data-stu-id="9714a-335">**General**</span></span>
    - <span data-ttu-id="9714a-336">Имя: MDATP MDAV — предоставление полного доступа к EDR и AV</span><span class="sxs-lookup"><span data-stu-id="9714a-336">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span></span>
    - <span data-ttu-id="9714a-337">Описание. Для macOS Catalina или более нового управления политикой конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="9714a-337">Description: On macOS Catalina or newer, the new Privacy Preferences Policy Control</span></span>
    - <span data-ttu-id="9714a-338">Категории: None (нет)</span><span class="sxs-lookup"><span data-stu-id="9714a-338">Category: None</span></span>
    - <span data-ttu-id="9714a-339">Метод рассылки: установка автоматически</span><span class="sxs-lookup"><span data-stu-id="9714a-339">Distribution method: Install Automatically</span></span>
    - <span data-ttu-id="9714a-340">Уровень: уровень компьютера</span><span class="sxs-lookup"><span data-stu-id="9714a-340">Level: Computer level</span></span>


    ![Изображение общего параметра настройки конфигурации](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. <span data-ttu-id="9714a-342">В **Настройка политики настройки предпочтений конфиденциальности выберите** **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="9714a-342">In **Configure Privacy Preferences Policy Control** select **Configure**.</span></span>

    ![Изображение управления политикой конфиденциальности конфигурации](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. <span data-ttu-id="9714a-344">В правилах управления **политиками конфиденциальности** введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9714a-344">In **Privacy Preferences Policy Control**, enter the following details:</span></span>

    - <span data-ttu-id="9714a-345">Идентификатор: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="9714a-345">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="9714a-346">Тип идентификатора: идентификатор пакета</span><span class="sxs-lookup"><span data-stu-id="9714a-346">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="9714a-347">Требование кода: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="9714a-347">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>


    ![Изображение сведений о настройке политики настройки конфиденциальности.](images/22cb439de958101c0a12f3038f905b27.png)

6. <span data-ttu-id="9714a-349">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-349">Select **+ Add**.</span></span>

    ![Изображение параметра конфигурации добавить системную политику во все файлы](images/bd93e78b74c2660a0541af4690dd9485.png)

    - <span data-ttu-id="9714a-351">В приложении или службе: установите **systemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="9714a-351">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="9714a-352">В статье "Доступ": набор **разрешить**</span><span class="sxs-lookup"><span data-stu-id="9714a-352">Under "access": Set to **Allow**</span></span>

7. <span data-ttu-id="9714a-353">Выберите **Сохранить** (не тот, который внизу справа).</span><span class="sxs-lookup"><span data-stu-id="9714a-353">Select **Save** (not the one at the bottom right).</span></span>

    ![Изображение параметра конфигурации сохранить изображения](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. <span data-ttu-id="9714a-355">Щелкните `+` знак рядом с **доступом к приложению,** чтобы добавить новую запись.</span><span class="sxs-lookup"><span data-stu-id="9714a-355">Click the `+` sign next to **App Access** to add a new entry.</span></span>

    ![Изображение доступа к приложению настройки конфигурации](images/tcc-add-entry.png)

9. <span data-ttu-id="9714a-357">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9714a-357">Enter the following details:</span></span>

    - <span data-ttu-id="9714a-358">Идентификатор: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="9714a-358">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="9714a-359">Тип идентификатора: идентификатор пакета</span><span class="sxs-lookup"><span data-stu-id="9714a-359">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="9714a-360">Требование кода: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="9714a-360">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

10. <span data-ttu-id="9714a-361">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-361">Select **+ Add**.</span></span>

    ![Изображение записи epsext параметра конфигурации tcc](images/tcc-epsext-entry.png)

    - <span data-ttu-id="9714a-363">В приложении или службе: установите **systemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="9714a-363">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="9714a-364">В статье "Доступ": набор **разрешить**</span><span class="sxs-lookup"><span data-stu-id="9714a-364">Under "access": Set to **Allow**</span></span>

11. <span data-ttu-id="9714a-365">Выберите **Сохранить** (не тот, который внизу справа).</span><span class="sxs-lookup"><span data-stu-id="9714a-365">Select **Save** (not the one at the bottom right).</span></span>

    ![Изображение параметра конфигурации tcc epsext image2](images/tcc-epsext-entry2.png)

12. <span data-ttu-id="9714a-367">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="9714a-367">Select the **Scope** tab.</span></span>

    ![Изображение области настройки конфигурации](images/2c49b16cd112729b3719724f581e6882.png)

13. <span data-ttu-id="9714a-369">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-369">Select **+ Add**.</span></span>

    ![Изображение надстройки параметра конфигурации](images/57cef926d1b9260fb74a5f460cee887a.png)

14. <span data-ttu-id="9714a-371">Выберите **группы** компьютеров > **под названием** группы > **выберите MachineGroup Contoso.**</span><span class="sxs-lookup"><span data-stu-id="9714a-371">Select **Computer Groups** > under **Group Name** > select **Contoso's MachineGroup**.</span></span>

    ![Изображение параметра конфигурации contoso machinegrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. <span data-ttu-id="9714a-373">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-373">Select **Add**.</span></span>

16. <span data-ttu-id="9714a-374">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-374">Select **Save**.</span></span>

17. <span data-ttu-id="9714a-375">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9714a-375">Select **Done**.</span></span>

    ![Изображение donimg параметра конфигурации](images/809cef630281b64b8f07f20913b0039b.png)

    ![Изображение параметра конфигурации donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)

<span data-ttu-id="9714a-378">Кроме того, вы можете скачать [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) и загрузить его в профили конфигурации JAMF, как описано в развертывании пользовательских профилей конфигурации с помощью [Jamf Pro| Метод 2. Upload профиль конфигурации в Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span><span class="sxs-lookup"><span data-stu-id="9714a-378">Alternatively, you can download [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="9714a-379">Шаг 7. Утверждение расширения ядра для Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9714a-379">Step 7: Approve Kernel extension for Microsoft Defender for Endpoint</span></span>

> [!CAUTION]
> <span data-ttu-id="9714a-380">Устройства Apple Silicon (M1) не поддерживают KEXT.</span><span class="sxs-lookup"><span data-stu-id="9714a-380">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="9714a-381">Установка профиля конфигурации, состоящего из политик KEXT, не будет работать на этих устройствах.</span><span class="sxs-lookup"><span data-stu-id="9714a-381">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="9714a-382">В **профилях конфигурации** выберите **+ New**.</span><span class="sxs-lookup"><span data-stu-id="9714a-382">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Снимок экрана сообщения в социальных сетях, автоматически созданный](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="9714a-384">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9714a-384">Enter the following details:</span></span>

    <span data-ttu-id="9714a-385">**Общие**</span><span class="sxs-lookup"><span data-stu-id="9714a-385">**General**</span></span>

    - <span data-ttu-id="9714a-386">Имя. Расширение Ядра MDAV MDAV</span><span class="sxs-lookup"><span data-stu-id="9714a-386">Name: MDATP MDAV Kernel Extension</span></span>
    - <span data-ttu-id="9714a-387">Описание: расширение ядра MDATP (kext)</span><span class="sxs-lookup"><span data-stu-id="9714a-387">Description: MDATP kernel extension (kext)</span></span>
    - <span data-ttu-id="9714a-388">Категории: None (нет)</span><span class="sxs-lookup"><span data-stu-id="9714a-388">Category: None</span></span>
    - <span data-ttu-id="9714a-389">Метод рассылки: установка автоматически</span><span class="sxs-lookup"><span data-stu-id="9714a-389">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="9714a-390">Уровень: уровень компьютера</span><span class="sxs-lookup"><span data-stu-id="9714a-390">Level: Computer Level</span></span>

    ![Изображение параметров конфигурации ядра mdatpmdav](images/24e290f5fc309932cf41f3a280d22c14.png)

3. <span data-ttu-id="9714a-392">В **Настройка утвержденных расширений ядра** выберите **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="9714a-392">In **Configure Approved Kernel Extensions** select **Configure**.</span></span>

    ![Изображение параметров конфигурации, утвержденных ext ядра](images/30be88b63abc5e8dde11b73f1b1ade6a.png)


4. <span data-ttu-id="9714a-394">В **утвержденных расширениях ядра** введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9714a-394">In **Approved Kernel Extensions** Enter the following details:</span></span>

    - <span data-ttu-id="9714a-395">Имя отображения: Корпорация Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9714a-395">Display Name: Microsoft Corp.</span></span>
    - <span data-ttu-id="9714a-396">ID команды: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="9714a-396">Team ID: UBF8T346G9</span></span>

    ![Изображение параметров конфигурации расширения ядра appr](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. <span data-ttu-id="9714a-398">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="9714a-398">Select the **Scope** tab.</span></span>

    ![Image of configuration settings scope tab img](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="9714a-400">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-400">Select **+ Add**.</span></span>

7. <span data-ttu-id="9714a-401">Выберите **группы** > **в соответствии с названием** группы > выберите **группу машин Contoso.**</span><span class="sxs-lookup"><span data-stu-id="9714a-401">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="9714a-402">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-402">Select **+ Add**.</span></span>

    ![Изображение параметров конфигурации добавить изображения](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="9714a-404">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-404">Select **Save**.</span></span>

    ![Изображение параметров конфигурации saveimag](images/0add8019b85a453b47fa5c402c72761b.png)

10. <span data-ttu-id="9714a-406">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9714a-406">Select **Done**.</span></span>

    ![Изображение параметров конфигурации doneimag](images/1c9bd3f68db20b80193dac18f33c22d0.png)

<span data-ttu-id="9714a-408">Кроме того, вы можете скачать [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) и загрузить его в профили конфигурации JAMF, как описано в развертывании пользовательских профилей конфигурации с помощью [Jamf Pro| Метод 2. Upload профиль конфигурации в Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span><span class="sxs-lookup"><span data-stu-id="9714a-408">Alternatively, you can download [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="9714a-409">Шаг 8. Утверждение расширений системы для Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9714a-409">Step 8: Approve System extensions for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="9714a-410">В **профилях конфигурации** выберите **+ New**.</span><span class="sxs-lookup"><span data-stu-id="9714a-410">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Снимок экрана сообщения в социальных сетях, автоматически созданный](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="9714a-412">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9714a-412">Enter the following details:</span></span>

    <span data-ttu-id="9714a-413">**Общие**</span><span class="sxs-lookup"><span data-stu-id="9714a-413">**General**</span></span>

    - <span data-ttu-id="9714a-414">Имя: MDATP MDAV System Extensions</span><span class="sxs-lookup"><span data-stu-id="9714a-414">Name: MDATP MDAV System Extensions</span></span>
    - <span data-ttu-id="9714a-415">Описание: расширения системы MDATP</span><span class="sxs-lookup"><span data-stu-id="9714a-415">Description: MDATP system extensions</span></span>
    - <span data-ttu-id="9714a-416">Категории: None (нет)</span><span class="sxs-lookup"><span data-stu-id="9714a-416">Category: None</span></span>
    - <span data-ttu-id="9714a-417">Метод рассылки: установка автоматически</span><span class="sxs-lookup"><span data-stu-id="9714a-417">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="9714a-418">Уровень: уровень компьютера</span><span class="sxs-lookup"><span data-stu-id="9714a-418">Level: Computer Level</span></span>

    ![Изображение параметров конфигурации sysext new prof](images/sysext-new-profile.png)

3. <span data-ttu-id="9714a-420">В **расширении системы** выберите **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="9714a-420">In **System Extensions** select **Configure**.</span></span>

   ![Изображение параметров конфигурации sysext config](images/sysext-configure.png)

4. <span data-ttu-id="9714a-422">В **расширении системы введите** следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9714a-422">In **System Extensions** enter the following details:</span></span>

   - <span data-ttu-id="9714a-423">Имя отображения: расширения системы Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="9714a-423">Display Name: Microsoft Corp. System Extensions</span></span>
   - <span data-ttu-id="9714a-424">Типы расширения системы: разрешенные расширения системы</span><span class="sxs-lookup"><span data-stu-id="9714a-424">System Extension Types: Allowed System Extensions</span></span>
   - <span data-ttu-id="9714a-425">Идентификатор команды: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="9714a-425">Team Identifier: UBF8T346G9</span></span>
   - <span data-ttu-id="9714a-426">Разрешенные расширения системы:</span><span class="sxs-lookup"><span data-stu-id="9714a-426">Allowed System Extensions:</span></span>
     - <span data-ttu-id="9714a-427">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="9714a-427">**com.microsoft.wdav.epsext**</span></span>
     - <span data-ttu-id="9714a-428">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="9714a-428">**com.microsoft.wdav.netext**</span></span>

    ![Изображение параметров конфигурации sysextconfig2](images/sysext-configure2.png)

5. <span data-ttu-id="9714a-430">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="9714a-430">Select the **Scope** tab.</span></span>

    ![Image of configuration settings scopeimage](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="9714a-432">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-432">Select **+ Add**.</span></span>

7. <span data-ttu-id="9714a-433">Выберите **группы** > **в соответствии с названием** группы > выберите **группу машин Contoso.**</span><span class="sxs-lookup"><span data-stu-id="9714a-433">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="9714a-434">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-434">Select **+ Add**.</span></span>

   ![Изображение параметров конфигурации addima](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="9714a-436">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-436">Select **Save**.</span></span>

   ![Изображение параметров конфигурации sysext](images/sysext-scope.png)

10. <span data-ttu-id="9714a-438">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9714a-438">Select **Done**.</span></span>

    ![Изображение параметров конфигурации sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a><span data-ttu-id="9714a-440">Шаг 9. Настройка расширения сети</span><span class="sxs-lookup"><span data-stu-id="9714a-440">Step 9: Configure Network Extension</span></span>

<span data-ttu-id="9714a-441">В рамках возможностей обнаружения конечных точек и ответов Microsoft Defender для конечной точки на macOS проверяет трафик розетки и передает эти сведения на Центр безопасности в Microsoft Defender портал.</span><span class="sxs-lookup"><span data-stu-id="9714a-441">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="9714a-442">Следующая политика позволяет сетевому расширению выполнять эту функцию.</span><span class="sxs-lookup"><span data-stu-id="9714a-442">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="9714a-443">Эти действия применимы к macOS 10.15 (Catalina) или более новым.</span><span class="sxs-lookup"><span data-stu-id="9714a-443">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="9714a-444">В панели мониторинга Jamf Pro выберите **компьютеры,** а затем **профили конфигурации.**</span><span class="sxs-lookup"><span data-stu-id="9714a-444">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="9714a-445">Нажмите **кнопку New** и введите следующие сведения для **Параметры**:</span><span class="sxs-lookup"><span data-stu-id="9714a-445">Click **New**, and enter the following details for **Options**:</span></span>

    - <span data-ttu-id="9714a-446">Tab **General:**</span><span class="sxs-lookup"><span data-stu-id="9714a-446">Tab **General**:</span></span>
        - <span data-ttu-id="9714a-447">**Имя:** Расширение сети ATP Защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9714a-447">**Name**: Microsoft Defender ATP Network Extension</span></span>
        - <span data-ttu-id="9714a-448">**Описание:** macOS 10.15 (Catalina) или более новый</span><span class="sxs-lookup"><span data-stu-id="9714a-448">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="9714a-449">**Категория:** Нет *(по умолчанию)*</span><span class="sxs-lookup"><span data-stu-id="9714a-449">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="9714a-450">**Метод рассылки:** Установка автоматически *(по умолчанию)*</span><span class="sxs-lookup"><span data-stu-id="9714a-450">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="9714a-451">**Уровень**: Уровень компьютера *(по умолчанию)*</span><span class="sxs-lookup"><span data-stu-id="9714a-451">**Level**: Computer Level *(default)*</span></span>

    - <span data-ttu-id="9714a-452">Фильтр **контента вкладок:**</span><span class="sxs-lookup"><span data-stu-id="9714a-452">Tab **Content Filter**:</span></span>
        - <span data-ttu-id="9714a-453">**Имя фильтра:** фильтр контента ATP Защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9714a-453">**Filter Name**: Microsoft Defender ATP Content Filter</span></span>
        - <span data-ttu-id="9714a-454">**Идентификатор:**`com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="9714a-454">**Identifier**: `com.microsoft.wdav`</span></span>
        - <span data-ttu-id="9714a-455">Оставьте **адрес службы**, **организация**, **имя пользователя**, **пароль**, **сертификат** пустой (**Включить** *не* выбран)</span><span class="sxs-lookup"><span data-stu-id="9714a-455">Leave **Service Address**, **Organization**, **User Name**, **Password**, **Certificate** blank (**Include** is *not* selected)</span></span>
        - <span data-ttu-id="9714a-456">**Порядок фильтрации:** Инспектор</span><span class="sxs-lookup"><span data-stu-id="9714a-456">**Filter Order**: Inspector</span></span>
        - <span data-ttu-id="9714a-457">**Фильтр socket:**`com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="9714a-457">**Socket Filter**: `com.microsoft.wdav.netext`</span></span>
        - <span data-ttu-id="9714a-458">**Назначенное требование фильтра socket:**`identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="9714a-458">**Socket Filter Designated Requirement**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
        - <span data-ttu-id="9714a-459">Оставьте **поля сетевого** фильтра пустыми **(Включить** *не* выбрано)</span><span class="sxs-lookup"><span data-stu-id="9714a-459">Leave **Network Filter** fields blank (**Include** is *not* selected)</span></span>

        <span data-ttu-id="9714a-460">Обратите **внимание, что идентификатор,** **фильтр socket и** **фильтр socket** назначенные точные значения требования, указанные выше.</span><span class="sxs-lookup"><span data-stu-id="9714a-460">Note that **Identifier**, **Socket Filter** and **Socket Filter Designated Requirement** exact values as specified above.</span></span>

        ![Изображение параметра конфигурации mdatpmdav](images/netext-create-profile.png)

3. <span data-ttu-id="9714a-462">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="9714a-462">Select the **Scope** tab.</span></span>

   ![Изображение параметров конфигурации вкладки sco](images/0df36fc308ba569db204ee32db3fb40a.png)

4. <span data-ttu-id="9714a-464">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-464">Select **+ Add**.</span></span>

5. <span data-ttu-id="9714a-465">Выберите **группы** > **в соответствии с названием** группы > выберите **группу машин Contoso.**</span><span class="sxs-lookup"><span data-stu-id="9714a-465">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

6. <span data-ttu-id="9714a-466">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-466">Select **+ Add**.</span></span>

    ![Изображение adim параметров конфигурации](images/0dde8a4c41110dbc398c485433a81359.png)

7. <span data-ttu-id="9714a-468">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-468">Select **Save**.</span></span>

    ![Изображение параметров конфигурации savimg netextscop](images/netext-scope.png)

8. <span data-ttu-id="9714a-470">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9714a-470">Select **Done**.</span></span>

    ![Изображение параметров конфигурации netextfinal](images/netext-final.png)

<span data-ttu-id="9714a-472">Кроме того, вы можете скачать [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) и загрузить его в профили конфигурации JAMF, как описано в развертывании пользовательских профилей конфигурации с помощью [Jamf Pro| Метод 2. Upload профиль конфигурации в Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span><span class="sxs-lookup"><span data-stu-id="9714a-472">Alternatively, you can download [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>


## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="9714a-473">Шаг 10. Расписание сканирования с помощью Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="9714a-473">Step 10: Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>
<span data-ttu-id="9714a-474">Следуйте инструкциям по [проверке расписания с помощью Microsoft Defender для конечной точки на macOS.](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)</span><span class="sxs-lookup"><span data-stu-id="9714a-474">Follow the instructions on [Schedule scans with Microsoft Defender for Endpoint on macOS](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span></span>


## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="9714a-475">Шаг 11. Развертывание Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="9714a-475">Step 11: Deploy Microsoft Defender for Endpoint on macOS</span></span>

1. <span data-ttu-id="9714a-476">Перейдите к сохраненным `wdav.pkg` местам.</span><span class="sxs-lookup"><span data-stu-id="9714a-476">Navigate to where you saved `wdav.pkg`.</span></span>

    ![Изображение проводника файлов wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. <span data-ttu-id="9714a-478">Переименуй его в `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="9714a-478">Rename it to `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![Изображение проводника файлов1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. <span data-ttu-id="9714a-480">Откройте панель мониторинга Pro Jamf.</span><span class="sxs-lookup"><span data-stu-id="9714a-480">Open the Jamf Pro dashboard.</span></span>

    ![Изображение параметров конфигурации jamfpro](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. <span data-ttu-id="9714a-482">Выберите компьютер и нажмите значок передач в верхней части, а затем выберите **управление компьютером**.</span><span class="sxs-lookup"><span data-stu-id="9714a-482">Select your computer and click the gear icon at the top, then select **Computer Management**.</span></span>

    ![Изображение параметров конфигурации compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. <span data-ttu-id="9714a-484">В **пакетах** выберите **+ New**.</span><span class="sxs-lookup"><span data-stu-id="9714a-484">In **Packages**, select **+ New**.</span></span>
    <span data-ttu-id="9714a-485">![Изображение, содержащее описание птицы, автоматически генерируется новый пакет](images/57aa4d21e2ccc65466bf284701d4e961.png)</span><span class="sxs-lookup"><span data-stu-id="9714a-485">![A picture containing bird Description automatically generated package new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span></span>

6. <span data-ttu-id="9714a-486">В **новом пакете** введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9714a-486">In **New Package** Enter the following details:</span></span>

    <span data-ttu-id="9714a-487">**Общая вкладка**</span><span class="sxs-lookup"><span data-stu-id="9714a-487">**General tab**</span></span>
    - <span data-ttu-id="9714a-488">Имя отображения. Оставьте его пустым на данный момент.</span><span class="sxs-lookup"><span data-stu-id="9714a-488">Display Name: Leave it blank for now.</span></span> <span data-ttu-id="9714a-489">Потому что она будет сброшена при выборе pkg.</span><span class="sxs-lookup"><span data-stu-id="9714a-489">Because it will be reset when you choose your pkg.</span></span>
    - <span data-ttu-id="9714a-490">Категория: Нет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9714a-490">Category: None (default)</span></span>
    - <span data-ttu-id="9714a-491">Имя файла: выберите файл</span><span class="sxs-lookup"><span data-stu-id="9714a-491">Filename: Choose File</span></span>

    ![Изображение общей вкладки параметры конфигурации](images/21de3658bf58b1b767a17358a3f06341.png)

    <span data-ttu-id="9714a-493">Откройте файл и указать его `wdav.pkg` или `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="9714a-493">Open the file and point it to `wdav.pkg` or `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![Снимок экрана компьютера Описание, автоматически сгенерированное](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. <span data-ttu-id="9714a-495">Выберите **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="9714a-495">Select **Open**.</span></span> <span data-ttu-id="9714a-496">Установите **имя отображения в** **Microsoft Defender Advanced Threat Protection и антивирусная программа в Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="9714a-496">Set the **Display Name** to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    <span data-ttu-id="9714a-497">**Файл Manifest не** требуется.</span><span class="sxs-lookup"><span data-stu-id="9714a-497">**Manifest File** is not required.</span></span> <span data-ttu-id="9714a-498">Microsoft Defender для конечной точки работает без Файла Манифеста.</span><span class="sxs-lookup"><span data-stu-id="9714a-498">Microsoft Defender for Endpoint works without Manifest File.</span></span>

    <span data-ttu-id="9714a-499">**Вкладка с параметрами**</span><span class="sxs-lookup"><span data-stu-id="9714a-499">**Options tab**</span></span><br> <span data-ttu-id="9714a-500">Сохранение значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9714a-500">Keep default values.</span></span>

    <span data-ttu-id="9714a-501">**Вкладка Ограничения**</span><span class="sxs-lookup"><span data-stu-id="9714a-501">**Limitations tab**</span></span><br> <span data-ttu-id="9714a-502">Сохранение значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9714a-502">Keep default values.</span></span>

     ![Изображение вкладки ограничения параметров конфигурации](images/56dac54634d13b2d3948ab50e8d3ef21.png)

8. <span data-ttu-id="9714a-504">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-504">Select **Save**.</span></span> <span data-ttu-id="9714a-505">Пакет загружается в Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="9714a-505">The package is uploaded to Jamf Pro.</span></span>

   ![Изображение параметров конфигурации упаковки upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   <span data-ttu-id="9714a-507">Чтобы пакет был доступен для развертывания, может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="9714a-507">It can take a few minutes for the package to be available for deployment.</span></span>

   ![Образ параметров конфигурации пакет upl](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. <span data-ttu-id="9714a-509">Перейдите на **страницу Политики.**</span><span class="sxs-lookup"><span data-stu-id="9714a-509">Navigate to the **Policies** page.</span></span>

    ![Изображение polocies параметров конфигурации](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. <span data-ttu-id="9714a-511">Выберите **+ Новое** для создания новой политики.</span><span class="sxs-lookup"><span data-stu-id="9714a-511">Select **+ New** to create a new policy.</span></span>

    ![Изображение параметров конфигурации новой политики](images/847b70e54ed04787e415f5180414b310.png)


11. <span data-ttu-id="9714a-513">В **общем введите** следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9714a-513">In **General** Enter the following details:</span></span>

    - <span data-ttu-id="9714a-514">Имя отображения: MDATP onboarding Contoso 200329 v100.86.92 или более поздней</span><span class="sxs-lookup"><span data-stu-id="9714a-514">Display name: MDATP Onboarding Contoso 200329 v100.86.92 or later</span></span>

    ![Изображение параметров конфигурацииmdatponboard](images/625ba6d19e8597f05e4907298a454d28.png)

12. <span data-ttu-id="9714a-516">Выберите **повторяемую регистрацию.**</span><span class="sxs-lookup"><span data-stu-id="9714a-516">Select **Recurring Check-in**.</span></span>

    ![Изображение параметров конфигурации повторно проверить](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)


13. <span data-ttu-id="9714a-518">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-518">Select **Save**.</span></span>

14. <span data-ttu-id="9714a-519">Выберите **пакеты > настройка**.</span><span class="sxs-lookup"><span data-stu-id="9714a-519">Select **Packages > Configure**.</span></span>

    ![Образ настройки пакета параметров конфигурации](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. <span data-ttu-id="9714a-521">Выберите **кнопку Добавить** рядом с **microsoft Defender Advanced Threat Protection и антивирусная программа в Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="9714a-521">Select the **Add** button next to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    ![Добавление изображений параметров конфигурации MDATP и MDA](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. <span data-ttu-id="9714a-523">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-523">Select **Save**.</span></span>

    ![Изображение параметров конфигурации](images/9d6e5386e652e00715ff348af72671c6.png)

17. <span data-ttu-id="9714a-525">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="9714a-525">Select the **Scope** tab.</span></span>

    ![Изображение параметров конфигурации scptab](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. <span data-ttu-id="9714a-527">Выберите целевые компьютеры.</span><span class="sxs-lookup"><span data-stu-id="9714a-527">Select the target computers.</span></span>

    ![Изображение параметров конфигурации tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    <span data-ttu-id="9714a-529">**Scope**</span><span class="sxs-lookup"><span data-stu-id="9714a-529">**Scope**</span></span>

    <span data-ttu-id="9714a-530">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9714a-530">Select **Add**.</span></span>

    ![Изображение параметров конфигурации ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Изображение параметров конфигурации ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    <span data-ttu-id="9714a-533">**Самообслуживка**</span><span class="sxs-lookup"><span data-stu-id="9714a-533">**Self-Service**</span></span>

    ![Изображение самообслуживи параметров конфигурации](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. <span data-ttu-id="9714a-535">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9714a-535">Select **Done**.</span></span>

    ![Изображение параметров конфигурации do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Изображение параметров конфигурации do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




