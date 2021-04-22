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
ms.openlocfilehash: 84d0b37632dc23615a37bbbd73c17fe509dedae5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934685"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a><span data-ttu-id="3213b-104">Настройка конечной точки Microsoft Defender для политик macOS в Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="3213b-104">Set up the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3213b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3213b-105">**Applies to:**</span></span>

- [<span data-ttu-id="3213b-106">Защитник для конечной точки на Mac</span><span class="sxs-lookup"><span data-stu-id="3213b-106">Defender for Endpoint on Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="3213b-107">На этой странице вы сможете найти необходимые действия, чтобы настроить политики macOS в Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="3213b-107">This page will guide you through the steps you need to take to set up macOS policies in Jamf Pro.</span></span>

<span data-ttu-id="3213b-108">Необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3213b-108">You'll need to take the following steps:</span></span>

1. [<span data-ttu-id="3213b-109">Получите пакет onboarding Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3213b-109">Get the Microsoft Defender for Endpoint onboarding package</span></span>](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [<span data-ttu-id="3213b-110">Создание профиля конфигурации в Jamf Pro с помощью бортового пакета</span><span class="sxs-lookup"><span data-stu-id="3213b-110">Create a configuration profile in Jamf Pro using the onboarding package</span></span>](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [<span data-ttu-id="3213b-111">Настройка параметров конечных точек Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3213b-111">Configure Microsoft Defender for Endpoint settings</span></span>](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [<span data-ttu-id="3213b-112">Настройка параметров уведомлений Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3213b-112">Configure Microsoft Defender for Endpoint notification settings</span></span>](#step-4-configure-notifications-settings)

5. [<span data-ttu-id="3213b-113">Настройка Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="3213b-113">Configure Microsoft AutoUpdate (MAU)</span></span>](#step-5-configure-microsoft-autoupdate-mau)

6. [<span data-ttu-id="3213b-114">Предоставление полного доступа к диску Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3213b-114">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [<span data-ttu-id="3213b-115">Утверждение расширения ядра для Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3213b-115">Approve Kernel extension for Microsoft Defender for Endpoint</span></span>](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [<span data-ttu-id="3213b-116">Утверждение расширений системы для Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3213b-116">Approve System extensions for Microsoft Defender for Endpoint</span></span>](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [<span data-ttu-id="3213b-117">Настройка расширения сети</span><span class="sxs-lookup"><span data-stu-id="3213b-117">Configure Network Extension</span></span>](#step-9-configure-network-extension)

10. [<span data-ttu-id="3213b-118">Расписание сканирования с помощью Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="3213b-118">Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [<span data-ttu-id="3213b-119">Развертывание Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="3213b-119">Deploy Microsoft Defender for Endpoint on macOS</span></span>](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a><span data-ttu-id="3213b-120">Шаг 1. Получить пакет onboarding Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3213b-120">Step 1: Get the Microsoft Defender for Endpoint onboarding package</span></span>

1. <span data-ttu-id="3213b-121">В [Центре безопасности Защитника Майкрософт](https://securitycenter.microsoft.com )перейдите к **параметрам > onboarding**.</span><span class="sxs-lookup"><span data-stu-id="3213b-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com ), navigate to **Settings > Onboarding**.</span></span> 

2. <span data-ttu-id="3213b-122">Выберите macOS в качестве операционной системы, а метод развертывания — управление мобильными устройствами и Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="3213b-122">Select macOS as the operating system and Mobile Device Management / Microsoft Intune as the deployment method.</span></span>

    ![Изображение Центра безопасности Защитника Майкрософт](images/onboarding-macos.png)

3. <span data-ttu-id="3213b-124">Выберите **пакет загрузки** (WindowsDefenderATPOnboardingPackage.zip).</span><span class="sxs-lookup"><span data-stu-id="3213b-124">Select **Download onboarding package** (WindowsDefenderATPOnboardingPackage.zip).</span></span>

4. <span data-ttu-id="3213b-125">`WindowsDefenderATPOnboardingPackage.zip`Извлечение .</span><span class="sxs-lookup"><span data-stu-id="3213b-125">Extract `WindowsDefenderATPOnboardingPackage.zip`.</span></span>

5. <span data-ttu-id="3213b-126">Скопируйте файл в предпочтительное расположение.</span><span class="sxs-lookup"><span data-stu-id="3213b-126">Copy the file to your preferred location.</span></span> <span data-ttu-id="3213b-127">Пример: `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span><span class="sxs-lookup"><span data-stu-id="3213b-127">For example,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span></span>


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a><span data-ttu-id="3213b-128">Шаг 2. Создание профиля конфигурации в Jamf Pro с помощью пакета onboarding</span><span class="sxs-lookup"><span data-stu-id="3213b-128">Step 2: Create a configuration profile in Jamf Pro using the onboarding package</span></span>

1. <span data-ttu-id="3213b-129">Найдите файл `WindowsDefenderATPOnboarding.plist` из предыдущего раздела.</span><span class="sxs-lookup"><span data-stu-id="3213b-129">Locate the file `WindowsDefenderATPOnboarding.plist` from the previous section.</span></span>

   ![Изображение файла WindowsDefenderATPOnboarding](images/plist-onboarding-file.png)

 
2. <span data-ttu-id="3213b-131">В панели мониторинга Jamf Pro выберите **New**.</span><span class="sxs-lookup"><span data-stu-id="3213b-131">In the Jamf Pro dashboard, select **New**.</span></span>

    ![Изображение создания новой панели мониторинга Jamf Pro](images/jamf-pro-configure-profile.png)

3. <span data-ttu-id="3213b-133">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="3213b-133">Enter the following details:</span></span>

   <span data-ttu-id="3213b-134">**Общие**</span><span class="sxs-lookup"><span data-stu-id="3213b-134">**General**</span></span>
   - <span data-ttu-id="3213b-135">Имя: бортовая система MDATP для macOS</span><span class="sxs-lookup"><span data-stu-id="3213b-135">Name: MDATP onboarding for macOS</span></span>
   - <span data-ttu-id="3213b-136">Описание. Бортовая система MDATP EDR для macOS</span><span class="sxs-lookup"><span data-stu-id="3213b-136">Description: MDATP EDR onboarding for macOS</span></span>
   - <span data-ttu-id="3213b-137">Категории: None (нет)</span><span class="sxs-lookup"><span data-stu-id="3213b-137">Category: None</span></span>
   - <span data-ttu-id="3213b-138">Метод рассылки: установка автоматически</span><span class="sxs-lookup"><span data-stu-id="3213b-138">Distribution Method: Install Automatically</span></span>
   - <span data-ttu-id="3213b-139">Уровень: уровень компьютера</span><span class="sxs-lookup"><span data-stu-id="3213b-139">Level: Computer Level</span></span>

4. <span data-ttu-id="3213b-140">В **приложении & настраиваемые параметры** выберите **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="3213b-140">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Изображение настройки приложения и настраиваемых параметров](images/jamfpro-mac-profile.png)

5. <span data-ttu-id="3213b-142">Выберите **Файл загрузки (PLIST-файл),** а затем **введите домен preference:** `com.microsoft.wdav.atp` .</span><span class="sxs-lookup"><span data-stu-id="3213b-142">Select **Upload File (PLIST file)** then in **Preference Domain** enter: `com.microsoft.wdav.atp`.</span></span> 

    ![Изображение файла загрузки списка jamfpro](images/jamfpro-plist-upload.png)

    ![Изображение файла списка свойств upload file](images/jamfpro-plist-file.png)

7. <span data-ttu-id="3213b-145">Выберите **Открыть** и выбрать файл вмеяния.</span><span class="sxs-lookup"><span data-stu-id="3213b-145">Select **Open** and select the onboarding file.</span></span>

    ![Изображение бортового файла](images/jamfpro-plist-file-onboard.png)

8. <span data-ttu-id="3213b-147">Выберите **Upload**.</span><span class="sxs-lookup"><span data-stu-id="3213b-147">Select **Upload**.</span></span> 

    ![Изображение загрузки файла plist](images/jamfpro-upload-plist.png)


9. <span data-ttu-id="3213b-149">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="3213b-149">Select the **Scope** tab.</span></span>

    ![Изображение вкладки области](images/jamfpro-scope-tab.png)

10. <span data-ttu-id="3213b-151">Выберите целевые компьютеры.</span><span class="sxs-lookup"><span data-stu-id="3213b-151">Select the target computers.</span></span>

    ![Изображение целевых компьютеров](images/jamfpro-target-computer.png)

    ![Изображение целей](images/jamfpro-targets.png) 

11. <span data-ttu-id="3213b-154">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-154">Select **Save**.</span></span>

    ![Изображение целевых компьютеров развертывания](images/jamfpro-deployment-target.png)

    ![Изображение выбранных целевых компьютеров](images/jamfpro-target-selected.png)

12. <span data-ttu-id="3213b-157">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3213b-157">Select **Done**.</span></span>

    ![Изображение компьютеров целевой группы](images/jamfpro-target-group.png)

    ![Список профилей конфигурации](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a><span data-ttu-id="3213b-160">Шаг 3. Настройка защитника Майкрософт для параметров конечной точки</span><span class="sxs-lookup"><span data-stu-id="3213b-160">Step 3: Configure Microsoft Defender for Endpoint settings</span></span>

1.  <span data-ttu-id="3213b-161">Используйте следующие параметры конфигурации Microsoft Defender для конечных точек:</span><span class="sxs-lookup"><span data-stu-id="3213b-161">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

    - <span data-ttu-id="3213b-162">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="3213b-162">enableRealTimeProtection</span></span>
    - <span data-ttu-id="3213b-163">passiveMode</span><span class="sxs-lookup"><span data-stu-id="3213b-163">passiveMode</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="3213b-164">Не включено по умолчанию, если вы планируете запустить сторонний AV для macOS, установите `true` его.</span><span class="sxs-lookup"><span data-stu-id="3213b-164">Not turned on by default, if you are planning to run a third-party AV for macOS, set it to `true`.</span></span>

    - <span data-ttu-id="3213b-165">исключения</span><span class="sxs-lookup"><span data-stu-id="3213b-165">exclusions</span></span>
    - <span data-ttu-id="3213b-166">excludedPath</span><span class="sxs-lookup"><span data-stu-id="3213b-166">excludedPath</span></span>
    - <span data-ttu-id="3213b-167">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="3213b-167">excludedFileExtension</span></span>
    - <span data-ttu-id="3213b-168">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="3213b-168">excludedFileName</span></span>
    - <span data-ttu-id="3213b-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="3213b-169">exclusionsMergePolicy</span></span>
    - <span data-ttu-id="3213b-170">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="3213b-170">allowedThreats</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="3213b-171">EICAR находится в примере, если вы проходите проверку концепции, удалите ее, особенно если вы тестируете EICAR.</span><span class="sxs-lookup"><span data-stu-id="3213b-171">EICAR is on the sample, if you are going through a proof-of-concept, remove it especially if you are testing EICAR.</span></span>
        
    - <span data-ttu-id="3213b-172">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="3213b-172">disallowedThreatActions</span></span>
    - <span data-ttu-id="3213b-173">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="3213b-173">potentially_unwanted_application</span></span>
    - <span data-ttu-id="3213b-174">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="3213b-174">archive_bomb</span></span>
    - <span data-ttu-id="3213b-175">cloudService</span><span class="sxs-lookup"><span data-stu-id="3213b-175">cloudService</span></span>
    - <span data-ttu-id="3213b-176">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="3213b-176">automaticSampleSubmission</span></span>
    - <span data-ttu-id="3213b-177">tags</span><span class="sxs-lookup"><span data-stu-id="3213b-177">tags</span></span>
    - <span data-ttu-id="3213b-178">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="3213b-178">hideStatusMenuIcon</span></span>
    
     <span data-ttu-id="3213b-179">Сведения см. в [списке свойств для профиля конфигурации Jamf.](mac-preferences.md#property-list-for-jamf-configuration-profile)</span><span class="sxs-lookup"><span data-stu-id="3213b-179">For information, see [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).</span></span>

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

2. <span data-ttu-id="3213b-180">Сохраните файл как `MDATP_MDAV_configuration_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="3213b-180">Save the file as `MDATP_MDAV_configuration_settings.plist`.</span></span>


3.  <span data-ttu-id="3213b-181">В панели мониторинга Jamf Pro выберите **General**.</span><span class="sxs-lookup"><span data-stu-id="3213b-181">In the Jamf Pro dashboard, select **General**.</span></span>

    ![Изображение новой панели мониторинга Jamf Pro](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. <span data-ttu-id="3213b-183">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="3213b-183">Enter the following details:</span></span>

    <span data-ttu-id="3213b-184">**Общие**</span><span class="sxs-lookup"><span data-stu-id="3213b-184">**General**</span></span>
    
    - <span data-ttu-id="3213b-185">Имя: параметры конфигурации MDATP MDAV</span><span class="sxs-lookup"><span data-stu-id="3213b-185">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="3213b-186">Описание:\<blank\></span><span class="sxs-lookup"><span data-stu-id="3213b-186">Description:\<blank\></span></span>
    - <span data-ttu-id="3213b-187">Категория: Нет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3213b-187">Category: None (default)</span></span>
    - <span data-ttu-id="3213b-188">Метод рассылки: установка автоматически (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3213b-188">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="3213b-189">Уровень: уровень компьютера (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3213b-189">Level: Computer Level(default)</span></span>

    ![Изображение параметров конфигурации MDATP MDAV](images/3160906404bc5a2edf84d1d015894e3b.png)

5. <span data-ttu-id="3213b-191">В **приложении & настраиваемые параметры** выберите **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="3213b-191">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Изображение параметров приложения и настраиваемого](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. <span data-ttu-id="3213b-193">Выберите **файл загрузки (PLIST-файл).**</span><span class="sxs-lookup"><span data-stu-id="3213b-193">Select **Upload File (PLIST file)**.</span></span>

    ![Изображение файла plist параметров конфигурации](images/6f85269276b2278eca4bce84f935f87b.png)

7. <span data-ttu-id="3213b-195">В **домене Preferences введите,** `com.microsoft.wdav` а затем выберите Файл  **загрузки PLIST**.</span><span class="sxs-lookup"><span data-stu-id="3213b-195">In **Preferences Domain**, enter `com.microsoft.wdav`, then select  **Upload PLIST File**.</span></span>

    ![Изображение домена настроек конфигурации](images/db15f147dd959e872a044184711d7d46.png)

8. <span data-ttu-id="3213b-197">Выберите **выберите файл**.</span><span class="sxs-lookup"><span data-stu-id="3213b-197">Select **Choose File**.</span></span>

    ![Изображение параметров конфигурации выберите файл](images/526e978761fc571cca06907da7b01fd6.png)

9. <span data-ttu-id="3213b-199">Выберите **список MDATP_MDAV_configuration_settings.plist,** а затем **откройте**.</span><span class="sxs-lookup"><span data-stu-id="3213b-199">Select the **MDATP_MDAV_configuration_settings.plist**, then select **Open**.</span></span>

    ![Изображение параметров конфигурации mdatpmdav](images/98acea3750113b8dbab334296e833003.png)

10. <span data-ttu-id="3213b-201">Выберите **Upload**.</span><span class="sxs-lookup"><span data-stu-id="3213b-201">Select **Upload**.</span></span>

    ![Изображение загрузки параметра конфигурации](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Изображение параметров настройки загрузки изображения](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    ><span data-ttu-id="3213b-204">Если вы загрузите файл Intune, вы получите следующую ошибку:</span><span class="sxs-lookup"><span data-stu-id="3213b-204">If you happen to upload the Intune file, you'll get the following error:</span></span><br>
    ><span data-ttu-id="3213b-205">![Изображение загрузки файлов intune параметров конфигурации](images/8e69f867664668796a3b2904896f0436.png)</span><span class="sxs-lookup"><span data-stu-id="3213b-205">![Image of configuration settings intune file upload](images/8e69f867664668796a3b2904896f0436.png)</span></span>


11. <span data-ttu-id="3213b-206">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-206">Select **Save**.</span></span> 

    ![Изображение параметров конфигурации Сохранить изображение](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. <span data-ttu-id="3213b-208">Файл загружен.</span><span class="sxs-lookup"><span data-stu-id="3213b-208">The file is uploaded.</span></span>

    ![Изображение загруженного изображения файла параметров конфигурации](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Изображение загруженного файла параметров конфигурации](images/a422e57fe8d45689227e784443e51bd1.png)

13. <span data-ttu-id="3213b-211">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="3213b-211">Select the **Scope** tab.</span></span>

    ![Изображение области параметров конфигурации](images/9fc17529e5577eefd773c658ec576a7d.png)

14. <span data-ttu-id="3213b-213">Выберите **машинную группу Contoso.**</span><span class="sxs-lookup"><span data-stu-id="3213b-213">Select **Contoso's Machine Group**.</span></span> 

15. <span data-ttu-id="3213b-214">Выберите **Добавить,** а затем **выберите Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-214">Select **Add**, then select **Save**.</span></span>

    ![Изображение параметров конфигурации addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Изображение параметров конфигурации сохранить добавить](images/6f093e42856753a3955cab7ee14f12d9.png)

16. <span data-ttu-id="3213b-217">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3213b-217">Select **Done**.</span></span> <span data-ttu-id="3213b-218">Вы увидите новый профиль **Конфигурация**.</span><span class="sxs-lookup"><span data-stu-id="3213b-218">You'll see the new **Configuration profile**.</span></span>

    ![Изображение конфигурации параметров конфигурировать изображение профиля](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a><span data-ttu-id="3213b-220">Шаг 4. Настройка параметров уведомлений</span><span class="sxs-lookup"><span data-stu-id="3213b-220">Step 4: Configure notifications settings</span></span>

<span data-ttu-id="3213b-221">Эти действия применимы к macOS 10.15 (Catalina) или более новым.</span><span class="sxs-lookup"><span data-stu-id="3213b-221">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="3213b-222">В панели мониторинга Jamf Pro выберите **компьютеры,** а затем **профили конфигурации.**</span><span class="sxs-lookup"><span data-stu-id="3213b-222">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="3213b-223">Нажмите **кнопку New** и введите следующие сведения для **Параметры**:</span><span class="sxs-lookup"><span data-stu-id="3213b-223">Click **New**, and enter the following details for **Options**:</span></span>
    
    - <span data-ttu-id="3213b-224">Tab **General:**</span><span class="sxs-lookup"><span data-stu-id="3213b-224">Tab **General**:</span></span> 
        - <span data-ttu-id="3213b-225">**Имя:** параметры MDATP MDAV Notification</span><span class="sxs-lookup"><span data-stu-id="3213b-225">**Name**: MDATP MDAV Notification settings</span></span>
        - <span data-ttu-id="3213b-226">**Описание:** macOS 10.15 (Catalina) или более новый</span><span class="sxs-lookup"><span data-stu-id="3213b-226">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="3213b-227">**Категория:** Нет *(по умолчанию)*</span><span class="sxs-lookup"><span data-stu-id="3213b-227">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="3213b-228">**Метод рассылки:** Установка автоматически *(по умолчанию)*</span><span class="sxs-lookup"><span data-stu-id="3213b-228">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="3213b-229">**Уровень**: Уровень компьютера *(по умолчанию)*</span><span class="sxs-lookup"><span data-stu-id="3213b-229">**Level**: Computer Level *(default)*</span></span>

        ![Изображение нового экрана профиля конфигурации macOS](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - <span data-ttu-id="3213b-231">Tab **Notifications,** **нажмите кнопку Добавить** и введите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="3213b-231">Tab **Notifications**, click **Add**, and enter the following values:</span></span>
        - <span data-ttu-id="3213b-232">**Bundle ID:**`com.microsoft.wdav.tray`</span><span class="sxs-lookup"><span data-stu-id="3213b-232">**Bundle ID**: `com.microsoft.wdav.tray`</span></span>
        - <span data-ttu-id="3213b-233">**Критические оповещения:** нажмите **кнопку Отключение**</span><span class="sxs-lookup"><span data-stu-id="3213b-233">**Critical Alerts**: Click **Disable**</span></span>
        - <span data-ttu-id="3213b-234">**Уведомления:** щелкните **Включить**</span><span class="sxs-lookup"><span data-stu-id="3213b-234">**Notifications**: Click **Enable**</span></span>
        - <span data-ttu-id="3213b-235">**Тип оповещения баннера:** **Выберите включить и** временно **(по** *умолчанию)*</span><span class="sxs-lookup"><span data-stu-id="3213b-235">**Banner alert type**: Select **Include** and **Temporary** *(default)*</span></span>
        - <span data-ttu-id="3213b-236">**Уведомления на экране блокировки:** нажмите кнопку **Скрыть**</span><span class="sxs-lookup"><span data-stu-id="3213b-236">**Notifications on lock screen**: Click **Hide**</span></span>
        - <span data-ttu-id="3213b-237">**Уведомления в Центре уведомлений:** щелкните **отображение**</span><span class="sxs-lookup"><span data-stu-id="3213b-237">**Notifications in Notification Center**: Click **Display**</span></span>
        - <span data-ttu-id="3213b-238">**Значок приложения Badge:** Щелкните **Дисплей**</span><span class="sxs-lookup"><span data-stu-id="3213b-238">**Badge app icon**: Click **Display**</span></span>

        ![Изображение лотка уведомлений mdatpmdav параметров конфигурации](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - <span data-ttu-id="3213b-240">Tab **Notifications**, **щелкните Добавить** еще раз, прокрутите вниз **к новым настройкам уведомлений**</span><span class="sxs-lookup"><span data-stu-id="3213b-240">Tab **Notifications**, click **Add** one more time, scroll down to **New Notifications Settings**</span></span>
        - <span data-ttu-id="3213b-241">**Bundle ID:**`com.microsoft.autoupdate2`</span><span class="sxs-lookup"><span data-stu-id="3213b-241">**Bundle ID**: `com.microsoft.autoupdate2`</span></span>
        - <span data-ttu-id="3213b-242">Настройка остальных параметров на те же значения, что и выше</span><span class="sxs-lookup"><span data-stu-id="3213b-242">Configure the rest of the settings to the same values as above</span></span>

        ![Изображение параметров конфигурации mdatpmdav notifications mau](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        <span data-ttu-id="3213b-244">Обратите внимание, что теперь у вас есть две "таблицы" с конфигурациями уведомлений, одна для bundle **ID: com.microsoft.wdav.tray** и другая для **Bundle ID: com.microsoft.autoupdate2**.</span><span class="sxs-lookup"><span data-stu-id="3213b-244">Note that now you have two 'tables' with notification configurations, one for **Bundle ID: com.microsoft.wdav.tray**, and another for **Bundle ID: com.microsoft.autoupdate2**.</span></span> <span data-ttu-id="3213b-245">Хотя вы можете настроить параметры оповещения в зависимости от ваших требований, набор ID должен быть точно таким же, как описано ранее, и **включить** переключатель должен быть **включен** для **уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="3213b-245">While you can configure alert settings per your requirements, Bundle IDs must be exactly the same as described before, and **Include** switch must be **On** for **Notifications**.</span></span>

3. <span data-ttu-id="3213b-246">Выберите **вкладку Область,** а **затем** добавьте .</span><span class="sxs-lookup"><span data-stu-id="3213b-246">Select the **Scope** tab, then select **Add**.</span></span>

    ![Добавлено изображение области параметров конфигурации](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. <span data-ttu-id="3213b-248">Выберите **машинную группу Contoso.**</span><span class="sxs-lookup"><span data-stu-id="3213b-248">Select **Contoso's Machine Group**.</span></span> 

5. <span data-ttu-id="3213b-249">Выберите **Добавить,** а затем **выберите Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-249">Select **Add**, then select **Save**.</span></span>
    
    ![Image of configuration settings contoso machine grp save](images/09a275e321268e5e3ac0c0865d3e2db5.png)
    
    ![Изображение параметров конфигурации добавить сохранить](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. <span data-ttu-id="3213b-252">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3213b-252">Select **Done**.</span></span> <span data-ttu-id="3213b-253">Вы увидите новый профиль **Конфигурация**.</span><span class="sxs-lookup"><span data-stu-id="3213b-253">You'll see the new **Configuration profile**.</span></span>
    <span data-ttu-id="3213b-254">![Изображение параметра конфигурации сделано img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span><span class="sxs-lookup"><span data-stu-id="3213b-254">![Image of configuration setting done img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span></span>

## <a name="step-5-configure-microsoft-autoupdate-mau"></a><span data-ttu-id="3213b-255">Шаг 5. Настройка Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="3213b-255">Step 5: Configure Microsoft AutoUpdate (MAU)</span></span>

1. <span data-ttu-id="3213b-256">Используйте следующие параметры конфигурации Microsoft Defender для конечных точек:</span><span class="sxs-lookup"><span data-stu-id="3213b-256">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

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

2. <span data-ttu-id="3213b-257">Сохраните его как `MDATP_MDAV_MAU_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="3213b-257">Save it as `MDATP_MDAV_MAU_settings.plist`.</span></span>

3. <span data-ttu-id="3213b-258">В панели мониторинга Jamf Pro выберите **General**.</span><span class="sxs-lookup"><span data-stu-id="3213b-258">In the Jamf Pro dashboard, select **General**.</span></span> 

    ![Изображение общего образа настройки конфигурации](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. <span data-ttu-id="3213b-260">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="3213b-260">Enter the following details:</span></span>

    <span data-ttu-id="3213b-261">**Общие**</span><span class="sxs-lookup"><span data-stu-id="3213b-261">**General**</span></span> 
    
    - <span data-ttu-id="3213b-262">Имя: параметры MDATP MDAV MAU</span><span class="sxs-lookup"><span data-stu-id="3213b-262">Name: MDATP MDAV MAU settings</span></span>
    - <span data-ttu-id="3213b-263">Описание. Параметры Microsoft AutoUpdate для MDATP для macOS</span><span class="sxs-lookup"><span data-stu-id="3213b-263">Description: Microsoft AutoUpdate settings for MDATP for macOS</span></span>
    - <span data-ttu-id="3213b-264">Категория: Нет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3213b-264">Category: None (default)</span></span>
    - <span data-ttu-id="3213b-265">Метод рассылки: установка автоматически (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3213b-265">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="3213b-266">Уровень: уровень компьютера (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3213b-266">Level: Computer Level(default)</span></span>

5. <span data-ttu-id="3213b-267">В **приложении & настраиваемые параметры** выберите **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="3213b-267">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Изображение приложения настройки конфигурации и настраиваемые параметры](images/1f72e9c15eaafcabf1504397e99be311.png)

6. <span data-ttu-id="3213b-269">Выберите **файл загрузки (PLIST-файл).**</span><span class="sxs-lookup"><span data-stu-id="3213b-269">Select **Upload File (PLIST file)**.</span></span>

    ![Изображение plist настройки конфигурации](images/1213872db5833aa8be535da57653219f.png)  

7. <span data-ttu-id="3213b-271">В **домене Preference** введите: `com.microsoft.autoupdate2` затем выберите Файл **загрузки PLIST.**</span><span class="sxs-lookup"><span data-stu-id="3213b-271">In **Preference Domain** enter: `com.microsoft.autoupdate2`, then select **Upload PLIST File**.</span></span>

    ![Изображение предварительного домена настройки настройки](images/1213872db5833aa8be535da57653219f.png)

8. <span data-ttu-id="3213b-273">Выберите **выберите файл**.</span><span class="sxs-lookup"><span data-stu-id="3213b-273">Select **Choose File**.</span></span>

    ![Изображение параметра конфигурации choosefile](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. <span data-ttu-id="3213b-275">Выберите **MDATP_MDAV_MAU_settings.plist**.</span><span class="sxs-lookup"><span data-stu-id="3213b-275">Select **MDATP_MDAV_MAU_settings.plist**.</span></span>

    ![Изображение параметров настройки mdatpmdavmau](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. <span data-ttu-id="3213b-277">Выберите **Upload**.</span><span class="sxs-lookup"><span data-stu-id="3213b-277">Select **Upload**.</span></span>
    <span data-ttu-id="3213b-278">![Изображение настройки настройки uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span><span class="sxs-lookup"><span data-stu-id="3213b-278">![Image of configuration setting uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span></span>

    ![Изображение настройки настройки uplimg](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. <span data-ttu-id="3213b-280">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-280">Select **Save**.</span></span>

    ![Изображение параметра конфигурации saveimg](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. <span data-ttu-id="3213b-282">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="3213b-282">Select the **Scope** tab.</span></span>
   
     ![Изображение scopetab настройки конфигурации](images/10ab98358b2d602f3f67618735fa82fb.png)

13. <span data-ttu-id="3213b-284">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-284">Select **Add**.</span></span>
    
    ![Изображение параметра конфигурации addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Изображение параметра конфигурации addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Изображение параметра конфигурации addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. <span data-ttu-id="3213b-288">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3213b-288">Select **Done**.</span></span>
    
    ![Image of configuration setting doneimage](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="3213b-290">Шаг 6. Предоставление полного доступа к диску Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3213b-290">Step 6: Grant full disk access to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="3213b-291">В панели мониторинга Jamf Pro выберите **профили конфигурации.**</span><span class="sxs-lookup"><span data-stu-id="3213b-291">In the Jamf Pro dashboard, select **Configuration Profiles**.</span></span>

    ![Изображение профиля конфигурации настройки конфигурации](images/264493cd01e62c7085659d6fdc26dc91.png)

2. <span data-ttu-id="3213b-293">Выберите **+ Новый**.</span><span class="sxs-lookup"><span data-stu-id="3213b-293">Select **+ New**.</span></span> 

3. <span data-ttu-id="3213b-294">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="3213b-294">Enter the following details:</span></span>

    <span data-ttu-id="3213b-295">**Общие**</span><span class="sxs-lookup"><span data-stu-id="3213b-295">**General**</span></span> 
    - <span data-ttu-id="3213b-296">Имя: MDATP MDAV — предоставление полного доступа к диску EDR и AV</span><span class="sxs-lookup"><span data-stu-id="3213b-296">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span></span>
    - <span data-ttu-id="3213b-297">Описание. Для macOS Catalina или более нового управления политикой конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="3213b-297">Description: On macOS Catalina or newer, the new Privacy Preferences Policy Control</span></span>
    - <span data-ttu-id="3213b-298">Категории: None (нет)</span><span class="sxs-lookup"><span data-stu-id="3213b-298">Category: None</span></span>
    - <span data-ttu-id="3213b-299">Метод рассылки: установка автоматически</span><span class="sxs-lookup"><span data-stu-id="3213b-299">Distribution method: Install Automatically</span></span>
    - <span data-ttu-id="3213b-300">Уровень: уровень компьютера</span><span class="sxs-lookup"><span data-stu-id="3213b-300">Level: Computer level</span></span>


    ![Изображение общего параметра настройки конфигурации](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. <span data-ttu-id="3213b-302">В **Настройка политики настройки предпочтений конфиденциальности выберите** **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="3213b-302">In **Configure Privacy Preferences Policy Control** select **Configure**.</span></span>

    ![Изображение управления политикой конфиденциальности конфигурации](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. <span data-ttu-id="3213b-304">В правилах управления **политиками конфиденциальности** введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="3213b-304">In **Privacy Preferences Policy Control**, enter the following details:</span></span>

    - <span data-ttu-id="3213b-305">Идентификатор: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="3213b-305">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="3213b-306">Тип идентификатора: идентификатор пакета</span><span class="sxs-lookup"><span data-stu-id="3213b-306">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="3213b-307">Требование кода: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="3213b-307">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>


    ![Изображение сведений о настройке политики настройки конфиденциальности.](images/22cb439de958101c0a12f3038f905b27.png)

6. <span data-ttu-id="3213b-309">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-309">Select **+ Add**.</span></span>

    ![Изображение параметра конфигурации добавить системную политику во все файлы](images/bd93e78b74c2660a0541af4690dd9485.png)

    - <span data-ttu-id="3213b-311">В приложении или службе: установите **systemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="3213b-311">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="3213b-312">В статье "Доступ": набор **разрешить**</span><span class="sxs-lookup"><span data-stu-id="3213b-312">Under "access": Set to **Allow**</span></span>

7. <span data-ttu-id="3213b-313">Выберите **Сохранить** (не тот, который внизу справа).</span><span class="sxs-lookup"><span data-stu-id="3213b-313">Select **Save** (not the one at the bottom right).</span></span>

    ![Изображение параметра конфигурации сохранить изображения](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. <span data-ttu-id="3213b-315">Щелкните `+` знак рядом с **доступом к приложению,** чтобы добавить новую запись.</span><span class="sxs-lookup"><span data-stu-id="3213b-315">Click the `+` sign next to **App Access** to add a new entry.</span></span>

    ![Изображение доступа к приложению настройки конфигурации](images/tcc-add-entry.png)

9. <span data-ttu-id="3213b-317">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="3213b-317">Enter the following details:</span></span>

    - <span data-ttu-id="3213b-318">Идентификатор: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="3213b-318">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="3213b-319">Тип идентификатора: идентификатор пакета</span><span class="sxs-lookup"><span data-stu-id="3213b-319">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="3213b-320">Требование кода: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="3213b-320">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

10. <span data-ttu-id="3213b-321">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-321">Select **+ Add**.</span></span>

    ![Изображение записи epsext параметра конфигурации tcc](images/tcc-epsext-entry.png)

    - <span data-ttu-id="3213b-323">В приложении или службе: установите **systemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="3213b-323">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="3213b-324">В статье "Доступ": набор **разрешить**</span><span class="sxs-lookup"><span data-stu-id="3213b-324">Under "access": Set to **Allow**</span></span>

11. <span data-ttu-id="3213b-325">Выберите **Сохранить** (не тот, который внизу справа).</span><span class="sxs-lookup"><span data-stu-id="3213b-325">Select **Save** (not the one at the bottom right).</span></span>

    ![Изображение параметра конфигурации tcc epsext image2](images/tcc-epsext-entry2.png)

12. <span data-ttu-id="3213b-327">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="3213b-327">Select the **Scope** tab.</span></span>

    ![Изображение области настройки конфигурации](images/2c49b16cd112729b3719724f581e6882.png)

13. <span data-ttu-id="3213b-329">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-329">Select **+ Add**.</span></span>

    ![Изображение надстройки параметра конфигурации](images/57cef926d1b9260fb74a5f460cee887a.png)

14. <span data-ttu-id="3213b-331">Выберите **группы** компьютеров > **под названием** группы > **выберите MachineGroup Contoso.**</span><span class="sxs-lookup"><span data-stu-id="3213b-331">Select **Computer Groups** > under **Group Name** > select **Contoso's MachineGroup**.</span></span> 

    ![Изображение параметра конфигурации contoso machinegrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. <span data-ttu-id="3213b-333">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-333">Select **Add**.</span></span> 

16. <span data-ttu-id="3213b-334">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-334">Select **Save**.</span></span> 
    
17. <span data-ttu-id="3213b-335">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3213b-335">Select **Done**.</span></span>
    
    ![Изображение donimg параметра конфигурации](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![Изображение параметра конфигурации donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)

<span data-ttu-id="3213b-338">Кроме того, вы можете скачать [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) и загрузить его в профили конфигурации JAMF, как описано в развертывании пользовательских профилей конфигурации с помощью [Jamf Pro| Метод 2. Загрузите профиль конфигурации в Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span><span class="sxs-lookup"><span data-stu-id="3213b-338">Alternatively, you can download [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="3213b-339">Шаг 7. Утверждение расширения ядра для Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3213b-339">Step 7: Approve Kernel extension for Microsoft Defender for Endpoint</span></span>

> [!CAUTION]
> <span data-ttu-id="3213b-340">Устройства Apple Silicon (M1) не поддерживают KEXT.</span><span class="sxs-lookup"><span data-stu-id="3213b-340">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="3213b-341">Установка профиля конфигурации, состоящего из политик KEXT, не будет работать на этих устройствах.</span><span class="sxs-lookup"><span data-stu-id="3213b-341">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="3213b-342">В **профилях конфигурации** выберите **+ New**.</span><span class="sxs-lookup"><span data-stu-id="3213b-342">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Снимок экрана сообщения в социальных сетях, автоматически созданный](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="3213b-344">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="3213b-344">Enter the following details:</span></span>

    <span data-ttu-id="3213b-345">**Общие**</span><span class="sxs-lookup"><span data-stu-id="3213b-345">**General**</span></span> 
    
    - <span data-ttu-id="3213b-346">Имя. Расширение Ядра MDAV MDAV</span><span class="sxs-lookup"><span data-stu-id="3213b-346">Name: MDATP MDAV Kernel Extension</span></span>
    - <span data-ttu-id="3213b-347">Описание: расширение ядра MDATP (kext)</span><span class="sxs-lookup"><span data-stu-id="3213b-347">Description: MDATP kernel extension (kext)</span></span>
    - <span data-ttu-id="3213b-348">Категории: None (нет)</span><span class="sxs-lookup"><span data-stu-id="3213b-348">Category: None</span></span>
    - <span data-ttu-id="3213b-349">Метод рассылки: установка автоматически</span><span class="sxs-lookup"><span data-stu-id="3213b-349">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="3213b-350">Уровень: уровень компьютера</span><span class="sxs-lookup"><span data-stu-id="3213b-350">Level: Computer Level</span></span>

    ![Изображение параметров конфигурации ядра mdatpmdav](images/24e290f5fc309932cf41f3a280d22c14.png)

3. <span data-ttu-id="3213b-352">В **Настройка утвержденных расширений ядра** выберите **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="3213b-352">In **Configure Approved Kernel Extensions** select **Configure**.</span></span>

    ![Изображение параметров конфигурации, утвержденных ext ядра](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. <span data-ttu-id="3213b-354">В **утвержденных расширениях ядра** введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="3213b-354">In **Approved Kernel Extensions** Enter the following details:</span></span>

    - <span data-ttu-id="3213b-355">Имя отображения: Корпорация Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3213b-355">Display Name: Microsoft Corp.</span></span>
    - <span data-ttu-id="3213b-356">ID команды: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="3213b-356">Team ID: UBF8T346G9</span></span>

    ![Изображение параметров конфигурации расширения ядра appr](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. <span data-ttu-id="3213b-358">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="3213b-358">Select the **Scope** tab.</span></span>

    ![Image of configuration settings scope tab img](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="3213b-360">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-360">Select **+ Add**.</span></span>

7. <span data-ttu-id="3213b-361">Выберите **группы** > **в соответствии с названием** группы > выберите **группу машин Contoso.**</span><span class="sxs-lookup"><span data-stu-id="3213b-361">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="3213b-362">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-362">Select **+ Add**.</span></span>

    ![Изображение параметров конфигурации добавить изображения](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="3213b-364">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-364">Select **Save**.</span></span>

    ![Изображение параметров конфигурации saveimag](images/0add8019b85a453b47fa5c402c72761b.png)

10. <span data-ttu-id="3213b-366">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3213b-366">Select **Done**.</span></span>

    ![Изображение параметров конфигурации doneimag](images/1c9bd3f68db20b80193dac18f33c22d0.png)

<span data-ttu-id="3213b-368">Кроме того, вы можете скачать [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) и загрузить его в профили конфигурации JAMF, как описано в развертывании пользовательских профилей конфигурации с помощью [Jamf Pro| Метод 2. Загрузите профиль конфигурации в Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span><span class="sxs-lookup"><span data-stu-id="3213b-368">Alternatively, you can download [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="3213b-369">Шаг 8. Утверждение расширений системы для Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3213b-369">Step 8: Approve System extensions for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="3213b-370">В **профилях конфигурации** выберите **+ New**.</span><span class="sxs-lookup"><span data-stu-id="3213b-370">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Снимок экрана сообщения в социальных сетях, автоматически созданный](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="3213b-372">Введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="3213b-372">Enter the following details:</span></span>

    <span data-ttu-id="3213b-373">**Общие**</span><span class="sxs-lookup"><span data-stu-id="3213b-373">**General**</span></span>
    
    - <span data-ttu-id="3213b-374">Имя: MDATP MDAV System Extensions</span><span class="sxs-lookup"><span data-stu-id="3213b-374">Name: MDATP MDAV System Extensions</span></span>
    - <span data-ttu-id="3213b-375">Описание: расширения системы MDATP</span><span class="sxs-lookup"><span data-stu-id="3213b-375">Description: MDATP system extensions</span></span>
    - <span data-ttu-id="3213b-376">Категории: None (нет)</span><span class="sxs-lookup"><span data-stu-id="3213b-376">Category: None</span></span>
    - <span data-ttu-id="3213b-377">Метод рассылки: установка автоматически</span><span class="sxs-lookup"><span data-stu-id="3213b-377">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="3213b-378">Уровень: уровень компьютера</span><span class="sxs-lookup"><span data-stu-id="3213b-378">Level: Computer Level</span></span>

    ![Изображение параметров конфигурации sysext new prof](images/sysext-new-profile.png)

3. <span data-ttu-id="3213b-380">В **расширении системы** выберите **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="3213b-380">In **System Extensions** select **Configure**.</span></span>

   ![Изображение параметров конфигурации sysext config](images/sysext-configure.png)

4. <span data-ttu-id="3213b-382">В **расширении системы введите** следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="3213b-382">In **System Extensions** enter the following details:</span></span>

   - <span data-ttu-id="3213b-383">Имя отображения: расширения системы Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="3213b-383">Display Name: Microsoft Corp. System Extensions</span></span>
   - <span data-ttu-id="3213b-384">Типы расширения системы: разрешенные расширения системы</span><span class="sxs-lookup"><span data-stu-id="3213b-384">System Extension Types: Allowed System Extensions</span></span>
   - <span data-ttu-id="3213b-385">Идентификатор команды: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="3213b-385">Team Identifier: UBF8T346G9</span></span>
   - <span data-ttu-id="3213b-386">Разрешенные расширения системы:</span><span class="sxs-lookup"><span data-stu-id="3213b-386">Allowed System Extensions:</span></span>
     - <span data-ttu-id="3213b-387">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="3213b-387">**com.microsoft.wdav.epsext**</span></span>
     - <span data-ttu-id="3213b-388">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="3213b-388">**com.microsoft.wdav.netext**</span></span>

    ![Изображение параметров конфигурации sysextconfig2](images/sysext-configure2.png)

5. <span data-ttu-id="3213b-390">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="3213b-390">Select the **Scope** tab.</span></span>

    ![Image of configuration settings scopeimage](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="3213b-392">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-392">Select **+ Add**.</span></span>

7. <span data-ttu-id="3213b-393">Выберите **группы** > **в соответствии с названием** группы > выберите **группу машин Contoso.**</span><span class="sxs-lookup"><span data-stu-id="3213b-393">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="3213b-394">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-394">Select **+ Add**.</span></span>

   ![Изображение параметров конфигурации addima](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="3213b-396">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-396">Select **Save**.</span></span>

   ![Изображение параметров конфигурации sysext](images/sysext-scope.png)

10. <span data-ttu-id="3213b-398">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3213b-398">Select **Done**.</span></span>

    ![Изображение параметров конфигурации sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a><span data-ttu-id="3213b-400">Шаг 9. Настройка расширения сети</span><span class="sxs-lookup"><span data-stu-id="3213b-400">Step 9: Configure Network Extension</span></span>

<span data-ttu-id="3213b-401">В рамках возможностей обнаружения конечных точек и ответов Microsoft Defender for Endpoint на macOS проверяет трафик розетки и передает эти сведения на портал Центра безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="3213b-401">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="3213b-402">Следующая политика позволяет сетевому расширению выполнять эту функцию.</span><span class="sxs-lookup"><span data-stu-id="3213b-402">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="3213b-403">Эти действия применимы к macOS 10.15 (Catalina) или более новым.</span><span class="sxs-lookup"><span data-stu-id="3213b-403">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="3213b-404">В панели мониторинга Jamf Pro выберите **компьютеры,** а затем **профили конфигурации.**</span><span class="sxs-lookup"><span data-stu-id="3213b-404">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="3213b-405">Нажмите **кнопку New** и введите следующие сведения для **Параметры**:</span><span class="sxs-lookup"><span data-stu-id="3213b-405">Click **New**, and enter the following details for **Options**:</span></span>

    - <span data-ttu-id="3213b-406">Tab **General:**</span><span class="sxs-lookup"><span data-stu-id="3213b-406">Tab **General**:</span></span> 
        - <span data-ttu-id="3213b-407">**Имя:** Расширение сети ATP Защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3213b-407">**Name**: Microsoft Defender ATP Network Extension</span></span>
        - <span data-ttu-id="3213b-408">**Описание:** macOS 10.15 (Catalina) или более новый</span><span class="sxs-lookup"><span data-stu-id="3213b-408">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="3213b-409">**Категория:** Нет *(по умолчанию)*</span><span class="sxs-lookup"><span data-stu-id="3213b-409">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="3213b-410">**Метод рассылки:** Установка автоматически *(по умолчанию)*</span><span class="sxs-lookup"><span data-stu-id="3213b-410">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="3213b-411">**Уровень**: Уровень компьютера *(по умолчанию)*</span><span class="sxs-lookup"><span data-stu-id="3213b-411">**Level**: Computer Level *(default)*</span></span>

    - <span data-ttu-id="3213b-412">Фильтр **контента вкладок:**</span><span class="sxs-lookup"><span data-stu-id="3213b-412">Tab **Content Filter**:</span></span>
        - <span data-ttu-id="3213b-413">**Имя фильтра:** фильтр контента ATP Защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3213b-413">**Filter Name**: Microsoft Defender ATP Content Filter</span></span>
        - <span data-ttu-id="3213b-414">**Идентификатор:**`com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="3213b-414">**Identifier**: `com.microsoft.wdav`</span></span>
        - <span data-ttu-id="3213b-415">Оставьте **адрес службы**, **организация**, **имя пользователя**, **пароль**, **сертификат** пустой (**Включить** *не* выбран)</span><span class="sxs-lookup"><span data-stu-id="3213b-415">Leave **Service Address**, **Organization**, **User Name**, **Password**, **Certificate** blank (**Include** is *not* selected)</span></span>
        - <span data-ttu-id="3213b-416">**Порядок фильтрации:** Инспектор</span><span class="sxs-lookup"><span data-stu-id="3213b-416">**Filter Order**: Inspector</span></span>
        - <span data-ttu-id="3213b-417">**Фильтр socket:**`com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="3213b-417">**Socket Filter**: `com.microsoft.wdav.netext`</span></span>
        - <span data-ttu-id="3213b-418">**Назначенное требование фильтра socket:**`identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="3213b-418">**Socket Filter Designated Requirement**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
        - <span data-ttu-id="3213b-419">Оставьте **поля сетевого** фильтра пустыми **(Включить** *не* выбрано)</span><span class="sxs-lookup"><span data-stu-id="3213b-419">Leave **Network Filter** fields blank (**Include** is *not* selected)</span></span>

        <span data-ttu-id="3213b-420">Обратите **внимание, что идентификатор,** **фильтр socket и** **фильтр socket** назначенные точные значения требования, указанные выше.</span><span class="sxs-lookup"><span data-stu-id="3213b-420">Note that **Identifier**, **Socket Filter** and **Socket Filter Designated Requirement** exact values as specified above.</span></span>

        ![Изображение параметра конфигурации mdatpmdav](images/netext-create-profile.png)

3. <span data-ttu-id="3213b-422">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="3213b-422">Select the **Scope** tab.</span></span>

   ![Изображение параметров конфигурации вкладки sco](images/0df36fc308ba569db204ee32db3fb40a.png)

4. <span data-ttu-id="3213b-424">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-424">Select **+ Add**.</span></span>

5. <span data-ttu-id="3213b-425">Выберите **группы** > **в соответствии с названием** группы > выберите **группу машин Contoso.**</span><span class="sxs-lookup"><span data-stu-id="3213b-425">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

6. <span data-ttu-id="3213b-426">Выберите **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-426">Select **+ Add**.</span></span>

    ![Изображение adim параметров конфигурации](images/0dde8a4c41110dbc398c485433a81359.png)

7. <span data-ttu-id="3213b-428">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-428">Select **Save**.</span></span>

    ![Изображение параметров конфигурации savimg netextscop](images/netext-scope.png)

8. <span data-ttu-id="3213b-430">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3213b-430">Select **Done**.</span></span>

    ![Изображение параметров конфигурации netextfinal](images/netext-final.png)

<span data-ttu-id="3213b-432">Кроме того, вы можете скачать [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) и загрузить его в профили конфигурации JAMF, как описано в развертывании пользовательских профилей конфигурации с помощью [Jamf Pro| Метод 2. Загрузите профиль конфигурации в Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span><span class="sxs-lookup"><span data-stu-id="3213b-432">Alternatively, you can download [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>


## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="3213b-433">Шаг 10. Расписание сканирования с помощью Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="3213b-433">Step 10: Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>
<span data-ttu-id="3213b-434">Следуйте инструкциям по [проверке расписания с помощью Microsoft Defender для конечной точки на macOS.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)</span><span class="sxs-lookup"><span data-stu-id="3213b-434">Follow the instructions on [Schedule scans with Microsoft Defender for Endpoint on macOS](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span></span>


## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="3213b-435">Шаг 11. Развертывание Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="3213b-435">Step 11: Deploy Microsoft Defender for Endpoint on macOS</span></span>

1. <span data-ttu-id="3213b-436">Перейдите к сохраненным `wdav.pkg` местам.</span><span class="sxs-lookup"><span data-stu-id="3213b-436">Navigate to where you saved `wdav.pkg`.</span></span>

    ![Изображение проводника файлов wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. <span data-ttu-id="3213b-438">Переименуй его в `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="3213b-438">Rename it to `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![Изображение проводника файлов1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. <span data-ttu-id="3213b-440">Откройте панель мониторинга Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="3213b-440">Open the Jamf Pro dashboard.</span></span>

    ![Изображение параметров конфигурации jamfpro](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. <span data-ttu-id="3213b-442">Выберите компьютер и нажмите значок передач в верхней части, а затем выберите **управление компьютером**.</span><span class="sxs-lookup"><span data-stu-id="3213b-442">Select your computer and click the gear icon at the top, then select **Computer Management**.</span></span>

    ![Изображение параметров конфигурации compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. <span data-ttu-id="3213b-444">В **пакетах** выберите **+ New**.</span><span class="sxs-lookup"><span data-stu-id="3213b-444">In **Packages**, select **+ New**.</span></span> 
    <span data-ttu-id="3213b-445">![Изображение, содержащее описание птицы, автоматически генерируется новый пакет](images/57aa4d21e2ccc65466bf284701d4e961.png)</span><span class="sxs-lookup"><span data-stu-id="3213b-445">![A picture containing bird Description automatically generated package new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span></span>

6. <span data-ttu-id="3213b-446">В **новом пакете** введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="3213b-446">In **New Package** Enter the following details:</span></span>

    <span data-ttu-id="3213b-447">**Общая вкладка**</span><span class="sxs-lookup"><span data-stu-id="3213b-447">**General tab**</span></span>
    - <span data-ttu-id="3213b-448">Имя отображения. Оставьте его пустым на данный момент.</span><span class="sxs-lookup"><span data-stu-id="3213b-448">Display Name: Leave it blank for now.</span></span> <span data-ttu-id="3213b-449">Потому что она будет сброшена при выборе pkg.</span><span class="sxs-lookup"><span data-stu-id="3213b-449">Because it will be reset when you choose your pkg.</span></span>
    - <span data-ttu-id="3213b-450">Категория: Нет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3213b-450">Category: None (default)</span></span>
    - <span data-ttu-id="3213b-451">Имя файла: выберите файл</span><span class="sxs-lookup"><span data-stu-id="3213b-451">Filename: Choose File</span></span>

    ![Изображение общей вкладки параметры конфигурации](images/21de3658bf58b1b767a17358a3f06341.png)

    <span data-ttu-id="3213b-453">Откройте файл и указать его `wdav.pkg` или `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="3213b-453">Open the file and point it to `wdav.pkg` or `wdav_MDM_Contoso_200329.pkg`.</span></span>
    
    ![Снимок экрана компьютера Описание, автоматически сгенерированное](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. <span data-ttu-id="3213b-455">Выберите **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="3213b-455">Select **Open**.</span></span> <span data-ttu-id="3213b-456">Установите имя **отображения в** Microsoft **Defender Advanced Threat Protection и антивирус Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="3213b-456">Set the **Display Name** to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    <span data-ttu-id="3213b-457">**Файл Manifest не** требуется.</span><span class="sxs-lookup"><span data-stu-id="3213b-457">**Manifest File** is not required.</span></span> <span data-ttu-id="3213b-458">Microsoft Defender для конечной точки работает без Файла Манифеста.</span><span class="sxs-lookup"><span data-stu-id="3213b-458">Microsoft Defender for Endpoint works without Manifest File.</span></span>
    
    <span data-ttu-id="3213b-459">**Вкладка с параметрами**</span><span class="sxs-lookup"><span data-stu-id="3213b-459">**Options tab**</span></span><br> <span data-ttu-id="3213b-460">Сохранение значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3213b-460">Keep default values.</span></span>

    <span data-ttu-id="3213b-461">**Вкладка Ограничения**</span><span class="sxs-lookup"><span data-stu-id="3213b-461">**Limitations tab**</span></span><br> <span data-ttu-id="3213b-462">Сохранение значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3213b-462">Keep default values.</span></span>
    
     ![Изображение вкладки ограничения параметров конфигурации](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. <span data-ttu-id="3213b-464">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-464">Select **Save**.</span></span> <span data-ttu-id="3213b-465">Пакет загружается в Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="3213b-465">The package is uploaded to Jamf Pro.</span></span> 

   ![Изображение параметров конфигурации упаковки upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   <span data-ttu-id="3213b-467">Чтобы пакет был доступен для развертывания, может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="3213b-467">It can take a few minutes for the package to be available for deployment.</span></span>
   
   ![Образ параметров конфигурации пакет upl](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. <span data-ttu-id="3213b-469">Перейдите на **страницу Политики.**</span><span class="sxs-lookup"><span data-stu-id="3213b-469">Navigate to the **Policies** page.</span></span>

    ![Изображение polocies параметров конфигурации](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. <span data-ttu-id="3213b-471">Выберите **+ Новое** для создания новой политики.</span><span class="sxs-lookup"><span data-stu-id="3213b-471">Select **+ New** to create a new policy.</span></span>

    ![Изображение параметров конфигурации новой политики](images/847b70e54ed04787e415f5180414b310.png)


11. <span data-ttu-id="3213b-473">В **общем введите** следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="3213b-473">In **General** Enter the following details:</span></span>

    - <span data-ttu-id="3213b-474">Имя отображения: MDATP onboarding Contoso 200329 v100.86.92 или более поздней</span><span class="sxs-lookup"><span data-stu-id="3213b-474">Display name: MDATP Onboarding Contoso 200329 v100.86.92 or later</span></span>

    ![<span data-ttu-id="3213b-475">Изображение параметров конфигурацииmdatponboard</span><span class="sxs-lookup"><span data-stu-id="3213b-475">Image of configuration settingsmdatponboard</span></span> ](images/625ba6d19e8597f05e4907298a454d28.png)

12. <span data-ttu-id="3213b-476">Выберите **повторяемую регистрацию.**</span><span class="sxs-lookup"><span data-stu-id="3213b-476">Select **Recurring Check-in**.</span></span> 
    
    ![Изображение параметров конфигурации повторно проверить](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. <span data-ttu-id="3213b-478">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-478">Select **Save**.</span></span> 
 
14. <span data-ttu-id="3213b-479">Выберите **пакеты > настройка**.</span><span class="sxs-lookup"><span data-stu-id="3213b-479">Select **Packages > Configure**.</span></span>
 
    ![Образ настройки пакета параметров конфигурации](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. <span data-ttu-id="3213b-481">Выберите **кнопку Добавить** рядом с **расширенным антивирусом Microsoft Defender Advanced Threat Protection и Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="3213b-481">Select the **Add** button next to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    ![Добавление изображений параметров конфигурации MDATP и MDA](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. <span data-ttu-id="3213b-483">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-483">Select **Save**.</span></span>

    ![Изображение параметров конфигурации](images/9d6e5386e652e00715ff348af72671c6.png)

17. <span data-ttu-id="3213b-485">Выберите **вкладку Область.**</span><span class="sxs-lookup"><span data-stu-id="3213b-485">Select the **Scope** tab.</span></span>  

    ![Изображение параметров конфигурации scptab](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. <span data-ttu-id="3213b-487">Выберите целевые компьютеры.</span><span class="sxs-lookup"><span data-stu-id="3213b-487">Select the target computers.</span></span>

    ![Изображение параметров конфигурации tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    <span data-ttu-id="3213b-489">**Scope**</span><span class="sxs-lookup"><span data-stu-id="3213b-489">**Scope**</span></span>
    
    <span data-ttu-id="3213b-490">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3213b-490">Select **Add**.</span></span>
    
    ![Изображение параметров конфигурации ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Изображение параметров конфигурации ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    <span data-ttu-id="3213b-493">**Самообслуживка**</span><span class="sxs-lookup"><span data-stu-id="3213b-493">**Self-Service**</span></span>
    
    ![Изображение самообслуживи параметров конфигурации](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. <span data-ttu-id="3213b-495">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3213b-495">Select **Done**.</span></span> 

    ![Изображение параметров конфигурации do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Изображение параметров конфигурации do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




