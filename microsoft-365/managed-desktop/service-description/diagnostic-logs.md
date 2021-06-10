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
# <a name="diagnostic-logs"></a><span data-ttu-id="d0e40-104">Журналы диагностики</span><span class="sxs-lookup"><span data-stu-id="d0e40-104">Diagnostic logs</span></span>

<span data-ttu-id="d0e40-105">При устранении неполадок на устройстве, управляемом компьютеры, управляемые Майкрософт, независимо от того, сообщили вы или определили службой, нам может потребоваться собирать определенные диагностические журналы с устройства без вмешательства пользователя.</span><span class="sxs-lookup"><span data-stu-id="d0e40-105">When we troubleshoot an issue on a device managed by Microsoft Managed Desktop, whether one you've reported or one identified by our service, we might have to collect certain diagnostic logs from the device without intervention from the user.</span></span> <span data-ttu-id="d0e40-106">Мы не собираем контент или сведения, созданные пользователем, из каталогов пользователей.</span><span class="sxs-lookup"><span data-stu-id="d0e40-106">We don't collect any user-generated content or information from user directories.</span></span> <span data-ttu-id="d0e40-107">Мы собираем только диагностические и журнальные данные, которые касаются состояния и состояния устройства.</span><span class="sxs-lookup"><span data-stu-id="d0e40-107">We only collect diagnostic and log data that concerns device health and status.</span></span>

<span data-ttu-id="d0e40-108">Мы храним все собранные журналы в течение 28 дней и удаляем их.</span><span class="sxs-lookup"><span data-stu-id="d0e40-108">We store any collected logs for 28 days, and then delete them.</span></span> <span data-ttu-id="d0e40-109">Мы обработчики журналов, собранных с устройства, следуя нашим стандартам [обработки данных.](privacy-personal-data.md)</span><span class="sxs-lookup"><span data-stu-id="d0e40-109">We process any logs collected from a device following our [data handling standards](privacy-personal-data.md).</span></span>

## <a name="data-collected"></a><span data-ttu-id="d0e40-110">Собранные данные</span><span class="sxs-lookup"><span data-stu-id="d0e40-110">Data collected</span></span>

<span data-ttu-id="d0e40-111">Этот список включает все папки, журналы событий, исполняемые или места реестра, из компьютеры, управляемые Майкрософт могут собирать диагностические журналы.</span><span class="sxs-lookup"><span data-stu-id="d0e40-111">This list includes all the folders, event logs, executables, or registry locations that Microsoft Managed Desktop might collect diagnostic logs from.</span></span> <span data-ttu-id="d0e40-112">Фактически собранные данные будут подмножество этого списка и зависит от выявленной проблемы.</span><span class="sxs-lookup"><span data-stu-id="d0e40-112">The actual data collected will be a subset of this list and depends on the identified issue.</span></span>

### <a name="registry-keys"></a><span data-ttu-id="d0e40-113">Разделы реестра</span><span class="sxs-lookup"><span data-stu-id="d0e40-113">Registry keys</span></span>

- <span data-ttu-id="d0e40-114">HKLM \\ SYSTEM \\ CurrentControlSet \\ Services</span><span class="sxs-lookup"><span data-stu-id="d0e40-114">HKLM\\SYSTEM\\CurrentControlSet\\Services</span></span>
- <span data-ttu-id="d0e40-115">HKLM \\ SOFTWARE \\ Microsoft \\ Surface</span><span class="sxs-lookup"><span data-stu-id="d0e40-115">HKLM\\SOFTWARE\\Microsoft\\Surface</span></span>
- <span data-ttu-id="d0e40-116">Политики \\ программного обеспечения \\ HKLM Microsoft \\ Windows \\ \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="d0e40-116">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate</span></span>
- <span data-ttu-id="d0e40-117">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ MUI \\ UILanguages</span><span class="sxs-lookup"><span data-stu-id="d0e40-117">HKLM\\SYSTEM\\CurrentControlSet\\Control\\MUI\\UILanguages</span></span>
- <span data-ttu-id="d0e40-118">Политики программного обеспечения HKLM \\ \\ Microsoft \\ \\ WindowsStore</span><span class="sxs-lookup"><span data-stu-id="d0e40-118">HKLM\\Software\\Policies\\Microsoft\\WindowsStore</span></span>
- <span data-ttu-id="d0e40-119">HKLM \\ Software Microsoft Windows \\ \\ \\ \\ CurrentVersion WindowsStore \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="d0e40-119">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\WindowsStore\\WindowsUpdate</span></span>
- <span data-ttu-id="d0e40-120">HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="d0e40-120">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="d0e40-121">HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="d0e40-121">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="d0e40-122">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ AppModel</span><span class="sxs-lookup"><span data-stu-id="d0e40-122">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel</span></span>
- <span data-ttu-id="d0e40-123">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ FirmwareResources</span><span class="sxs-lookup"><span data-stu-id="d0e40-123">HKLM\\SYSTEM\\CurrentControlSet\\Control\\FirmwareResources</span></span>
- <span data-ttu-id="d0e40-124">HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost</span><span class="sxs-lookup"><span data-stu-id="d0e40-124">HKLM\\SOFTWARE\\Microsoft\\WindowsSelfhost</span></span>
- <span data-ttu-id="d0e40-125">HKLM \\ SOFTWARE \\ Microsoft \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="d0e40-125">HKLM\\SOFTWARE\\Microsoft\\WindowsUpdate</span></span>
- <span data-ttu-id="d0e40-126">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ Appx</span><span class="sxs-lookup"><span data-stu-id="d0e40-126">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Appx</span></span>
- <span data-ttu-id="d0e40-127">HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion \\ Superfetch</span><span class="sxs-lookup"><span data-stu-id="d0e40-127">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Superfetch</span></span>
- <span data-ttu-id="d0e40-128">Установка системы \\ HKLM \\</span><span class="sxs-lookup"><span data-stu-id="d0e40-128">HKLM\\SYSTEM\\Setup</span></span>
- <span data-ttu-id="d0e40-129">HKLM \\ Software \\ Microsoft \\ IntuneManagementExtension</span><span class="sxs-lookup"><span data-stu-id="d0e40-129">HKLM\\Software\\Microsoft\\IntuneManagementExtension</span></span>
- <span data-ttu-id="d0e40-130">HKLM \\ SOFTWARE \\ Microsoft \\ SystemCertificates \\ AuthRoot</span><span class="sxs-lookup"><span data-stu-id="d0e40-130">HKLM\\SOFTWARE\\Microsoft\\SystemCertificates\\AuthRoot</span></span>
- <span data-ttu-id="d0e40-131">HKLM \\ SOFTWARE Microsoft Windows \\ \\ advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d0e40-131">HKLM\\SOFTWARE\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="d0e40-132">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ Authentication \\ LogonUI</span><span class="sxs-lookup"><span data-stu-id="d0e40-132">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI</span></span>
- <span data-ttu-id="d0e40-133">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion Internet \\ Параметры</span><span class="sxs-lookup"><span data-stu-id="d0e40-133">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings</span></span>
- <span data-ttu-id="d0e40-134">HKLM \\ Software Microsoft Windows \\ \\ \\ CurrentVersion \\ Uninstall</span><span class="sxs-lookup"><span data-stu-id="d0e40-134">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="d0e40-135">Политики \\ программного обеспечения HKLM \\</span><span class="sxs-lookup"><span data-stu-id="d0e40-135">HKLM\\Software\\Policies</span></span>
- <span data-ttu-id="d0e40-136">Политики \\ программного обеспечения \\ HKLM Microsoft \\ \\ Cryptography \\ Configuration \\ SSL</span><span class="sxs-lookup"><span data-stu-id="d0e40-136">HKLM\\SOFTWARE\\Policies\\Microsoft\\Cryptography\\Configuration\\SSL</span></span>
- <span data-ttu-id="d0e40-137">Политики \\ программного обеспечения \\ HKLM Microsoft \\ Windows \\ advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d0e40-137">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="d0e40-138">HKLM \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion \\ Uninstall</span><span class="sxs-lookup"><span data-stu-id="d0e40-138">HKLM\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="d0e40-139">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL</span><span class="sxs-lookup"><span data-stu-id="d0e40-139">HKLM\\SYSTEM\\CurrentControlSet\\Control\\SecurityProviders\\SCHANNEL</span></span>

### <a name="commands"></a><span data-ttu-id="d0e40-140">Команды</span><span class="sxs-lookup"><span data-stu-id="d0e40-140">Commands</span></span>

- <span data-ttu-id="d0e40-141">%programfiles% \\ защитник \\ windowsmpcmdrun.exe-GetFiles</span><span class="sxs-lookup"><span data-stu-id="d0e40-141">%programfiles%\\windows defender\\mpcmdrun.exe -GetFiles</span></span>
- <span data-ttu-id="d0e40-142">%windir% \\ system32 \\certutil.exe-store</span><span class="sxs-lookup"><span data-stu-id="d0e40-142">%windir%\\system32\\certutil.exe -store</span></span>
- <span data-ttu-id="d0e40-143">%windir% \\ system32 \\certutil.exe-store-user my</span><span class="sxs-lookup"><span data-stu-id="d0e40-143">%windir%\\system32\\certutil.exe -store -user my</span></span>
- <span data-ttu-id="d0e40-144">%windir% \\ system32 \\Dsregcmd.exe/status</span><span class="sxs-lookup"><span data-stu-id="d0e40-144">%windir%\\system32\\Dsregcmd.exe /status</span></span>
- <span data-ttu-id="d0e40-145">%windir% \\ system32 \\ipconfig.exe /all</span><span class="sxs-lookup"><span data-stu-id="d0e40-145">%windir%\\system32\\ipconfig.exe /all</span></span>
- <span data-ttu-id="d0e40-146">%windir% \\ system32 \\ipconfig.exe /displaydns</span><span class="sxs-lookup"><span data-stu-id="d0e40-146">%windir%\\system32\\ipconfig.exe /displaydns</span></span>
- <span data-ttu-id="d0e40-147">%windir% \\ system32 \\mdmdiagnosticstool.exe</span><span class="sxs-lookup"><span data-stu-id="d0e40-147">%windir%\\system32\\mdmdiagnosticstool.exe</span></span>
- <span data-ttu-id="d0e40-148">%windir% \\ \\ system32msinfo32.exe /report %temp% \\ MDMDiagnostics \\ msinfo32.log</span><span class="sxs-lookup"><span data-stu-id="d0e40-148">%windir%\\system32\\msinfo32.exe /report %temp%\\MDMDiagnostics\\msinfo32.log</span></span>
- <span data-ttu-id="d0e40-149">%windir% \\ system32 \\netsh.exe advfirewall show allprofiles</span><span class="sxs-lookup"><span data-stu-id="d0e40-149">%windir%\\system32\\netsh.exe advfirewall show allprofiles</span></span>
- <span data-ttu-id="d0e40-150">%windir% \\ system32 \\netsh.exe advfirewall show global</span><span class="sxs-lookup"><span data-stu-id="d0e40-150">%windir%\\system32\\netsh.exe advfirewall show global</span></span>
- <span data-ttu-id="d0e40-151">%windir% \\ system32 \\netsh.exe lan show profiles</span><span class="sxs-lookup"><span data-stu-id="d0e40-151">%windir%\\system32\\netsh.exe lan show profiles</span></span>
- <span data-ttu-id="d0e40-152">%windir% \\ system32 \\netsh.exe winhttp show proxy</span><span class="sxs-lookup"><span data-stu-id="d0e40-152">%windir%\\system32\\netsh.exe winhttp show proxy</span></span>
- <span data-ttu-id="d0e40-153">%windir% \\ system32 \\netsh.exe wlan show profiles</span><span class="sxs-lookup"><span data-stu-id="d0e40-153">%windir%\\system32\\netsh.exe wlan show profiles</span></span>
- <span data-ttu-id="d0e40-154">%windir% \\ system32 \\netsh.exe wlan show wlanreport</span><span class="sxs-lookup"><span data-stu-id="d0e40-154">%windir%\\system32\\netsh.exe wlan show wlanreport</span></span>
- <span data-ttu-id="d0e40-155">%windir% \\ system32 \\ping.exe -n 50 localhost</span><span class="sxs-lookup"><span data-stu-id="d0e40-155">%windir%\\system32\\ping.exe -n 50 localhost</span></span>
- <span data-ttu-id="d0e40-156">%windir% \\ \\ system32powercfg.exe/batteryreport/output %temp% \\ MDMDiagnostics \\battery-report.html</span><span class="sxs-lookup"><span data-stu-id="d0e40-156">%windir%\\system32\\powercfg.exe /batteryreport /output %temp%\\MDMDiagnostics\\battery-report.html</span></span>
- <span data-ttu-id="d0e40-157">%windir% \\ \\ system32powercfg.exe /energy/output %temp% \\ MDMDiagnostics \\energy-report.html</span><span class="sxs-lookup"><span data-stu-id="d0e40-157">%windir%\\system32\\powercfg.exe /energy /output %temp%\\MDMDiagnostics\\energy-report.html</span></span>
- <span data-ttu-id="d0e40-158">bitsadmin /list /allusers/verbose</span><span class="sxs-lookup"><span data-stu-id="d0e40-158">bitsadmin /list /allusers /verbose</span></span>
- <span data-ttu-id="d0e40-159">fltMC.exe</span><span class="sxs-lookup"><span data-stu-id="d0e40-159">fltMC.exe</span></span>
- <span data-ttu-id="d0e40-160">bcdedit /enum all /v</span><span class="sxs-lookup"><span data-stu-id="d0e40-160">bcdedit /enum all /v</span></span>
- <span data-ttu-id="d0e40-161">manage-bde-protectors-get</span><span class="sxs-lookup"><span data-stu-id="d0e40-161">manage-bde -protectors -get</span></span>
- <span data-ttu-id="d0e40-162">Windows PowerShell команд:</span><span class="sxs-lookup"><span data-stu-id="d0e40-162">Windows PowerShell commands:</span></span>
    - <span data-ttu-id="d0e40-163">Allusers Get-appxpackage</span><span class="sxs-lookup"><span data-stu-id="d0e40-163">Get-appxpackage -allusers</span></span>
    - <span data-ttu-id="d0e40-164">Пакет Get-appxpackage-packagetype</span><span class="sxs-lookup"><span data-stu-id="d0e40-164">Get-appxpackage -packagetype bundle</span></span>
    - <span data-ttu-id="d0e40-165">Get-Service wuauserv</span><span class="sxs-lookup"><span data-stu-id="d0e40-165">Get-Service wuauserv</span></span>
    - <span data-ttu-id="d0e40-166">Get-NetFirewallRule</span><span class="sxs-lookup"><span data-stu-id="d0e40-166">Get-NetFirewallRule</span></span>
    - <span data-ttu-id="d0e40-167">Get-WmiObject-Class \_ win32</span><span class="sxs-lookup"><span data-stu-id="d0e40-167">Get-WmiObject -Class win32\_product</span></span>
    - <span data-ttu-id="d0e40-168">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="d0e40-168">Get-ComputerInfo</span></span>
    - <span data-ttu-id="d0e40-169">Get-Service</span><span class="sxs-lookup"><span data-stu-id="d0e40-169">Get-Service</span></span>
    - <span data-ttu-id="d0e40-170">Get-Process</span><span class="sxs-lookup"><span data-stu-id="d0e40-170">Get-Process</span></span>
    - <span data-ttu-id="d0e40-171">Get-WmiObject Win32 \_ PnPSignedDriver</span><span class="sxs-lookup"><span data-stu-id="d0e40-171">Get-WmiObject Win32\_PnPSignedDriver</span></span>

### <a name="event-logs"></a><span data-ttu-id="d0e40-172">Журналы событий</span><span class="sxs-lookup"><span data-stu-id="d0e40-172">Event logs</span></span>

- <span data-ttu-id="d0e40-173">Приложение</span><span class="sxs-lookup"><span data-stu-id="d0e40-173">Application</span></span>
- <span data-ttu-id="d0e40-174">Microsoft-Windows-AppLocker/EXE и DLL</span><span class="sxs-lookup"><span data-stu-id="d0e40-174">Microsoft-Windows-AppLocker/EXE and DLL</span></span>
- <span data-ttu-id="d0e40-175">Microsoft-Windows-AppLocker/MSI и script</span><span class="sxs-lookup"><span data-stu-id="d0e40-175">Microsoft-Windows-AppLocker/MSI and Script</span></span>
- <span data-ttu-id="d0e40-176">Microsoft-Windows-AppLocker/Packaged app-Deployment</span><span class="sxs-lookup"><span data-stu-id="d0e40-176">Microsoft-Windows-AppLocker/Packaged app-Deployment</span></span>
- <span data-ttu-id="d0e40-177">Microsoft-Windows-AppLocker/Packaged app-Execution</span><span class="sxs-lookup"><span data-stu-id="d0e40-177">Microsoft-Windows-AppLocker/Packaged app-Execution</span></span>
- <span data-ttu-id="d0e40-178">Управление microsoft-Windows-Bitlocker/Bitlocker</span><span class="sxs-lookup"><span data-stu-id="d0e40-178">Microsoft-Windows-Bitlocker/Bitlocker Management</span></span>
- <span data-ttu-id="d0e40-179">Microsoft-Windows-SENSE/Operational</span><span class="sxs-lookup"><span data-stu-id="d0e40-179">Microsoft-Windows-SENSE/Operational</span></span>
- <span data-ttu-id="d0e40-180">Microsoft-Windows-SenseIR/Operational</span><span class="sxs-lookup"><span data-stu-id="d0e40-180">Microsoft-Windows-SenseIR/Operational</span></span>
- <span data-ttu-id="d0e40-181">Настройка</span><span class="sxs-lookup"><span data-stu-id="d0e40-181">Setup</span></span>
- <span data-ttu-id="d0e40-182">Системные</span><span class="sxs-lookup"><span data-stu-id="d0e40-182">System</span></span>

### <a name="files"></a><span data-ttu-id="d0e40-183">Файлы</span><span class="sxs-lookup"><span data-stu-id="d0e40-183">Files</span></span>

- <span data-ttu-id="d0e40-184">%ProgramData% \\ Сборщики Microsoft \\ DiagnosticLogCSP \\ \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="d0e40-184">%ProgramData%\\Microsoft\\DiagnosticLogCSP\\Collectors\\\*.etl</span></span>
- <span data-ttu-id="d0e40-185">%ProgramData% \\ Журналы \\ Microsoft IntuneManagementExtension \\ \\ \* .\*</span><span class="sxs-lookup"><span data-stu-id="d0e40-185">%ProgramData%\\Microsoft\\IntuneManagementExtension\\Logs\\\*.\*</span></span>
- <span data-ttu-id="d0e40-186">%ProgramData% \\ Microsoft Защитник Windows поддержка \\ \\ \\MpSupportFiles.cab</span><span class="sxs-lookup"><span data-stu-id="d0e40-186">%ProgramData%\\Microsoft\\Windows Defender\\Support\\MpSupportFiles.cab</span></span>
- <span data-ttu-id="d0e40-187">%ProgramData% \\ Microsoft \\ Windows \\ WlanReport \\wlan-report-latest.html</span><span class="sxs-lookup"><span data-stu-id="d0e40-187">%ProgramData%\\Microsoft\\Windows\\WlanReport\\wlan-report-latest.html</span></span>
- <span data-ttu-id="d0e40-188">%ProgramData% \\ Microsoft \\ Windows \\ WlanReport-SourceFileName wlan-report-latest.html</span><span class="sxs-lookup"><span data-stu-id="d0e40-188">%ProgramData%\\Microsoft\\Windows\\WlanReport -SourceFileName wlan-report-latest.html</span></span>
- <span data-ttu-id="d0e40-189">%windir% \\ ccm \\ \* logs .log</span><span class="sxs-lookup"><span data-stu-id="d0e40-189">%windir%\\ccm\\logs\*.log</span></span>
- <span data-ttu-id="d0e40-190">%windir% \\ ccmsetup \\ log \* .log</span><span class="sxs-lookup"><span data-stu-id="d0e40-190">%windir%\\ccmsetup\\logs\*.log</span></span>
- <span data-ttu-id="d0e40-191">%windir% \\ \\ журналы CBS \\ cbs.log</span><span class="sxs-lookup"><span data-stu-id="d0e40-191">%windir%\\logs\\CBS\\cbs.log</span></span>
- <span data-ttu-id="d0e40-192">%windir% \\ logs \\ measuredboot \* .\*</span><span class="sxs-lookup"><span data-stu-id="d0e40-192">%windir%\\logs\\measuredboot\*.\*</span></span>
- <span data-ttu-id="d0e40-193">%windir% \\ Logs \\ WindowsUpdate \* .etl</span><span class="sxs-lookup"><span data-stu-id="d0e40-193">%windir%\\Logs\\WindowsUpdate\*.etl</span></span>
- <span data-ttu-id="d0e40-194">%windir% \\ inf \\ \* .log</span><span class="sxs-lookup"><span data-stu-id="d0e40-194">%windir%\\inf\\\*.log</span></span>
- <span data-ttu-id="d0e40-195">%windir% \\ \\ сеансы обслуживания \\ActionList.xml</span><span class="sxs-lookup"><span data-stu-id="d0e40-195">%windir%\\servicing\\sessions\\ActionList.xml</span></span>
- <span data-ttu-id="d0e40-196">%windir% \\ \\ сеансы обслуживания \\Sessions.xml</span><span class="sxs-lookup"><span data-stu-id="d0e40-196">%windir%\\servicing\\sessions\\Sessions.xml</span></span>
- <span data-ttu-id="d0e40-197">%windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log</span><span class="sxs-lookup"><span data-stu-id="d0e40-197">%windir%\\SoftwareDistribution\\DataStore\\Logs\\edb.log</span></span>
- <span data-ttu-id="d0e40-198">%windir% \\ SoftwareDistribution \\ \\ DataStore DataStore.edb</span><span class="sxs-lookup"><span data-stu-id="d0e40-198">%windir%\\SoftwareDistribution\\DataStore\\DataStore.edb</span></span>
- <span data-ttu-id="d0e40-199">%windir% \\ logs \\ dism \\ dism.log</span><span class="sxs-lookup"><span data-stu-id="d0e40-199">%windir%\\logs\\dism\\dism.log</span></span>
- <span data-ttu-id="d0e40-200">%SystemRoot% \\ System32 \\ Winevt \\ Logs</span><span class="sxs-lookup"><span data-stu-id="d0e40-200">%SystemRoot%\\System32\\Winevt\\Logs</span></span>\\
- <span data-ttu-id="d0e40-201">%appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .blog</span><span class="sxs-lookup"><span data-stu-id="d0e40-201">%appdata%\\Microsoft\\Teams\\media-stack\\\*.blog</span></span>
- <span data-ttu-id="d0e40-202">%appdata% \\ Microsoft \\ Teams \\ skylib \\ \* .blog</span><span class="sxs-lookup"><span data-stu-id="d0e40-202">%appdata%\\Microsoft\\Teams\\skylib\\\*.blog</span></span>
- <span data-ttu-id="d0e40-203">%appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="d0e40-203">%appdata%\\Microsoft\\Teams\\media-stack\\\*.etl</span></span>
- <span data-ttu-id="d0e40-204">%appdata% \\ Microsoft \\ Teams \\logs.txt</span><span class="sxs-lookup"><span data-stu-id="d0e40-204">%appdata%\\Microsoft\\Teams\\logs.txt</span></span>
- <span data-ttu-id="d0e40-205">%windir% \\ Windows \\ System32 \\ winevt \\ \* .\*</span><span class="sxs-lookup"><span data-stu-id="d0e40-205">%windir%\\Windows\\System32\\winevt\\\*.\*</span></span>