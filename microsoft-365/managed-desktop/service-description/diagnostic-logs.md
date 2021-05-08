---
title: Журналы диагностики
description: Журналы, которые могут быть собраны с устройств во время устранения неполадок и их хранения
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ef7d19fef989610c10323c2a9820a5314d5e1641
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272899"
---
# <a name="diagnostic-logs"></a>Журналы диагностики

При устранении неполадок на устройстве, управляемом компьютеры, управляемые Майкрософт, независимо от того, сообщили вы или определили службой, нам может потребоваться собирать определенные диагностические журналы с устройства без вмешательства пользователя. Мы не собираем контент или сведения, созданные пользователем, из каталогов пользователей. Мы собираем только диагностические и журнальные данные, которые касаются состояния и состояния устройства.

Мы храним все собранные журналы в течение 28 дней и удаляем их. Мы обработчики журналов, собранных с устройства, следуя нашим стандартам [обработки данных.](privacy-personal-data.md)

## <a name="data-collected"></a>Собранные данные

Этот список включает все папки, журналы событий, исполняемые или места реестра, из компьютеры, управляемые Майкрософт могут собирать диагностические журналы. Фактически собранные данные будут подмножество этого списка и зависит от выявленной проблемы.

### <a name="registry-keys"></a>Разделы реестра

- HKLM \\ SYSTEM \\ CurrentControlSet \\ Services
- HKLM \\ SOFTWARE \\ Microsoft \\ Surface
- Политики \\ программного обеспечения \\ HKLM Microsoft \\ Windows \\ \\ WindowsUpdate
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ MUI \\ UILanguages
- Политики программного обеспечения HKLM \\ \\ Microsoft \\ \\ WindowsStore
- HKLM \\ Software Microsoft Windows \\ \\ \\ \\ CurrentVersion WindowsStore \\ WindowsUpdate
- HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion
- HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ AppModel
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ FirmwareResources
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsUpdate
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ Appx
- HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion \\ Superfetch
- Установка системы \\ HKLM \\
- HKLM \\ Software \\ Microsoft \\ IntuneManagementExtension
- HKLM \\ SOFTWARE \\ Microsoft \\ SystemCertificates \\ AuthRoot
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ advanced Threat Protection
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ Authentication \\ LogonUI
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion Internet \\ Параметры
- HKLM \\ Software Microsoft Windows \\ \\ \\ CurrentVersion \\ Uninstall
- Политики \\ программного обеспечения HKLM \\
- Политики \\ программного обеспечения \\ HKLM Microsoft \\ \\ Cryptography \\ Configuration \\ SSL
- Политики \\ программного обеспечения \\ HKLM Microsoft \\ Windows \\ advanced Threat Protection
- HKLM \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion \\ Uninstall
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL

### <a name="commands"></a>Команды

- %programfiles% \\ защитник \\ windowsmpcmdrun.exe-GetFiles
- %windir% \\ system32 \\certutil.exe-store
- %windir% \\ system32 \\certutil.exe-store-user my
- %windir% \\ system32 \\Dsregcmd.exe/status
- %windir% \\ system32 \\ipconfig.exe /all
- %windir% \\ system32 \\ipconfig.exe /displaydns
- %windir% \\ system32 \\mdmdiagnosticstool.exe
- %windir% \\ \\ system32msinfo32.exe /report %temp% \\ MDMDiagnostics \\ msinfo32.log
- %windir% \\ system32 \\netsh.exe advfirewall show allprofiles
- %windir% \\ system32 \\netsh.exe advfirewall show global
- %windir% \\ system32 \\netsh.exe lan show profiles
- %windir% \\ system32 \\netsh.exe winhttp show proxy
- %windir% \\ system32 \\netsh.exe wlan show profiles
- %windir% \\ system32 \\netsh.exe wlan show wlanreport
- %windir% \\ system32 \\ping.exe -n 50 localhost
- %windir% \\ \\ system32powercfg.exe/batteryreport/output %temp% \\ MDMDiagnostics \\battery-report.html
- %windir% \\ \\ system32powercfg.exe /energy/output %temp% \\ MDMDiagnostics \\energy-report.html
- bitsadmin /list /allusers/verbose
- fltMC.exe
- bcdedit /enum all /v
- manage-bde-protectors-get
- Windows PowerShell команд:
    - Allusers Get-appxpackage
    - Пакет Get-appxpackage-packagetype
    - Get-Service wuauserv
    - Get-NetFirewallRule
    - Get-WmiObject-Class \_ win32
    - Get-ComputerInfo
    - Get-Service
    - Get-Process
    - Get-WmiObject Win32 \_ PnPSignedDriver

### <a name="event-logs"></a>Журналы событий

- Для приложений
- Microsoft-Windows-AppLocker/EXE и DLL
- Microsoft-Windows-AppLocker/MSI и script
- Microsoft-Windows-AppLocker/Packaged app-Deployment
- Microsoft-Windows-AppLocker/Packaged app-Execution
- Управление microsoft-Windows-Bitlocker/Bitlocker
- Microsoft-Windows-SENSE/Operational
- Microsoft-Windows-SenseIR/Operational
- Настройка
- Системные

### <a name="files"></a>Файлы

- %ProgramData% \\ Сборщики Microsoft \\ DiagnosticLogCSP \\ \\ \* .etl
- %ProgramData% \\ Журналы \\ Microsoft IntuneManagementExtension \\ \\ \* .\*
- %ProgramData% \\ Microsoft Защитник Windows поддержка \\ \\ \\MpSupportFiles.cab
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReport \\wlan-report-latest.html
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReport-SourceFileName wlan-report-latest.html
- %windir% \\ ccm \\ \* logs .log
- %windir% \\ ccmsetup \\ log \* .log
- %windir% \\ \\ журналы CBS \\ cbs.log
- %windir% \\ logs \\ measuredboot \* .\*
- %windir% \\ Logs \\ WindowsUpdate \* .etl
- %windir% \\ inf \\ \* .log
- %windir% \\ \\ сеансы обслуживания \\ActionList.xml
- %windir% \\ \\ сеансы обслуживания \\Sessions.xml
- %windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log
- %windir% \\ SoftwareDistribution \\ \\ DataStore DataStore.edb
- %windir% \\ logs \\ dism \\ dism.log
- %SystemRoot% \\ System32 \\ Winevt \\ Logs\\
- %appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .blog
- %appdata% \\ Microsoft \\ Teams \\ skylib \\ \* .blog
- %appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .etl
- %appdata% \\ Microsoft \\ Teams \\logs.txt
- %windir% \\ Windows \\ System32 \\ winevt \\ \* .\*