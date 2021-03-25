---
title: Управление Microsoft Defender для конечной точки с помощью PowerShell, WMI и MPCmdRun.exe
description: Узнайте, как управлять Microsoft Defender для конечной точки с помощью PowerShell, WMI и MPCmdRun.exe
keywords: после миграции, управления, операций, обслуживания, использования, PowerShell, WMI, MPCmdRun.exe, защита от угроз защитника Windows, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 5f0e94360cfaa0c66aedec400e81adc85f4f5450
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185877"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a><span data-ttu-id="ebd3b-104">Управление Microsoft Defender для конечной точки с помощью PowerShell, WMI и MPCmdRun.exe</span><span class="sxs-lookup"><span data-stu-id="ebd3b-104">Manage Microsoft Defender for Endpoint with PowerShell, WMI, and MPCmdRun.exe</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ebd3b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ebd3b-105">**Applies to:**</span></span>
- [<span data-ttu-id="ebd3b-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ebd3b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ebd3b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ebd3b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ebd3b-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ebd3b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ebd3b-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> <span data-ttu-id="ebd3b-110">Мы рекомендуем использовать [Microsoft Endpoint Manager](https://docs.microsoft.com/mem) для управления функциями защиты от угроз для устройств (также именуемой конечными точками).</span><span class="sxs-lookup"><span data-stu-id="ebd3b-110">We recommend using [Microsoft Endpoint Manager](https://docs.microsoft.com/mem) to manage your organization's threat protection features for devices (also referred to as endpoints).</span></span> <span data-ttu-id="ebd3b-111">Endpoint Manager включает [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) и [Microsoft Endpoint Configuration Manager.](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)</span><span class="sxs-lookup"><span data-stu-id="ebd3b-111">Endpoint Manager includes [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span></span> 
> - [<span data-ttu-id="ebd3b-112">Дополнительные дополнительные информацию о диспетчере конечных точек</span><span class="sxs-lookup"><span data-stu-id="ebd3b-112">Learn more about Endpoint Manager</span></span>](https://docs.microsoft.com/mem/endpoint-manager-overview)
> - [<span data-ttu-id="ebd3b-113">Совместное управление Microsoft Defender для конечной точки на устройствах Windows 10 с помощью configuration Manager и Intune</span><span class="sxs-lookup"><span data-stu-id="ebd3b-113">Co-manage Microsoft Defender for Endpoint on Windows 10 devices with Configuration Manager and Intune</span></span>](manage-atp-post-migration-intune.md)
> - [<span data-ttu-id="ebd3b-114">Управление microsoft Defender для конечной точки с помощью Intune</span><span class="sxs-lookup"><span data-stu-id="ebd3b-114">Manage Microsoft Defender for Endpoint with Intune</span></span>](manage-atp-post-migration-intune.md) 

<span data-ttu-id="ebd3b-115">Вы можете управлять некоторыми антивирусными настройками Microsoft Defender на устройствах [с powerShell,](#configure-microsoft-defender-for-endpoint-with-powershell) [инструментами](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) управления Windows (WMI) и командной строкой microsoft [Malware Protection (MPCmdRun.exe).](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe)</span><span class="sxs-lookup"><span data-stu-id="ebd3b-115">You can manage some Microsoft Defender Antivirus settings on devices with [PowerShell](#configure-microsoft-defender-for-endpoint-with-powershell),  [Windows Management Instrumentation](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) (WMI), and the [Microsoft Malware Protection Command Line Utility](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) (MPCmdRun.exe).</span></span> <span data-ttu-id="ebd3b-116">Например, можно управлять некоторыми антивирусными настройками Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-116">For example, you can manage some Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="ebd3b-117">В некоторых случаях можно настроить правила уменьшения поверхности атаки и использовать параметры защиты.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-117">And, in some cases, you can customize your attack surface reduction rules and exploit protection settings.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ebd3b-118">Функции защиты от угроз, настроенные с помощью PowerShell, WMI или MCPmdRun.exe, можно перезаписать с помощью параметров конфигурации, развернутых с помощью Intune или Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-118">Threat protection features that you configure by using PowerShell, WMI, or MCPmdRun.exe can be overwritten by configuration settings that are deployed with Intune or Configuration Manager.</span></span>

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a><span data-ttu-id="ebd3b-119">Настройка Microsoft Defender для конечной точки с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebd3b-119">Configure Microsoft Defender for Endpoint with PowerShell</span></span>

<span data-ttu-id="ebd3b-120">С помощью PowerShell можно управлять антивирусом Microsoft Defender, использовать защиту и правила уменьшения поверхности атак.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-120">You can use PowerShell to manage Microsoft Defender Antivirus, exploit protection, and your attack surface reduction rules.</span></span>

|<span data-ttu-id="ebd3b-121">Задача</span><span class="sxs-lookup"><span data-stu-id="ebd3b-121">Task</span></span>  |<span data-ttu-id="ebd3b-122">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ebd3b-122">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="ebd3b-123">**Управление антивирусной программой Microsoft Defender**</span><span class="sxs-lookup"><span data-stu-id="ebd3b-123">**Manage Microsoft Defender Antivirus**</span></span> <br/><br/><span data-ttu-id="ebd3b-124">*Просмотр состояния защиты от антивирусных программ, настройка предпочтений для & обновлений и внесение других изменений в антивирусную защиту.*</span><span class="sxs-lookup"><span data-stu-id="ebd3b-124">*View status of antimalware protection, configure preferences for antivirus scans & updates, and make other changes to your antivirus protection.*</span></span>    |[<span data-ttu-id="ebd3b-125">Используйте cmdlets PowerShell для настройки и управления антивирусом Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ebd3b-125">Use PowerShell cmdlets to configure and manage Microsoft Defender Antivirus</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus)  <br/><br/>[<span data-ttu-id="ebd3b-126">Использование cmdlets PowerShell для обеспечения облачной защиты</span><span class="sxs-lookup"><span data-stu-id="ebd3b-126">Use PowerShell cmdlets to enable cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)       |
|<span data-ttu-id="ebd3b-127">**Настройка защиты от эксплойтов** для смягчения угроз на устройствах организации</span><span class="sxs-lookup"><span data-stu-id="ebd3b-127">**Configure exploit protection** to mitigate threats on your organization's devices</span></span><br/><br/> <span data-ttu-id="ebd3b-128">*Рекомендуется сначала использовать защиту от [эксплойтов в режиме](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) аудита. Таким образом можно увидеть, как защита от эксплойтов влияет на приложения, которые использует ваша организация.*</span><span class="sxs-lookup"><span data-stu-id="ebd3b-128">*We recommend using exploit protection in [audit mode](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) at first. That way, you can see how exploit protection affects apps your organization is using.*</span></span>     | [<span data-ttu-id="ebd3b-129">Настройка защиты от эксплойтов</span><span class="sxs-lookup"><span data-stu-id="ebd3b-129">Customize exploit protection</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection)<br/><br/>[<span data-ttu-id="ebd3b-130">Cmdlets PowerShell для защиты от эксплойтов</span><span class="sxs-lookup"><span data-stu-id="ebd3b-130">PowerShell cmdlets for exploit protection</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)        |
|<span data-ttu-id="ebd3b-131">**Настройка правил уменьшения поверхности атаки** с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebd3b-131">**Configure attack surface reduction rules** with PowerShell</span></span> <br/><br/><span data-ttu-id="ebd3b-132">*Вы можете использовать PowerShell, чтобы исключить файлы и папки из правил уменьшения поверхности атаки.*</span><span class="sxs-lookup"><span data-stu-id="ebd3b-132">*You can use PowerShell to exclude files and folders from attack surface reduction rules.*</span></span> |[<span data-ttu-id="ebd3b-133">Настройка правил уменьшения поверхности атаки: использование PowerShell для исключения файлов & папок</span><span class="sxs-lookup"><span data-stu-id="ebd3b-133">Customize attack surface reduction rules: Use PowerShell to exclude files & folders</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders)<br/><br/><span data-ttu-id="ebd3b-134">Кроме того, см. в графическом средстве пользовательского интерфейса [António Vasconcelo](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)для установки правил уменьшения поверхности атаки с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-134">Also, see [António Vasconcelo's graphical user interface tool for setting attack surface reduction rules with PowerShell](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI).</span></span> |
|<span data-ttu-id="ebd3b-135">**Включить защиту сети** с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebd3b-135">**Enable Network Protection** with PowerShell</span></span> <br/><br/><span data-ttu-id="ebd3b-136">*Вы можете использовать PowerShell для обеспечения сетевой защиты.*</span><span class="sxs-lookup"><span data-stu-id="ebd3b-136">*You can use PowerShell to enable Network Protection.*</span></span> |[<span data-ttu-id="ebd3b-137">Включив защиту сети с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebd3b-137">Turn on Network Protection with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#powershell) |
|<span data-ttu-id="ebd3b-138">**Настройка управляемого доступа к папкам для** защиты от программ-вымогателей</span><span class="sxs-lookup"><span data-stu-id="ebd3b-138">**Configure controlled folder access** to protect against ransomware</span></span> <br/><br/><span data-ttu-id="ebd3b-139">*[Управляемый доступ к папкам](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) также называется защитой от антивирусных программ.*</span><span class="sxs-lookup"><span data-stu-id="ebd3b-139">*[Controlled folder access](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) is also referred to as antiransomware protection.*</span></span> |[<span data-ttu-id="ebd3b-140">Включить управляемый доступ к папкам с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebd3b-140">Enable controlled folder access with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell) |
|<span data-ttu-id="ebd3b-141">**Настройка брандмауэра Microsoft Defender,** чтобы блокировать несанкционированный сетевой трафик, который втекает на устройства организации или выходит из нее.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-141">**Configure Microsoft Defender Firewall** to block unauthorized network traffic flowing into or out of your organization's devices</span></span> |[<span data-ttu-id="ebd3b-142">Брандмауэр Microsoft Defender с расширенным администрированием безопасности с Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebd3b-142">Microsoft Defender Firewall with Advanced Security Administration using Windows PowerShell</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell) |
|<span data-ttu-id="ebd3b-143">**Настройка шифрования и BitLocker для** защиты информации на устройствах организации под управлением Windows</span><span class="sxs-lookup"><span data-stu-id="ebd3b-143">**Configure encryption and BitLocker** to protect information on your organization's devices running Windows</span></span> |[<span data-ttu-id="ebd3b-144">Справочный справочник BitLocker PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebd3b-144">BitLocker PowerShell reference guide</span></span>](https://docs.microsoft.com/powershell/module/bitlocker/?view=win10-ps&preserve-view=true) |

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a><span data-ttu-id="ebd3b-145">Настройка Microsoft Defender для конечной точки с помощью инструментов управления Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="ebd3b-145">Configure Microsoft Defender for Endpoint with Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="ebd3b-146">WMI — это интерфейс скриптов, который позволяет извлекать, изменять и обновлять параметры.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-146">WMI is a scripting interface that allows you to retrieve, modify, and update settings.</span></span> <span data-ttu-id="ebd3b-147">Дополнительные дополнительные информации см. [в см. в этой ленте Using WMI.](https://docs.microsoft.com/windows/win32/wmisdk/using-wmi)</span><span class="sxs-lookup"><span data-stu-id="ebd3b-147">To learn more, see [Using WMI](https://docs.microsoft.com/windows/win32/wmisdk/using-wmi).</span></span> 

|<span data-ttu-id="ebd3b-148">Задача</span><span class="sxs-lookup"><span data-stu-id="ebd3b-148">Task</span></span>  |<span data-ttu-id="ebd3b-149">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ebd3b-149">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="ebd3b-150">**Включить облачную защиту** на устройстве</span><span class="sxs-lookup"><span data-stu-id="ebd3b-150">**Enable cloud-delivered protection** on a device</span></span>    |[<span data-ttu-id="ebd3b-151">Использование инструкции по управлению Windows (WMI) для обеспечения облачной защиты</span><span class="sxs-lookup"><span data-stu-id="ebd3b-151">Use Windows Management Instruction (WMI) to enable cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)       |
|<span data-ttu-id="ebd3b-152">**Извлечение, изменение и обновление параметров** антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ebd3b-152">**Retrieve, modify, and update settings** for Microsoft Defender Antivirus</span></span>     | [<span data-ttu-id="ebd3b-153">Использование WMI для настройки и управления антивирусом Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ebd3b-153">Use WMI to configure and manage Microsoft Defender Antivirus</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus)<br/><br/>[<span data-ttu-id="ebd3b-154">Просмотрите список доступных классов WMI и сценариев примера</span><span class="sxs-lookup"><span data-stu-id="ebd3b-154">Review the list of available WMI classes and example scripts</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <br/><br/><span data-ttu-id="ebd3b-155">Также см. архивные [Защитник Windows WMIv2 Provider](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)</span><span class="sxs-lookup"><span data-stu-id="ebd3b-155">Also see the archived [Windows Defender WMIv2 Provider reference information](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)</span></span>   |


## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a><span data-ttu-id="ebd3b-156">Настройка Microsoft Defender для конечной точки с помощью microsoft Malware Protection Command-Line Utility (MPCmdRun.exe)</span><span class="sxs-lookup"><span data-stu-id="ebd3b-156">Configure Microsoft Defender for Endpoint with Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe)</span></span>

<span data-ttu-id="ebd3b-157">На отдельном устройстве можно выполнить сканирование, начать диагностику, проверить обновления сведений о безопасности и другие сведения с помощью средства mpcmdrun.exe командной строки.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-157">On an individual device, you can run a scan, start diagnostic tracing, check for security intelligence updates, and more using the mpcmdrun.exe command-line tool.</span></span> <span data-ttu-id="ebd3b-158">Вы можете найти утилиту `%ProgramFiles%\Windows Defender\MpCmdRun.exe` в .</span><span class="sxs-lookup"><span data-stu-id="ebd3b-158">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="ebd3b-159">Запустите его из командной подсказки.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-159">Run it from a command prompt.</span></span>

|<span data-ttu-id="ebd3b-160">Задача</span><span class="sxs-lookup"><span data-stu-id="ebd3b-160">Task</span></span>  |<span data-ttu-id="ebd3b-161">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ebd3b-161">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="ebd3b-162">**Управление антивирусной программой Microsoft Defender**</span><span class="sxs-lookup"><span data-stu-id="ebd3b-162">**Manage Microsoft Defender Antivirus**</span></span>  |[<span data-ttu-id="ebd3b-163">Настройка и управление антивирусом Microsoft Defender с помощью mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="ebd3b-163">Configure and manage Microsoft Defender Antivirus with mpcmdrun.exe</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)        |

## <a name="configure-your-microsoft-defender-security-center"></a><span data-ttu-id="ebd3b-164">Настройка центра безопасности Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ebd3b-164">Configure your Microsoft Defender Security Center</span></span>

<span data-ttu-id="ebd3b-165">Если вы еще этого не сделали, настройте центр безопасности **Microsoft Defender** Для просмотра оповещений, настройки функций защиты от угроз и просмотра подробных сведений об общей позиции безопасности [https://securitycenter.windows.com](https://securitycenter.windows.com) организации.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-165">If you haven't already done so, **configure your Microsoft Defender Security Center** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) to view alerts, configure threat protection features, and view detailed information about your organization's overall security posture.</span></span> 

<span data-ttu-id="ebd3b-166">Вы также можете настроить, можно ли и какие функции конечные пользователи могут видеть в Центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-166">You can also configure whether and what features end users can see in the Microsoft Defender Security Center.</span></span>

- [<span data-ttu-id="ebd3b-167">Обзор Центра безопасности Защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ebd3b-167">Overview of the Microsoft Defender Security Center</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [<span data-ttu-id="ebd3b-168">Защита конечной точки: Центр безопасности Защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ebd3b-168">Endpoint protection: Microsoft Defender Security Center</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)


## <a name="next-steps"></a><span data-ttu-id="ebd3b-169">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="ebd3b-169">Next steps</span></span>

- [<span data-ttu-id="ebd3b-170">Обзор управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="ebd3b-170">Get an overview of threat and vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [<span data-ttu-id="ebd3b-171">Посетите панель мониторинга операций безопасности Центра безопасности Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ebd3b-171">Visit the Microsoft Defender Security Center security operations dashboard</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [<span data-ttu-id="ebd3b-172">Управление microsoft Defender для конечной точки с помощью Intune</span><span class="sxs-lookup"><span data-stu-id="ebd3b-172">Manage Microsoft Defender for Endpoint with Intune</span></span>](manage-atp-post-migration-intune.md)