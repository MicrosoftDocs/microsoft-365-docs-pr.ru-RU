---
title: Настройка правил сокращения направлений атак
description: Индивидуально устанавливайте правила в режимах аудита, блокировки или отключения, добавляйте файлы и папки, которые следует исключить из правил уменьшения поверхности атаки
keywords: Уменьшение поверхности атаки, бедра, система предотвращения вторжения на хост, правила защиты, антиэкспозиция, антиэкспплойт, эксплойт, профилактика инфекции, настройка, настройка, исключение
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 232f7133f177e3d0aa93fcb2835fb86bcfd0d37c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769327"
---
# <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="7c446-104">Настройка правил сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="7c446-104">Customize attack surface reduction rules</span></span>

<span data-ttu-id="7c446-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7c446-105">**Applies to:**</span></span>
- [<span data-ttu-id="7c446-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7c446-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7c446-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7c446-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="7c446-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="7c446-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7c446-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="7c446-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="7c446-110">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="7c446-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7c446-111">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="7c446-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="7c446-112">[Правила уменьшения поверхности атаки](enable-attack-surface-reduction.md) помогают предотвратить поведение программного обеспечения, которое часто используется для компрометации устройства или сети.</span><span class="sxs-lookup"><span data-stu-id="7c446-112">[Attack surface reduction rules](enable-attack-surface-reduction.md) help prevent software behaviors that are often abused to compromise your device or network.</span></span> <span data-ttu-id="7c446-113">Например, злоумышленник может попытаться запустить неподписавший сценарий с USB-диска или иметь макрос в документе, Office сделать вызовы непосредственно в API Win32.</span><span class="sxs-lookup"><span data-stu-id="7c446-113">For example, an attacker might try to run an unsigned script off of a USB drive, or have a macro in an Office document make calls directly to the Win32 API.</span></span> <span data-ttu-id="7c446-114">Правила уменьшения поверхности атаки могут ограничить такие рискованные действия и улучшить защитную позицию организации.</span><span class="sxs-lookup"><span data-stu-id="7c446-114">Attack surface reduction rules can constrain these kinds of risky behaviors and improve your organization's defensive posture.</span></span>

<span data-ttu-id="7c446-115">Узнайте, как настроить правила уменьшения [](#exclude-files-and-folders) поверхности атаки, [](#customize-the-notification) исключив файлы и папки или добавив настраиваемый текст в оповещение, которое отображается на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="7c446-115">Learn how to customize attack surface reduction rules by [excluding files and folders](#exclude-files-and-folders) or [adding custom text to the notification](#customize-the-notification) alert that appears on a user's computer.</span></span>

<span data-ttu-id="7c446-116">Вы можете установить правила уменьшения поверхности атаки для устройств, работающих с любыми из следующих выпусков и версий Windows:</span><span class="sxs-lookup"><span data-stu-id="7c446-116">You can set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="7c446-117">Windows 10 Pro версии [1709](/windows/whats-new/whats-new-windows-10-version-1709) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="7c446-117">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="7c446-118">Windows 10 Корпоративная версии [1709](/windows/whats-new/whats-new-windows-10-version-1709) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="7c446-118">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="7c446-119">Windows Сервер, [версия 1803 (полугодовой канал)](/windows-server/get-started/whats-new-in-windows-server-1803) или более поздний</span><span class="sxs-lookup"><span data-stu-id="7c446-119">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- <span data-ttu-id="7c446-120">[Windows Server 2019](/windows-server/get-started-19/whats-new-19) Для настройки этих параметров можно использовать поставщики услуг групповой политики, PowerShell и Службы управления мобильными устройствами (MDM).</span><span class="sxs-lookup"><span data-stu-id="7c446-120">[Windows Server 2019](/windows-server/get-started-19/whats-new-19) You can use Group Policy, PowerShell, and Mobile Device Management (MDM) configuration service providers (CSP) to configure these settings.</span></span>

## <a name="exclude-files-and-folders"></a><span data-ttu-id="7c446-121">Исключение файлов и папок</span><span class="sxs-lookup"><span data-stu-id="7c446-121">Exclude files and folders</span></span>

<span data-ttu-id="7c446-122">Вы можете исключить оценку файлов и папок правилами уменьшения поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="7c446-122">You can choose to exclude files and folders from being evaluated by attack surface reduction rules.</span></span> <span data-ttu-id="7c446-123">После исключения файл не будет заблокирован, даже если правило уменьшения поверхности атаки обнаруживает, что файл содержит вредоносное поведение.</span><span class="sxs-lookup"><span data-stu-id="7c446-123">Once excluded, the file won't be blocked from running even if an attack surface reduction rule detects that the file contains malicious behavior.</span></span>

> [!WARNING]
> <span data-ttu-id="7c446-124">Это потенциально может позволить небезопасным файлам запускать и заражать устройства.</span><span class="sxs-lookup"><span data-stu-id="7c446-124">This could potentially allow unsafe files to run and infect your devices.</span></span> <span data-ttu-id="7c446-125">Исключение файлов или папок может значительно снизить защиту, предоставляемую правилами сокращения направлений атак.</span><span class="sxs-lookup"><span data-stu-id="7c446-125">Excluding files or folders can severely reduce the protection provided by attack surface reduction rules.</span></span> <span data-ttu-id="7c446-126">Файлы, заблокированные правилом, будут разрешены к запуску, и отчет или событие не будут записываться.</span><span class="sxs-lookup"><span data-stu-id="7c446-126">Files that would have been blocked by a rule will be allowed to run, and there will be no report or event recorded.</span></span>

<span data-ttu-id="7c446-127">Исключение применяется ко всем правилам, допускающим эти исключения.</span><span class="sxs-lookup"><span data-stu-id="7c446-127">An exclusion applies to all rules that allow exclusions.</span></span> <span data-ttu-id="7c446-128">Можно указать отдельный файл, путь папки или полное доменное имя для ресурса.</span><span class="sxs-lookup"><span data-stu-id="7c446-128">You can specify an individual file, folder path, or the fully qualified domain name for a resource.</span></span> <span data-ttu-id="7c446-129">Однако нельзя ограничить исключение определенным правилом.</span><span class="sxs-lookup"><span data-stu-id="7c446-129">However, you cannot limit an exclusion to a specific rule.</span></span>

<span data-ttu-id="7c446-130">Исключение применяется только при старте исключенного приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="7c446-130">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="7c446-131">Например, если добавлено исключение для уже запущенной службы обновления, служба обновления будет продолжать запускать события до тех пор, пока служба не будет остановлена и перезапущена.</span><span class="sxs-lookup"><span data-stu-id="7c446-131">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="7c446-132">Уменьшение поверхности атаки поддерживает переменные среды и подкарды.</span><span class="sxs-lookup"><span data-stu-id="7c446-132">Attack surface reduction supports environment variables and wildcards.</span></span> <span data-ttu-id="7c446-133">Сведения об использовании поддиальдов см. в материалах использования подкардов в списке имен файлов и папок [или списках исключений расширения.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="7c446-133">For information about using wildcards, see [use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) .</span></span>
<span data-ttu-id="7c446-134">Если возникают проблемы с обнаружением файлов правил, которые, по вашим мнению, не следует обнаруживать, используйте режим аудита для [проверки правила.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="7c446-134">If you are encountering problems with rules detecting files that you believe should not be detected, [use audit mode to test the rule](evaluate-attack-surface-reduction.md).</span></span>

| <span data-ttu-id="7c446-135">Описание правила</span><span class="sxs-lookup"><span data-stu-id="7c446-135">Rule description</span></span> | <span data-ttu-id="7c446-136">GUID</span><span class="sxs-lookup"><span data-stu-id="7c446-136">GUID</span></span> |
|:----|:----|:----|
| <span data-ttu-id="7c446-137">Блокировка всех Office приложений от создания детских процессов</span><span class="sxs-lookup"><span data-stu-id="7c446-137">Block all Office applications from creating child processes</span></span> | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` |
| <span data-ttu-id="7c446-138">Блокировка выполнения потенциально запутаных скриптов</span><span class="sxs-lookup"><span data-stu-id="7c446-138">Block execution of potentially obfuscated scripts</span></span> | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` |
| <span data-ttu-id="7c446-139">Блоки вызовов API Win32 Office макроса</span><span class="sxs-lookup"><span data-stu-id="7c446-139">Block Win32 API calls from Office macro</span></span> | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` |
| <span data-ttu-id="7c446-140">Блокировка Office приложений от создания исполняемого контента</span><span class="sxs-lookup"><span data-stu-id="7c446-140">Block Office applications from creating executable content</span></span> | `3B576869-A4EC-4529-8536-B80A7769E899` |
| <span data-ttu-id="7c446-141">Блокировка Office приложений от внесения кода в другие процессы</span><span class="sxs-lookup"><span data-stu-id="7c446-141">Block Office applications from injecting code into other processes</span></span> | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` |
| <span data-ttu-id="7c446-142">Блокировка JavaScript или VBScript от запуска загружаемого исполняемого контента</span><span class="sxs-lookup"><span data-stu-id="7c446-142">Block JavaScript or VBScript from launching downloaded executable content</span></span> | `D3E037E1-3EB8-44C8-A917-57927947596D` |
| <span data-ttu-id="7c446-143">Блокировка исполняемого контента из клиента электронной почты и веб-почты</span><span class="sxs-lookup"><span data-stu-id="7c446-143">Block executable content from email client and webmail</span></span> | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` |
| <span data-ttu-id="7c446-144">Блокировать выполнение файлов, если они не соответствуют критериям распространенности, возраста или доверенного списка</span><span class="sxs-lookup"><span data-stu-id="7c446-144">Block executable files from running unless they meet a prevalence, age, or trusted list criteria</span></span> | `01443614-cd74-433a-b99e-2ecdc07bfc25` |
| <span data-ttu-id="7c446-145">Используйте расширенные средства защиты от программ-вымогателей</span><span class="sxs-lookup"><span data-stu-id="7c446-145">Use advanced protection against ransomware</span></span> | `c1db55ab-c21a-4637-bb3f-a12568109d35` |
| <span data-ttu-id="7c446-146">Блокировка кражи учетных данных из Windows локальной подсистемы органов безопасности (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="7c446-146">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span> | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` |
| <span data-ttu-id="7c446-147">Блокировка создания процессов, происходящих из команд PSExec и WMI</span><span class="sxs-lookup"><span data-stu-id="7c446-147">Block process creations originating from PSExec and WMI commands</span></span> | `d1e49aac-8f56-4280-b9ba-993a6d77406c` |
| <span data-ttu-id="7c446-148">Блокировка ненарушимых и неподписаных процессов, которые запускают из USB</span><span class="sxs-lookup"><span data-stu-id="7c446-148">Block untrusted and unsigned processes that run from USB</span></span> | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` |
| <span data-ttu-id="7c446-149">Блокировка Office приложений связи от создания детских процессов</span><span class="sxs-lookup"><span data-stu-id="7c446-149">Block Office communication applications from creating child processes</span></span> | `26190899-1602-49e8-8b27-eb1d0a1ce869` |
| <span data-ttu-id="7c446-150">Блокировка Adobe Reader от создания детских процессов</span><span class="sxs-lookup"><span data-stu-id="7c446-150">Block Adobe Reader from creating child processes</span></span> | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` |
| <span data-ttu-id="7c446-151">Блокировка сохраняемости с помощью подписки на события WMI</span><span class="sxs-lookup"><span data-stu-id="7c446-151">Block persistence through WMI event subscription</span></span> | `e6db77e5-3df2-4cf1-b95a-636979351e5b` |

<span data-ttu-id="7c446-152">Подробные [сведения](attack-surface-reduction.md) о каждом правиле см. в разделе уменьшение поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="7c446-152">See the [attack surface reduction](attack-surface-reduction.md) topic for details on each rule.</span></span>

### <a name="use-group-policy-to-exclude-files-and-folders"></a><span data-ttu-id="7c446-153">Использование групповой политики для исключения файлов и папок</span><span class="sxs-lookup"><span data-stu-id="7c446-153">Use Group Policy to exclude files and folders</span></span>

1. <span data-ttu-id="7c446-154">Для этого на компьютере, управляющем групповыми политиками, откройте [Консоль управления групповой политикой](https://technet.microsoft.com/library/cc731212.aspx), щелкните правой кнопкой мыши нужный объект групповой политики и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="7c446-154">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="7c446-155">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и щелкните **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="7c446-155">In the **Group Policy Management Editor**, go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="7c446-156">Расширь **дерево, Windows компоненты антивирусная программа в Microsoft Defender** Защитник Windows с уменьшением поверхности  >    >  **exploit**  >  **Guard Attack.**</span><span class="sxs-lookup"><span data-stu-id="7c446-156">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="7c446-157">Дважды нажмите кнопку **Исключить файлы и пути** из параметра Правила уменьшения поверхности атаки и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="7c446-157">Double-click the **Exclude files and paths from Attack surface reduction Rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="7c446-158">Выберите **Показать и** ввести каждый файл или папку в столбце Имя **значения.**</span><span class="sxs-lookup"><span data-stu-id="7c446-158">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="7c446-159">Введите **0** в **столбце Значение** для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="7c446-159">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="7c446-160">Не используйте кавычка, так как они не поддерживаются ни для столбца **value name,** ни для **столбца Value.**</span><span class="sxs-lookup"><span data-stu-id="7c446-160">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

### <a name="use-powershell-to-exclude-files-and-folders"></a><span data-ttu-id="7c446-161">Использование PowerShell для исключения файлов и папок</span><span class="sxs-lookup"><span data-stu-id="7c446-161">Use PowerShell to exclude files and folders</span></span>

1. <span data-ttu-id="7c446-162">Введите **powershell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**</span><span class="sxs-lookup"><span data-stu-id="7c446-162">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="7c446-163">Введите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7c446-163">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

<span data-ttu-id="7c446-164">Продолжайте использовать `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` для добавления дополнительных папок в список.</span><span class="sxs-lookup"><span data-stu-id="7c446-164">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more folders to the list.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c446-165">Используйте `Add-MpPreference` для добавления или добавления приложений в список.</span><span class="sxs-lookup"><span data-stu-id="7c446-165">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="7c446-166">С помощью `Set-MpPreference` этого комлета будет переописывать существующий список.</span><span class="sxs-lookup"><span data-stu-id="7c446-166">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a><span data-ttu-id="7c446-167">Использование CSPs MDM для исключения файлов и папок</span><span class="sxs-lookup"><span data-stu-id="7c446-167">Use MDM CSPs to exclude files and folders</span></span>

<span data-ttu-id="7c446-168">Для добавления исключений используйте поставщика служб конфигурации [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions.](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions)</span><span class="sxs-lookup"><span data-stu-id="7c446-168">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="7c446-169">Настройка уведомления</span><span class="sxs-lookup"><span data-stu-id="7c446-169">Customize the notification</span></span>

<span data-ttu-id="7c446-170">Вы можете настроить уведомление о срабатывке правила и блокировке приложения или файла.</span><span class="sxs-lookup"><span data-stu-id="7c446-170">You can customize the notification for when a rule is triggered and blocks an app or file.</span></span> <span data-ttu-id="7c446-171">См. [статью Безопасность Windows.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="7c446-171">See the [Windows Security](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) article.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7c446-172">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="7c446-172">Related topics</span></span>

* [<span data-ttu-id="7c446-173">Уменьшение поверхностей атаки с помощью правил уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="7c446-173">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="7c446-174">Включить правила сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="7c446-174">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)
* [<span data-ttu-id="7c446-175">Оценка правил сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="7c446-175">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
* [<span data-ttu-id="7c446-176">Сокращение направлений атак: вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="7c446-176">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
