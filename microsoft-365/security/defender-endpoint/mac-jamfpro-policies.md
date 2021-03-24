---
title: Настройка ATP защитника Майкрософт для политик macOS в Jamf Pro
description: Узнайте, как настроить ATP Защитника Майкрософт для политик macOS в Jamf Pro
keywords: политики, microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 1559d8dca6b6909f22473c5a8f4d25d4bac501d1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070293"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-for-macos-policies-in-jamf-pro"></a><span data-ttu-id="d71b8-104">Настройка конечной точки Microsoft Defender для политик macOS в Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="d71b8-104">Set up the Microsoft Defender for Endpoint for macOS policies in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d71b8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d71b8-105">**Applies to:**</span></span>

- [<span data-ttu-id="d71b8-106">Защитник для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="d71b8-106">Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="d71b8-107">На этой странице вы сможете найти необходимые действия, чтобы настроить политики macOS в Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="d71b8-107">This page will guide you through the steps you need to take to set up macOS policies in Jamf Pro.</span></span>

<span data-ttu-id="d71b8-108">Необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d71b8-108">You'll need to take the following steps:</span></span>

1. [<span data-ttu-id="d71b8-109">Получите пакет onboarding Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d71b8-109">Get the Microsoft Defender for Endpoint onboarding package</span></span>](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [<span data-ttu-id="d71b8-110">Создание профиля конфигурации в Jamf Pro с помощью бортового пакета</span><span class="sxs-lookup"><span data-stu-id="d71b8-110">Create a configuration profile in Jamf Pro using the onboarding package</span></span>](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [<span data-ttu-id="d71b8-111">Настройка параметров конечных точек Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d71b8-111">Configure Microsoft Defender for Endpoint settings</span></span>](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [<span data-ttu-id="d71b8-112">Настройка параметров уведомлений Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d71b8-112">Configure Microsoft Defender for Endpoint notification settings</span></span>](#step-4-configure-notifications-settings)

5. [<span data-ttu-id="d71b8-113">Настройка Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="d71b8-113">Configure Microsoft AutoUpdate (MAU)</span></span>](#step-5-configure-microsoft-autoupdate-mau)

6. [<span data-ttu-id="d71b8-114">Предоставление полного доступа к диску Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d71b8-114">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [<span data-ttu-id="d71b8-115">Утверждение расширения ядра для Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d71b8-115">Approve Kernel extension for Microsoft Defender for Endpoint</span></span>](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [<span data-ttu-id="d71b8-116">Утверждение расширений системы для Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d71b8-116">Approve System extensions for Microsoft Defender for Endpoint</span></span>](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [<span data-ttu-id="d71b8-117">Настройка расширения сети</span><span class="sxs-lookup"><span data-stu-id="d71b8-117">Configure Network Extension</span></span>](#step-9-configure-network-extension)

10. [<span data-ttu-id="d71b8-118">Расписание сканирования с помощью Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="d71b8-118">Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [<span data-ttu-id="d71b8-119">Развертывание Microsoft Defender для конечной точки для macOS</span><span class="sxs-lookup"><span data-stu-id="d71b8-119">Deploy Microsoft Defender for Endpoint for macOS</span></span>](#step-11-deploy-microsoft-defender-for-endpoint-for-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a><span data-ttu-id="d71b8-120">Шаг 1. Получить пакет onboarding Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d71b8-120">Step 1: Get the Microsoft Defender for Endpoint onboarding package</span></span>

1. <span data-ttu-id="d71b8-121">В [Центре безопасности Защитника Майкрософт](https://securitycenter.microsoft.com )перейдите к **параметрам > onboarding**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com ), navigate to **Settings > Onboarding**.</span></span> 

2. <span data-ttu-id="d71b8-122">Выберите macOS в качестве операционной системы, а метод развертывания — управление мобильными устройствами и Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="d71b8-122">Select macOS as the operating system and Mobile Device Management / Microsoft Intune as the deployment method.</span></span>

    ![Изображение Центра безопасности Защитника Майкрософт](images/onboarding-macos.png)

3. <span data-ttu-id="d71b8-124">Выберите **пакет загрузки** (WindowsDefenderATPOnboardingPackage.zip).</span><span class="sxs-lookup"><span data-stu-id="d71b8-124">Select **Download onboarding package** (WindowsDefenderATPOnboardingPackage.zip).</span></span>

4. <span data-ttu-id="d71b8-125">`WindowsDefenderATPOnboardingPackage.zip`Извлечение .</span><span class="sxs-lookup"><span data-stu-id="d71b8-125">Extract `WindowsDefenderATPOnboardingPackage.zip`.</span></span>

5. <span data-ttu-id="d71b8-126">Скопируйте файл в предпочтительное расположение.</span><span class="sxs-lookup"><span data-stu-id="d71b8-126">Copy the file to your preferred location.</span></span> <span data-ttu-id="d71b8-127">Пример: `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span><span class="sxs-lookup"><span data-stu-id="d71b8-127">For example,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span></span>


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a><span data-ttu-id="d71b8-128">Шаг 2. Создание профиля конфигурации в Jamf Pro с помощью пакета onboarding</span><span class="sxs-lookup"><span data-stu-id="d71b8-128">Step 2: Create a configuration profile in Jamf Pro using the onboarding package</span></span>

1. <span data-ttu-id="d71b8-129">Найдите файл `WindowsDefenderATPOnboarding.plist` из предыдущего раздела.</span><span class="sxs-lookup"><span data-stu-id="d71b8-129">Locate the file `WindowsDefenderATPOnboarding.plist` from the previous section.</span></span>

   ![Изображение файла WindowsDefenderATPOnboarding](images/plist-onboarding-file.png)

 
2. <span data-ttu-id="d71b8-131">В панели мониторинга Jamf Pro выберите **New**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-131">In the Jamf Pro dashboard, select **New**.</span></span>

    ![Изображение создания новой панели мониторинга Jamf Pro](images/jamf-pro-configure-profile.png)

3. <span data-ttu-id="d71b8-133">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d71b8-133">Enter the following details:</span></span>

   <span data-ttu-id="d71b8-134">**Общие**</span><span class="sxs-lookup"><span data-stu-id="d71b8-134">**General**</span></span>
   - <span data-ttu-id="d71b8-135">Имя: бортовая система MDATP для macOS</span><span class="sxs-lookup"><span data-stu-id="d71b8-135">Name: MDATP onboarding for macOS</span></span>
   - <span data-ttu-id="d71b8-136">Описание. Бортовая система MDATP EDR для macOS</span><span class="sxs-lookup"><span data-stu-id="d71b8-136">Description: MDATP EDR onboarding for macOS</span></span>
   - <span data-ttu-id="d71b8-137">Категории: None (нет)</span><span class="sxs-lookup"><span data-stu-id="d71b8-137">Category: None</span></span>
   - <span data-ttu-id="d71b8-138">Метод рассылки: установка автоматически</span><span class="sxs-lookup"><span data-stu-id="d71b8-138">Distribution Method: Install Automatically</span></span>
   - <span data-ttu-id="d71b8-139">Уровень: уровень компьютера</span><span class="sxs-lookup"><span data-stu-id="d71b8-139">Level: Computer Level</span></span>

4. <span data-ttu-id="d71b8-140">В **приложении & настраиваемые параметры** выберите **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-140">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Изображение настройки приложения и настраиваемых параметров](images/jamfpro-mac-profile.png)

5. <span data-ttu-id="d71b8-142">Выберите **Файл загрузки (PLIST-файл),** а затем **введите домен preference:** `com.microsoft.wdav.atp` .</span><span class="sxs-lookup"><span data-stu-id="d71b8-142">Select **Upload File (PLIST file)** then in **Preference Domain** enter: `com.microsoft.wdav.atp`.</span></span> 

    ![Изображение файла загрузки списка jamfpro](images/jamfpro-plist-upload.png)

    ![Изображение файла списка свойств upload file](images/jamfpro-plist-file.png)

7. <span data-ttu-id="d71b8-145">Выберите **Открыть** и выбрать файл вмеяния.</span><span class="sxs-lookup"><span data-stu-id="d71b8-145">Select **Open** and select the onboarding file.</span></span>

    ![Изображение бортового файла](images/jamfpro-plist-file-onboard.png)

8. <span data-ttu-id="d71b8-147">Выберите **Upload**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-147">Select **Upload**.</span></span> 

    ![Изображение загрузки файла plist](images/jamfpro-upload-plist.png)


9. <span data-ttu-id="d71b8-149">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-149">Select the **Scope** tab.</span></span>

    ![Изображение вкладки области](images/jamfpro-scope-tab.png)

10. <span data-ttu-id="d71b8-151">Выберите целевые компьютеры.</span><span class="sxs-lookup"><span data-stu-id="d71b8-151">Select the target computers.</span></span>

    ![Изображение целевых компьютеров](images/jamfpro-target-computer.png)

    ![Изображение целей](images/jamfpro-targets.png) 

11. <span data-ttu-id="d71b8-154">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-154">Select **Save**.</span></span>

    ![Изображение целевых компьютеров развертывания](images/jamfpro-deployment-target.png)

    ![Изображение выбранных целевых компьютеров](images/jamfpro-target-selected.png)

12. <span data-ttu-id="d71b8-157">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-157">Select **Done**.</span></span>

    ![Изображение компьютеров целевой группы](images/jamfpro-target-group.png)

    ![Список профилей конфигурации](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a><span data-ttu-id="d71b8-160">Шаг 3. Настройка защитника Майкрософт для параметров конечной точки</span><span class="sxs-lookup"><span data-stu-id="d71b8-160">Step 3: Configure Microsoft Defender for Endpoint settings</span></span>

1.  <span data-ttu-id="d71b8-161">Используйте следующие параметры конфигурации Microsoft Defender для конечных точек:</span><span class="sxs-lookup"><span data-stu-id="d71b8-161">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

    - <span data-ttu-id="d71b8-162">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="d71b8-162">enableRealTimeProtection</span></span>
    - <span data-ttu-id="d71b8-163">passiveMode</span><span class="sxs-lookup"><span data-stu-id="d71b8-163">passiveMode</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="d71b8-164">Не включено по умолчанию, если вы планируете запустить сторонний AV для macOS, установите `true` его.</span><span class="sxs-lookup"><span data-stu-id="d71b8-164">Not turned on by default, if you are planning to run a third-party AV for macOS, set it to `true`.</span></span>

    - <span data-ttu-id="d71b8-165">исключения</span><span class="sxs-lookup"><span data-stu-id="d71b8-165">exclusions</span></span>
    - <span data-ttu-id="d71b8-166">excludedPath</span><span class="sxs-lookup"><span data-stu-id="d71b8-166">excludedPath</span></span>
    - <span data-ttu-id="d71b8-167">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="d71b8-167">excludedFileExtension</span></span>
    - <span data-ttu-id="d71b8-168">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="d71b8-168">excludedFileName</span></span>
    - <span data-ttu-id="d71b8-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="d71b8-169">exclusionsMergePolicy</span></span>
    - <span data-ttu-id="d71b8-170">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="d71b8-170">allowedThreats</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="d71b8-171">EICAR находится в примере, если вы проходите проверку концепции, удалите ее, особенно если вы тестируете EICAR.</span><span class="sxs-lookup"><span data-stu-id="d71b8-171">EICAR is on the sample, if you are going through a proof-of-concept, remove it especially if you are testing EICAR.</span></span>
        
    - <span data-ttu-id="d71b8-172">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="d71b8-172">disallowedThreatActions</span></span>
    - <span data-ttu-id="d71b8-173">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="d71b8-173">potentially_unwanted_application</span></span>
    - <span data-ttu-id="d71b8-174">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="d71b8-174">archive_bomb</span></span>
    - <span data-ttu-id="d71b8-175">cloudService</span><span class="sxs-lookup"><span data-stu-id="d71b8-175">cloudService</span></span>
    - <span data-ttu-id="d71b8-176">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="d71b8-176">automaticSampleSubmission</span></span>
    - <span data-ttu-id="d71b8-177">tags</span><span class="sxs-lookup"><span data-stu-id="d71b8-177">tags</span></span>
    - <span data-ttu-id="d71b8-178">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="d71b8-178">hideStatusMenuIcon</span></span>
    
     <span data-ttu-id="d71b8-179">Сведения см. в [списке свойств для профиля конфигурации Jamf.](mac-preferences.md#property-list-for-jamf-configuration-profile)</span><span class="sxs-lookup"><span data-stu-id="d71b8-179">For information, see [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).</span></span>

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

2. <span data-ttu-id="d71b8-180">Сохраните файл как `MDATP_MDAV_configuration_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="d71b8-180">Save the file as `MDATP_MDAV_configuration_settings.plist`.</span></span>


3.  <span data-ttu-id="d71b8-181">В панели мониторинга Jamf Pro выберите **General**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-181">In the Jamf Pro dashboard, select **General**.</span></span>

    ![Изображение новой панели мониторинга Jamf Pro](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. <span data-ttu-id="d71b8-183">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d71b8-183">Enter the following details:</span></span>

    <span data-ttu-id="d71b8-184">**Общие**</span><span class="sxs-lookup"><span data-stu-id="d71b8-184">**General**</span></span>
    
    - <span data-ttu-id="d71b8-185">Имя: параметры конфигурации MDATP MDAV</span><span class="sxs-lookup"><span data-stu-id="d71b8-185">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="d71b8-186">Описание:\<blank\></span><span class="sxs-lookup"><span data-stu-id="d71b8-186">Description:\<blank\></span></span>
    - <span data-ttu-id="d71b8-187">Категория: Нет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d71b8-187">Category: None (default)</span></span>
    - <span data-ttu-id="d71b8-188">Метод рассылки: установка автоматически (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d71b8-188">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="d71b8-189">Уровень: уровень компьютера (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d71b8-189">Level: Computer Level(default)</span></span>

    ![Изображение параметров конфигурации MDATP MDAV](images/3160906404bc5a2edf84d1d015894e3b.png)

5. <span data-ttu-id="d71b8-191">В **приложении & настраиваемые параметры** выберите **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-191">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Изображение параметров приложения и настраиваемого](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. <span data-ttu-id="d71b8-193">Выберите **файл загрузки (PLIST-файл).**</span><span class="sxs-lookup"><span data-stu-id="d71b8-193">Select **Upload File (PLIST file)**.</span></span>

    ![Изображение файла plist параметров конфигурации](images/6f85269276b2278eca4bce84f935f87b.png)

7. <span data-ttu-id="d71b8-195">В **домене Preferences введите,** `com.microsoft.wdav` а затем выберите Файл  **загрузки PLIST**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-195">In **Preferences Domain**, enter `com.microsoft.wdav`, then select  **Upload PLIST File**.</span></span>

    ![Изображение домена настроек конфигурации](images/db15f147dd959e872a044184711d7d46.png)

8. <span data-ttu-id="d71b8-197">Выберите **выберите файл**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-197">Select **Choose File**.</span></span>

    ![Изображение параметров конфигурации выберите файл](images/526e978761fc571cca06907da7b01fd6.png)

9. <span data-ttu-id="d71b8-199">Выберите **список MDATP_MDAV_configuration_settings.plist,** а затем **откройте**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-199">Select the **MDATP_MDAV_configuration_settings.plist**, then select **Open**.</span></span>

    ![Изображение параметров конфигурации mdatpmdav](images/98acea3750113b8dbab334296e833003.png)

10. <span data-ttu-id="d71b8-201">Выберите **Upload**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-201">Select **Upload**.</span></span>

    ![Изображение загрузки параметра конфигурации](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Изображение параметров настройки загрузки изображения](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    ><span data-ttu-id="d71b8-204">Если вы загрузите файл Intune, вы получите следующую ошибку:</span><span class="sxs-lookup"><span data-stu-id="d71b8-204">If you happen to upload the Intune file, you'll get the following error:</span></span><br>
    ><span data-ttu-id="d71b8-205">![Изображение загрузки файлов intune параметров конфигурации](images/8e69f867664668796a3b2904896f0436.png)</span><span class="sxs-lookup"><span data-stu-id="d71b8-205">![Image of configuration settings intune file upload](images/8e69f867664668796a3b2904896f0436.png)</span></span>


11. <span data-ttu-id="d71b8-206">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-206">Select **Save**.</span></span> 

    ![Изображение параметров конфигурации Сохранить изображение](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. <span data-ttu-id="d71b8-208">Файл загружен.</span><span class="sxs-lookup"><span data-stu-id="d71b8-208">The file is uploaded.</span></span>

    ![Изображение загруженного изображения файла параметров конфигурации](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Изображение загруженного файла параметров конфигурации](images/a422e57fe8d45689227e784443e51bd1.png)

13. <span data-ttu-id="d71b8-211">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-211">Select the **Scope** tab.</span></span>

    ![Изображение области параметров конфигурации](images/9fc17529e5577eefd773c658ec576a7d.png)

14. <span data-ttu-id="d71b8-213">Выберите **машинную группу Contoso.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-213">Select **Contoso's Machine Group**.</span></span> 

15. <span data-ttu-id="d71b8-214">Выберите **Добавить,** а затем **выберите Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-214">Select **Add**, then select **Save**.</span></span>

    ![Изображение параметров конфигурации addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Изображение параметров конфигурации сохранить добавить](images/6f093e42856753a3955cab7ee14f12d9.png)

16. <span data-ttu-id="d71b8-217">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-217">Select **Done**.</span></span> <span data-ttu-id="d71b8-218">Вы увидите новый профиль **Конфигурация**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-218">You'll see the new **Configuration profile**.</span></span>

    ![Изображение конфигурации параметров конфигурировать изображение профиля](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a><span data-ttu-id="d71b8-220">Шаг 4. Настройка параметров уведомлений</span><span class="sxs-lookup"><span data-stu-id="d71b8-220">Step 4: Configure notifications settings</span></span>

<span data-ttu-id="d71b8-221">Эти действия применимы к macOS 10.15 (Catalina) или более новым.</span><span class="sxs-lookup"><span data-stu-id="d71b8-221">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="d71b8-222">Скачивание `notif.mobileconfig` из [нашего репозитория GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig)</span><span class="sxs-lookup"><span data-stu-id="d71b8-222">Download `notif.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig)</span></span>

2. <span data-ttu-id="d71b8-223">Сохраните его как `MDATP_MDAV_notification_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="d71b8-223">Save it as `MDATP_MDAV_notification_settings.plist`.</span></span>

3. <span data-ttu-id="d71b8-224">В панели мониторинга Jamf Pro выберите **General**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-224">In the Jamf Pro dashboard, select **General**.</span></span> 
       
4. <span data-ttu-id="d71b8-225">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d71b8-225">Enter the following details:</span></span>

    <span data-ttu-id="d71b8-226">**Общие**</span><span class="sxs-lookup"><span data-stu-id="d71b8-226">**General**</span></span> 
    
    - <span data-ttu-id="d71b8-227">Имя: параметры MDAV-уведомлений MDATP</span><span class="sxs-lookup"><span data-stu-id="d71b8-227">Name: MDATP MDAV Notification settings</span></span>
    - <span data-ttu-id="d71b8-228">Описание: macOS 10.15 (Catalina) или более новый</span><span class="sxs-lookup"><span data-stu-id="d71b8-228">Description: macOS 10.15 (Catalina) or newer</span></span>
    - <span data-ttu-id="d71b8-229">Категория: Нет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d71b8-229">Category: None (default)</span></span>
    - <span data-ttu-id="d71b8-230">Метод рассылки: установка автоматически (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d71b8-230">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="d71b8-231">Уровень: уровень компьютера (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d71b8-231">Level: Computer Level(default)</span></span>

    ![Изображение параметров конфигурации mdatpmdav](images/c9820a5ff84aaf21635c04a23a97ca93.png)


5. <span data-ttu-id="d71b8-233">Выберите **файл загрузки (PLIST-файл).**</span><span class="sxs-lookup"><span data-stu-id="d71b8-233">Select **Upload File (PLIST file)**.</span></span>

    ![Изображение параметров конфигурации загрузить plistfile](images/7f9138053dbcbf928e5182ee7b295ebe.png)
 

6. <span data-ttu-id="d71b8-235">Выберите **выберите файл**  >  **MDATP_MDAV_Notification_Settings.plist**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-235">Select **Choose File** > **MDATP_MDAV_Notification_Settings.plist**.</span></span>


    ![Изображение параметров конфигурации mdatpmdav notsettings](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)


    ![Изображение параметров конфигурации mdatpmdav notifsettings](images/20e33b98eb54447881dc6c89e58b890f.png)

7. <span data-ttu-id="d71b8-238">Выберите **открытую**  >  **загрузку.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-238">Select **Open** > **Upload**.</span></span>

    ![Изображение параметров конфигурации upl img](images/7697c33b9fd376ae5a8023d01f9d3857.png)


    ![Изображение образа upl параметров конфигурации](images/2bda9244ec25d1526811da4ea91b1c86.png)

8. <span data-ttu-id="d71b8-241">Выберите **вкладку Область,** а **затем** добавьте .</span><span class="sxs-lookup"><span data-stu-id="d71b8-241">Select the **Scope** tab, then select **Add**.</span></span>

    ![Добавлено изображение области параметров конфигурации](images/441aa2ecd36abadcdd8aed03556080b5.png)


9. <span data-ttu-id="d71b8-243">Выберите **машинную группу Contoso.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-243">Select **Contoso's Machine Group**.</span></span> 

10. <span data-ttu-id="d71b8-244">Выберите **Добавить,** а затем **выберите Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-244">Select **Add**, then select **Save**.</span></span>
    
    ![Image of configuration settings contoso machine grp save](images/09a275e321268e5e3ac0c0865d3e2db5.png)

    
    ![Изображение параметров конфигурации добавить сохранить](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

11. <span data-ttu-id="d71b8-247">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-247">Select **Done**.</span></span> <span data-ttu-id="d71b8-248">Вы увидите новый профиль **Конфигурация**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-248">You'll see the new **Configuration profile**.</span></span>
    <span data-ttu-id="d71b8-249">![Изображение параметра конфигурации сделано img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span><span class="sxs-lookup"><span data-stu-id="d71b8-249">![Image of configuration setting done img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span></span>

## <a name="step-5-configure-microsoft-autoupdate-mau"></a><span data-ttu-id="d71b8-250">Шаг 5. Настройка Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="d71b8-250">Step 5: Configure Microsoft AutoUpdate (MAU)</span></span>

1. <span data-ttu-id="d71b8-251">Используйте следующие параметры конфигурации Microsoft Defender для конечных точек:</span><span class="sxs-lookup"><span data-stu-id="d71b8-251">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

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

2. <span data-ttu-id="d71b8-252">Сохраните его как `MDATP_MDAV_MAU_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="d71b8-252">Save it as `MDATP_MDAV_MAU_settings.plist`.</span></span>

3. <span data-ttu-id="d71b8-253">В панели мониторинга Jamf Pro выберите **General**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-253">In the Jamf Pro dashboard, select **General**.</span></span> 

    ![Изображение общего образа настройки конфигурации](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. <span data-ttu-id="d71b8-255">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d71b8-255">Enter the following details:</span></span>

    <span data-ttu-id="d71b8-256">**Общие**</span><span class="sxs-lookup"><span data-stu-id="d71b8-256">**General**</span></span> 
    
    - <span data-ttu-id="d71b8-257">Имя: параметры MDATP MDAV MAU</span><span class="sxs-lookup"><span data-stu-id="d71b8-257">Name: MDATP MDAV MAU settings</span></span>
    - <span data-ttu-id="d71b8-258">Описание. Параметры Microsoft AutoUpdate для MDATP для macOS</span><span class="sxs-lookup"><span data-stu-id="d71b8-258">Description: Microsoft AutoUpdate settings for MDATP for macOS</span></span>
    - <span data-ttu-id="d71b8-259">Категория: Нет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d71b8-259">Category: None (default)</span></span>
    - <span data-ttu-id="d71b8-260">Метод рассылки: установка автоматически (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d71b8-260">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="d71b8-261">Уровень: уровень компьютера (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d71b8-261">Level: Computer Level(default)</span></span>

5. <span data-ttu-id="d71b8-262">В **приложении & настраиваемые параметры** выберите **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-262">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Изображение приложения настройки конфигурации и настраиваемые параметры](images/1f72e9c15eaafcabf1504397e99be311.png)

6. <span data-ttu-id="d71b8-264">Выберите **файл загрузки (PLIST-файл).**</span><span class="sxs-lookup"><span data-stu-id="d71b8-264">Select **Upload File (PLIST file)**.</span></span>

    ![Изображение plist настройки конфигурации](images/1213872db5833aa8be535da57653219f.png)  

7. <span data-ttu-id="d71b8-266">В **домене Preference** введите: `com.microsoft.autoupdate2` затем выберите Файл **загрузки PLIST.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-266">In **Preference Domain** enter: `com.microsoft.autoupdate2`, then select **Upload PLIST File**.</span></span>

    ![Изображение предварительного домена настройки настройки](images/1213872db5833aa8be535da57653219f.png)

8. <span data-ttu-id="d71b8-268">Выберите **выберите файл**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-268">Select **Choose File**.</span></span>

    ![Изображение параметра конфигурации choosefile](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. <span data-ttu-id="d71b8-270">Выберите **MDATP_MDAV_MAU_settings.plist**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-270">Select **MDATP_MDAV_MAU_settings.plist**.</span></span>

    ![Изображение параметров настройки mdatpmdavmau](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. <span data-ttu-id="d71b8-272">Выберите **Upload**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-272">Select **Upload**.</span></span>
    <span data-ttu-id="d71b8-273">![Изображение настройки настройки uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span><span class="sxs-lookup"><span data-stu-id="d71b8-273">![Image of configuration setting uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span></span>

    ![Изображение настройки настройки uplimg](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. <span data-ttu-id="d71b8-275">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-275">Select **Save**.</span></span>

    ![Изображение параметра конфигурации saveimg](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. <span data-ttu-id="d71b8-277">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-277">Select the **Scope** tab.</span></span>
   
     ![Изображение scopetab настройки конфигурации](images/10ab98358b2d602f3f67618735fa82fb.png)

13. <span data-ttu-id="d71b8-279">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-279">Select **Add**.</span></span>
    
    ![Изображение параметра конфигурации addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Изображение параметра конфигурации addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Изображение параметра конфигурации addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. <span data-ttu-id="d71b8-283">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-283">Select **Done**.</span></span>
    
    ![Image of configuration setting doneimage](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="d71b8-285">Шаг 6. Предоставление полного доступа к диску Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d71b8-285">Step 6: Grant full disk access to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="d71b8-286">В панели мониторинга Jamf Pro выберите **профили конфигурации.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-286">In the Jamf Pro dashboard, select **Configuration Profiles**.</span></span>

    ![Изображение профиля конфигурации настройки конфигурации](images/264493cd01e62c7085659d6fdc26dc91.png)

2. <span data-ttu-id="d71b8-288">Выберите **+ Новый**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-288">Select **+ New**.</span></span> 

3. <span data-ttu-id="d71b8-289">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d71b8-289">Enter the following details:</span></span>

    <span data-ttu-id="d71b8-290">**Общие**</span><span class="sxs-lookup"><span data-stu-id="d71b8-290">**General**</span></span> 
    - <span data-ttu-id="d71b8-291">Имя: MDATP MDAV — предоставление полного доступа к диску EDR и AV</span><span class="sxs-lookup"><span data-stu-id="d71b8-291">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span></span>
    - <span data-ttu-id="d71b8-292">Описание. Для macOS Catalina или более нового управления политикой конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="d71b8-292">Description: On macOS Catalina or newer, the new Privacy Preferences Policy Control</span></span>
    - <span data-ttu-id="d71b8-293">Категории: None (нет)</span><span class="sxs-lookup"><span data-stu-id="d71b8-293">Category: None</span></span>
    - <span data-ttu-id="d71b8-294">Метод рассылки: установка автоматически</span><span class="sxs-lookup"><span data-stu-id="d71b8-294">Distribution method: Install Automatically</span></span>
    - <span data-ttu-id="d71b8-295">Уровень: уровень компьютера</span><span class="sxs-lookup"><span data-stu-id="d71b8-295">Level: Computer level</span></span>


    ![Изображение общего параметра настройки конфигурации](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. <span data-ttu-id="d71b8-297">В **Настройка политики настройки предпочтений конфиденциальности выберите** **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-297">In **Configure Privacy Preferences Policy Control** select **Configure**.</span></span>

    ![Изображение управления политикой конфиденциальности конфигурации](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. <span data-ttu-id="d71b8-299">В правилах управления **политиками конфиденциальности** введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d71b8-299">In **Privacy Preferences Policy Control**, enter the following details:</span></span>

    - <span data-ttu-id="d71b8-300">Идентификатор: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="d71b8-300">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="d71b8-301">Тип идентификатора: идентификатор пакета</span><span class="sxs-lookup"><span data-stu-id="d71b8-301">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="d71b8-302">Требование кода: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="d71b8-302">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>


    ![Изображение сведений о настройке политики настройки конфиденциальности.](images/22cb439de958101c0a12f3038f905b27.png)

6. <span data-ttu-id="d71b8-304">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-304">Select **+ Add**.</span></span>

    ![Изображение параметра конфигурации добавить системную политику во все файлы](images/bd93e78b74c2660a0541af4690dd9485.png)

    - <span data-ttu-id="d71b8-306">В приложении или службе: установите **systemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="d71b8-306">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="d71b8-307">В статье "Доступ": набор **разрешить**</span><span class="sxs-lookup"><span data-stu-id="d71b8-307">Under "access": Set to **Allow**</span></span>

7. <span data-ttu-id="d71b8-308">Выберите **Сохранить** (не тот, который внизу справа).</span><span class="sxs-lookup"><span data-stu-id="d71b8-308">Select **Save** (not the one at the bottom right).</span></span>

    ![Изображение параметра конфигурации сохранить изображения](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. <span data-ttu-id="d71b8-310">Щелкните `+` знак рядом с **доступом к приложению,** чтобы добавить новую запись.</span><span class="sxs-lookup"><span data-stu-id="d71b8-310">Click the `+` sign next to **App Access** to add a new entry.</span></span>

    ![Изображение доступа к приложению настройки конфигурации](images/tcc-add-entry.png)

9. <span data-ttu-id="d71b8-312">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d71b8-312">Enter the following details:</span></span>

    - <span data-ttu-id="d71b8-313">Идентификатор: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="d71b8-313">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="d71b8-314">Тип идентификатора: идентификатор пакета</span><span class="sxs-lookup"><span data-stu-id="d71b8-314">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="d71b8-315">Требование кода: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="d71b8-315">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

10. <span data-ttu-id="d71b8-316">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-316">Select **+ Add**.</span></span>

    ![Изображение записи epsext параметра конфигурации tcc](images/tcc-epsext-entry.png)

    - <span data-ttu-id="d71b8-318">В приложении или службе: установите **systemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="d71b8-318">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="d71b8-319">В статье "Доступ": набор **разрешить**</span><span class="sxs-lookup"><span data-stu-id="d71b8-319">Under "access": Set to **Allow**</span></span>

11. <span data-ttu-id="d71b8-320">Выберите **Сохранить** (не тот, который внизу справа).</span><span class="sxs-lookup"><span data-stu-id="d71b8-320">Select **Save** (not the one at the bottom right).</span></span>

    ![Изображение параметра конфигурации tcc epsext image2](images/tcc-epsext-entry2.png)

12. <span data-ttu-id="d71b8-322">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-322">Select the **Scope** tab.</span></span>

    ![Изображение области настройки конфигурации](images/2c49b16cd112729b3719724f581e6882.png)

13. <span data-ttu-id="d71b8-324">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-324">Select **+ Add**.</span></span>

    ![Изображение надстройки параметра конфигурации](images/57cef926d1b9260fb74a5f460cee887a.png)

14. <span data-ttu-id="d71b8-326">Выберите **группы** компьютеров > **под названием** группы > **выберите MachineGroup Contoso.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-326">Select **Computer Groups** > under **Group Name** > select **Contoso's MachineGroup**.</span></span> 

    ![Изображение параметра конфигурации contoso machinegrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. <span data-ttu-id="d71b8-328">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-328">Select **Add**.</span></span> 

16. <span data-ttu-id="d71b8-329">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-329">Select **Save**.</span></span> 
    
17. <span data-ttu-id="d71b8-330">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-330">Select **Done**.</span></span>
    
    ![Изображение donimg параметра конфигурации](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![Изображение параметра конфигурации donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)


## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="d71b8-333">Шаг 7. Утверждение расширения ядра для Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d71b8-333">Step 7: Approve Kernel extension for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="d71b8-334">В **профилях конфигурации** выберите **+ New**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-334">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Снимок экрана сообщения в социальных сетях, автоматически созданный](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="d71b8-336">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d71b8-336">Enter the following details:</span></span>

    <span data-ttu-id="d71b8-337">**Общие**</span><span class="sxs-lookup"><span data-stu-id="d71b8-337">**General**</span></span> 
    
    - <span data-ttu-id="d71b8-338">Имя. Расширение Ядра MDAV MDAV</span><span class="sxs-lookup"><span data-stu-id="d71b8-338">Name: MDATP MDAV Kernel Extension</span></span>
    - <span data-ttu-id="d71b8-339">Описание: расширение ядра MDATP (kext)</span><span class="sxs-lookup"><span data-stu-id="d71b8-339">Description: MDATP kernel extension (kext)</span></span>
    - <span data-ttu-id="d71b8-340">Категории: None (нет)</span><span class="sxs-lookup"><span data-stu-id="d71b8-340">Category: None</span></span>
    - <span data-ttu-id="d71b8-341">Метод рассылки: установка автоматически</span><span class="sxs-lookup"><span data-stu-id="d71b8-341">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="d71b8-342">Уровень: уровень компьютера</span><span class="sxs-lookup"><span data-stu-id="d71b8-342">Level: Computer Level</span></span>

    ![Изображение параметров конфигурации ядра mdatpmdav](images/24e290f5fc309932cf41f3a280d22c14.png)

3. <span data-ttu-id="d71b8-344">В **Настройка утвержденных расширений ядра** выберите **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-344">In **Configure Approved Kernel Extensions** select **Configure**.</span></span>

    ![Изображение параметров конфигурации, утвержденных ext ядра](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. <span data-ttu-id="d71b8-346">В **утвержденных расширениях ядра** введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d71b8-346">In **Approved Kernel Extensions** Enter the following details:</span></span>

    - <span data-ttu-id="d71b8-347">Имя отображения: Корпорация Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d71b8-347">Display Name: Microsoft Corp.</span></span>
    - <span data-ttu-id="d71b8-348">ID команды: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="d71b8-348">Team ID: UBF8T346G9</span></span>

    ![Изображение параметров конфигурации расширения ядра appr](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. <span data-ttu-id="d71b8-350">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-350">Select the **Scope** tab.</span></span>

    ![Image of configuration settings scope tab img](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="d71b8-352">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-352">Select **+ Add**.</span></span>

7. <span data-ttu-id="d71b8-353">Выберите **группы** > **в соответствии с названием** группы > выберите **группу машин Contoso.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-353">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="d71b8-354">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-354">Select **+ Add**.</span></span>

    ![Изображение параметров конфигурации добавить изображения](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="d71b8-356">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-356">Select **Save**.</span></span>

    ![Изображение параметров конфигурации saveimag](images/0add8019b85a453b47fa5c402c72761b.png)

10. <span data-ttu-id="d71b8-358">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-358">Select **Done**.</span></span>

    ![Изображение параметров конфигурации doneimag](images/1c9bd3f68db20b80193dac18f33c22d0.png)


## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="d71b8-360">Шаг 8. Утверждение расширений системы для Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d71b8-360">Step 8: Approve System extensions for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="d71b8-361">В **профилях конфигурации** выберите **+ New**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-361">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Снимок экрана сообщения в социальных сетях, автоматически созданный](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="d71b8-363">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d71b8-363">Enter the following details:</span></span>

    <span data-ttu-id="d71b8-364">**Общие**</span><span class="sxs-lookup"><span data-stu-id="d71b8-364">**General**</span></span>
    
    - <span data-ttu-id="d71b8-365">Имя: MDATP MDAV System Extensions</span><span class="sxs-lookup"><span data-stu-id="d71b8-365">Name: MDATP MDAV System Extensions</span></span>
    - <span data-ttu-id="d71b8-366">Описание: расширения системы MDATP</span><span class="sxs-lookup"><span data-stu-id="d71b8-366">Description: MDATP system extensions</span></span>
    - <span data-ttu-id="d71b8-367">Категории: None (нет)</span><span class="sxs-lookup"><span data-stu-id="d71b8-367">Category: None</span></span>
    - <span data-ttu-id="d71b8-368">Метод рассылки: установка автоматически</span><span class="sxs-lookup"><span data-stu-id="d71b8-368">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="d71b8-369">Уровень: уровень компьютера</span><span class="sxs-lookup"><span data-stu-id="d71b8-369">Level: Computer Level</span></span>

    ![Изображение параметров конфигурации sysext new prof](images/sysext-new-profile.png)

3. <span data-ttu-id="d71b8-371">В **расширении системы** выберите **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-371">In **System Extensions** select **Configure**.</span></span>

   ![Изображение параметров конфигурации sysext config](images/sysext-configure.png)

4. <span data-ttu-id="d71b8-373">В **расширении системы введите** следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d71b8-373">In **System Extensions** enter the following details:</span></span>

   - <span data-ttu-id="d71b8-374">Имя отображения: расширения системы Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="d71b8-374">Display Name: Microsoft Corp. System Extensions</span></span>
   - <span data-ttu-id="d71b8-375">Типы расширения системы: разрешенные расширения системы</span><span class="sxs-lookup"><span data-stu-id="d71b8-375">System Extension Types: Allowed System Extensions</span></span>
   - <span data-ttu-id="d71b8-376">Идентификатор команды: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="d71b8-376">Team Identifier: UBF8T346G9</span></span>
   - <span data-ttu-id="d71b8-377">Разрешенные расширения системы:</span><span class="sxs-lookup"><span data-stu-id="d71b8-377">Allowed System Extensions:</span></span>
     - <span data-ttu-id="d71b8-378">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="d71b8-378">**com.microsoft.wdav.epsext**</span></span>
     - <span data-ttu-id="d71b8-379">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="d71b8-379">**com.microsoft.wdav.netext**</span></span>

    ![Изображение параметров конфигурации sysextconfig2](images/sysext-configure2.png)

5. <span data-ttu-id="d71b8-381">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-381">Select the **Scope** tab.</span></span>

    ![Image of configuration settings scopeimage](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="d71b8-383">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-383">Select **+ Add**.</span></span>

7. <span data-ttu-id="d71b8-384">Выберите **группы** > **в соответствии с названием** группы > выберите **группу машин Contoso.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-384">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="d71b8-385">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-385">Select **+ Add**.</span></span>

   ![Изображение параметров конфигурации addima](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="d71b8-387">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-387">Select **Save**.</span></span>

   ![Изображение параметров конфигурации sysext](images/sysext-scope.png)

10. <span data-ttu-id="d71b8-389">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-389">Select **Done**.</span></span>

    ![Изображение параметров конфигурации sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a><span data-ttu-id="d71b8-391">Шаг 9. Настройка расширения сети</span><span class="sxs-lookup"><span data-stu-id="d71b8-391">Step 9: Configure Network Extension</span></span>

<span data-ttu-id="d71b8-392">В рамках возможностей обнаружения конечных точек и ответов Microsoft Defender for Endpoint для Mac проверяет трафик розетки и передает эти сведения на портал Центра безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="d71b8-392">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="d71b8-393">Следующая политика позволяет сетевому расширению выполнять эту функцию.</span><span class="sxs-lookup"><span data-stu-id="d71b8-393">The following policy allows the network extension to perform this functionality.</span></span>

>[!NOTE]
><span data-ttu-id="d71b8-394">JAMF не имеет встроенной поддержки политик фильтрации контента, которые являются необходимым условием для включения расширений сети, которые Microsoft Defender для конечной точки для Mac устанавливает на устройстве.</span><span class="sxs-lookup"><span data-stu-id="d71b8-394">JAMF doesn’t have built-in support for content filtering policies, which are a pre-requisite for enabling the network extensions that Microsoft Defender for Endpoint for Mac installs on the device.</span></span> <span data-ttu-id="d71b8-395">Кроме того, JAMF иногда изменяет содержимое развернутых политик.</span><span class="sxs-lookup"><span data-stu-id="d71b8-395">Furthermore, JAMF sometimes changes the content of the policies being deployed.</span></span>
><span data-ttu-id="d71b8-396">Таким образом, следующие действия предоставляют обходное решение, которое включает подписание профиля конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d71b8-396">As such, the following steps provide a workaround that involve signing the configuration profile.</span></span>

1. <span data-ttu-id="d71b8-397">Скачайте `netfilter.mobileconfig` [из нашего репозитория GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) на ваше устройство и сохраните его как `com.microsoft.network-extension.mobileconfig`</span><span class="sxs-lookup"><span data-stu-id="d71b8-397">Download `netfilter.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) to your device and save it as `com.microsoft.network-extension.mobileconfig`</span></span>

2. <span data-ttu-id="d71b8-398">Следуйте инструкциям на [этой странице,](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) чтобы создать сертификат подписи с помощью встроенного органа сертификата JAMF</span><span class="sxs-lookup"><span data-stu-id="d71b8-398">Follow the instructions on [this page](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) to create a signing certificate using JAMF’s built-in certificate authority</span></span>

3. <span data-ttu-id="d71b8-399">После создания и установки сертификата на устройство запустите следующую команду из терминала с устройства macOS:</span><span class="sxs-lookup"><span data-stu-id="d71b8-399">After the certificate is created and installed to your device, run the following command from the Terminal from a macOS device:</span></span>

   ```bash
   $ security cms -S -N "<certificate name>" -i com.microsoft.network-extension.mobileconfig -o com.microsoft.network-extension.signed.mobileconfig
   ```

   ![Окно терминала с командой для создания подписанной конфигурации](images/netext-create-profile.png)

4. <span data-ttu-id="d71b8-401">С портала JAMF перейдите к **профилям конфигурации** и нажмите кнопку **Upload.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-401">From the JAMF portal, navigate to **Configuration Profiles** and click the **Upload** button.</span></span> 

   ![Изображение окна загрузки](images/netext-upload-file.png)

5. <span data-ttu-id="d71b8-403">Выберите **Выберите файл** и выберите `microsoft.network-extension.signed.mobileconfig` .</span><span class="sxs-lookup"><span data-stu-id="d71b8-403">Select **Choose File** and select `microsoft.network-extension.signed.mobileconfig`.</span></span>

   ![Изображение файла выбора netext окна для загрузки](images/netext-choose-file.png)

6. <span data-ttu-id="d71b8-405">Выберите **Upload**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-405">Select **Upload**.</span></span>

   ![Изображение файла загрузки окна netext upload2](images/netext-upload-file2.png)

7. <span data-ttu-id="d71b8-407">После отправки файла вы перенаправляетсяе на новую страницу для окончательного создания этого профиля.</span><span class="sxs-lookup"><span data-stu-id="d71b8-407">After uploading the file, you are redirected to a new page to finalize the creation of this profile.</span></span>

   ![Изображение страницы профиля netext профиля нового профиля конфигурации](images/netext-profile-page.png)

8. <span data-ttu-id="d71b8-409">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-409">Select the **Scope** tab.</span></span>

   ![Изображение параметров конфигурации вкладки sco](images/0df36fc308ba569db204ee32db3fb40a.png)

9. <span data-ttu-id="d71b8-411">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-411">Select **+ Add**.</span></span>

10. <span data-ttu-id="d71b8-412">Выберите **группы** > **в соответствии с названием** группы > выберите **группу машин Contoso.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-412">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

11. <span data-ttu-id="d71b8-413">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-413">Select **+ Add**.</span></span>

    ![Изображение adim параметров конфигурации](images/0dde8a4c41110dbc398c485433a81359.png)

12. <span data-ttu-id="d71b8-415">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-415">Select **Save**.</span></span>

    ![Изображение параметров конфигурации savimg netextscop](images/netext-scope.png)

13. <span data-ttu-id="d71b8-417">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-417">Select **Done**.</span></span>

    ![Изображение параметров конфигурации netextfinal](images/netext-final.png)

## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="d71b8-419">Шаг 10. Расписание сканирования в Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="d71b8-419">Step 10: Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>
<span data-ttu-id="d71b8-420">Следуйте инструкциям по [проверке расписания с помощью Microsoft Defender для конечной точки для Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span><span class="sxs-lookup"><span data-stu-id="d71b8-420">Follow the instructions on [Schedule scans with Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span></span>

## <a name="step-11-deploy-microsoft-defender-for-endpoint-for-macos"></a><span data-ttu-id="d71b8-421">Шаг 11. Развертывание Microsoft Defender для конечной точки для macOS</span><span class="sxs-lookup"><span data-stu-id="d71b8-421">Step 11: Deploy Microsoft Defender for Endpoint for macOS</span></span>

1. <span data-ttu-id="d71b8-422">Перейдите к сохраненным `wdav.pkg` местам.</span><span class="sxs-lookup"><span data-stu-id="d71b8-422">Navigate to where you saved `wdav.pkg`.</span></span>

    ![Изображение проводника файлов wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. <span data-ttu-id="d71b8-424">Переименуй его в `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="d71b8-424">Rename it to `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![Изображение проводника файлов1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. <span data-ttu-id="d71b8-426">Откройте панель мониторинга Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="d71b8-426">Open the Jamf Pro dashboard.</span></span>

    ![Изображение параметров конфигурации jamfpro](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. <span data-ttu-id="d71b8-428">Выберите компьютер и нажмите значок передач в верхней части, а затем выберите **управление компьютером**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-428">Select your computer and click the gear icon at the top, then select **Computer Management**.</span></span>

    ![Изображение параметров конфигурации compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. <span data-ttu-id="d71b8-430">В **пакетах** выберите **+ New**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-430">In **Packages**, select **+ New**.</span></span> 
    <span data-ttu-id="d71b8-431">![Изображение, содержащее описание птицы, автоматически генерируется новый пакет](images/57aa4d21e2ccc65466bf284701d4e961.png)</span><span class="sxs-lookup"><span data-stu-id="d71b8-431">![A picture containing bird Description automatically generated package new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span></span>

6. <span data-ttu-id="d71b8-432">В **новом пакете** введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d71b8-432">In **New Package** Enter the following details:</span></span>

    <span data-ttu-id="d71b8-433">**Общая вкладка**</span><span class="sxs-lookup"><span data-stu-id="d71b8-433">**General tab**</span></span>
    - <span data-ttu-id="d71b8-434">Имя отображения. Оставьте его пустым на данный момент.</span><span class="sxs-lookup"><span data-stu-id="d71b8-434">Display Name: Leave it blank for now.</span></span> <span data-ttu-id="d71b8-435">Потому что она будет сброшена при выборе pkg.</span><span class="sxs-lookup"><span data-stu-id="d71b8-435">Because it will be reset when you choose your pkg.</span></span>
    - <span data-ttu-id="d71b8-436">Категория: Нет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d71b8-436">Category: None (default)</span></span>
    - <span data-ttu-id="d71b8-437">Имя файла: выберите файл</span><span class="sxs-lookup"><span data-stu-id="d71b8-437">Filename: Choose File</span></span>

    ![Изображение общей вкладки параметры конфигурации](images/21de3658bf58b1b767a17358a3f06341.png)

    <span data-ttu-id="d71b8-439">Откройте файл и указать его `wdav.pkg` или `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="d71b8-439">Open the file and point it to `wdav.pkg` or `wdav_MDM_Contoso_200329.pkg`.</span></span>
    
    ![Снимок экрана компьютера Описание, автоматически сгенерированное](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. <span data-ttu-id="d71b8-441">Выберите **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-441">Select **Open**.</span></span> <span data-ttu-id="d71b8-442">Установите имя **отображения в** Microsoft **Defender Advanced Threat Protection и антивирус Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-442">Set the **Display Name** to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    <span data-ttu-id="d71b8-443">**Файл Manifest не** требуется.</span><span class="sxs-lookup"><span data-stu-id="d71b8-443">**Manifest File** is not required.</span></span> <span data-ttu-id="d71b8-444">Расширенные средства защиты от угроз Microsoft Defender работают без файла Манифеста.</span><span class="sxs-lookup"><span data-stu-id="d71b8-444">Microsoft Defender Advanced Threat Protection works without Manifest File.</span></span>
    
    <span data-ttu-id="d71b8-445">**Вкладка с параметрами**</span><span class="sxs-lookup"><span data-stu-id="d71b8-445">**Options tab**</span></span><br> <span data-ttu-id="d71b8-446">Сохранение значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d71b8-446">Keep default values.</span></span>

    <span data-ttu-id="d71b8-447">**Вкладка Ограничения**</span><span class="sxs-lookup"><span data-stu-id="d71b8-447">**Limitations tab**</span></span><br> <span data-ttu-id="d71b8-448">Сохранение значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d71b8-448">Keep default values.</span></span>
    
     ![Изображение вкладки ограничения параметров конфигурации](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. <span data-ttu-id="d71b8-450">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-450">Select **Save**.</span></span> <span data-ttu-id="d71b8-451">Пакет загружается в Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="d71b8-451">The package is uploaded to Jamf Pro.</span></span> 

   ![Изображение параметров конфигурации упаковки upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   <span data-ttu-id="d71b8-453">Чтобы пакет был доступен для развертывания, может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="d71b8-453">It can take a few minutes for the package to be available for deployment.</span></span>
   
   ![Образ параметров конфигурации пакет upl](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. <span data-ttu-id="d71b8-455">Перейдите на **страницу Политики.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-455">Navigate to the **Policies** page.</span></span>

    ![Изображение polocies параметров конфигурации](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. <span data-ttu-id="d71b8-457">Выберите **+ Новое** для создания новой политики.</span><span class="sxs-lookup"><span data-stu-id="d71b8-457">Select **+ New** to create a new policy.</span></span>

    ![Изображение параметров конфигурации новой политики](images/847b70e54ed04787e415f5180414b310.png)


11. <span data-ttu-id="d71b8-459">В **общем введите** следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d71b8-459">In **General** Enter the following details:</span></span>

    - <span data-ttu-id="d71b8-460">Имя отображения: MDATP onboarding Contoso 200329 v100.86.92 или более поздней</span><span class="sxs-lookup"><span data-stu-id="d71b8-460">Display name: MDATP Onboarding Contoso 200329 v100.86.92 or later</span></span>

    ![<span data-ttu-id="d71b8-461">Изображение параметров конфигурацииmdatponboard</span><span class="sxs-lookup"><span data-stu-id="d71b8-461">Image of configuration settingsmdatponboard</span></span> ](images/625ba6d19e8597f05e4907298a454d28.png)

12. <span data-ttu-id="d71b8-462">Выберите **повторяемую регистрацию.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-462">Select **Recurring Check-in**.</span></span> 
    
    ![Изображение параметров конфигурации повторно проверить](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. <span data-ttu-id="d71b8-464">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-464">Select **Save**.</span></span> 
 
14. <span data-ttu-id="d71b8-465">Выберите **пакеты > настройка**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-465">Select **Packages > Configure**.</span></span>
 
    ![Образ настройки пакета параметров конфигурации](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. <span data-ttu-id="d71b8-467">Выберите **кнопку Добавить** рядом с **расширенным антивирусом Microsoft Defender Advanced Threat Protection и Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-467">Select the **Add** button next to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    ![Добавление изображений параметров конфигурации MDATP и MDA](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. <span data-ttu-id="d71b8-469">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-469">Select **Save**.</span></span>

    ![Изображение параметров конфигурации](images/9d6e5386e652e00715ff348af72671c6.png)

17. <span data-ttu-id="d71b8-471">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="d71b8-471">Select the **Scope** tab.</span></span>  

    ![Изображение параметров конфигурации scptab](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. <span data-ttu-id="d71b8-473">Выберите целевые компьютеры.</span><span class="sxs-lookup"><span data-stu-id="d71b8-473">Select the target computers.</span></span>

    ![Изображение параметров конфигурации tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    <span data-ttu-id="d71b8-475">**Scope**</span><span class="sxs-lookup"><span data-stu-id="d71b8-475">**Scope**</span></span>
    
    <span data-ttu-id="d71b8-476">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-476">Select **Add**.</span></span>
    
    ![Изображение параметров конфигурации ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Изображение параметров конфигурации ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    <span data-ttu-id="d71b8-479">**Самообслуживка**</span><span class="sxs-lookup"><span data-stu-id="d71b8-479">**Self-Service**</span></span>
    
    ![Изображение самообслуживи параметров конфигурации](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. <span data-ttu-id="d71b8-481">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d71b8-481">Select **Done**.</span></span> 

    ![Изображение параметров конфигурации do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Изображение параметров конфигурации do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




