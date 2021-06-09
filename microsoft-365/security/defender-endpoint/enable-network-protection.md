---
title: Включить защиту сети
description: Включить защиту сети с помощью групповой политики, PowerShell или диспетчера управления и конфигурации мобильных устройств.
keywords: Защита ANetwork, эксплойтов, вредоносный веб-сайт, IP, домен, домены, включить, включить
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6afdcc16493839e83771ac831831fdbb121663a1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841778"
---
# <a name="turn-on-network-protection"></a>Включить защиту сети

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Защита сети](network-protection.md) помогает предотвратить использование сотрудниками любого приложения для доступа к опасным доменам, в которые могут быть организованы фишинговые атаки, эксплойты и другой вредоносный контент в Интернете. Вы можете [проверить защиту сети](evaluate-network-protection.md) в тестовой среде, чтобы просмотреть, какие приложения будут заблокированы, прежде чем включить ее.

[Дополнительные информацию о параметрах конфигурации фильтрации сети](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>Проверьте, включена ли защита сети

Проверьте, включена ли защита сети на локальном устройстве с помощью редактора реестра.

1. Выберите **кнопку Начните** в панели задач и введите **regedit** для открытия редактора реестра

2. Выберите **HKEY_LOCAL_MACHINE** из бокового меню

3. Перейдите через вложенные меню к **политикам ПРОГРАММНОГО**  >  **ОБЕСПЕЧЕНИЯ**  >  **Microsoft**  >  **Защитник Windows**  >  **Policy Manager** 

4. Выберите **EnableNetworkProtection,** чтобы увидеть текущее состояние сетевой защиты на устройстве

    * 0 или **off**
    * 1 или **On**
    * 2 или **режим аудита**
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a>Включить защиту сети

Включить защиту сети с помощью любого из этих методов:

* [PowerShell](#powershell)
* [Управление мобильными устройствами (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Manager / Intune](#microsoft-endpoint-manager-formerly-intune)
* [Групповая политика](#group-policy)

### <a name="powershell"></a>PowerShell

1. Введите **powershell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**
2. Введите следующий cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. Необязательный вариант: включить функцию в режиме аудита с помощью следующего cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    Используйте `Disabled` вместо или для `AuditMode` `Enabled` отключения функции.

### <a name="mobile-device-management-mdm"></a>Управление мобильными устройствами (MDM)

Используйте [поставщик услуг конфигурации ./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) (CSP), чтобы включить или отключить защиту сети или включить режим аудита.

### <a name="microsoft-endpoint-manager-formerly-intune"></a>Microsoft Endpoint Manager (ранее Intune)

1. Вход в центр Microsoft Endpoint Manager администратора (https://endpoint.microsoft.com)

2. Создание или изменение профиля конфигурации [защиты конечной точки](/mem/intune/protect/endpoint-protection-configure)

3. В **соответствии Параметры** конфигурации в потоке профилей перейдите к Exploit Guard в Microsoft Defender сетевой **защиты** фильтрующих сетей  >    >    >  **Включить** или аудит **только**

### <a name="group-policy"></a>Групповая политика

Используйте следующую процедуру, чтобы включить защиту сети на компьютерах с доменом или на автономных компьютерах.

1. На автономных компьютерах перейдите в **Начните,** а затем введите и выберите **групповую политику редактирования.**

    *-Or-*

    На компьютере управления групповой политикой, примыкаемом к домену, откройте консоль управления групповой политикой [правой](https://technet.microsoft.com/library/cc731212.aspx)кнопкой мыши объект групповой политики, который необходимо настроить, и выберите **Изменить**.

2. В **редакторе управления групповыми политиками** перейдите к **конфигурации компьютера** и выберите **Административные шаблоны**.

3. Расширь **дерево, чтобы Windows компоненты антивирусная программа в Microsoft Defender**  >    >  **Защитник Windows защита сети exploit**  >  **Guard.**

> [!NOTE]
> В более старых версиях Windows путь групповой политики может антивирусная программа вместо "антивирусная программа в Microsoft Defender".

4. Дважды щелкните кнопку **Запретить пользователям и приложениям доступ** к опасным настройкам веб-сайтов и установите параметр **Включено**. В разделе Параметры необходимо указать один из следующих вариантов:
    * **Block** . Пользователи не могут получить доступ к вредоносным IP-адресам и доменам
    * **Отключение (по умолчанию)** — функция защиты сети не будет работать. Пользователям не будет заблокирован доступ к вредоносным доменам
    * **Режим аудита** . Если пользователь посещает вредоносный IP-адрес или домен, событие будет записано в журнале Windows событий. Однако пользователю не будет заблокировано посещение адреса.

> [!IMPORTANT]
> Чтобы полностью включить защиту сети, необходимо настроить  параметр Групповой политики для включения, а также выбрать **Блок** в выпадаемом меню параметров.

Подтверждение того, что защита сети включена на локальном компьютере с помощью редактора реестра:

1. Выберите **regedit Начните и** введите, чтобы открыть **редактор реестра.** 

2. Перейдите **кHKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\EnableNetworkProtection**

3. Выберите **EnableNetworkProtection** и подтвердите значение:
   * 0=Off
   * 1=On
   * 2=Audit

## <a name="see-also"></a>См. также

* [Защита сети](network-protection.md)
* [Оценка защиты сети](evaluate-network-protection.md)
* [Защита сети от неполадок](troubleshoot-np.md)
