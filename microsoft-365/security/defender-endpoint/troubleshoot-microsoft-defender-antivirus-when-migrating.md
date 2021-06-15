---
title: Устранение неполадок с антивирусной программой в Microsoft Defender при миграции из сторонного решения
description: Устранение распространенных ошибок при миграции в антивирусная программа в Microsoft Defender
keywords: событие, код ошибки, ведение журнала, устранение неполадок, антивирус защитника Майкрософт, антивирус защитника Windows, миграция
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3eb4d01957383efc8df47e9fee6eb6394c80015a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924387"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a><span data-ttu-id="c800d-104">Устранение неполадок с антивирусной программой в Microsoft Defender при миграции из сторонного решения</span><span class="sxs-lookup"><span data-stu-id="c800d-104">Troubleshoot Microsoft Defender Antivirus while migrating from a third-party solution</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c800d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c800d-105">**Applies to:**</span></span>

- [<span data-ttu-id="c800d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c800d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


<span data-ttu-id="c800d-107">Вы можете найти помощь здесь, если вы столкнулись с проблемой при переходе из сторонного решения безопасности в антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c800d-107">You can find help here if you encounter issues while migrating from a third-party security solution to Microsoft Defender Antivirus.</span></span>

## <a name="review-event-logs"></a><span data-ttu-id="c800d-108">Просмотр журналов событий</span><span class="sxs-lookup"><span data-stu-id="c800d-108">Review event logs</span></span>

<span data-ttu-id="c800d-109">Откройте приложение для просмотра событий, выбрав значок **Поиска** в панели задач и ищите *зрителя событий.*</span><span class="sxs-lookup"><span data-stu-id="c800d-109">Open the Event viewer app by selecting the **Search** icon in the taskbar, and searching for *event viewer*.</span></span>

<span data-ttu-id="c800d-110">Сведения о антивирусная программа в Microsoft Defender можно найти в журналах **приложений** и служб  >  **Microsoft**  >  **Windows**  >  **Защитник Windows.**</span><span class="sxs-lookup"><span data-stu-id="c800d-110">Information about Microsoft Defender Antivirus can be found under  **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender**.</span></span> 

<span data-ttu-id="c800d-111">Оттуда выберите **Открыть под операционной** . </span><span class="sxs-lookup"><span data-stu-id="c800d-111">From there, select **Open** underneath **Operational**.</span></span>

<span data-ttu-id="c800d-112">Выбор события из области сведений позволит вам получить дополнительные сведения о событии в нижней области в вкладке **Общие** и **Подробные** сведения.</span><span class="sxs-lookup"><span data-stu-id="c800d-112">Selecting an event from the details pane will show you more information about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

## <a name="microsoft-defender-antivirus-wont-start"></a><span data-ttu-id="c800d-113">антивирусная программа в Microsoft Defender не начнется</span><span class="sxs-lookup"><span data-stu-id="c800d-113">Microsoft Defender Antivirus won't start</span></span>

<span data-ttu-id="c800d-114">Эта проблема может проявляться в виде нескольких различных ИД событий, все из которых имеют ту же причину.</span><span class="sxs-lookup"><span data-stu-id="c800d-114">This issue can manifest in the form of  several different event IDs, all of which have the same underlying cause.</span></span>

### <a name="associated-event-ids"></a><span data-ttu-id="c800d-115">Связанные ID события</span><span class="sxs-lookup"><span data-stu-id="c800d-115">Associated event IDs</span></span>

 <span data-ttu-id="c800d-116">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c800d-116">Event ID</span></span> | <span data-ttu-id="c800d-117">Имя журнала</span><span class="sxs-lookup"><span data-stu-id="c800d-117">Log name</span></span> | <span data-ttu-id="c800d-118">Описание</span><span class="sxs-lookup"><span data-stu-id="c800d-118">Description</span></span> | <span data-ttu-id="c800d-119">Источник</span><span class="sxs-lookup"><span data-stu-id="c800d-119">Source</span></span>
-|-|-|-
<span data-ttu-id="c800d-120">15</span><span class="sxs-lookup"><span data-stu-id="c800d-120">15</span></span> | <span data-ttu-id="c800d-121">Для приложений</span><span class="sxs-lookup"><span data-stu-id="c800d-121">Application</span></span> | <span data-ttu-id="c800d-122">Обновленный Защитник Windows успешно для SECURITY_PRODUCT_STATE_OFF.</span><span class="sxs-lookup"><span data-stu-id="c800d-122">Updated Windows Defender status successfully to SECURITY_PRODUCT_STATE_OFF.</span></span> | <span data-ttu-id="c800d-123">Центр безопасности</span><span class="sxs-lookup"><span data-stu-id="c800d-123">Security Center</span></span>
<span data-ttu-id="c800d-124">5007</span><span class="sxs-lookup"><span data-stu-id="c800d-124">5007</span></span> | <span data-ttu-id="c800d-125">Microsoft-Windows-Защитник Windows/operational</span><span class="sxs-lookup"><span data-stu-id="c800d-125">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="c800d-126">антивирусная программа Конфигурация изменилась.</span><span class="sxs-lookup"><span data-stu-id="c800d-126">Windows Defender Antivirus Configuration has changed.</span></span>  <span data-ttu-id="c800d-127">Если это неожиданное событие, необходимо просмотреть параметры, так как это может быть результатом вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="c800d-127">If this is an unexpected event you should review the settings as this may be the result of malware.</span></span><br /><br /><span data-ttu-id="c800d-128">**Старое значение:** Default\IsServiceRunning = 0x0</span><span class="sxs-lookup"><span data-stu-id="c800d-128">**Old value:** Default\IsServiceRunning = 0x0</span></span><br /><span data-ttu-id="c800d-129">**Новое значение:** HKLM\SOFTWARE\Microsoft\Защитник Windows\IsServiceRunning = 0x1</span><span class="sxs-lookup"><span data-stu-id="c800d-129">**New value:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span></span> | <span data-ttu-id="c800d-130">Защитник Windows</span><span class="sxs-lookup"><span data-stu-id="c800d-130">Windows Defender</span></span>
<span data-ttu-id="c800d-131">5010</span><span class="sxs-lookup"><span data-stu-id="c800d-131">5010</span></span> | <span data-ttu-id="c800d-132">Microsoft-Windows-Защитник Windows/operational</span><span class="sxs-lookup"><span data-stu-id="c800d-132">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="c800d-133">антивирусная программа для шпионских программ и другого потенциально нежелательного программного обеспечения отключен.</span><span class="sxs-lookup"><span data-stu-id="c800d-133">Windows Defender Antivirus scanning for spyware and other potentially unwanted software is disabled.</span></span> | <span data-ttu-id="c800d-134">Защитник Windows</span><span class="sxs-lookup"><span data-stu-id="c800d-134">Windows Defender</span></span>

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a><span data-ttu-id="c800d-135">Как узнать, антивирусная программа в Microsoft Defender не будет запускаться, так как установлен сторонний антивирус</span><span class="sxs-lookup"><span data-stu-id="c800d-135">How to tell if Microsoft Defender Antivirus won't start because a third-party antivirus is installed</span></span>

<span data-ttu-id="c800d-136">На устройстве Windows 10, если вы не используете Microsoft Defender для endpoint и у вас установлен сторонний антивирус, антивирусная программа в Microsoft Defender автоматически отключается.</span><span class="sxs-lookup"><span data-stu-id="c800d-136">On a Windows 10 device, if you are not using Microsoft Defender for Endpoint, and you have a third-party antivirus installed, then Microsoft Defender Antivirus will be automatically turned off.</span></span> <span data-ttu-id="c800d-137">Если вы используете Microsoft Defender для конечной точки с установленным сторонним антивирусом, антивирусная программа в Microsoft Defender начнется в пассивном режиме с пониженной функциональностью.</span><span class="sxs-lookup"><span data-stu-id="c800d-137">If you are using Microsoft Defender for Endpoint with a third-party antivirus installed, Microsoft Defender Antivirus will start in passive mode, with reduced functionality.</span></span>

> [!TIP]
> <span data-ttu-id="c800d-138">Описанный сценарий применяется только к Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c800d-138">The scenario just described applies only to Windows 10.</span></span> <span data-ttu-id="c800d-139">Другие версии Windows [имеют](microsoft-defender-antivirus-compatibility.md) различные ответы на антивирусная программа в Microsoft Defender, которые запускаются вместе с сторонним программным обеспечением безопасности.</span><span class="sxs-lookup"><span data-stu-id="c800d-139">Other versions of Windows have [different responses](microsoft-defender-antivirus-compatibility.md) to Microsoft Defender Antivirus being run alongside third-party security software.</span></span>

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a><span data-ttu-id="c800d-140">Используйте приложение Services для проверки антивирусная программа в Microsoft Defender отключения</span><span class="sxs-lookup"><span data-stu-id="c800d-140">Use Services app to check if Microsoft Defender Antivirus is turned off</span></span>

<span data-ttu-id="c800d-141">Чтобы открыть приложение Services, выберите значок **Поиска** из панели задач и поиск *служб.*</span><span class="sxs-lookup"><span data-stu-id="c800d-141">To open the Services app, select the **Search** icon from the taskbar and search for *services*.</span></span> <span data-ttu-id="c800d-142">Вы также можете открыть приложение из командной строки, введя *services.msc*.</span><span class="sxs-lookup"><span data-stu-id="c800d-142">You can also open the app from the command-line by typing *services.msc*.</span></span>

<span data-ttu-id="c800d-143">Сведения о антивирусная программа в Microsoft Defender будут перечислены в приложении Services в **Защитник Windows**  >  **Operational.**</span><span class="sxs-lookup"><span data-stu-id="c800d-143">Information about Microsoft Defender Antivirus will be listed within the Services app under **Windows Defender** > **Operational**.</span></span> <span data-ttu-id="c800d-144">Имя антивирусной службы *антивирусная программа Service*.</span><span class="sxs-lookup"><span data-stu-id="c800d-144">The antivirus service name is *Windows Defender Antivirus Service*.</span></span>

<span data-ttu-id="c800d-145">При проверке приложения вы можете увидеть, что антивирусная программа *служба* настроена вручную, но при попытке запустить эту службу вручную вы получите предупреждение о том, что служба антивирусная программа на локальном компьютере запущена, а затем *остановлена. Некоторые службы автоматически останавливаются,* если они не используются другими службами или программами.</span><span class="sxs-lookup"><span data-stu-id="c800d-145">While checking the app, you may see that *Windows Defender Antivirus Service* is set to manual — but when you try to start this service manually, you get a warning stating, *The Windows Defender Antivirus Service service on Local Computer started and then stopped. Some services stop automatically if they are not in use by other services or programs.*</span></span>

<span data-ttu-id="c800d-146">Это означает, антивирусная программа в Microsoft Defender автоматически отключен для сохранения совместимости с сторонним антивирусом.</span><span class="sxs-lookup"><span data-stu-id="c800d-146">This indicates that Microsoft Defender Antivirus has been automatically turned off to preserve compatibility with a third-party antivirus.</span></span>

#### <a name="generate-a-detailed-report"></a><span data-ttu-id="c800d-147">Создание подробного отчета</span><span class="sxs-lookup"><span data-stu-id="c800d-147">Generate a detailed report</span></span>

<span data-ttu-id="c800d-148">Подробный отчет о текущих активных групповых политиках можно создать, открыв командную подсказку в **режиме Run as admin,** а затем введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c800d-148">You can generate a detailed report about currently active group policies by opening a command prompt in **Run as admin** mode, then entering the following command:</span></span>

```powershell
GPresult.exe /h gpresult.html
```

<span data-ttu-id="c800d-149">Это позволит создать отчет, расположенный *на уровне ./gpresult.html*.</span><span class="sxs-lookup"><span data-stu-id="c800d-149">This will generate a report located at *./gpresult.html*.</span></span> <span data-ttu-id="c800d-150">Откройте этот файл, и вы можете увидеть следующие результаты, в зависимости от антивирусная программа в Microsoft Defender отключения.</span><span class="sxs-lookup"><span data-stu-id="c800d-150">Open this file and you might see the following results, depending on how Microsoft Defender Antivirus was turned off.</span></span>

##### <a name="group-policy-results"></a><span data-ttu-id="c800d-151">Результаты групповой политики</span><span class="sxs-lookup"><span data-stu-id="c800d-151">Group policy results</span></span>

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a><span data-ttu-id="c800d-152">Если параметры безопасности реализованы с помощью групповой политики (GPO) на домене или локальном уровне, или если диспетчер конфигурации центра систем (SCCM)</span><span class="sxs-lookup"><span data-stu-id="c800d-152">If security settings are implemented via group policy (GPO) at the domain or local level, or though System center configuration manager (SCCM)</span></span>

<span data-ttu-id="c800d-153">В отчете GPResults в заголовке *Windows компоненты/антивирусная программа* вы можете увидеть что-то похожее на следующую запись, указав, что антивирусная программа в Microsoft Defender отключено.</span><span class="sxs-lookup"><span data-stu-id="c800d-153">Within the GPResults report, under the heading, *Windows Components/Windows Defender Antivirus*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="c800d-154">Политика</span><span class="sxs-lookup"><span data-stu-id="c800d-154">Policy</span></span> | <span data-ttu-id="c800d-155">Setting</span><span class="sxs-lookup"><span data-stu-id="c800d-155">Setting</span></span> | <span data-ttu-id="c800d-156">Выигрыш GPO</span><span class="sxs-lookup"><span data-stu-id="c800d-156">Winning GPO</span></span>
-|-|-
<span data-ttu-id="c800d-157">Отключите антивирусная программа</span><span class="sxs-lookup"><span data-stu-id="c800d-157">Turn off Windows Defender Antivirus</span></span> | <span data-ttu-id="c800d-158">Включено</span><span class="sxs-lookup"><span data-stu-id="c800d-158">Enabled</span></span> | <span data-ttu-id="c800d-159">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="c800d-159">Win10-Workstations</span></span>

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a><span data-ttu-id="c800d-160">Если параметры безопасности реализованы с помощью предпочтений групповой политики (GPP)</span><span class="sxs-lookup"><span data-stu-id="c800d-160">If security settings are implemented via Group policy preference (GPP)</span></span>

<span data-ttu-id="c800d-161">В заголовке Элемент реестра *(ключевой путь: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, имя значения: DisableAntiSpyware)* вы можете увидеть что-то похожее на следующую запись, указав, что антивирусная программа в Microsoft Defender отключено.</span><span class="sxs-lookup"><span data-stu-id="c800d-161">Under the heading, *Registry item (Key path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Value name: DisableAntiSpyware)*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="c800d-162">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="c800d-162">DisableAntiSpyware</span></span> | -
-|-
<span data-ttu-id="c800d-163">Выигрыш GPO</span><span class="sxs-lookup"><span data-stu-id="c800d-163">Winning GPO</span></span> | <span data-ttu-id="c800d-164">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="c800d-164">Win10-Workstations</span></span>
<span data-ttu-id="c800d-165">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="c800d-165">Result: Success</span></span> | 
<span data-ttu-id="c800d-166">**Общие**</span><span class="sxs-lookup"><span data-stu-id="c800d-166">**General**</span></span> | 
<span data-ttu-id="c800d-167">Действие</span><span class="sxs-lookup"><span data-stu-id="c800d-167">Action</span></span> | <span data-ttu-id="c800d-168">Update</span><span class="sxs-lookup"><span data-stu-id="c800d-168">Update</span></span>
<span data-ttu-id="c800d-169">**Свойства**</span><span class="sxs-lookup"><span data-stu-id="c800d-169">**Properties**</span></span> | 
<span data-ttu-id="c800d-170">Куст</span><span class="sxs-lookup"><span data-stu-id="c800d-170">Hive</span></span> | <span data-ttu-id="c800d-171">HKEY_LOCAL_MACHINE</span><span class="sxs-lookup"><span data-stu-id="c800d-171">HKEY_LOCAL_MACHINE</span></span>
<span data-ttu-id="c800d-172">Путь ключа</span><span class="sxs-lookup"><span data-stu-id="c800d-172">Key path</span></span> | <span data-ttu-id="c800d-173">SOFTWARE\Policies\Microsoft\Защитник Windows</span><span class="sxs-lookup"><span data-stu-id="c800d-173">SOFTWARE\Policies\Microsoft\Windows Defender</span></span>
<span data-ttu-id="c800d-174">Value name</span><span class="sxs-lookup"><span data-stu-id="c800d-174">Value name</span></span> | <span data-ttu-id="c800d-175">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="c800d-175">DisableAntiSpyware</span></span>
<span data-ttu-id="c800d-176">Тип значения</span><span class="sxs-lookup"><span data-stu-id="c800d-176">Value type</span></span> | <span data-ttu-id="c800d-177">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c800d-177">REG_DWORD</span></span>
<span data-ttu-id="c800d-178">Value data</span><span class="sxs-lookup"><span data-stu-id="c800d-178">Value data</span></span> | <span data-ttu-id="c800d-179">0x1 (1)</span><span class="sxs-lookup"><span data-stu-id="c800d-179">0x1 (1)</span></span>

###### <a name="if-security-settings-are-implemented-via-registry-key"></a><span data-ttu-id="c800d-180">Если параметры безопасности реализованы с помощью ключа реестра</span><span class="sxs-lookup"><span data-stu-id="c800d-180">If security settings are implemented via registry key</span></span>

<span data-ttu-id="c800d-181">В отчете может содержаться следующий текст, указывающий, что антивирусная программа в Microsoft Defender отключен:</span><span class="sxs-lookup"><span data-stu-id="c800d-181">The report may contain the following text, indicating that Microsoft Defender Antivirus is turned off:</span></span>
 
> <span data-ttu-id="c800d-182">Реестр (regedit.exe)</span><span class="sxs-lookup"><span data-stu-id="c800d-182">Registry (regedit.exe)</span></span>
>
> <span data-ttu-id="c800d-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)</span><span class="sxs-lookup"><span data-stu-id="c800d-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)</span></span>

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a><span data-ttu-id="c800d-184">Если параметры безопасности установлены в Windows или изображении Windows Server</span><span class="sxs-lookup"><span data-stu-id="c800d-184">If security settings are set in Windows or your Windows Server image</span></span>

<span data-ttu-id="c800d-185">Ваш воображающий администратор мог установить политику **[безопасности, DisableAntiSpyware,](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)** локально через *GPEdit.exe,* *LGPO.exe* или путем изменения реестра в последовательности задач.</span><span class="sxs-lookup"><span data-stu-id="c800d-185">Your imagining admin might have set the security policy, **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, locally via *GPEdit.exe*, *LGPO.exe*, or by modifying the registry in their task sequence.</span></span> <span data-ttu-id="c800d-186">Можно настроить [идентификатор доверенных изображений](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) для антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c800d-186">You can [configure a Trusted Image Identifier](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) for Microsoft Defender Antivirus.</span></span>

### <a name="turn-microsoft-defender-antivirus-back-on"></a><span data-ttu-id="c800d-187">Включаем антивирусная программа в Microsoft Defender обратно</span><span class="sxs-lookup"><span data-stu-id="c800d-187">Turn Microsoft Defender Antivirus back on</span></span>

<span data-ttu-id="c800d-188">антивирусная программа в Microsoft Defender автоматически включит, если другой антивирус в настоящее время не активен.</span><span class="sxs-lookup"><span data-stu-id="c800d-188">Microsoft Defender Antivirus will automatically turn on if no other antivirus is currently active.</span></span> <span data-ttu-id="c800d-189">Чтобы полностью отключить сторонний антивирус, антивирусная программа в Microsoft Defender работать с полным функционалом.</span><span class="sxs-lookup"><span data-stu-id="c800d-189">You'll need to turn the third-party antivirus completely off to ensure Microsoft Defender Antivirus can run with full functionality.</span></span>

> [!WARNING]
> <span data-ttu-id="c800d-190">Решения, предполагающие изменение значений *Защитник Windows* для *wdboot,* *wdfilter,* *wdnisdrv,* *wdnissvc* и *windefend* в HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services неподтвердимы, и могут заставить вас повторное изображение системы.</span><span class="sxs-lookup"><span data-stu-id="c800d-190">Solutions suggesting that you edit the *Windows Defender* start values for *wdboot*, *wdfilter*, *wdnisdrv*, *wdnissvc*, and *windefend* in  HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services are unsupported, and may force you to re-image your system.</span></span>

<span data-ttu-id="c800d-191">Пассивный режим доступен, если вы начинаете использовать Microsoft Defender для endpoint и сторонний антивирус вместе с антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c800d-191">Passive mode is available if you start using Microsoft Defender for Endpoint and a third-party antivirus together with Microsoft Defender Antivirus.</span></span> <span data-ttu-id="c800d-192">Пассивный режим позволяет Microsoft Defender сканировать файлы и обновлять себя, но не устраняет угрозы.</span><span class="sxs-lookup"><span data-stu-id="c800d-192">Passive mode allows Microsoft Defender to scan files and update itself, but it will not remediate threats.</span></span> <span data-ttu-id="c800d-193">Кроме того, мониторинг поведения в [режиме](configure-real-time-protection-microsoft-defender-antivirus.md) реального времени не доступен в пассивном режиме, если только не развернута защита от потери данных конечной точки [(DLP).](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview)</span><span class="sxs-lookup"><span data-stu-id="c800d-193">In addition, behavior monitoring via [Real Time Protection](configure-real-time-protection-microsoft-defender-antivirus.md) is not available under passive mode, unless [Endpoint data loss prevention (DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) is deployed.</span></span>

<span data-ttu-id="c800d-194">Еще одна функция, [известная](limited-periodic-scanning-microsoft-defender-antivirus.md)как ограниченное периодическое сканирование, доступна конечным пользователям, антивирусная программа в Microsoft Defender установлено автоматическое отключение.</span><span class="sxs-lookup"><span data-stu-id="c800d-194">Another feature, known as [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md), is available to end-users when Microsoft Defender Antivirus is set to automatically turn off.</span></span> <span data-ttu-id="c800d-195">Эта функция позволяет антивирусная программа в Microsoft Defender периодически сканировать файлы рядом с сторонним антивирусом, используя ограниченное число обнаружения.</span><span class="sxs-lookup"><span data-stu-id="c800d-195">This feature allows Microsoft Defender Antivirus to scan files periodically alongside a third-party antivirus, using a limited number of detections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c800d-196">Ограниченное периодическое сканирование не рекомендуется в корпоративных средах.</span><span class="sxs-lookup"><span data-stu-id="c800d-196">Limited periodic scanning is not recommended in enterprise environments.</span></span> <span data-ttu-id="c800d-197">Возможности обнаружения, управления и отчетов, доступные при антивирусная программа в Microsoft Defender в этом режиме, уменьшаются по сравнению с активным режимом.</span><span class="sxs-lookup"><span data-stu-id="c800d-197">The detection, management and reporting capabilities available when running Microsoft Defender Antivirus in this mode are reduced as compared to active mode.</span></span>

### <a name="see-also"></a><span data-ttu-id="c800d-198">См. также</span><span class="sxs-lookup"><span data-stu-id="c800d-198">See also</span></span>

* [<span data-ttu-id="c800d-199">антивирусная программа в Microsoft Defender совместимости</span><span class="sxs-lookup"><span data-stu-id="c800d-199">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
* [<span data-ttu-id="c800d-200">антивирусная программа в Microsoft Defender в приложении Безопасность Windows</span><span class="sxs-lookup"><span data-stu-id="c800d-200">Microsoft Defender Antivirus in the Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)