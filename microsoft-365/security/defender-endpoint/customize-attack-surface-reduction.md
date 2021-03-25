---
title: Настройка правил уменьшения поверхности атаки
description: Индивидуально устанавливайте правила в режимах аудита, блокировки или отключения, добавляйте файлы и папки, которые следует исключить из правил уменьшения поверхности атаки
keywords: Уменьшение поверхности атаки, бедра, система предотвращения вторжения на хост, правила защиты, антиэкспозиция, антиэкспплойт, эксплойт, профилактика инфекции, настройка, настройка, исключение
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 99a88a869c8a79f79cbc3a16fc73bf556416c51a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163304"
---
# <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="916cd-104">Настройка правил уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="916cd-104">Customize attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="916cd-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="916cd-105">**Applies to:**</span></span>
- [<span data-ttu-id="916cd-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="916cd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="916cd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="916cd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="916cd-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="916cd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="916cd-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="916cd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="916cd-110">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="916cd-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="916cd-111">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="916cd-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="916cd-112">[Правила уменьшения поверхности атаки](enable-attack-surface-reduction.md) помогают предотвратить поведение программного обеспечения, которое часто используется для компрометации устройства или сети.</span><span class="sxs-lookup"><span data-stu-id="916cd-112">[Attack surface reduction rules](enable-attack-surface-reduction.md) help prevent software behaviors that are often abused to compromise your device or network.</span></span> <span data-ttu-id="916cd-113">Например, злоумышленник может попытаться запустить неподписавший сценарий с USB-диска или иметь макрос в документе Office, который вызывается непосредственно в API Win32.</span><span class="sxs-lookup"><span data-stu-id="916cd-113">For example, an attacker might try to run an unsigned script off of a USB drive, or have a macro in an Office document make calls directly to the Win32 API.</span></span> <span data-ttu-id="916cd-114">Правила уменьшения поверхности атаки могут ограничить такие рискованные действия и улучшить защитную позицию организации.</span><span class="sxs-lookup"><span data-stu-id="916cd-114">Attack surface reduction rules can constrain these kinds of risky behaviors and improve your organization's defensive posture.</span></span>

<span data-ttu-id="916cd-115">Узнайте, как настроить правила уменьшения [](#exclude-files-and-folders) поверхности атаки, [](#customize-the-notification) исключив файлы и папки или добавив настраиваемый текст в оповещение, которое отображается на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="916cd-115">Learn how to customize attack surface reduction rules by [excluding files and folders](#exclude-files-and-folders) or [adding custom text to the notification](#customize-the-notification) alert that appears on a user's computer.</span></span>

<span data-ttu-id="916cd-116">Вы можете установить правила уменьшения поверхности атаки для устройств, работающих с любыми из следующих выпусков и версий Windows:</span><span class="sxs-lookup"><span data-stu-id="916cd-116">You can set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="916cd-117">Windows 10 Pro, [версия 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="916cd-117">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="916cd-118">Windows 10 Enterprise, [версия 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="916cd-118">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="916cd-119">Windows Server, [версия 1803 (полугодовой канал)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="916cd-119">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- <span data-ttu-id="916cd-120">[Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19) Для настройки этих параметров можно использовать поставщики услуг групповой политики, PowerShell и Службы управления мобильными устройствами (MDM).</span><span class="sxs-lookup"><span data-stu-id="916cd-120">[Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19) You can use Group Policy, PowerShell, and Mobile Device Management (MDM) configuration service providers (CSP) to configure these settings.</span></span>

## <a name="exclude-files-and-folders"></a><span data-ttu-id="916cd-121">Исключение файлов и папок</span><span class="sxs-lookup"><span data-stu-id="916cd-121">Exclude files and folders</span></span>

<span data-ttu-id="916cd-122">Вы можете исключить оценку файлов и папок правилами уменьшения поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="916cd-122">You can choose to exclude files and folders from being evaluated by attack surface reduction rules.</span></span> <span data-ttu-id="916cd-123">После исключения файл не будет заблокирован, даже если правило уменьшения поверхности атаки обнаруживает, что файл содержит вредоносное поведение.</span><span class="sxs-lookup"><span data-stu-id="916cd-123">Once excluded, the file won't be blocked from running even if an attack surface reduction rule detects that the file contains malicious behavior.</span></span>

> [!WARNING]
> <span data-ttu-id="916cd-124">Это потенциально может позволить небезопасным файлам запускать и заражать устройства.</span><span class="sxs-lookup"><span data-stu-id="916cd-124">This could potentially allow unsafe files to run and infect your devices.</span></span> <span data-ttu-id="916cd-125">Исключение файлов или папок может серьезно уменьшить защиту, предоставляемую правилами уменьшения поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="916cd-125">Excluding files or folders can severely reduce the protection provided by attack surface reduction rules.</span></span> <span data-ttu-id="916cd-126">Файлы, заблокированные правилом, будут разрешены к запуску, и отчет или событие не будут записываться.</span><span class="sxs-lookup"><span data-stu-id="916cd-126">Files that would have been blocked by a rule will be allowed to run, and there will be no report or event recorded.</span></span>

<span data-ttu-id="916cd-127">Исключение применяется ко всем правилам, допуская исключения.</span><span class="sxs-lookup"><span data-stu-id="916cd-127">An exclusion applies to all rules that allow exclusions.</span></span> <span data-ttu-id="916cd-128">Можно указать отдельный файл, путь папки или полное доменное имя для ресурса.</span><span class="sxs-lookup"><span data-stu-id="916cd-128">You can specify an individual file, folder path, or the fully qualified domain name for a resource.</span></span> <span data-ttu-id="916cd-129">Однако нельзя ограничить исключение определенным правилом.</span><span class="sxs-lookup"><span data-stu-id="916cd-129">However, you cannot limit an exclusion to a specific rule.</span></span>

<span data-ttu-id="916cd-130">Исключение применяется только при старте исключенного приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="916cd-130">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="916cd-131">Например, если добавлено исключение для уже запущенной службы обновления, служба обновления будет продолжать запускать события до тех пор, пока служба не будет остановлена и перезапущена.</span><span class="sxs-lookup"><span data-stu-id="916cd-131">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="916cd-132">Уменьшение поверхности атаки поддерживает переменные среды и подкарды.</span><span class="sxs-lookup"><span data-stu-id="916cd-132">Attack surface reduction supports environment variables and wildcards.</span></span> <span data-ttu-id="916cd-133">Сведения об использовании поддиальдов см. в материалах использования подкардов в списке имен файлов и папок [или списках исключений расширения.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="916cd-133">For information about using wildcards, see [use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>
<span data-ttu-id="916cd-134">Если возникают проблемы с обнаружением файлов правил, которые, по вашим мнению, не следует обнаруживать, используйте режим аудита для [проверки правила.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="916cd-134">If you are encountering problems with rules detecting files that you believe should not be detected, [use audit mode to test the rule](evaluate-attack-surface-reduction.md).</span></span>

<span data-ttu-id="916cd-135">Описание правила</span><span class="sxs-lookup"><span data-stu-id="916cd-135">Rule description</span></span> | <span data-ttu-id="916cd-136">GUID</span><span class="sxs-lookup"><span data-stu-id="916cd-136">GUID</span></span>
-|-|-
<span data-ttu-id="916cd-137">Блокировка всех приложений Office от создания детских процессов</span><span class="sxs-lookup"><span data-stu-id="916cd-137">Block all Office applications from creating child processes</span></span> | <span data-ttu-id="916cd-138">D4F940AB-401B-4EFC-AADC-AD5F3C50688A</span><span class="sxs-lookup"><span data-stu-id="916cd-138">D4F940AB-401B-4EFC-AADC-AD5F3C50688A</span></span>
<span data-ttu-id="916cd-139">Блокировка выполнения потенциально запутаных скриптов</span><span class="sxs-lookup"><span data-stu-id="916cd-139">Block execution of potentially obfuscated scripts</span></span> | <span data-ttu-id="916cd-140">5BEB7EFE-FD9A-4556-801D-275E5FFC04CC</span><span class="sxs-lookup"><span data-stu-id="916cd-140">5BEB7EFE-FD9A-4556-801D-275E5FFC04CC</span></span>
<span data-ttu-id="916cd-141">Блокировка вызовов API Win32 из макроса Office</span><span class="sxs-lookup"><span data-stu-id="916cd-141">Block Win32 API calls from Office macro</span></span> | <span data-ttu-id="916cd-142">92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B</span><span class="sxs-lookup"><span data-stu-id="916cd-142">92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B</span></span>
<span data-ttu-id="916cd-143">Блокировка приложений Office от создания исполняемого контента</span><span class="sxs-lookup"><span data-stu-id="916cd-143">Block Office applications from creating executable content</span></span> | <span data-ttu-id="916cd-144">3B576869-A4EC-4529-8536-B80A7769E899</span><span class="sxs-lookup"><span data-stu-id="916cd-144">3B576869-A4EC-4529-8536-B80A7769E899</span></span>
<span data-ttu-id="916cd-145">Блокировка приложений Office от внесения кода в другие процессы</span><span class="sxs-lookup"><span data-stu-id="916cd-145">Block Office applications from injecting code into other processes</span></span> | <span data-ttu-id="916cd-146">75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84</span><span class="sxs-lookup"><span data-stu-id="916cd-146">75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84</span></span>
<span data-ttu-id="916cd-147">Блокировка JavaScript или VBScript от запуска загружаемого исполняемого контента</span><span class="sxs-lookup"><span data-stu-id="916cd-147">Block JavaScript or VBScript from launching downloaded executable content</span></span> | <span data-ttu-id="916cd-148">D3E037E1-3EB8-44C8-A917-57927947596D</span><span class="sxs-lookup"><span data-stu-id="916cd-148">D3E037E1-3EB8-44C8-A917-57927947596D</span></span>
<span data-ttu-id="916cd-149">Блокировка исполняемого контента из клиента электронной почты и веб-почты</span><span class="sxs-lookup"><span data-stu-id="916cd-149">Block executable content from email client and webmail</span></span> | <span data-ttu-id="916cd-150">BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550</span><span class="sxs-lookup"><span data-stu-id="916cd-150">BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550</span></span>
<span data-ttu-id="916cd-151">Блокировать выполнение файлов, если они не соответствуют критериям распространенности, возраста или доверенного списка</span><span class="sxs-lookup"><span data-stu-id="916cd-151">Block executable files from running unless they meet a prevalence, age, or trusted list criteria</span></span> | <span data-ttu-id="916cd-152">01443614-cd74-433a-b99e-2ecdc07bfc25</span><span class="sxs-lookup"><span data-stu-id="916cd-152">01443614-cd74-433a-b99e-2ecdc07bfc25</span></span>
<span data-ttu-id="916cd-153">Используйте расширенные средства защиты от программ-вымогателей</span><span class="sxs-lookup"><span data-stu-id="916cd-153">Use advanced protection against ransomware</span></span> | <span data-ttu-id="916cd-154">c1db55ab-c21a-4637-bb3f-a12568109d35</span><span class="sxs-lookup"><span data-stu-id="916cd-154">c1db55ab-c21a-4637-bb3f-a12568109d35</span></span>
<span data-ttu-id="916cd-155">Блокировка кражи учетных данных из подсистемы локального органа безопасности Windows (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="916cd-155">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span> | <span data-ttu-id="916cd-156">9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2</span><span class="sxs-lookup"><span data-stu-id="916cd-156">9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2</span></span>
<span data-ttu-id="916cd-157">Блокировка создания процессов, происходящих из команд PSExec и WMI</span><span class="sxs-lookup"><span data-stu-id="916cd-157">Block process creations originating from PSExec and WMI commands</span></span> | <span data-ttu-id="916cd-158">d1e49aac-8f56-4280-b9ba-993a6d77406c</span><span class="sxs-lookup"><span data-stu-id="916cd-158">d1e49aac-8f56-4280-b9ba-993a6d77406c</span></span>
<span data-ttu-id="916cd-159">Блокировка ненарушимых и неподписаных процессов, которые запускают из USB</span><span class="sxs-lookup"><span data-stu-id="916cd-159">Block untrusted and unsigned processes that run from USB</span></span> | <span data-ttu-id="916cd-160">b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4</span><span class="sxs-lookup"><span data-stu-id="916cd-160">b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4</span></span>
<span data-ttu-id="916cd-161">Блокировка приложений связи Office от создания детских процессов</span><span class="sxs-lookup"><span data-stu-id="916cd-161">Block Office communication applications from creating child processes</span></span> | <span data-ttu-id="916cd-162">26190899-1602-49e8-8b27-eb1d0a1ce869</span><span class="sxs-lookup"><span data-stu-id="916cd-162">26190899-1602-49e8-8b27-eb1d0a1ce869</span></span>
<span data-ttu-id="916cd-163">Блокировка Adobe Reader от создания детских процессов</span><span class="sxs-lookup"><span data-stu-id="916cd-163">Block Adobe Reader from creating child processes</span></span> | <span data-ttu-id="916cd-164">7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c</span><span class="sxs-lookup"><span data-stu-id="916cd-164">7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c</span></span>
<span data-ttu-id="916cd-165">Блокировка сохраняемости с помощью подписки на события WMI</span><span class="sxs-lookup"><span data-stu-id="916cd-165">Block persistence through WMI event subscription</span></span> | <span data-ttu-id="916cd-166">e6db77e5-3df2-4cf1-b95a-636979351e5b</span><span class="sxs-lookup"><span data-stu-id="916cd-166">e6db77e5-3df2-4cf1-b95a-636979351e5b</span></span>

<span data-ttu-id="916cd-167">Подробные [сведения](attack-surface-reduction.md) о каждом правиле см. в разделе уменьшение поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="916cd-167">See the [attack surface reduction](attack-surface-reduction.md) topic for details on each rule.</span></span>

### <a name="use-group-policy-to-exclude-files-and-folders"></a><span data-ttu-id="916cd-168">Использование групповой политики для исключения файлов и папок</span><span class="sxs-lookup"><span data-stu-id="916cd-168">Use Group Policy to exclude files and folders</span></span>

1. <span data-ttu-id="916cd-169">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](https://technet.microsoft.com/library/cc731212.aspx)кнопкой мыши объект групповой политики, который необходимо настроить, и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="916cd-169">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="916cd-170">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и щелкните **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="916cd-170">In the **Group Policy Management Editor**, go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="916cd-171">Расширь дерево до **компонентов Microsoft** Defender Antivirus Защитник Windows с уменьшением поверхности  >    >  **атаки guard.**  >  </span><span class="sxs-lookup"><span data-stu-id="916cd-171">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="916cd-172">Дважды нажмите кнопку **Исключить файлы и пути** из параметра Правила уменьшения поверхности атаки и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="916cd-172">Double-click the **Exclude files and paths from Attack surface reduction Rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="916cd-173">Выберите **Показать и** ввести каждый файл или папку в столбце Имя **значения.**</span><span class="sxs-lookup"><span data-stu-id="916cd-173">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="916cd-174">Введите **0** в **столбце Значение** для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="916cd-174">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="916cd-175">Не используйте кавычка, так как они не поддерживаются ни для столбца **value name,** ни для **столбца Value.**</span><span class="sxs-lookup"><span data-stu-id="916cd-175">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

### <a name="use-powershell-to-exclude-files-and-folders"></a><span data-ttu-id="916cd-176">Использование PowerShell для исключения файлов и папок</span><span class="sxs-lookup"><span data-stu-id="916cd-176">Use PowerShell to exclude files and folders</span></span>

1. <span data-ttu-id="916cd-177">Введите **powershell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**</span><span class="sxs-lookup"><span data-stu-id="916cd-177">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="916cd-178">Введите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="916cd-178">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

<span data-ttu-id="916cd-179">Продолжайте использовать `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` для добавления дополнительных папок в список.</span><span class="sxs-lookup"><span data-stu-id="916cd-179">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more folders to the list.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="916cd-180">Используйте `Add-MpPreference` для добавления или добавления приложений в список.</span><span class="sxs-lookup"><span data-stu-id="916cd-180">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="916cd-181">С помощью `Set-MpPreference` этого комлета будет переописывать существующий список.</span><span class="sxs-lookup"><span data-stu-id="916cd-181">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a><span data-ttu-id="916cd-182">Использование CSPs MDM для исключения файлов и папок</span><span class="sxs-lookup"><span data-stu-id="916cd-182">Use MDM CSPs to exclude files and folders</span></span>

<span data-ttu-id="916cd-183">Для добавления исключений используйте поставщика служб конфигурации [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions)</span><span class="sxs-lookup"><span data-stu-id="916cd-183">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="916cd-184">Настройка уведомления</span><span class="sxs-lookup"><span data-stu-id="916cd-184">Customize the notification</span></span>

<span data-ttu-id="916cd-185">Вы можете настроить уведомление о срабатывке правила и блокировке приложения или файла.</span><span class="sxs-lookup"><span data-stu-id="916cd-185">You can customize the notification for when a rule is triggered and blocks an app or file.</span></span> <span data-ttu-id="916cd-186">См. [статью Windows Security.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="916cd-186">See the [Windows Security](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) article.</span></span>

## <a name="related-topics"></a><span data-ttu-id="916cd-187">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="916cd-187">Related topics</span></span>

* [<span data-ttu-id="916cd-188">Уменьшение поверхностей атаки с помощью правил уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="916cd-188">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="916cd-189">Включить правила уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="916cd-189">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)
* [<span data-ttu-id="916cd-190">Оценка правил уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="916cd-190">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
* [<span data-ttu-id="916cd-191">FaQ уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="916cd-191">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)