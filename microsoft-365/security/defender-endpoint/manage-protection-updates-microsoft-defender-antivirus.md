---
title: Управление получением обновлений антивирусной программой Microsoft Defender и ее получением
description: Управление порядком отката для получения обновлений защиты антивирусом Microsoft Defender.
keywords: обновления, базовые показатели безопасности, защита, порядок отката, ADL, MMPC, UNC, путь к файлу, share, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 9b1c9bc8c86c5b348e3c4d2a51e0bfafaf3e7174
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765471"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a>Управление источниками обновлений антивирусной программы в Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=22154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

Важно поддерживать антивирусную защиту в соответствии с данными. Для управления обновлениями защиты антивируса Microsoft Defender существуют два компонента: 
- *Загрузка* обновлений; и 
- *При* загрузке и применении обновлений. 

В этой статье описывается, как указать, откуда должны загружаться обновления (это также называется заказом на откат). Сведения о работе обновлений и настройке других аспектов обновлений (например, планирования обновлений) см. в разделе Управление обновлениями антивируса Microsoft [Defender](manage-updates-baselines-microsoft-defender-antivirus.md) и применение базовых версий.

> [!IMPORTANT]
> Обновления антивирусной безопасности Microsoft Defender доставляются с помощью обновления Windows, и начиная с понедельника, 21 октября 2019 г., все обновления аналитики безопасности будут подписаны исключительно на SHA-2. Чтобы обновить сведения о безопасности, необходимо обновить устройства для поддержки SHA-2. Дополнительные новости см. в [ок. 2019 требование](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)о поддержке подписи кода SHA-2 для Windows и WSUS.  


<a id="fallback-order"></a>

## <a name="fallback-order"></a>Порядок отката

Обычно конечные точки настраиваются для индивидуальной загрузки обновлений из основного источника, а затем из других источников в порядке приоритета в зависимости от конфигурации сети. Обновления получаются из источников в порядке, который вы указываете. Если источник не доступен, следующий источник в списке используется немедленно.

При публикации обновлений применяется какая-то логика, чтобы свести к минимуму размер обновления. В большинстве случаев на устройстве загружаются и применяются только различия между последним обновлением и установленным в настоящее время обновлением (это называется дельта). Однако размер дельты зависит от двух основных факторов:
- Возраст последнего обновления на устройстве; и 
- Источник, используемый для скачивания и применения обновлений. 

Чем старше будут обновления на конечной точке, тем больше будет скачивание. Однако необходимо также учитывать частоту скачивания. Более частое расписание обновлений может привести к большему использованию сети, в то время как менее частое расписание может привести к большим размерам файлов для загрузки. 

Существует пять местоположений, в которых можно указать, где конечная точка должна получать обновления: 

- [Центр обновления Майкрософт](https://support.microsoft.com/help/12373/windows-update-faq)
- [Служба обновления Windows Server](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/core/servers/manage/updates)
- [Доля сетевых файлов](#unc-share)
- [Обновления сведений](https://www.microsoft.com/en-us/wdsi/defenderupdates) о безопасности для антивируса Microsoft Defender и других антивирусных программ Майкрософт (ваша политика и реестр могут иметь этот список как Центр Майкрософт по защите от вредоносных программ безопасности (MMPC) с его прежним именем.)

Чтобы обеспечить наилучший уровень защиты, Microsoft Update позволяет быстро выпускать, что означает частые скачивания. Службы обновления Windows Server, Microsoft Endpoint Configuration Manager и источники обновлений службы безопасности Майкрософт обеспечивают менее частые обновления. Таким образом, дельта может быть больше, что приводит к большим загрузкам. 

> [!IMPORTANT]
> Если после [](https://www.microsoft.com/security/portal/definitions/adl.aspx) обновления Windows Server Update или Microsoft Update вы задаете обновления страницы разведки Майкрософт в качестве источника отката, обновления загружаются только из обновлений разведки безопасности, если текущее обновление считается устарелым. (По умолчанию это семь дней подряд, когда не удалось применить обновления из Службы обновления Windows Server или службы обновления Майкрософт).
> Однако можно установить количество дней до того, как защита будет отчитаться о том, что она [устарела.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)<p>
> Начиная с понедельника, 21 октября 2019 г., обновления аналитики безопасности будут подписывался исключительно sha-2. Устройства должны обновляться для поддержки SHA-2 для получения последних обновлений разведки безопасности. Дополнительные новости см. в [ок. 2019 требование](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)о поддержке подписи кода SHA-2 для Windows и WSUS.

Каждый источник имеет типичные сценарии, которые зависят от настройки сети, а также от того, как часто они публикуют обновления, как описано в следующей таблице:

|Расположение | Пример сценария |
|---|---|
|Служба обновления Windows Server | Вы используете службу обновления Windows Server для управления обновлениями для вашей сети.|
|Центр обновления Майкрософт | Вы хотите, чтобы конечные точки подключались непосредственно к Microsoft Update. Это может быть полезно для конечных точек, которые нерегулярно подключаются к корпоративной сети, или если вы не используете службу обновления Windows Server для управления обновлениями.|
|Файловый ресурс | У вас есть устройства, не подключенные к Интернету (например, VMs). Вы можете использовать подключенный к Интернету VM-хост для скачивания обновлений в сеть, из которой VMs могут получать обновления. См. руководство по развертыванию [VDI](deployment-vdi-microsoft-defender-antivirus.md) для использования файловых акций в средах виртуальной инфраструктуры настольных компьютеров (VDI).|
|Менеджер конечных точек Майкрософт | Вы используете Microsoft Endpoint Manager для обновления конечных точек.|
|Обновления аналитики безопасности для антивируса Microsoft Defender и других антивирусных программ Майкрософт (ранее именуемого MMPC) |[Убедитесь, что ваши устройства обновляются для поддержки SHA-2.](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus) Обновления антивирусной безопасности Microsoft Defender доставляются с помощью обновления Windows, и начиная с понедельника 21 октября 2019 г. обновления аналитики безопасности будут подписываться исключительно на SHA-2. <br/>Скачайте последние обновления защиты из-за недавней инфекции или чтобы помочь в предоставлении сильного базового изображения для [развертывания VDI.](deployment-vdi-microsoft-defender-antivirus.md) Обычно этот параметр следует использовать только в качестве конечного источника отката, а не основного источника. Он будет использоваться только в том случае, если обновления не могут быть загружены из службы обновления Windows Server или Обновления Microsoft в течение определенного числа [дней.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)|

Вы можете управлять порядком, в котором источники обновления используются с помощью групповой политики, Microsoft Endpoint Configuration Manager, команды PowerShell и WMI.

> [!IMPORTANT]
> Если вы установите службу обновления Windows Server в качестве места загрузки, необходимо утвердить обновления независимо от средства управления, используемого для указания местоположения. Вы можете настроить автоматическое правило утверждения в службе обновления Windows Server, которое может быть полезно по мере поступления обновлений по крайней мере один раз в день. Дополнительные данные см. в дополнительных данных о синхронизации обновлений защиты конечных точек в автономных [службах обновления Windows Server.](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)

Процедуры в этой статье сначала описывают, как настроить порядок, а затем настроить параметр **Share File,** если он включен.

## <a name="use-group-policy-to-manage-the-update-location"></a>Использование групповой политики для управления расположением обновления

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **Политики,** а **затем административные шаблоны**.

4. Расширь дерево до **компонентов Windows > Защитник Windows > обновлений Signature** и настройте следующие параметры:

   1.  Дважды щелкните **кнопку Определить порядок источников** для скачивания параметров обновлений разведки безопасности и установите параметр **Включено**.

   2.  Введите порядок источников, разделенных одной трубой, например: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` , как показано на следующем скриншоте.

   ![Снимок экрана настройки групповой политики с перечислением порядка источников](images/defender/wdav-order-update-sources.png)

   3. Нажмите кнопку **ОК**. При этом будет установлен порядок источников обновления защиты.

   4. Дважды щелкните **файл Define shares для скачивания** параметра обновлений разведки безопасности и установите параметр **Включено**.

   5. Введите источник файловой папки. Если у вас несколько источников, введите каждый источник в том порядке, в который они должны использоваться, разделенные одной трубой. Используйте [стандартную нотацию UNC](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) для обозначания пути, например: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` .  Если вы не введите какие-либо пути, этот источник будет пропущен при загрузке обновлений VM.

   6. Нажмите кнопку **ОК**. При этом будет задат порядок файловых акций при ссылке на этот источник в параметре **Определить порядок источников...**

> [!NOTE]
> Для Windows 10 версии 1703 до 1809 и включая 1809 путь политики — это **антивирусные** компоненты Windows > Антивирус Microsoft Defender > Обновления подписей для Windows 10, версия 1903, путь политики — Windows **Components > Антивирус Microsoft Defender >** Обновления разведки безопасности

## <a name="use-configuration-manager-to-manage-the-update-location"></a>Использование диспетчера конфигурации для управления расположением обновления

Сведения о настройке Microsoft Endpoint Manager (текущая ветвь) см. в странице Configure Security intelligence [Updates for Endpoint Protection.](/configmgr/protect/deploy-use/endpoint-definition-updates)


## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a>Чтобы управлять расположением обновления, используйте cmdlets PowerShell

Чтобы установить порядок обновления, используйте следующие cmdlets PowerShell.

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```
Дополнительные сведения см. в следующих статьях:
- [Set-MpPreference -SignatureFallbackOrder](/powershell/module/defender/set-mppreference)
- [Set-MpPreference -SignatureDefinitionUpdateFileSharesSource](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [Для настройки и запуска антивируса Microsoft Defender используйте cmdlets PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Cmdlets Defender](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a>Использование инструкции по управлению Windows (WMI) для управления расположением обновления

Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

Дополнительные сведения см. в следующих статьях:
- [Защитник Windows API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a>Управление мобильными устройствами (MDM) для управления расположением обновления

Сведения о настройке MDM см. в материале [Policy CSP - Defender/SignatureUpdateFallbackOrder.](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder)

## <a name="what-if-were-using-a-third-party-vendor"></a>Что делать, если мы используем сторонного поставщика?

В этой статье описывается настройка и управление обновлениями антивируса Microsoft Defender. Однако для выполнения этих задач можно использовать сторонних поставщиков. 

Например, предположим, что Contoso наняла Fabrikam для управления решением безопасности, которое включает антивирус Microsoft Defender. Fabrikam обычно использует [средства управления Windows,](./use-wmi-microsoft-defender-antivirus.md) [командлеты PowerShell](./use-powershell-cmdlets-microsoft-defender-antivirus.md)или [командную](./command-line-arguments-microsoft-defender-antivirus.md) строку Windows для развертывания исправлений и обновлений. 

> [!NOTE]
> Корпорация Майкрософт не тестировать сторонние решения для управления антивирусом Microsoft Defender.

<a id="unc-share"></a>
## <a name="create-a-unc-share-for-security-intelligence-updates"></a>Создание доли UNC для обновлений сведений о безопасности

Настройка доли сетевых файлов (unC/mapped drive) для загрузки обновлений аналитики безопасности с сайта MMPC с помощью запланированной задачи.

1. В системе, в которой необходимо создать долю и скачать обновления, создайте папку, в которой будет сохраняться скрипт.
    ```DOS
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. Создайте папку, в которой будут сохраняться обновления подписей.
    ```DOS
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. Скачайте сценарий PowerShell из [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4).

4. Нажмите **кнопку Ручная загрузка**.

5. Нажмите **кнопку Скачать необработанные файлы nupkg**.

6. Извлечение файла.

7. Скопируйте файл SignatureDownloadCustomTask.ps1 в ранее созданную папку C:\Tool\PS-Scripts\.

8. Чтобы настроить запланированную задачу, используйте командную строку.
    > [!NOTE]
    > Существует два типа обновлений: полный и дельта.
   - Для дельты x64:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - Для полного x64:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - Для дельты x86:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - Для полного x86:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

    > [!NOTE]
    > После создания запланированных задач их можно найти в план-графике задач в Microsoft\Windows\Защитник Windows
9. Запустите каждую задачу вручную и убедитесь, что у вас есть данные (mpam-d.exe, mpam-fe.exe и nis_full.exe) в следующих папках (возможно, вы выбрали различные расположения):

   - C:\Temp\TempSigs\x86
   - C:\Temp\TempSigs\x64

   Если запланированная задача сбой, запустите следующие команды:

    ```DOS
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86″
    ```
    > [!NOTE]
    > Проблемы также могут быть вызваны политикой выполнения.
    
10. Создайте акцию, указывав на C:\Temp\TempSigs (например, \\ сервер\обновления).
    > [!NOTE]
    > По крайней мере, пользователи с проверкой подлинности должны иметь доступ к "Чтение".
11. Установите расположение доли в политике для этой доли.

    > [!NOTE]
    > Не добавляйте папку x64 (или x86) в путь. Процесс mpcmdrun.exe добавляет его автоматически.

## <a name="related-articles"></a>Статьи по теме

- [Развертывание антивируса Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
- [Управление обновлениями антивируса Microsoft Defender и применение базовых показателей](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Управление обновлениями для устарели конечных точек](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Управление принудительными обновлениями на основе событий](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Управление обновлениями для мобильных устройств и VMs](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)