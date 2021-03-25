---
title: Развертывание на основе intune для ATP Microsoft Defender для Mac
description: Установите Microsoft Defender для конечной точки для Mac с помощью Microsoft Intune.
keywords: Microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 94cb92974b0e73a1254fd024c39d9a6ee620aad3
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199541"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-for-mac"></a>Развертывание на основе intune для Microsoft Defender для конечной точки для Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> [!NOTE]
> В этой документации объясняется устаревший метод развертывания и настройки Microsoft Defender для конечной точки на устройствах macOS. Родной опыт теперь доступен в консоли MEM. Выпуск родного пользовательского интерфейса в консоли MEM предоставляет администраторам гораздо более простой способ настройки и развертывания приложения и отправки его на устройства macOS. <br> <br>
>В блоге meM упрощает развертывание [Microsoft Defender для конечной точки для macOS,](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/microsoft-endpoint-manager-simplifies-deployment-of-microsoft/ba-p/1322995) объясняя новые возможности. Чтобы настроить приложение, перейдите в [Параметры для Microsoft Defender для конечной](https://docs.microsoft.com/mem/intune/protect/antivirus-microsoft-defender-settings-macos)точки для Mac в Microsoft InTune . Чтобы развернуть приложение, перейдите к [добавлению Microsoft Defender для конечной точки в macOS-устройства с помощью Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)

**Область применения:**

- [Microsoft Defender для конечной точки для Mac](microsoft-defender-endpoint-mac.md)

В этом разделе описывается развертывание Microsoft Defender для конечной точки для Mac с помощью Intune. Успешное развертывание требует выполнения всех следующих действий:

1. [Загрузка пакетов установки и загрузки](#download-installation-and-onboarding-packages)
1. [Установка клиентских устройств](#client-device-setup)
1. [Утверждение расширений системы](#approve-system-extensions)
1. [Создание профилей конфигурации системы](#create-system-configuration-profiles)
1. [Публикация приложения](#publish-application)

## <a name="prerequisites-and-system-requirements"></a>Необходимые условия и требования к системе

Перед началом работы см. на главной странице [Microsoft Defender for Endpoint для Mac](microsoft-defender-endpoint-mac.md) описание необходимых условий и системных требований к текущей версии программного обеспечения.

## <a name="overview"></a>Обзор

В следующей таблице подводятся итоги действий, которые необходимо предпринять для развертывания и управления Microsoft Defender для конечных точек для Mac с помощью Intune. Более подробные действия доступны ниже.

| Действие | Примеры имен файлов | BundleIdentifier |
|-|-|-|
| [Загрузка пакетов установки и загрузки](#download-installation-and-onboarding-packages) | WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml | com.microsoft.wdav.atp |
| [Утверждение расширения системы для Защитника Майкрософт для конечной точки](#approve-system-extensions) | MDATP_SysExt.xml | Недоступно |
| [Утверждение расширения ядра для Microsoft Defender для конечной точки](#download-installation-and-onboarding-packages) | MDATP_KExt.xml | Недоступно |
| [Предоставление полного доступа к диску Microsoft Defender для конечной точки](#create-system-configuration-profiles-step-8) | MDATP_tcc_Catalina_or_newer.xml | com.microsoft.wdav.tcc |
| [Политика расширения сети](#create-system-configuration-profiles-step-9) | MDATP_NetExt.xml | Недоступно |
| [Настройка Microsoft AutoUpdate (MAU)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-updates#intune) | MDATP_Microsoft_AutoUpdate.xml | com.microsoft.autoupdate2 |
| [Microsoft Defender для параметров конфигурации конечной точки](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-preferences#intune-profile-1)<br/><br/> **Примечание:** Если вы планируете запустить сторонний AV для macOS, установите `passiveMode` . `true` | MDATP_WDAV_and_exclusion_settings_Preferences.xml | com.microsoft.wdav |
| [Настройка уведомлений Microsoft Defender для конечной точки и ms AutoUpdate (MAU)](#create-system-configuration-profiles-step-10) | MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig | com.microsoft.autoupdate2 или com.microsoft.wdav.tray |

## <a name="download-installation-and-onboarding-packages"></a>Загрузка пакетов установки и загрузки

Скачайте пакеты установки и загрузки из Центра безопасности Защитника Майкрософт:

1. В центре безопасности Microsoft Defender перейдите к **onboarding Settings**  >  **Device Management**  >  **Onboarding**.

2. Установите операционную систему **для macOS** и метод развертывания для управления мобильными устройствами **/ Microsoft Intune**.

    ![Скриншот параметров onboarding](images/atp-mac-install.png)

3. Выберите **пакет установки Загрузка**. Сохраните его _как wdav.pkg_ в локальном каталоге.

4. Выберите **пакет загрузки.** Сохраните его _WindowsDefenderATPOnboardingPackage.zip_ в том же каталоге.

5. Скачайте **IntuneAppUtil из** [https://docs.microsoft.com/intune/lob-apps-macos](https://docs.microsoft.com/intune/lob-apps-macos) .

6. В командной подсказке убедитесь, что у вас есть три файла.
  

    ```bash
    ls -l
    ```

    ```Output
    total 721688
    -rw-r--r--  1 test  staff     269280 Mar 15 11:25 IntuneAppUtil
    -rw-r--r--  1 test  staff      11821 Mar 15 09:23 WindowsDefenderATPOnboardingPackage.zip
    -rw-r--r--  1 test  staff  354531845 Mar 13 08:57 wdav.pkg
    ```
7. Извлечение содержимого файлов .zip:

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

8. Сделайте IntuneAppUtil исполняемым:

    ```bash
    chmod +x IntuneAppUtil
    ```

9. Создание пакета wdav.pkg.intunemac из wdav.pkg:

    ```bash
    ./IntuneAppUtil -c wdav.pkg -o . -i "com.microsoft.wdav" -n "1.0.0"
    ```
    ```Output
    Microsoft Intune Application Utility for Mac OS X
    Version: 1.0.0.0
    Copyright 2018 Microsoft Corporation

    Creating intunemac file for /Users/test/Downloads/wdav.pkg
    Composing the intunemac file output
    Output written to ./wdav.pkg.intunemac.

    IntuneAppUtil successfully processed "wdav.pkg",
    to deploy refer to the product documentation.
    ```

## <a name="client-device-setup"></a>Установка клиентских устройств

Вам не требуется специальная подготовка для устройства Mac за пределами стандартной [установки портала компании.](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp)

1. Подтверждение управления устройствами.

    ![Подтверждение экрана управления устройствами](./images/mdatp-3-confirmdevicemgmt.png)

    Выберите **параметры Open System Preferences,** найдите **профиль** управления в списке и выберите **Утверждение...**. Ваш профиль управления будет отображаться как **Проверенный:**

    ![Снимок экрана профиля управления](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-4-managementprofile)

2. Выберите **Продолжить** и завершить регистрацию.

   Теперь вы можете записать больше устройств. Вы также можете записать их позже, после завершения настройки системы и пакетов приложений.

3. В Intune откройте **управление**  >  **устройствами**  >  **все устройства.** Здесь вы можете увидеть ваше устройство среди перечисленных ниже.

   > [!div class="mx-imgBorder"]
   > ![Добавление экрана устройства](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-5-alldevices)

## <a name="approve-system-extensions"></a>Утверждение расширений системы

Утверждение расширений системы:

1. В Intune откройте **конфигурацию Manage**  >  **Device.** Выберите **Управление**  >  **профилями**  >  **Создание профиля**.

2. Выберите имя для профиля. Изменение **платформы=macOS на** **тип profile=Extensions**. Нажмите **Создать**.

3. На **вкладке Basics** назови имя этому новому профилю.

4. На **вкладке Параметры конфигурации** добавьте следующие записи в разделе Разрешенные расширения **системы:**

    Идентификатор bundle         | Идентификатор группы
    --------------------------|----------------
    com.microsoft.wdav.epsext | UBF8T346G9
    com.microsoft.wdav.netext | UBF8T346G9

    > [!div class="mx-imgBorder"]
    > ![Снимок экрана параметров расширения в настройках конфигурации на вкладке Basics](images/mac-system-extension-intune2.png)

5. На **вкладке Назначения** назначьте этот профиль всем пользователям **& всем устройствам.**

6. Просмотрите и создайте этот профиль конфигурации.

## <a name="create-system-configuration-profiles"></a>Создание профилей конфигурации системы

1. В Intune откройте **конфигурацию Manage**  >  **Device.** Выберите **Управление**  >  **профилями**  >  **Создание профиля**.

2. Выберите имя для профиля. Изменение **platform=macOS на** **тип profile=Custom.** Выберите **Configure**.

3. Откройте профиль конфигурации и загрузите intune/kext.xml. Этот файл был создан в одном из предыдущих разделов.

4. Нажмите кнопку **ОК**.

    ![Импорт конфигурации из файла для настраиваемого профиля конфигурации](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-6-systemconfigurationprofiles)

5. Выберите **управление**  >  **назначениями.** На **вкладке Включить** выберите Назначение всем пользователям & **всех устройств.**

6. Повторите шаги с 1 по 5 для дополнительных профилей.

7. Создайте другой профиль, назовите ему имя и загрузите файл intune/WindowsDefenderATPOnboarding.xml.

8. Скачайте **fulldisk.mobileconfig из** нашего репозитория [GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) и сохраните его как **tcc.xml**. Создайте другой профиль, дайте ему любое имя и загрузите в него этот файл.<a name="create-system-configuration-profiles-step-8" id = "create-system-configuration-profiles-step-8"></a>

   > [!CAUTION]
   > MacOS 10.15 (Catalina) содержит новые улучшения безопасности и конфиденциальности. Начиная с этой версии, по умолчанию приложения не могут получить доступ к определенным расположениям на диске (например, документы, скачивания, настольные компьютеры и т.д.) без явного согласия. При отсутствии такого согласия Microsoft Defender для конечной точки не может полностью защитить ваше устройство.
   >
   > Этот профиль конфигурации предоставляет полный дисковый доступ к Microsoft Defender для конечной точки. Если вы ранее настраивали Microsoft Defender для конечной точки через Intune, рекомендуем обновить развертывание с помощью этого профиля конфигурации.

9. В рамках возможностей обнаружения конечных точек и ответов Microsoft Defender for Endpoint для Mac проверяет трафик розетки и передает эти сведения на портал Центра безопасности Microsoft Defender. Следующая политика позволяет сетевому расширению выполнять эту функцию. Скачайте **netfilter.mobileconfig** из нашего репозитория [GitHub,](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig)сохраните его как netext.xml и разверните его с помощью тех же действий, что и в предыдущих разделах. <a name = "create-system-configuration-profiles-step-9" id = "create-system-configuration-profiles-step-9"></a>

10. Чтобы позволить Microsoft Defender для конечной точки для Mac и Microsoft Auto Update отображать уведомления в пользовательском интерфейсе на macOS 10.15 (Catalina), скачайте из нашего репозитория `notif.mobileconfig` [GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) и импортируете их в качестве настраиваемой полезной нагрузки. <a name = "create-system-configuration-profiles-step-10" id = "create-system-configuration-profiles-step-10"></a>

11. Выберите **Управление > назначения**.  На **вкладке Включить** выберите Назначение всем пользователям & **всех устройств.**

После распространения изменений Intune на зарегистрированные устройства вы можете увидеть их, перечисленные в состоянии **Monitor**  >  **Device:**

> [!div class="mx-imgBorder"]
> ![Просмотр состояния устройства в мониторе](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-7-devicestatusblade.png)

## <a name="publish-application"></a>Публикация приложения

1. В Intune откройте лезвие **> клиентских приложений.** Выберите **приложения > добавить**.

2. Выберите **тип приложения=Other/Line-of-business app**.

3. Выберите **file=wdav.pkg.intunemac**. Выберите **ОК** для отправки.

4. Выберите **Настройка и** добавление необходимых сведений.

5. Используйте **macOS High Sierra 10.14** в качестве минимальной ОС.

6. Установите *версию приложения Ignore* на **да**. Другие параметры могут быть любым произвольным значением.

    > [!CAUTION]
    > Параметр *Игнорировать версию приложения* **не** влияет на способность приложения получать обновления с помощью Microsoft AutoUpdate. Дополнительные сведения об обновлении продукта см. в [веб-сайте Deploy updates for Microsoft Defender for Endpoint for Mac.](mac-updates.md)
    >
    > Если версия, загруженная Intune, ниже, чем версия на устройстве, то будет установлена более низкая версия, что фактически понизит рейтинг Microsoft Defender для endpoint. Это может привести к не функционируют приложения. Дополнительные сведения об обновлении продукта см. в [веб-сайте Deploy updates for Microsoft Defender for Endpoint for Mac.](mac-updates.md) Если вы развернули Microsoft Defender  для конечной точки с набором **"Нет"** версии приложения, измените ее на **Да.** Если Microsoft Defender для конечной точки по-прежнему не может быть установлен на клиентских устройствах, удалить Microsoft Defender для конечной точки и нажмите обновленную политику.
     
    > [!div class="mx-imgBorder"]
    > ![Отображение сведений о приложении в добавлении Приложения](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-8-intuneappinfo)

7. Выберите **ОК** и **Добавьте**.

    > [!div class="mx-imgBorder"]
    > ![Состояние устройства, показанное в окне Уведомлений](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-9-intunepkginfo)

8. Загрузка пакета может занять несколько минут. После этого выберите пакет из списка и перейдите в **группу "Назначения"** **и "Добавить".**

    > [!div class="mx-imgBorder"]
    > ![Снимок экрана клиентских приложений](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-10-clientapps)

9. Изменение **типа назначения** на **Required**.

10. Выберите **включенные группы.** Выберите **Make this app required for all devices=Yes.** Выберите **группу Выберите, чтобы** включить и добавить группу, которая содержит пользователей, на которые нужно нацелить. Выберите **ОК** и **сохранить**.

    > [!div class="mx-imgBorder"]
    > ![Снимок экрана информации о назначениях Intune](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-11-assignments)

11. Через некоторое время приложение будет опубликовано на всех зарегистрированных устройствах. Вы можете увидеть его, перечисленные в **Монитор**  >  **устройства**, в **состоянии установки устройства**:

    > [!div class="mx-imgBorder"]
    > ![Скриншот состояния устройства Intune](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-12-deviceinstall)

## <a name="verify-client-device-state"></a>Проверка состояния клиентского устройства

1. После развертывания профилей конфигурации на устройствах откройте **профили** системных  >  **предпочтений** на устройстве Mac.

    ![Снимок экрана "Параметры системы"](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-13-systempreferences)<br/>
    ![Снимок экрана профилей системных предпочтений](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-14-systempreferencesprofiles)

2. Убедитесь, что следующие профили конфигурации присутствуют и устанавливаются. Профиль **управления должен** быть профилем системы Intune. _Wdav-config_ и _wdav-kext_ — это профили конфигурации системы, добавленные в Intune: ![ Скриншот профилей](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-15-managementprofileconfig)

3. Вы также должны увидеть значок Microsoft Defender в правом верхнем углу:

    > [!div class="mx-imgBorder"]
    > ![Значок Microsoft Defender в скриншоте панели состояния](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-icon-bar)

## <a name="troubleshooting"></a>Устранение неполадок

Проблема. Лицензия не найдена

Решение. Выполните действия, которые были выше, чтобы создать профиль устройства с помощью WindowsDefenderATPOnboarding.xml

## <a name="logging-installation-issues"></a>Проблемы с установкой журнала

Дополнительные сведения о том, как найти автоматически созданный журнал, созданный установщиком при ошибке, см. в примере проблемы с [установкой журнала.](mac-resources.md#logging-installation-issues)

## <a name="uninstallation"></a>Uninstallation

Сведения о том, как удалить Microsoft Defender для конечной точки для Mac с клиентских устройств, см. в материале [Uninstalling.](mac-resources.md#uninstalling)
