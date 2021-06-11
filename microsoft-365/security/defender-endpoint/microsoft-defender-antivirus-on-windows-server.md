---
title: Антивирусная программа в Microsoft Defender в Windows Server
description: Узнайте, как включить и настроить антивирусная программа в Microsoft Defender на Windows Server 2016 и Windows Server 2019.
keywords: защитник windows, сервер, scep, защита конечных точек центра системы, сервер 2016, текущая ветвь, сервер 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 05/13/2021
ms.openlocfilehash: 1a1083d15698eb5bbdf2f6080b152b6f326c689a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539279"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Антивирусная программа в Microsoft Defender в Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

антивирусная программа в Microsoft Defender доступны в следующих выпусках и версиях Windows Server:
- Windows Server 2019
- Windows Сервер, версия 1803 или более поздней версии
- Windows Server 2016. 

В некоторых случаях антивирусная программа в Microsoft Defender называются *Endpoint Protection;* однако механизм защиты один и тот же. Несмотря на то, что функциональные возможности, конфигурация и управление в основном одинаковы для антивирусная программа в Microsoft Defender [Windows 10,](microsoft-defender-antivirus-in-windows-10.md)на сервере Windows несколько ключевых различий:

- На Windows Server [автоматические исключения](configure-server-exclusions-microsoft-defender-antivirus.md) применяются в зависимости от определенной роли сервера.
 
- На Windows Server, если вы работаете с антивирусным решением, не относяжимся к Майкрософт, антивирусная программа в Microsoft Defender автоматически не переходить в пассивный или отключенный режим. Однако можно настроить режим антивирусная программа в Microsoft Defender или отключить вручную.

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>Настройка антивирусная программа в Microsoft Defender на Windows Server

Процесс настройки и запуска антивирусная программа в Microsoft Defender на серверной платформе включает в себя несколько действий:

1. [Включить интерфейс](#enable-the-user-interface-on-windows-server).
2. [Установка антивирусная программа в Microsoft Defender](#install-microsoft-defender-antivirus-on-windows-server).
3. [Проверка антивирусная программа в Microsoft Defender запущена.](#verify-microsoft-defender-antivirus-is-running)
4. [Обновление сведений о безопасности антивирусных программ.](#update-antimalware-security-intelligence)
5. (По мере необходимости) [Отправка образцов](#submit-samples).
6. (По мере необходимости) [Настройка автоматических исключений.](#configure-automatic-exclusions)
7. (Только при необходимости) [Установите антивирусная программа в Microsoft Defender пассивный режим](#need-to-set-microsoft-defender-antivirus-to-passive-mode).

## <a name="enable-the-user-interface-on-windows-server"></a>Включить пользовательский интерфейс на Windows Server

По умолчанию антивирусная программа в Microsoft Defender устанавливается и функционирует на Windows Server. Иногда пользовательский интерфейс (GUI) устанавливается по умолчанию, но GUI не требуется. Для управления антивирусная программа в Microsoft Defender можно использовать PowerShell, Group Policy или другие методы. 

Если GUI не установлен на сервере, и вы хотите  установить его, мастер добавить роли и функции или powerShell cmdlets.

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>Включив GUI с помощью мастера добавить роли и функции

1. См. в рублях Install [roles, role services and features by using the Add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the Add Roles and Features **Wizard.**

2. Когда вы доберетеся до шага **Features** мастера, **Защитник Windows функции** выберите **GUI** для Защитник Windows параметра.

   В Windows Server 2016, мастер **добавления ролей** и функций выглядит так:

   ![Добавление ролей и мастер функций, показывающих GUI для Защитник Windows параметра](images/server-add-gui.png)

   В Windows Server 2019 мастер **добавления ролей** и функций похож.

### <a name="turn-on-the-gui-using-powershell"></a>Включив GUI с помощью PowerShell

Следующий cmdlet PowerShell будет включить интерфейс: 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Установка антивирусная программа в Microsoft Defender на Windows Server

Если вам необходимо установить или переустановить антивирусная программа в Microsoft Defender на Windows Server, вы  можете сделать это с помощью мастера добавить роли и функции или PowerShell.

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a>Используйте мастер добавления ролей и функций для установки антивирусная программа в Microsoft Defender

1. Обратитесь [к этой статье](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)и используйте мастер добавить роли и **функции**.

2. Когда вы дойдете до шага **Features** мастера, выберите антивирусная программа в Microsoft Defender. Также выберите **GUI для Защитник Windows** параметра.

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a>Используйте PowerShell для установки антивирусная программа в Microsoft Defender

Чтобы использовать PowerShell для установки антивирусная программа в Microsoft Defender, запустите следующий cmdlet:

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

Сообщения о событиях для двигателя антивирусного программного обеспечения, включенного в антивирусная программа в Microsoft Defender, можно найти в [событиях Microsoft Defender AV.](troubleshoot-microsoft-defender-antivirus.md)


## <a name="verify-microsoft-defender-antivirus-is-running"></a>Проверка антивирусная программа в Microsoft Defender запущена

После антивирусная программа в Microsoft Defender установлен, следующим шагом будет проверка его работы. На конечной Windows Server запустите следующий комдлет PowerShell:

```PowerShell
Get-Service -Name windefend
```

Чтобы убедиться, что защита брандмауэра включена, запустите следующий кодлет PowerShell:

```PowerShell 
Get-Service -Name mpssvc
```

В качестве альтернативы PowerShell можно использовать командную подсказку, чтобы убедиться, что антивирусная программа в Microsoft Defender запущена. Для этого запустите следующую команду из командной подсказки: 

```console
sc query Windefend
```

Команда `sc query` возвращает сведения о службе антивирусная программа в Microsoft Defender. Когда антивирусная программа в Microsoft Defender запущен, отображается `STATE` значение `RUNNING` .

## <a name="update-antimalware-security-intelligence"></a>Обновление сведений о безопасности антивирусных программ 

Чтобы получить обновленные сведения о безопасности антивирусных программ, необходимо Windows службу обновления. Если вы используете службу управления обновлениями, например Windows Server Update Services (WSUS), убедитесь, что обновления для антивирусная программа в Microsoft Defender безопасности будут утверждены для управляемых компьютеров.

По умолчанию Windows обновления не загружаются и устанавливаются автоматически на Windows Server 2019 или Windows Server 2016. Эту конфигурацию можно изменить с помощью одного из следующих методов:


|Метод  |Описание  |
|---------|---------|
|**Windows панели** управления     | **Установка обновлений автоматически приводит** к автоматической установке всех обновлений, включая обновления Защитник Windows безопасности. <p>**Скачайте** обновления, но позвольте мне выбрать, следует ли их устанавливать, Защитник Windows автоматически загружать и устанавливать обновления разведки безопасности, но другие обновления не устанавливаются автоматически.       |
|**Групповая политика**     | Настройка и управление обновлением Windows с помощью параметров, доступных в групповой политике, по следующему пути: Административные **шаблоны\Windows компоненты\Windows Update\Configure Automatic Updates**         |
|Ключ **реестра AUOptions**     | Следующие два значения позволяют Windows обновления для автоматической загрузки и установки обновлений разведки безопасности: <p>**4**  -  **Установка обновлений автоматически.** Это значение приводит к автоматической установке всех обновлений, в том числе Защитник Windows обновлений разведки безопасности. <p>**3**  -  **Скачайте обновления, но позвольте мне выбрать, следует ли их устанавливать.**  Это значение позволяет Защитник Windows автоматически загружать и устанавливать обновления разведки безопасности, но другие обновления не устанавливаются автоматически.         |

Чтобы обеспечить защиту от вредоносных программ, рекомендуется включить следующие службы:

- отчеты об ошибках Windows службы

- Windows Обновление службы

В следующей таблице перечислены службы для антивирусная программа в Microsoft Defender и зависимых служб.

|Имя службы|Расположение файла|Описание|
|--------|---------|--------|
|Защитник Windows Служба (WinDefend)|`C:\Program Files\Windows Defender\MsMpEng.exe`|Это основная служба антивирусная программа в Microsoft Defender, которая должна быть запущена во все времена.|
|отчеты об ошибках Windows Служба (Wersvc)|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|Эта служба отправляет отчеты об ошибках обратно в Корпорацию Майкрософт.|
|брандмауэр Защитника Windows (MpsSvc)|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|Рекомендуется оставить включенную брандмауэр Защитника Windows службу.|
|Windows Обновление (Wuauserv)|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|Windows Обновление необходимо для получения обновлений аналитики безопасности и обновлений антивирусного двигателя|

## <a name="submit-samples"></a>Отправка образцов

Пример отправки позволяет Корпорации Майкрософт собирать образцы потенциально вредоносного программного обеспечения. Чтобы обеспечить постоянное и обновленное обеспечение защиты, исследователи Корпорации Майкрософт используют эти примеры для анализа подозрительных действий и создания обновленных сведений о безопасности антивирусных программ. Мы собираем исполняемые файлы программы, такие как .exe и .dll файлы. Мы не собираем файлы, содержащие персональные данные, Microsoft Word документы и PDF-файлы.

### <a name="submit-a-file"></a>Отправка файла

1. Просмотрите [руководство по отправке.](/windows/security/threat-protection/intelligence/submission-guide)

2. Посетите пример [портала отправки](https://www.microsoft.com/wdsi/filesubmission)и отправьте файл.


### <a name="enable-automatic-sample-submission"></a>Включить автоматическую отправку образца

Чтобы включить автоматическую отправку примера, запустите консоль Windows PowerShell в качестве администратора и установите данные **значения SubmitSamplesConsent** в соответствии с одним из следующих параметров:

|Параметр  |Описание  |
|---------|---------|
|**0**  -  **Всегда подсказка**     |Служба антивирусная программа в Microsoft Defender вас, чтобы подтвердить отправку всех необходимых файлов. Это параметр по умолчанию для антивирусная программа в Microsoft Defender, но не рекомендуется для установок на Windows Server 2016 или 2019 без GUI.         |
|**1**   -  **Автоматически отправлять безопасные образцы**     |Служба антивирусная программа в Microsoft Defender отправляет все файлы, помеченные как "безопасные", и подсказок для остальных файлов.         |
|**2**  -  **Никогда не отправлять**      |Служба антивирусная программа в Microsoft Defender не подсказывает и не отправляет файлы.         |
|**3**  -  **Отправка всех образцов автоматически**     |Служба антивирусная программа в Microsoft Defender отправляет все файлы без запроса на подтверждение.         |

## <a name="configure-automatic-exclusions"></a>Настройка автоматических исключений

Чтобы обеспечить безопасность и производительность, автоматически добавляются определенные исключения в зависимости от ролей и функций, устанавливаемой при использовании антивирусная программа в Microsoft Defender в Windows Server 2016 или 2019 году.

См. в рубке Настройка исключений [антивирусная программа в Microsoft Defender на Windows Server.](configure-server-exclusions-microsoft-defender-antivirus.md) 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a>Необходимо настроить антивирусная программа в Microsoft Defender пассивный режим?

Если в качестве основного антивирусного решения на Windows Server используется антивирусный продукт, не относячий к Майкрософт, необходимо антивирусная программа в Microsoft Defender режим пассивного или отключенного.

- На Windows Server версии 1803 или более новой версии Windows Server 2019 можно антивирусная программа в Microsoft Defender пассивный режим.  

- На Windows Server 2016, антивирусная программа в Microsoft Defender не поддерживается наряду с антивирусным и антивирусным продуктом не Microsoft. В этих случаях необходимо антивирусная программа в Microsoft Defender режим отключения.

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>Установите антивирусная программа в Microsoft Defender пассивный режим с помощью ключа реестра

Если вы используете Windows Server, версию 1803 или Windows Server 2019, вы можете антивирусная программа в Microsoft Defender пассивный режим, установив следующий ключ реестра:
- Путь: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Имя: `ForceDefenderPassiveMode`
- Тип: `REG_DWORD`
- Значение: `1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>Отключение антивирусная программа в Microsoft Defender с помощью мастера "Удалить роли и функции"

1. См. в рублях Install или [Uninstall Roles, Role Services или Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)и use the **Remove Roles and Features Wizard**. 

2. Когда вы доберется до шага **Features** мастера, уберем **Защитник Windows Features.** 

    Если вы **Защитник Windows** в разделе **Защитник Windows Features,** вам будет предложено удалить интерфейс **GUI** параметра для Защитник Windows . 
    
    антивирусная программа в Microsoft Defender по-прежнему будет работать нормально без пользовательского интерфейса, но пользовательский интерфейс  не может быть включен, если отключить Защитник Windows функцию.

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>Отключение интерфейса антивирусная программа в Microsoft Defender с помощью PowerShell

Чтобы отключить антивирусная программа в Microsoft Defender GUI, используйте следующий cmdlet PowerShell:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a>Вы используете Windows Server 2016?

Если вы используете Windows Server 2016 и сторонний антивирусный продукт, который не предлагается или не разрабатывается Корпорацией Майкрософт, необходимо отключить или удалить антивирусная программа в Microsoft Defender. 

> [!NOTE]
> Вы не можете удалить приложение Безопасность Windows, но вы можете отключить интерфейс с этими инструкциями.

Следующие кодлеты PowerShell антивирусная программа в Microsoft Defender на Windows Server 2016:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

Чтобы отключить антивирусная программа в Microsoft Defender на Windows Server 2016, используйте следующий cmdlet PowerShell:

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a>См. также

- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [антивирусная программа в Microsoft Defender совместимости](microsoft-defender-antivirus-compatibility.md)
