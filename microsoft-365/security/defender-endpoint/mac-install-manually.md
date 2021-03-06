---
title: Ручное развертывание для Microsoft Defender для конечной точки на macOS
description: Установите Microsoft Defender для конечной точки на macOS вручную из командной строки.
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
ms.openlocfilehash: d8458f1bacc6577d83878a94c24e649371d90038
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935333"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-on-macos"></a>Ручное развертывание для Microsoft Defender для конечной точки на macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

В этом разделе описывается, как вручную развертывать Microsoft Defender для конечной точки на macOS. Успешное развертывание требует выполнения всех следующих действий:
- [Загрузка пакетов установки и загрузки](#download-installation-and-onboarding-packages)
- [Установка приложения (macOS 10.15 и более старые версии)](#application-installation-macos-1015-and-older-versions)
- [Установка приложения (macOS 11 и более новые версии)](#application-installation-macos-11-and-newer-versions)
- [Конфигурация клиента](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a>Необходимые условия и требования к системе

Перед началом работы см. в главной странице [Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md) на странице macOS описание необходимых условий и системных требований к текущей версии программного обеспечения.

## <a name="download-installation-and-onboarding-packages"></a>Загрузка пакетов установки и загрузки

Скачайте пакеты установки и загрузки из Центр безопасности в Microsoft Defender:

1. В Центр безопасности в Microsoft Defender перейдите **к Параметры > управления устройствами > onboarding**.
2. В разделе 1 страницы установите операционную систему для **macOS** и метода развертывания к **локальному сценарию.**
3. В разделе 2 страницы выберите **пакет установки Загрузка**. Сохраните его как wdav.pkg в локальном каталоге.
4. В разделе 2 страницы выберите **пакет Загрузка onboarding**. Сохраните его WindowsDefenderATPOnboardingPackage.zip в том же каталоге.

    ![Центр безопасности в Microsoft Defender скриншот](images/atp-portal-onboarding-page.png)

5. В командной подсказке убедитесь, что у вас есть два файла.
    
## <a name="application-installation-macos-1015-and-older-versions"></a>Установка приложения (macOS 10.15 и более старые версии)

Чтобы завершить этот процесс, на устройстве должны быть привилегии администратора.

1. Перейдите к скачаемой wdav.pkg в Finder и откройте его.

    ![Снимок экрана установки приложения1](images/mdatp-28-appinstall.png)

2. Выберите **Продолжить,** согласитесь с условиями лицензии и введите пароль при запросе.

    ![Скриншот установки приложения2](images/mdatp-29-appinstalllogin.png)

   > [!IMPORTANT]
   > Вам будет предложено разрешить установку драйвера из Microsoft (либо "Расширение системы заблокировано", либо "Установка заблокирована" или оба. Необходимо разрешить установку драйвера.

   ![Снимок экрана установки приложения3](images/mdatp-30-systemextension.png)

3. Выберите **параметры Open Security Preferences** или **Open System Preferences > безопасности & конфиденциальности.** Выберите **Разрешить:**

    ![Снимок экрана окна безопасности и конфиденциальности](images/mdatp-31-securityprivacysettings.png)

   Продолжается установка.

   > [!CAUTION]
   > Если вы не выберите **Разрешить,** установка будет продолжаться через 5 минут. Microsoft Defender для конечной точки будет загружен, но некоторые функции, например защита в режиме реального времени, будут отключены. Сведения [о том,](mac-support-kext.md) как устранить неполадки в расширении ядра, см. в выпуске "Устранение неполадок".

> [!NOTE]
> MacOS может потребовать перезагрузить устройство при первой установке Microsoft Defender для конечной точки. Защита в режиме реального времени не будет доступна до перезагрузки устройства.

## <a name="application-installation-macos-11-and-newer-versions"></a>Установка приложения (macOS 11 и более новые версии)

Чтобы завершить этот процесс, на устройстве должны быть привилегии администратора.

1. Перейдите к скачаемой wdav.pkg в Finder и откройте его.

    ![Скриншот установки приложения4](images/big-sur-install-1.png)

2. Выберите **Продолжить,** согласитесь с условиями лицензии и введите пароль при запросе.

3. По завершении процесса установки вам будет назначено утверждение системных расширений, используемых продуктом. Выберите **параметры открытой безопасности.**

    ![Утверждение расширения системы](images/big-sur-install-2.png)

4. Из окна **конфиденциальности & безопасности** выберите **Разрешить**.

    ![Параметры безопасности расширения системы1](images/big-sur-install-3.png)

5. Повторите действия 3 & 4 для всех расширений системы, распространяемых с Помощью Microsoft Defender для конечной точки на Mac.

6. В рамках возможностей обнаружения конечных точек и ответов Microsoft Defender для конечной точки на Mac проверяет трафик розетки и передает эти сведения на Центр безопасности в Microsoft Defender портал. Если вам предложено предоставить разрешения Microsoft Defender для конечной точки для фильтрации сетевого трафика, выберите **Разрешить**.

    ![Параметры безопасности расширения системы2](images/big-sur-install-4.png)

7. Open **System Preferences** Security & конфиденциальность и перейдите на вкладку Конфиденциальность. Предоставление полного доступа к дискам для ATP в Защитнике Microsoft и ATP в Защитнике Microsoft расширения  >   безопасности  **конечной точки.**  

    ![Полный доступ к диску](images/big-sur-install-5.png)

## <a name="client-configuration"></a>Конфигурация клиента

1. Скопируйте wdav.pkg и MicrosoftDefenderATPOnboardingMacOs.py на устройство, на котором развернут Microsoft Defender для конечной точки на macOS.

    Клиентские устройства не связаны с org_id. Обратите внимание, *что org_id* является пустым.

    ```bash
    mdatp health --field org_id
    ```

2. Запустите скрипт Python для установки файла конфигурации:

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. Убедитесь, что устройство теперь связано с организацией и сообщает действительный удостоверение организации:

    ```bash
    mdatp health --field org_id
    ```

    После установки вы увидите значок Microsoft Defender в панели состояния macOS в правом верхнем углу.
    
    > [!div class="mx-imgBorder"]
    > ![Значок Microsoft Defender в скриншоте панели состояния](images/mdatp-icon-bar.png)


## <a name="how-to-allow-full-disk-access"></a>Как разрешить полный доступ к диску

> [!CAUTION]
> MacOS 10.15 (Catalina) содержит новые улучшения безопасности и конфиденциальности. Начиная с этой версии, по умолчанию приложения не могут получить доступ к определенным расположениям на диске (например, документы, скачивания, настольные компьютеры и т.д.) без явного согласия. При отсутствии такого согласия Microsoft Defender для конечной точки не может полностью защитить ваше устройство.

1. Чтобы предоставить согласие, откройте **систему настройки** безопасности  >  **&**  >  **конфиденциальности**  >  **полный доступ к диску**. Щелкните значок блокировки, чтобы внести изменения (в нижней части диалогового окна). Выберите Microsoft Defender для конечной точки.

2. Запустите тест обнаружения AV, чтобы убедиться, что устройство правильно на борту, и сообщить об этом службе. Выполните следующие действия на недавно созданном устройстве:

    1. Убедитесь, что в режиме реального времени включена защита (обозначаемая результатом 1 от запуска следующей команды):

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    1. Откройте окно терминала. Скопируйте и выполните следующую команду:

        ```bash
        curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    1. Файл должен был быть карантин для Защитника для конечной точки на Mac. Чтобы перечислить все обнаруженные угрозы, используйте следующую команду:

        ```bash
        mdatp threat list
        ```

3. Запустите EDR проверку обнаружения, чтобы убедиться, что устройство правильно на борту, и сообщить об этом службе. Выполните следующие действия на недавно созданном устройстве:

   1. В браузере, например Microsoft Edge для Mac или Safari.

   1. Скачайте MDATP MacOS DIY.zip и https://aka.ms/mdatpmacosdiy извлеките.

      Вам может быть предложено:

      > Хотите разрешить загрузку на "mdatpclientanalyzer.blob.core.windows.net"?<br/>
      > Вы можете изменить, какие веб-сайты могут загружать файлы в Настройках веб-сайтов.

4. Нажмите **кнопку Разрешить**.

5. Open **Downloads**.

6. Вы должны увидеть **MDATP MacOS DIY**.

   > [!TIP]
   > Если дважды щелкнуть, вы получите следующее сообщение:
   > 
   > > **"MDATP MacOS DIY" нельзя открыть, так как разработчик не может быть более проверяем.**<br/>
   > > MacOS не может убедиться, что это приложение является свободным от вредоносных программ.<br/>
   > > **\[ Переход к \] отмене** **\[ \] корзины** 
  
7. Нажмите кнопку **Отмена**.

8. Щелкните **правой кнопкой мыши MDATP MacOS DIY,** а затем нажмите кнопку **Открыть**. 

    Система должна отображать следующее сообщение:

    > **MacOS не может проверить разработчика MDATP **MacOS DIY**. Вы уверены, что хотите открыть его?**<br/>
    > Открыв это приложение, вы будете переопределять системную безопасность, которая может подвергать компьютер и личную информацию вредоносным программам, которые могут нанести вред вашему Mac или нарушить конфиденциальность.

10. Нажмите кнопку **Open** (Открыть).

    Система должна отображать следующее сообщение:

    > Microsoft Defender для конечной точки — тестовый файл macOS EDR DIY<br/>
    > Соответствующее оповещение будет доступно на MDATP портале.

11. Нажмите кнопку **Open** (Открыть).

    Через несколько минут должно быть поднято оповещение с именем "macOS EDR Test Alert".

12. Перейдите в Центр безопасности в Microsoft Defender ( https://SecurityCenter.microsoft.com) .

13. Перейдите в очередь оповещения.

    :::image type="content" source="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png" alt-text="Пример тестового оповещений EDR macOS, которое показывает серьезность, категорию, источник обнаружения и свернутое меню действий.":::
    
    Посмотрите на сведения о оповещениях и временной шкале устройства и выполните регулярные действия по расследованию.

## <a name="logging-installation-issues"></a>Проблемы с установкой журнала

Дополнительные [сведения](mac-resources.md#logging-installation-issues) о том, как найти автоматически созданный журнал, созданный установщиком при ошибке, см. в дополнительных сведениях.

## <a name="uninstallation"></a>Uninstallation

Сведения о том, как удалить Microsoft Defender для конечной точки на macOS с клиентских устройств, см. в материале [Uninstalling.](mac-resources.md#uninstalling)
