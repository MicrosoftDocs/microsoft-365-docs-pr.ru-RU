---
title: Антивирусная программа в Microsoft Defender в Windows Server
description: Узнайте, как включить и настроить антивирус Microsoft Defender на Windows Server 2016 и Windows Server 2019.
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
ms.date: 04/23/2021
ms.openlocfilehash: 175b06738b8c1508dab68c1e19648aa5385a7137
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269496"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Антивирусная программа в Microsoft Defender в Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Антивирус Microsoft Defender доступен в следующих выпусках и версиях Windows Server:
- Windows Server 2019
- Windows Server, версия 1803 или более поздней версии
- Windows Server 2016. 

В некоторых случаях антивирус Microsoft Defender называется *endpoint Protection;* однако механизм защиты один и тот же. Несмотря на то, что функциональность, конфигурация и управление в основном одинаковы для антивируса [Microsoft Defender в Windows 10,](microsoft-defender-antivirus-in-windows-10.md)в Windows Server есть несколько ключевых отличий:

- На Windows Server [автоматические исключения](configure-server-exclusions-microsoft-defender-antivirus.md) применяются в зависимости от определенной роли сервера.
 
- На Windows Server, если вы работаете с антивирусным или антивирусным решением, которое не является microsoft, антивирус Microsoft Defender не будет автоматически переходить в пассивный или отключенный режим. Однако антивирус Microsoft Defender можно настроить в пассивном или отключенном режиме вручную.

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>Настройка антивируса Microsoft Defender на Windows Server

Процесс настройки и запуска антивируса Microsoft Defender на серверной платформе включает в себя несколько действий:

1. [Включить интерфейс](#enable-the-user-interface-on-windows-server).
2. [Установка антивируса Microsoft Defender](#install-microsoft-defender-antivirus-on-windows-server).
3. [Проверка работы антивируса Microsoft Defender.](#verify-microsoft-defender-antivirus-is-running)
4. [Обновление сведений о безопасности антивирусных программ.](#update-antimalware-security-intelligence)
5. (По мере необходимости) [Отправка образцов](#submit-samples).
6. (По мере необходимости) [Настройка автоматических исключений.](#configure-automatic-exclusions)
7. (Только при необходимости) [Установите антивирус Microsoft Defender в пассивный режим.](#need-to-set-microsoft-defender-antivirus-to-passive-mode)

## <a name="enable-the-user-interface-on-windows-server"></a>Включить пользовательский интерфейс на Windows Server

По умолчанию антивирус Microsoft Defender устанавливается и функционирует на Windows Server. Иногда пользовательский интерфейс (GUI) устанавливается по умолчанию, но GUI не требуется. Для управления антивирусным вирусом Microsoft Defender можно использовать PowerShell, Group Policy или другие методы. 

Если GUI не установлен на сервере, и вы хотите  установить его, мастер добавить роли и функции или powerShell cmdlets.

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>Включив GUI с помощью мастера добавить роли и функции

1. См. в рублях Install [roles, role services and features by using the Add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the Add Roles and Features **Wizard.**

2. Когда вы доберетеся до шага **Features** мастера, в **Защитник Windows features** выберите **GUI** для Защитник Windows параметра.

   В Windows Server 2016 мастер **добавления ролей** и функций выглядит так:

   ![Добавление ролей и мастер функций, показывающих GUI для Защитник Windows параметра](images/server-add-gui.png)

   В Windows Server 2019 мастер **добавления ролей** и функций похож.

### <a name="turn-on-the-gui-using-powershell"></a>Включив GUI с помощью PowerShell

Следующий cmdlet PowerShell будет включить интерфейс: 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Установка антивируса Microsoft Defender на Windows Server

Если вам необходимо установить или переустановить антивирус Microsoft Defender на  Windows Server, вы можете сделать это с помощью мастера добавить роли и функции или PowerShell.

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a>Используйте мастер добавления ролей и функций для установки антивируса Microsoft Defender

1. Обратитесь [к этой статье](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)и используйте мастер добавить роли и **функции**.

2. Когда вы дойдете до шага **Features** мастера, выберите параметр Антивирус Microsoft Defender. Также выберите **GUI для Защитник Windows** параметра.

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a>Использование PowerShell для установки антивируса Microsoft Defender

Чтобы использовать PowerShell для установки антивируса Microsoft Defender, запустите следующий cmdlet:

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

Сообщения о событиях для антивирусного двигателя, включенного в антивирус Microsoft Defender, можно найти в [событиях Microsoft Defender AV.](troubleshoot-microsoft-defender-antivirus.md)


## <a name="verify-microsoft-defender-antivirus-is-running"></a>Проверка запуска антивируса Microsoft Defender

После установки антивируса Microsoft Defender следующий шаг — проверка его работы. В конечной точке Windows Server запустите следующий комдлет PowerShell:

```PowerShell
Get-Service -Name windefend
```

Чтобы убедиться, что защита брандмауэра включена, запустите следующий кодлет PowerShell:

```PowerShell 
Get-Service -Name mpssvc
```

В качестве альтернативы PowerShell можно использовать командную подсказку для проверки работы антивируса Microsoft Defender. Для этого запустите следующую команду из командной подсказки: 

```console
sc query Windefend
```

Команда `sc query` возвращает сведения о антивирусной службе Microsoft Defender. При запуске антивируса Microsoft Defender отображается `STATE` значение `RUNNING` .

## <a name="update-antimalware-security-intelligence"></a>Обновление сведений о безопасности антивирусных программ 

Чтобы получить обновленные сведения о безопасности антивирусных программ, необходимо иметь службу обновления Windows. Если вы используете службу управления обновлениями, например cлужбы Windows Server Update Services (WSUS), убедитесь, что обновления для антивирусной безопасности Microsoft Defender утверждены для управляемых компьютеров.

По умолчанию Обновление Windows не загружает и не устанавливает обновления автоматически на Windows Server 2019 или Windows Server 2016. Эту конфигурацию можно изменить с помощью одного из следующих методов:


|Метод  |Описание  |
|---------|---------|
|**Обновление Windows в** панели управления     |- **Установка обновлений автоматически** приводит к автоматической установке всех обновлений, включая обновления Защитник Windows безопасности. <br/>- **Скачайте** обновления, но позвольте мне выбрать, следует ли их устанавливать, Защитник Windows автоматически загружать и устанавливать обновления разведки безопасности, но другие обновления не устанавливаются автоматически.       |
|**Групповая политика**     | Настроить и управлять обновлением Windows можно с помощью параметров, доступных в групповой политике, по следующему пути: Административные **шаблоны\компоненты Windows\Windows Update\Configure Automatic Updates**         |
|Ключ **реестра AUOptions**     |Следующие два значения позволяют Windows Update автоматически загружать и устанавливать обновления разведки безопасности: <br/>- **4**  -  **Установка обновлений автоматически.** Это значение приводит к автоматической установке всех обновлений, включая обновления Защитник Windows безопасности. <br/>- **3**  -  **Скачайте обновления, но позвольте мне выбрать, следует ли их устанавливать.**  Это значение позволяет Защитник Windows автоматически загружать и устанавливать обновления разведки безопасности, но другие обновления не устанавливаются автоматически.         |

Чтобы обеспечить защиту от вредоносных программ, рекомендуется включить следующие службы:

- Служба отчетности об ошибках Windows

- Служба обновления Windows

В следующей таблице перечислены службы антивируса Microsoft Defender и зависимых служб.

|Имя службы|Расположение файла|Описание|
|--------|---------|--------|
|Защитник Windows (WinDefend)|`C:\Program Files\Windows Defender\MsMpEng.exe`|Это основная антивирусная служба Microsoft Defender, которая должна быть запущена во все времена.|
|Служба отчетности об ошибках Windows (Wersvc)|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|Эта служба отправляет отчеты об ошибках обратно в Корпорацию Майкрософт.|
|Защитник Windows брандмауэра (MpsSvc)|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|Рекомендуется оставить включенную Защитник Windows брандмауэра.|
|Обновление Windows (Wuauserv)|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|Обновление Windows необходимо для получения обновлений аналитики безопасности и обновлений движка антивирусного программного обеспечения|

## <a name="submit-samples"></a>Отправка образцов

Пример отправки позволяет Корпорации Майкрософт собирать образцы потенциально вредоносного программного обеспечения. Чтобы обеспечить постоянное и обновленное обеспечение защиты, исследователи Корпорации Майкрософт используют эти примеры для анализа подозрительных действий и создания обновленных сведений о безопасности антивирусных программ. Мы собираем исполняемые файлы программы, такие как .exe и .dll файлы. Мы не собираем файлы, содержащие персональные данные, такие как документы Microsoft Word и PDF-файлы.

### <a name="submit-a-file"></a>Отправка файла

1. Просмотрите [руководство по отправке.](/windows/security/threat-protection/intelligence/submission-guide)

2. Посетите пример [портала отправки](https://www.microsoft.com/wdsi/filesubmission)и отправьте файл.


### <a name="enable-automatic-sample-submission"></a>Включить автоматическую отправку образца

Чтобы включить автоматическую отправку примера, запустите консоль Windows PowerShell в качестве администратора и установите данные значения **SubmitSamplesConsent** в соответствии с одним из следующих параметров:

|Setting  |Описание  |
|---------|---------|
|**0**  -  **Всегда подсказка**     |Антивирусная служба Microsoft Defender подсказает вам подтверждение отправки всех необходимых файлов. Это параметр по умолчанию для антивируса Microsoft Defender, но не рекомендуется для установок на Windows Server 2016 или 2019 без GUI.         |
|**1**   -  **Автоматически отправлять безопасные образцы**     |Антивирусная служба Microsoft Defender отправляет все файлы, помеченные как "безопасные" и подсказок для остальных файлов.         |
|**2**  -  **Никогда не отправлять**      |Антивирусная служба Microsoft Defender не подсказывает и не отправляет файлы.         |
|**3**  -  **Отправка всех образцов автоматически**     |Антивирусная служба Microsoft Defender отправляет все файлы без запроса на подтверждение.         |

## <a name="configure-automatic-exclusions"></a>Настройка автоматических исключений

Чтобы обеспечить безопасность и производительность, автоматически добавляются определенные исключения в зависимости от ролей и функций, устанавливаемой при использовании антивируса Microsoft Defender на Windows Server 2016 или 2019.

См. [в рубке Настройка исключений в антивирусе Microsoft Defender на Windows Server.](configure-server-exclusions-microsoft-defender-antivirus.md) 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a>Необходимо настроить антивирус Microsoft Defender в пассивный режим?

Если в качестве основного антивирусного решения на Windows Server используется антивирусный продукт, не относячий к Майкрософт, необходимо настроить антивирус Microsoft Defender в пассивный или отключенный режим.

- На Windows Server версии 1803 или более новой версии или Windows Server 2019 можно настроить антивирус Microsoft Defender в пассивный режим.  

- В Windows Server 2016 антивирус Microsoft Defender не поддерживается наряду с антивирусным и антивирусным продуктом, не относя к Майкрософт. В этих случаях необходимо настроить режим отключения антивируса Microsoft Defender.

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-powershell"></a>Установите антивирус Microsoft Defender в пассивный режим с помощью PowerShell

Если вы используете Windows Server, версию 1803 или Windows Server 2019, можно настроить антивирус Microsoft Defender в пассивный режим с помощью следующего cmdlet PowerShell:

`CMDLET NEEDED`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-group-policy"></a>Установите антивирус Microsoft Defender в пассивный режим с помощью групповой политики

НЕОБХОДИМЫЕ ПРОЦЕДУРЫ

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>Установите антивирус Microsoft Defender в пассивный режим с помощью ключа реестра

Если вы используете Windows Server, версию 1803 или Windows Server 2019, можно настроить антивирус Microsoft Defender в пассивный режим, установив следующий ключ реестра:
- Путь: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Имя: `ForceDefenderPassiveMode`
- Тип: `REG_DWORD`
- Значение: `1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>Отключение антивируса Microsoft Defender с помощью мастера по удалению ролей и функций

1. См. в рублях Install или [Uninstall Roles, Role Services или Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)и use the **Remove Roles and Features Wizard**. 

2. Когда вы доберется до шага **Features** мастера, уберем **Защитник Windows Features.** 

    Если вы **Защитник Windows** в разделе **Защитник Windows Features,** вам будет предложено удалить интерфейс **GUI** параметра для Защитник Windows . 
    
    Антивирус Microsoft Defender по-прежнему будет работать нормально без пользовательского интерфейса, но  пользовательский интерфейс не может быть включен, если отключить Защитник Windows функцию.

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>Отключение пользовательского интерфейса антивируса Microsoft Defender с помощью PowerShell

Чтобы отключить интерфейс антивирусного интерфейса Microsoft Defender, используйте следующий комдлет PowerShell:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a>Используете ли вы Windows Server 2016?

Если вы используете Windows Server 2016 и сторонний антивирусный продукт, который не предлагается или не разрабатывается Корпорацией Майкрософт, необходимо отключить или удалить антивирус Microsoft Defender. 

> [!NOTE]
> Вы не можете удалить приложение Безопасности Windows, но вы можете отключить интерфейс с этими инструкциями.

Следующий кодлет PowerShell отстрагирует антивирус Microsoft Defender на Windows Server 2016:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

Чтобы отключить антивирус Microsoft Defender на Windows Server 2016, используйте следующий cmdlet PowerShell:

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a>См. также

- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Совместимость антивируса Microsoft Defender](microsoft-defender-antivirus-compatibility.md)
