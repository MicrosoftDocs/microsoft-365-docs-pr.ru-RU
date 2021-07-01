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
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a>Настройка конечной точки Microsoft Defender для политик macOS в Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Защитник для конечной точки на Mac](microsoft-defender-endpoint-mac.md)

На этой странице вы сможете найти необходимые действия, чтобы настроить политики macOS в Jamf Pro.

Необходимо предпринять следующие действия:

1. [Получите пакет onboarding Microsoft Defender для конечной точки](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [Создание профиля конфигурации в Jamf Pro с помощью пакета onboarding](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [Настройка параметров конечных точек Microsoft Defender](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [Настройка параметров уведомлений Microsoft Defender для конечной точки](#step-4-configure-notifications-settings)

5. [Настройка Microsoft AutoUpdate (MAU)](#step-5-configure-microsoft-autoupdate-mau)

6. [Предоставление полного доступа к диску Microsoft Defender для конечной точки](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [Утверждение расширения ядра для Microsoft Defender для конечной точки](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [Утверждение расширений системы для Microsoft Defender для конечной точки](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [Настройка расширения сети](#step-9-configure-network-extension)

10. [Расписание сканирования с помощью Microsoft Defender для конечной точки на macOS](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [Развертывание Microsoft Defender для конечной точки на macOS](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a>Шаг 1. Получить пакет onboarding Microsoft Defender для конечной точки

1. В [Центр безопасности в Microsoft Defender](https://securitycenter.microsoft.com)перейдите **к Параметры > onboarding**.

2. Выберите macOS в качестве операционной системы и метод управления мобильными устройствами Microsoft Intune в качестве метода развертывания.

    ![Изображение Центр безопасности в Microsoft Defender](images/onboarding-macos.png)

3. Выберите **пакет загрузки** (WindowsDefenderATPOnboardingPackage.zip).

4. `WindowsDefenderATPOnboardingPackage.zip`Извлечение .

5. Скопируйте файл в предпочтительное расположение. Пример: `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a>Шаг 2. Создание профиля конфигурации в Jamf Pro с помощью бортового пакета

1. Найдите файл `WindowsDefenderATPOnboarding.plist` из предыдущего раздела.

   ![Изображение файла WindowsDefenderATPOnboarding](images/plist-onboarding-file.png)


2. В панели мониторинга Jamf Pro выберите **New**.

    ![Изображение создания новой панели мониторинга Pro Jamf](images/jamf-pro-configure-profile.png)

3. Введите следующие сведения:

   **Общие**
   - Имя: бортовая система MDATP для macOS
   - Описание: MDATP EDR для macOS
   - Категории: None (нет)
   - Метод рассылки: установка автоматически
   - Уровень: уровень компьютера

4. В **приложении & настраиваемые Параметры** выберите **Configure**.

    ![Изображение настройки приложения и настраиваемых параметров](images/jamfpro-mac-profile.png)

5. Выберите **Upload файл (PLIST-файл),** а затем **введите параметр Preference Domain:** `com.microsoft.wdav.atp` .

    ![Изображение файла загрузки списка jamfpro](images/jamfpro-plist-upload.png)

    ![Изображение файла списка свойств upload file](images/jamfpro-plist-file.png)

6. Выберите **Открыть** и выбрать файл вмеяния.

    ![Изображение бортового файла](images/jamfpro-plist-file-onboard.png)

7. Выберите **Upload**.

    ![Изображение загрузки файла plist](images/jamfpro-upload-plist.png)

8. Выберите **вкладку Область.**

    ![Изображение вкладки области](images/jamfpro-scope-tab.png)

9. Выберите целевые компьютеры.

    ![Изображение целевых компьютеров](images/jamfpro-target-computer.png)

    ![Изображение целей](images/jamfpro-targets.png)

10. Нажмите **Сохранить**.

    ![Изображение целевых компьютеров развертывания](images/jamfpro-deployment-target.png)

    ![Изображение выбранных целевых компьютеров](images/jamfpro-target-selected.png)

11. Нажмите кнопку **Готово**.

    ![Изображение компьютеров целевой группы](images/jamfpro-target-group.png)

    ![Список профилей конфигурации](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a>Шаг 3. Настройка защитника Майкрософт для параметров конечной точки

Вы можете использовать интерфейс JAMF Pro для редактирования отдельных параметров конфигурации Microsoft Defender или использовать устаревший метод, создав Plist конфигурации в текстовом редакторе и загрузив его в JAMF Pro.

Обратите внимание, что вы должны использовать точные параметры в качестве домена preference, Microsoft Defender использует только это имя и `com.microsoft.wdav`  `com.microsoft.wdav.ext` загружает управляемые параметры!

(Версия может использоваться в редких случаях, когда вы предпочитаете использовать метод GUI, но также необходимо настроить параметр, который еще не был добавлен в `com.microsoft.wdav.ext` схему.)

### <a name="gui-method"></a>Метод GUI

1. Скачайте schema.jsфайл из GitHub Defender и [сохраните](https://github.com/microsoft/mdatp-xplat/tree/master/macos/schema) его в локальном файле:

    ```bash
    curl -o ~/Documents/schema.json https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/schema/schema.json
    ```

2. Создайте новый профиль конфигурации в профиле компьютеров > конфигурации, введите следующие сведения на вкладке **General:**

    ![New profile](images/644e0f3af40c29e80ca1443535b2fe32.png)

    - Имя: параметры конфигурации MDATP MDAV
    - Описание:\<blank\>
    - Категория: Нет (по умолчанию)
    - Уровень: уровень компьютера (по умолчанию)
    - Метод рассылки: установка автоматически (по умолчанию)

3. Прокрутите вниз до **вкладки Application & custom Параметры,** выберите внешние **приложения,** нажмите кнопку **Добавить** и использовать настраиваемую схему в качестве источника для использования для домена предпочтений. 

    ![Добавление настраиваемой схемы](images/4137189bc3204bb09eed3aabc41afd78.png)

4. Введите в качестве домена настройки нажмите кнопку Добавить схему и Upload schema.jsфайл, `com.microsoft.wdav` загруженный на шаге  1.  Щелкните **Сохранить**.

    ![Upload схемы](images/a6f9f556037c42fabcfdcb1b697244cf.png)

5. Все поддерживаемые параметры конфигурации Microsoft Defender можно увидеть ниже в **статье Preference Domain Properties.** Нажмите **кнопку Добавить или Удалить свойства,** чтобы выбрать параметры, которыми вы хотите управлять, и нажмите **кнопку Ок,** чтобы сохранить изменения. (Параметры невыбранный не будет включен в управляемой конфигурации, конечный пользователь сможет настроить эти параметры на своих машинах.)

    ![Выбор управляемых параметров](images/817b3b760d11467abe9bdd519513f54f.png)

6. Изменение значений параметров на нужные значения. Дополнительные сведения **можно нажать,** чтобы получить документацию для определенного параметра. (Вы можете щелкнуть предварительный просмотр **списка Plist,** чтобы проверить, как будет выглядеть plist конфигурации. Щелкните **редактор формы,** чтобы вернуться к визуальному редактору.)

    ![Изменение значений параметров](images/a14a79efd5c041bb8974cb5b12b3a9b6.png)

7. Выберите **вкладку Область.**

    ![Область профилей конфигурации](images/9fc17529e5577eefd773c658ec576a7d.png)

8. Выберите **машинную группу Contoso.**

9. Выберите **Добавить,** а затем **выберите Сохранить**.

    ![Параметры конфигурации — добавьте](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Параметры конфигурации — сохранение](images/6f093e42856753a3955cab7ee14f12d9.png)

10. Нажмите кнопку **Готово**. Вы увидите новый профиль **Конфигурация**.

    ![Параметры конфигурации — сделано](images/dd55405106da0dfc2f50f8d4525b01c8.png)

Microsoft Defender со временем добавляет новые параметры. Эти новые параметры будут добавлены в схему, а новая версия будет опубликована в Github.
Для обновления необходимо скачать обновленную схему, изменить существующий профиль конфигурации и изменить схему на вкладке **Application & Custom Параметры.** 

### <a name="legacy-method"></a>Устаревший метод

1. Используйте следующие параметры конфигурации Microsoft Defender для конечных точек:

    - enableRealTimeProtection
    - passiveMode

    >[!NOTE]
    >Не включено по умолчанию, если вы планируете запустить сторонний AV для macOS, установите `true` его.

    - исключения
    - excludedPath
    - excludedFileExtension
    - excludedFileName
    - exclusionsMergePolicy
    - allowedThreats

    >[!NOTE]
    >EICAR находится в примере, если вы проходите проверку концепции, удалите ее, особенно если вы тестируете EICAR.

    - disallowedThreatActions
    - potentially_unwanted_application
    - archive_bomb
    - cloudService
    - automaticSampleSubmission
    - tags
    - hideStatusMenuIcon

     Сведения см. в [списке свойств для профиля конфигурации Jamf.](mac-preferences.md#property-list-for-jamf-configuration-profile)

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

2. Сохраните файл как `MDATP_MDAV_configuration_settings.plist` .

3. В панели мониторинга Jamf Pro откройте **компьютеры,** а также там **профили конфигурации.** Нажмите *кнопку* * New (и перейдите на **вкладку General.**

    ![New profile](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. Введите следующие сведения:

    **Общие**

    - Имя: параметры конфигурации MDATP MDAV
    - Описание:\<blank\>
    - Категория: Нет (по умолчанию)
    - Метод рассылки: установка автоматически (по умолчанию)
    - Уровень: уровень компьютера (по умолчанию)

    ![Изображение параметров конфигурации MDATP MDAV](images/3160906404bc5a2edf84d1d015894e3b.png)

5. В **приложении & настраиваемые Параметры** выберите **Configure**.

    ![Изображение параметров приложения и настраиваемого](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. Выберите **Upload файл (PLIST-файл).**

    ![Изображение файла plist параметров конфигурации](images/6f85269276b2278eca4bce84f935f87b.png)

7. В **домене Preferences** введите, а затем `com.microsoft.wdav` выберите Upload **PLIST File**.

    ![Изображение домена настроек конфигурации](images/db15f147dd959e872a044184711d7d46.png)

8. Выберите **выберите файл**.

    ![Изображение параметров конфигурации выберите файл](images/526e978761fc571cca06907da7b01fd6.png)

9. Выберите **список MDATP_MDAV_configuration_settings.plist,** а затем **откройте**.

    ![Изображение параметров конфигурации mdatpmdav](images/98acea3750113b8dbab334296e833003.png)

10. Выберите **Upload**.

    ![Изображение загрузки параметра конфигурации](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Изображение параметров настройки загрузки изображения](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    >Если вы загрузите файл Intune, вы получите следующую ошибку:<br>
    >![Изображение загрузки файлов intune параметров конфигурации](images/8e69f867664668796a3b2904896f0436.png)


11. Нажмите **Сохранить**.

    ![Изображение параметров конфигурации Сохранить изображение](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. Файл загружен.

    ![Изображение загруженного изображения файла параметров конфигурации](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Изображение загруженного файла параметров конфигурации](images/a422e57fe8d45689227e784443e51bd1.png)

13. Выберите **вкладку Область.**

    ![Изображение области параметров конфигурации](images/9fc17529e5577eefd773c658ec576a7d.png)

14. Выберите **машинную группу Contoso.**

15. Выберите **Добавить,** а затем **выберите Сохранить**.

    ![Изображение параметров конфигурации addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Изображение параметров конфигурации сохранить добавить](images/6f093e42856753a3955cab7ee14f12d9.png)

16. Нажмите кнопку **Готово**. Вы увидите новый профиль **Конфигурация**.

    ![Изображение конфигурации параметров конфигурировать изображение профиля](images/dd55405106da0dfc2f50f8d4525b01c8.png)

## <a name="step-4-configure-notifications-settings"></a>Шаг 4. Настройка параметров уведомлений

Эти действия применимы к macOS 10.15 (Catalina) или более новым.

1. В панели мониторинга Jamf Pro выберите **компьютеры,** а затем **профили конфигурации.**

2. Нажмите **кнопку New** и введите следующие сведения для **Параметры**:

    - Tab **General:**
        - **Имя:** параметры MDATP MDAV Notification
        - **Описание:** macOS 10.15 (Catalina) или более новый
        - **Категория:** Нет *(по умолчанию)*
        - **Метод рассылки:** Установка автоматически *(по умолчанию)*
        - **Уровень**: Уровень компьютера *(по умолчанию)*

        ![Изображение нового экрана профиля конфигурации macOS](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - Tab **Notifications,** **нажмите кнопку Добавить** и введите следующие значения:
        - **Bundle ID:**`com.microsoft.wdav.tray`
        - **Критические оповещения:** нажмите **кнопку Отключение**
        - **Уведомления:** щелкните **Включить**
        - **Тип оповещения баннера:** **Выберите включить и** временно **(по** *умолчанию)*
        - **Уведомления на экране блокировки:** нажмите кнопку **Скрыть**
        - **Уведомления в Центре уведомлений:** щелкните **отображение**
        - **Значок приложения Badge:** Щелкните **Дисплей**

        ![Изображение лотка уведомлений mdatpmdav параметров конфигурации](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - Tab **Notifications**, **щелкните Добавить** еще раз, прокрутите вниз, чтобы **новые уведомления Параметры**
        - **Bundle ID:**`com.microsoft.autoupdate2`
        - Настройка остальных параметров на те же значения, что и выше

        ![Изображение параметров конфигурации mdatpmdav notifications mau](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        Обратите внимание, что теперь у вас есть две "таблицы" с конфигурациями уведомлений, одна для bundle **ID: com.microsoft.wdav.tray** и другая для **Bundle ID: com.microsoft.autoupdate2**. Хотя вы можете настроить параметры оповещения в зависимости от ваших требований, набор ID должен быть точно таким же, как описано ранее, и **включить** переключатель должен быть **включен** для **уведомлений**.

3. Выберите **вкладку Область,** а **затем** добавьте .

    ![Добавлено изображение области параметров конфигурации](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. Выберите **машинную группу Contoso.**

5. Выберите **Добавить,** а затем **выберите Сохранить**.

    ![Image of configuration settings contoso machine grp save](images/09a275e321268e5e3ac0c0865d3e2db5.png)

    ![Изображение параметров конфигурации добавить сохранить](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. Нажмите кнопку **Готово**. Вы увидите новый профиль **Конфигурация**.
    ![Изображение параметра конфигурации сделано img](images/633ad26b8bf24ec683c98b2feb884bdf.png)

## <a name="step-5-configure-microsoft-autoupdate-mau"></a>Шаг 5. Настройка Microsoft AutoUpdate (MAU)

1. Используйте следующие параметры конфигурации Microsoft Defender для конечных точек:

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

2. Сохраните его как `MDATP_MDAV_MAU_settings.plist` .

3. В панели мониторинга Jamf Pro выберите **General**.

    ![Изображение общего образа настройки конфигурации](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. Введите следующие сведения:

    **Общие**

    - Имя: параметры MDATP MDAV MAU
    - Описание. Параметры Microsoft AutoUpdate для MDATP для macOS
    - Категория: Нет (по умолчанию)
    - Метод рассылки: установка автоматически (по умолчанию)
    - Уровень: уровень компьютера (по умолчанию)

5. В **приложении & настраиваемые Параметры** выберите **Configure**.

    ![Изображение приложения настройки конфигурации и настраиваемые параметры](images/1f72e9c15eaafcabf1504397e99be311.png)

6. Выберите **Upload файл (PLIST-файл).**

    ![Изображение plist настройки конфигурации](images/1213872db5833aa8be535da57653219f.png)

7. В **домене Preference** введите: `com.microsoft.autoupdate2` затем выберите Upload **PLIST File**.

    ![Изображение предварительного домена настройки настройки](images/1213872db5833aa8be535da57653219f.png)

8. Выберите **выберите файл**.

    ![Изображение параметра конфигурации choosefile](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. Выберите **MDATP_MDAV_MAU_settings.plist**.

    ![Изображение параметров настройки mdatpmdavmau](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. Выберите **Upload**.
    ![Изображение настройки настройки uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)

    ![Изображение настройки настройки uplimg](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. Нажмите **Сохранить**.

    ![Изображение параметра конфигурации saveimg](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. Выберите **вкладку Область.**

     ![Изображение scopetab настройки конфигурации](images/10ab98358b2d602f3f67618735fa82fb.png)

13. Нажмите кнопку **Добавить**.

    ![Изображение параметра конфигурации addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Изображение параметра конфигурации addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Изображение параметра конфигурации addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. Нажмите кнопку **Готово**.

    ![Image of configuration setting doneimage](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a>Шаг 6. Предоставление полного доступа к диску Microsoft Defender для конечной точки

1. В панели мониторинга Jamf Pro выберите **профили конфигурации.**

    ![Изображение профиля конфигурации настройки конфигурации](images/264493cd01e62c7085659d6fdc26dc91.png)

2. Выберите **+ Новый**.

3. Введите следующие сведения:

    **Общие**
    - Имя: MDATP MDAV — предоставление полного доступа к EDR и AV
    - Описание. Для macOS Catalina или более нового управления политикой конфиденциальности
    - Категории: None (нет)
    - Метод рассылки: установка автоматически
    - Уровень: уровень компьютера


    ![Изображение общего параметра настройки конфигурации](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. В **Настройка политики настройки предпочтений конфиденциальности выберите** **Настройка**.

    ![Изображение управления политикой конфиденциальности конфигурации](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. В правилах управления **политиками конфиденциальности** введите следующие сведения:

    - Идентификатор: `com.microsoft.wdav`
    - Тип идентификатора: идентификатор пакета
    - Требование кода: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`


    ![Изображение сведений о настройке политики настройки конфиденциальности.](images/22cb439de958101c0a12f3038f905b27.png)

6. Выберите **+ Добавить**.

    ![Изображение параметра конфигурации добавить системную политику во все файлы](images/bd93e78b74c2660a0541af4690dd9485.png)

    - В приложении или службе: установите **systemPolicyAllFiles**

    - В статье "Доступ": набор **разрешить**

7. Выберите **Сохранить** (не тот, который внизу справа).

    ![Изображение параметра конфигурации сохранить изображения](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. Щелкните `+` знак рядом с **доступом к приложению,** чтобы добавить новую запись.

    ![Изображение доступа к приложению настройки конфигурации](images/tcc-add-entry.png)

9. Введите следующие сведения:

    - Идентификатор: `com.microsoft.wdav.epsext`
    - Тип идентификатора: идентификатор пакета
    - Требование кода: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

10. Выберите **+ Добавить**.

    ![Изображение записи epsext параметра конфигурации tcc](images/tcc-epsext-entry.png)

    - В приложении или службе: установите **systemPolicyAllFiles**

    - В статье "Доступ": набор **разрешить**

11. Выберите **Сохранить** (не тот, который внизу справа).

    ![Изображение параметра конфигурации tcc epsext image2](images/tcc-epsext-entry2.png)

12. Выберите **вкладку Область.**

    ![Изображение области настройки конфигурации](images/2c49b16cd112729b3719724f581e6882.png)

13. Выберите **+ Добавить**.

    ![Изображение надстройки параметра конфигурации](images/57cef926d1b9260fb74a5f460cee887a.png)

14. Выберите **группы** компьютеров > **под названием** группы > **выберите MachineGroup Contoso.**

    ![Изображение параметра конфигурации contoso machinegrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. Нажмите кнопку **Добавить**.

16. Нажмите **Сохранить**.

17. Нажмите кнопку **Готово**.

    ![Изображение donimg параметра конфигурации](images/809cef630281b64b8f07f20913b0039b.png)

    ![Изображение параметра конфигурации donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)

Кроме того, вы можете скачать [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) и загрузить его в профили конфигурации JAMF, как описано в развертывании пользовательских профилей конфигурации с помощью [Jamf Pro| Метод 2. Upload профиль конфигурации в Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a>Шаг 7. Утверждение расширения ядра для Microsoft Defender для конечной точки

> [!CAUTION]
> Устройства Apple Silicon (M1) не поддерживают KEXT. Установка профиля конфигурации, состоящего из политик KEXT, не будет работать на этих устройствах.

1. В **профилях конфигурации** выберите **+ New**.

    ![Снимок экрана сообщения в социальных сетях, автоматически созданный](images/6c8b406ee224335a8c65d06953dc756e.png)

2. Введите следующие сведения:

    **Общие**

    - Имя. Расширение Ядра MDAV MDAV
    - Описание: расширение ядра MDATP (kext)
    - Категории: None (нет)
    - Метод рассылки: установка автоматически
    - Уровень: уровень компьютера

    ![Изображение параметров конфигурации ядра mdatpmdav](images/24e290f5fc309932cf41f3a280d22c14.png)

3. В **Настройка утвержденных расширений ядра** выберите **Настройка**.

    ![Изображение параметров конфигурации, утвержденных ext ядра](images/30be88b63abc5e8dde11b73f1b1ade6a.png)


4. В **утвержденных расширениях ядра** введите следующие сведения:

    - Имя отображения: Корпорация Майкрософт.
    - ID команды: UBF8T346G9

    ![Изображение параметров конфигурации расширения ядра appr](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. Выберите **вкладку Область.**

    ![Image of configuration settings scope tab img](images/0df36fc308ba569db204ee32db3fb40a.png)

6. Выберите **+ Добавить**.

7. Выберите **группы** > **в соответствии с названием** группы > выберите **группу машин Contoso.**

8. Выберите **+ Добавить**.

    ![Изображение параметров конфигурации добавить изображения](images/0dde8a4c41110dbc398c485433a81359.png)

9. Нажмите **Сохранить**.

    ![Изображение параметров конфигурации saveimag](images/0add8019b85a453b47fa5c402c72761b.png)

10. Нажмите кнопку **Готово**.

    ![Изображение параметров конфигурации doneimag](images/1c9bd3f68db20b80193dac18f33c22d0.png)

Кроме того, вы можете скачать [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) и загрузить его в профили конфигурации JAMF, как описано в развертывании пользовательских профилей конфигурации с помощью [Jamf Pro| Метод 2. Upload профиль конфигурации в Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a>Шаг 8. Утверждение расширений системы для Microsoft Defender для конечной точки

1. В **профилях конфигурации** выберите **+ New**.

    ![Снимок экрана сообщения в социальных сетях, автоматически созданный](images/6c8b406ee224335a8c65d06953dc756e.png)

2. Введите следующие сведения:

    **Общие**

    - Имя: MDATP MDAV System Extensions
    - Описание: расширения системы MDATP
    - Категории: None (нет)
    - Метод рассылки: установка автоматически
    - Уровень: уровень компьютера

    ![Изображение параметров конфигурации sysext new prof](images/sysext-new-profile.png)

3. В **расширении системы** выберите **Настройка**.

   ![Изображение параметров конфигурации sysext config](images/sysext-configure.png)

4. В **расширении системы введите** следующие сведения:

   - Имя отображения: расширения системы Microsoft Corp.
   - Типы расширения системы: разрешенные расширения системы
   - Идентификатор команды: UBF8T346G9
   - Разрешенные расширения системы:
     - **com.microsoft.wdav.epsext**
     - **com.microsoft.wdav.netext**

    ![Изображение параметров конфигурации sysextconfig2](images/sysext-configure2.png)

5. Выберите **вкладку Область.**

    ![Image of configuration settings scopeimage](images/0df36fc308ba569db204ee32db3fb40a.png)

6. Выберите **+ Добавить**.

7. Выберите **группы** > **в соответствии с названием** группы > выберите **группу машин Contoso.**

8. Выберите **+ Добавить**.

   ![Изображение параметров конфигурации addima](images/0dde8a4c41110dbc398c485433a81359.png)

9. Нажмите **Сохранить**.

   ![Изображение параметров конфигурации sysext](images/sysext-scope.png)

10. Нажмите кнопку **Готово**.

    ![Изображение параметров конфигурации sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a>Шаг 9. Настройка расширения сети

В рамках возможностей обнаружения конечных точек и ответов Microsoft Defender для конечной точки на macOS проверяет трафик розетки и передает эти сведения на Центр безопасности в Microsoft Defender портал. Следующая политика позволяет сетевому расширению выполнять эту функцию.

Эти действия применимы к macOS 10.15 (Catalina) или более новым.

1. В панели мониторинга Jamf Pro выберите **компьютеры,** а затем **профили конфигурации.**

2. Нажмите **кнопку New** и введите следующие сведения для **Параметры**:

    - Tab **General:**
        - **Имя:** Расширение сети ATP Защитника Майкрософт
        - **Описание:** macOS 10.15 (Catalina) или более новый
        - **Категория:** Нет *(по умолчанию)*
        - **Метод рассылки:** Установка автоматически *(по умолчанию)*
        - **Уровень**: Уровень компьютера *(по умолчанию)*

    - Фильтр **контента вкладок:**
        - **Имя фильтра:** фильтр контента ATP Защитника Майкрософт
        - **Идентификатор:**`com.microsoft.wdav`
        - Оставьте **адрес службы**, **организация**, **имя пользователя**, **пароль**, **сертификат** пустой (**Включить** *не* выбран)
        - **Порядок фильтрации:** Инспектор
        - **Фильтр socket:**`com.microsoft.wdav.netext`
        - **Назначенное требование фильтра socket:**`identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
        - Оставьте **поля сетевого** фильтра пустыми **(Включить** *не* выбрано)

        Обратите **внимание, что идентификатор,** **фильтр socket и** **фильтр socket** назначенные точные значения требования, указанные выше.

        ![Изображение параметра конфигурации mdatpmdav](images/netext-create-profile.png)

3. Выберите **вкладку Область.**

   ![Изображение параметров конфигурации вкладки sco](images/0df36fc308ba569db204ee32db3fb40a.png)

4. Выберите **+ Добавить**.

5. Выберите **группы** > **в соответствии с названием** группы > выберите **группу машин Contoso.**

6. Выберите **+ Добавить**.

    ![Изображение adim параметров конфигурации](images/0dde8a4c41110dbc398c485433a81359.png)

7. Нажмите **Сохранить**.

    ![Изображение параметров конфигурации savimg netextscop](images/netext-scope.png)

8. Нажмите кнопку **Готово**.

    ![Изображение параметров конфигурации netextfinal](images/netext-final.png)

Кроме того, вы можете скачать [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) и загрузить его в профили конфигурации JAMF, как описано в развертывании пользовательских профилей конфигурации с помощью [Jamf Pro| Метод 2. Upload профиль конфигурации в Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).


## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>Шаг 10. Расписание сканирования с помощью Microsoft Defender для конечной точки на macOS
Следуйте инструкциям по [проверке расписания с помощью Microsoft Defender для конечной точки на macOS.](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)


## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a>Шаг 11. Развертывание Microsoft Defender для конечной точки на macOS

1. Перейдите к сохраненным `wdav.pkg` местам.

    ![Изображение проводника файлов wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. Переименуй его в `wdav_MDM_Contoso_200329.pkg` .

    ![Изображение проводника файлов1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. Откройте панель мониторинга Pro Jamf.

    ![Изображение параметров конфигурации jamfpro](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. Выберите компьютер и нажмите значок передач в верхней части, а затем выберите **управление компьютером**.

    ![Изображение параметров конфигурации compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. В **пакетах** выберите **+ New**.
    ![Изображение, содержащее описание птицы, автоматически генерируется новый пакет](images/57aa4d21e2ccc65466bf284701d4e961.png)

6. В **новом пакете** введите следующие сведения:

    **Общая вкладка**
    - Имя отображения. Оставьте его пустым на данный момент. Потому что она будет сброшена при выборе pkg.
    - Категория: Нет (по умолчанию)
    - Имя файла: выберите файл

    ![Изображение общей вкладки параметры конфигурации](images/21de3658bf58b1b767a17358a3f06341.png)

    Откройте файл и указать его `wdav.pkg` или `wdav_MDM_Contoso_200329.pkg` .

    ![Снимок экрана компьютера Описание, автоматически сгенерированное](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. Выберите **Открыть**. Установите **имя отображения в** **Microsoft Defender Advanced Threat Protection и антивирусная программа в Microsoft Defender**.

    **Файл Manifest не** требуется. Microsoft Defender для конечной точки работает без Файла Манифеста.

    **Вкладка с параметрами**<br> Сохранение значений по умолчанию.

    **Вкладка Ограничения**<br> Сохранение значений по умолчанию.

     ![Изображение вкладки ограничения параметров конфигурации](images/56dac54634d13b2d3948ab50e8d3ef21.png)

8. Нажмите **Сохранить**. Пакет загружается в Jamf Pro.

   ![Изображение параметров конфигурации упаковки upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   Чтобы пакет был доступен для развертывания, может занять несколько минут.

   ![Образ параметров конфигурации пакет upl](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. Перейдите на **страницу Политики.**

    ![Изображение polocies параметров конфигурации](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. Выберите **+ Новое** для создания новой политики.

    ![Изображение параметров конфигурации новой политики](images/847b70e54ed04787e415f5180414b310.png)


11. В **общем введите** следующие сведения:

    - Имя отображения: MDATP onboarding Contoso 200329 v100.86.92 или более поздней

    ![Изображение параметров конфигурацииmdatponboard](images/625ba6d19e8597f05e4907298a454d28.png)

12. Выберите **повторяемую регистрацию.**

    ![Изображение параметров конфигурации повторно проверить](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)


13. Нажмите **Сохранить**.

14. Выберите **пакеты > настройка**.

    ![Образ настройки пакета параметров конфигурации](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. Выберите **кнопку Добавить** рядом с **microsoft Defender Advanced Threat Protection и антивирусная программа в Microsoft Defender.**

    ![Добавление изображений параметров конфигурации MDATP и MDA](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. Нажмите **Сохранить**.

    ![Изображение параметров конфигурации](images/9d6e5386e652e00715ff348af72671c6.png)

17. Выберите **вкладку Область.**

    ![Изображение параметров конфигурации scptab](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. Выберите целевые компьютеры.

    ![Изображение параметров конфигурации tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    **Scope**

    Нажмите кнопку **Добавить**.

    ![Изображение параметров конфигурации ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Изображение параметров конфигурации ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    **Самообслуживка**

    ![Изображение самообслуживи параметров конфигурации](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. Нажмите кнопку **Готово**.

    ![Изображение параметров конфигурации do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Изображение параметров конфигурации do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




