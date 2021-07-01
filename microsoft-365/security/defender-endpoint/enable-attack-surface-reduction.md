---
title: Включить правила сокращения направлений атак
description: Включить правила уменьшения поверхности атаки для защиты устройств от атак с использованием макросов, скриптов и распространенных методов впрыскивания.
keywords: Уменьшение поверхности атаки, бедра, система предотвращения вторжения на хост, правила защиты, антиэкспозиция, антиэкспплойт, эксплойт, профилактика инфекции, включить, включить
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.date: 06/02/2021
ms.openlocfilehash: 65215d15e79ab03611bbf28c153d6882fd1c355d
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229147"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="5daa3-104">Включить правила сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="5daa3-104">Enable attack surface reduction rules</span></span>

<span data-ttu-id="5daa3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5daa3-105">**Applies to:**</span></span>

- [<span data-ttu-id="5daa3-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5daa3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5daa3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5daa3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="5daa3-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="5daa3-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="5daa3-109">[Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="5daa3-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="5daa3-110">[Правила уменьшения поверхности](attack-surface-reduction.md) атаки (правила ASR) помогают предотвратить действия, которые вредоносные программы часто используют для компрометации устройств и сетей.</span><span class="sxs-lookup"><span data-stu-id="5daa3-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span>

## <a name="requirements"></a><span data-ttu-id="5daa3-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5daa3-111">Requirements</span></span>

<span data-ttu-id="5daa3-112">Функции уменьшения поверхности атаки в Windows версиях</span><span class="sxs-lookup"><span data-stu-id="5daa3-112">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="5daa3-113">Вы можете установить правила уменьшения поверхности атаки для устройств, которые работают с любыми из следующих выпусков и версий Windows:</span><span class="sxs-lookup"><span data-stu-id="5daa3-113">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="5daa3-114">Windows 10 Pro версии [1709](/windows/whats-new/whats-new-windows-10-version-1709) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="5daa3-114">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="5daa3-115">Windows 10 Корпоративная версии [1709](/windows/whats-new/whats-new-windows-10-version-1709) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="5daa3-115">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="5daa3-116">Windows Сервер, [версия 1803 (полугодовой канал)](/windows-server/get-started/whats-new-in-windows-server-1803) или более поздний</span><span class="sxs-lookup"><span data-stu-id="5daa3-116">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="5daa3-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5daa3-117">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="5daa3-118">Чтобы использовать весь набор функций правил уменьшения поверхности атаки, необходимо:</span><span class="sxs-lookup"><span data-stu-id="5daa3-118">To use the entire feature-set of attack surface reduction rules, you need:</span></span>

- <span data-ttu-id="5daa3-119">антивирусная программа как основной av (защита в режиме реального времени)</span><span class="sxs-lookup"><span data-stu-id="5daa3-119">Windows Defender Antivirus as primary AV (real-time protection on)</span></span>
- <span data-ttu-id="5daa3-120">[Защита облачной доставки](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) (для этого требуются некоторые правила)</span><span class="sxs-lookup"><span data-stu-id="5daa3-120">[Cloud-Delivery Protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) on (some rules require that)</span></span>
- <span data-ttu-id="5daa3-121">Windows 10 Корпоративная Лицензия E5 или E3 или Microsoft 365 бизнес-лицензия</span><span class="sxs-lookup"><span data-stu-id="5daa3-121">Windows 10 Enterprise E5 or E3 License or Microsoft 365 Business License</span></span>

<span data-ttu-id="5daa3-122">Хотя правила уменьшения поверхности атаки не требуют лицензии Windows E5 с лицензией Windows [E5,](/windows/deployment/deploy-enterprise-licenses)вы получаете расширенные возможности управления, включая мониторинг, аналитику и рабочий процесс, доступные в Defender for Endpoint, а также возможности отчетности и конфигурации в центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5daa3-122">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), with a Windows E5 license, you get advanced management capabilities including monitoring, analytics, and workflows available in Defender for Endpoint, as well as reporting and configuration capabilities in the Microsoft 365 security center.</span></span> <span data-ttu-id="5daa3-123">Эти расширенные возможности недоступны с лицензией E3, но вы все равно можете использовать viewer событий для просмотра событий, чтобы просмотреть события правила уменьшения поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="5daa3-123">These advanced capabilities aren't available with an E3 license, but you can still use Event Viewer to review attack surface reduction rule events.</span></span>

<span data-ttu-id="5daa3-124">Каждое правило ASR содержит один из четырех параметров:</span><span class="sxs-lookup"><span data-stu-id="5daa3-124">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="5daa3-125">**Не настроен:** отключить правило ASR</span><span class="sxs-lookup"><span data-stu-id="5daa3-125">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="5daa3-126">**Блок**: Включить правило ASR</span><span class="sxs-lookup"><span data-stu-id="5daa3-126">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="5daa3-127">**Аудит.** Оцените, как правило ASR повлияет на организацию, если включено</span><span class="sxs-lookup"><span data-stu-id="5daa3-127">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="5daa3-128">**Предупреждение.** Включить правило ASR, но разрешить конечному пользователю обойти блокировку</span><span class="sxs-lookup"><span data-stu-id="5daa3-128">**Warn**: Enable the ASR rule but allow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5daa3-129">В настоящее время режим предупреждения не поддерживается для трех правил ASR при настройке правил ASR в Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="5daa3-129">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="5daa3-130">Дополнительные дополнительные информации см. [в том, как не](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)поддерживается режим предупреждения.</span><span class="sxs-lookup"><span data-stu-id="5daa3-130">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="5daa3-131">Настоятельно рекомендуется использовать правила ASR с лицензией Windows E5 (или аналогичный SKU лицензирования), чтобы использовать расширенные возможности мониторинга и отчетности, доступные в [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint).</span><span class="sxs-lookup"><span data-stu-id="5daa3-131">It's highly recommended to use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint).</span></span> <span data-ttu-id="5daa3-132">Однако если у вас есть другая лицензия, например Windows Professional или Windows E3, которая не включает расширенные возможности мониторинга и отчетности, вы можете разработать собственные средства мониторинга и отчетности в верхней части событий, которые создаются на каждой конечной точке при запуске правил ASR (например, переададка событий).</span><span class="sxs-lookup"><span data-stu-id="5daa3-132">However, if you have another license, such as Windows Professional or Windows E3 that don't include advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (for example, Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="5daa3-133">Дополнительные дополнительные Windows см. Windows 10 [лицензирование](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) и руководство по лицензированию томов [для Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span><span class="sxs-lookup"><span data-stu-id="5daa3-133">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="5daa3-134">Вы можете включить правила уменьшения поверхности атаки с помощью любого из этих методов:</span><span class="sxs-lookup"><span data-stu-id="5daa3-134">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="5daa3-135">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5daa3-135">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="5daa3-136">Управление мобильными устройствами (MDM)</span><span class="sxs-lookup"><span data-stu-id="5daa3-136">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="5daa3-137">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5daa3-137">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="5daa3-138">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="5daa3-138">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="5daa3-139">PowerShell</span><span class="sxs-lookup"><span data-stu-id="5daa3-139">PowerShell</span></span>](#powershell)

<span data-ttu-id="5daa3-140">Enterprise, например Intune или Microsoft Endpoint Manager, рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="5daa3-140">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="5daa3-141">Enterprise управления на уровне будет переписать любые противоречивые параметры групповой политики или PowerShell при запуске.</span><span class="sxs-lookup"><span data-stu-id="5daa3-141">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="5daa3-142">Исключение файлов и папок из правил ASR</span><span class="sxs-lookup"><span data-stu-id="5daa3-142">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="5daa3-143">Вы можете исключить оценку файлов и папок большинством правил уменьшения поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="5daa3-143">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="5daa3-144">Это означает, что даже если правило ASR определяет файл или папку с вредоносным поведением, оно не будет блокировать работу файла.</span><span class="sxs-lookup"><span data-stu-id="5daa3-144">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="5daa3-145">Это потенциально может позволить небезопасным файлам запускать и заражать устройства.</span><span class="sxs-lookup"><span data-stu-id="5daa3-145">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="5daa3-146">Вы также можете исключить запуск правил ASR на основе хеш-файлов сертификатов и файлов, разрешив указанные индикаторы файла и сертификата Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5daa3-146">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="5daa3-147">[(См. управление индикаторами.)](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="5daa3-147">(See [Manage indicators](manage-indicators.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5daa3-148">Исключение файлов или папок может серьезно уменьшить защиту, предоставляемую правилами ASR.</span><span class="sxs-lookup"><span data-stu-id="5daa3-148">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="5daa3-149">Исключенные файлы будут разрешены для запуска, и отчет или событие не будут записаны.</span><span class="sxs-lookup"><span data-stu-id="5daa3-149">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="5daa3-150">Если правила ASR обнаруживают файлы, которые, как вы считаете, не следует обнаруживать, сначала следует использовать режим аудита для [проверки правила.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="5daa3-150">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>

<span data-ttu-id="5daa3-151">Вы можете указать отдельные файлы или папки (с помощью путей папок или полностью квалифицированных имен ресурсов), но вы не можете указать правила, к которым применяются исключения.</span><span class="sxs-lookup"><span data-stu-id="5daa3-151">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="5daa3-152">Исключение применяется только при старте исключенного приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="5daa3-152">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="5daa3-153">Например, если добавлено исключение для уже запущенной службы обновления, служба обновления будет продолжать запускать события до тех пор, пока служба не будет остановлена и перезапущена.</span><span class="sxs-lookup"><span data-stu-id="5daa3-153">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="5daa3-154">Правила ASR поддерживают переменные среды и подкарды.</span><span class="sxs-lookup"><span data-stu-id="5daa3-154">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="5daa3-155">Сведения об использовании подмастерьев см. в материалах [Use wildcards in the file name and folder path or extension exclusion lists.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="5daa3-155">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="5daa3-156">Следующие процедуры включения правил ASR включают инструкции по исключению файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="5daa3-156">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="5daa3-157">Intune</span><span class="sxs-lookup"><span data-stu-id="5daa3-157">Intune</span></span>

1. <span data-ttu-id="5daa3-158">Выберите **профили**  >  **конфигурации устройств.**</span><span class="sxs-lookup"><span data-stu-id="5daa3-158">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="5daa3-159">Выберите существующий профиль защиты конечной точки или создайте новый.</span><span class="sxs-lookup"><span data-stu-id="5daa3-159">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="5daa3-160">Чтобы создать новый, выберите **Создать профиль** и ввести сведения для этого профиля.</span><span class="sxs-lookup"><span data-stu-id="5daa3-160">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="5daa3-161">Для **типа профиля** выберите защиту **конечных точек.**</span><span class="sxs-lookup"><span data-stu-id="5daa3-161">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="5daa3-162">Если вы выбрали существующий профиль, выберите **свойства** и **выберите** Параметры.</span><span class="sxs-lookup"><span data-stu-id="5daa3-162">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="5daa3-163">В области **защиты конечной** точки выберите Защитник Windows **Exploit Guard,** а затем выберите **сокращение поверхности атаки.**</span><span class="sxs-lookup"><span data-stu-id="5daa3-163">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="5daa3-164">Выберите нужный параметр для каждого правила ASR.</span><span class="sxs-lookup"><span data-stu-id="5daa3-164">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="5daa3-165">В **соответствии с исключениями для** уменьшения поверхности атаки введите отдельные файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="5daa3-165">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="5daa3-166">Вы также можете выбрать **Импорт для** импорта CSV-файла, который содержит файлы и папки, чтобы исключить из правил ASR.</span><span class="sxs-lookup"><span data-stu-id="5daa3-166">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="5daa3-167">Каждая строка в CSV-файле должна быть отформатирована следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5daa3-167">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="5daa3-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="5daa3-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="5daa3-169">Выберите **ОК** на трех стемнах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5daa3-169">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="5daa3-170">Затем выберите **Создать,** если вы создаете новый файл защиты конечной точки или **сохраните,** если вы редактируете существующий.</span><span class="sxs-lookup"><span data-stu-id="5daa3-170">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mem"></a><span data-ttu-id="5daa3-171">MEM</span><span class="sxs-lookup"><span data-stu-id="5daa3-171">MEM</span></span>

<span data-ttu-id="5daa3-172">Вы можете использовать Microsoft Endpoint Manager (MEM) OMA-URI для настройки настраиваемых правил ASR.</span><span class="sxs-lookup"><span data-stu-id="5daa3-172">You can use Microsoft Endpoint Manager (MEM) OMA-URI to configure custom ASR rules.</span></span> <span data-ttu-id="5daa3-173">В следующей процедуре используется правило [Block abuse of exploited vulnerable signed drivers](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) for the example.</span><span class="sxs-lookup"><span data-stu-id="5daa3-173">The following procedure uses the rule [Block abuse of exploited vulnerable signed drivers](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) for the example.</span></span>

1. <span data-ttu-id="5daa3-174">Откройте центр администрирования Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="5daa3-174">Open the Microsoft Endpoint Manager (MEM) admin center.</span></span> <span data-ttu-id="5daa3-175">В **домашнем меню** нажмите  **кнопку Устройства,** выберите **профиль конфигурации** и нажмите **кнопку Создать профиль**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-175">In the **Home** menu, click  **Devices**, select **Configuration profile**, and then click **Create profile**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5daa3-176">![MEM Create Profile](images/mem01-create-profile.png)</span><span class="sxs-lookup"><span data-stu-id="5daa3-176">![MEM Create Profile](images/mem01-create-profile.png)</span></span>

2. <span data-ttu-id="5daa3-177">В **"Создание профиля"** в следующих двух списках выпадаемой части выберите следующее:</span><span class="sxs-lookup"><span data-stu-id="5daa3-177">In **Create a profile**, in the following two drop-down lists, select the following:</span></span>

   - <span data-ttu-id="5daa3-178">В **Платформе** выберите Windows 10 **и более поздней**</span><span class="sxs-lookup"><span data-stu-id="5daa3-178">In **Platform**, select **Windows 10 and later**</span></span>
   - <span data-ttu-id="5daa3-179">В **типе profile** выберите **Шаблоны**</span><span class="sxs-lookup"><span data-stu-id="5daa3-179">In **Profile type**, select **Templates**</span></span>

   <span data-ttu-id="5daa3-180">Выберите **настраиваемый,** а затем нажмите **кнопку Создать**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-180">Select **Custom**, and then click **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5daa3-181">![Атрибуты профилей правил MEM](images/mem02-profile-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="5daa3-181">![MEM rule profile attributes](images/mem02-profile-attributes.png)</span></span>

3. <span data-ttu-id="5daa3-182">Настраиваемый инструмент шаблона открывается для шага **1 Basics**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-182">The Custom template tool opens to step **1 Basics**.</span></span> <span data-ttu-id="5daa3-183">В **1 Basics,** in **Name** введите имя шаблона, а в **Описании** можно ввести описание (необязательно).</span><span class="sxs-lookup"><span data-stu-id="5daa3-183">In **1 Basics**, in **Name**, type a name for your template, and in **Description** you can type a description (optional).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5daa3-184">![Основные атрибуты MEM](images/mem03-1-basics.png)</span><span class="sxs-lookup"><span data-stu-id="5daa3-184">![MEM basic attributes](images/mem03-1-basics.png)</span></span>

4. <span data-ttu-id="5daa3-185">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-185">Click **Next**.</span></span> <span data-ttu-id="5daa3-186">Параметры **конфигурации шага 2 открываются.**</span><span class="sxs-lookup"><span data-stu-id="5daa3-186">Step **2 Configuration settings** opens.</span></span> <span data-ttu-id="5daa3-187">Для OMA-URI Параметры нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-187">For OMA-URI Settings, click **Add**.</span></span> <span data-ttu-id="5daa3-188">Теперь отображаются два варианта: **Добавить и** **экспортировать**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-188">Two options now appear: **Add** and **Export**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5daa3-189">![Параметры конфигурации MEM](images/mem04-2-configuration-settings.png)</span><span class="sxs-lookup"><span data-stu-id="5daa3-189">![MEM Configuration settings](images/mem04-2-configuration-settings.png)</span></span>

5. <span data-ttu-id="5daa3-190">Щелкните **Добавить** еще раз.</span><span class="sxs-lookup"><span data-stu-id="5daa3-190">Click **Add** again.</span></span> <span data-ttu-id="5daa3-191">Откроется **добавление строки OMA-URI Параметры.**</span><span class="sxs-lookup"><span data-stu-id="5daa3-191">The **Add Row OMA-URI Settings** opens.</span></span> <span data-ttu-id="5daa3-192">В **строке Добавить** строку сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="5daa3-192">In **Add Row**, do the following:</span></span>

   - <span data-ttu-id="5daa3-193">В **Name** введите имя правила.</span><span class="sxs-lookup"><span data-stu-id="5daa3-193">In **Name**, type a name for the rule.</span></span>
   - <span data-ttu-id="5daa3-194">В **описании** введите краткое описание.</span><span class="sxs-lookup"><span data-stu-id="5daa3-194">In **Description**, type a brief description.</span></span>
   - <span data-ttu-id="5daa3-195">В **OMA-URI** введите или введите определенную ссылку OMA-URI для правила, которое вы добавляете.</span><span class="sxs-lookup"><span data-stu-id="5daa3-195">In **OMA-URI**, type or paste the specific OMA-URI link for the rule that you are adding.</span></span>
   - <span data-ttu-id="5daa3-196">В **типе Data** выберите **строку**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-196">In **Data type**, select **String**.</span></span>
   - <span data-ttu-id="5daa3-197">В **Значение**, введите или введите значение GUID, знак и значение состояния без пробелов \= _(GUID=StateValue)._</span><span class="sxs-lookup"><span data-stu-id="5daa3-197">In **Value**, type or paste the GUID value, the \= sign and the State value with no spaces (_GUID=StateValue_).</span></span> <span data-ttu-id="5daa3-198">Где: {0: Отключение (Отключите правило ASR)}, {1: Блок (Включить правило ASR)}, {2: Аудит (Оценка влияния правила ASR на организацию при включении)}, {6 : Предупреждение (Включить правило ASR, но разрешить конечному пользователю обойти блокировку)}</span><span class="sxs-lookup"><span data-stu-id="5daa3-198">Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5daa3-199">![Конфигурация MEM OMA URI](images/mem05-add-row-oma-uri.png)</span><span class="sxs-lookup"><span data-stu-id="5daa3-199">![MEM OMA URI configuration](images/mem05-add-row-oma-uri.png)</span></span>

6. <span data-ttu-id="5daa3-200">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-200">Click **Save**.</span></span> <span data-ttu-id="5daa3-201">**Добавление строки** закрывается.</span><span class="sxs-lookup"><span data-stu-id="5daa3-201">**Add Row** closes.</span></span> <span data-ttu-id="5daa3-202">В **настраиваемом**, нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-202">In **Custom**, click **Next**.</span></span> <span data-ttu-id="5daa3-203">В **тегах 3 Scope** теги области необязательны.</span><span class="sxs-lookup"><span data-stu-id="5daa3-203">In step **3 Scope tags**, scope tags are optional.</span></span> <span data-ttu-id="5daa3-204">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="5daa3-204">Do one of the following:</span></span>

   - <span data-ttu-id="5daa3-205">Нажмите **кнопку Выберите теги Область,** выберите тег области (необязательный), а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-205">Click **Select Scope tags**, select the scope tag (optional) and then click **Next**.</span></span>
   - <span data-ttu-id="5daa3-206">Или нажмите **кнопку Далее**</span><span class="sxs-lookup"><span data-stu-id="5daa3-206">Or click **Next**</span></span>

7. <span data-ttu-id="5daa3-207">В **шаге 4 Назначения** в включенных группах **для** групп, которые необходимо применить это правило, выберите из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="5daa3-207">In step **4 Assignments**, in **Included Groups** - for the groups that you want this rule to apply - select from the following options:</span></span>

   - <span data-ttu-id="5daa3-208">**Добавление групп**</span><span class="sxs-lookup"><span data-stu-id="5daa3-208">**Add groups**</span></span>
   - <span data-ttu-id="5daa3-209">**Добавление всех пользователей**</span><span class="sxs-lookup"><span data-stu-id="5daa3-209">**Add all users**</span></span>
   - <span data-ttu-id="5daa3-210">**Добавление всех устройств**</span><span class="sxs-lookup"><span data-stu-id="5daa3-210">**Add all devices**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5daa3-211">![Назначения MEM](images/mem06-4-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="5daa3-211">![MEM assignments](images/mem06-4-assignments.png)</span></span>

8. <span data-ttu-id="5daa3-212">В **исключенных группах** выберите все группы, которые необходимо исключить из этого правила, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-212">In **Excluded groups**, select any groups that you want to exclude from this rule, and then click **Next**.</span></span>

9. <span data-ttu-id="5daa3-213">В **шаге 5 Правила применимости** для следующих параметров сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="5daa3-213">In step **5 Applicability Rules** for the following settings, do the following:</span></span>

   - <span data-ttu-id="5daa3-214">В **правиле** выберите либо **Назначение профиля, если**, или не **назначать профиль, если**</span><span class="sxs-lookup"><span data-stu-id="5daa3-214">In **Rule**, select either **Assign profile if**, or **Don’t assign profile if**</span></span>
   - <span data-ttu-id="5daa3-215">В **Свойстве** выберите свойство, к которому необходимо применить это правило</span><span class="sxs-lookup"><span data-stu-id="5daa3-215">In **Property**, select the property to which you want this rule to apply</span></span>
   - <span data-ttu-id="5daa3-216">В **Value** введите применимое значение или диапазон значений</span><span class="sxs-lookup"><span data-stu-id="5daa3-216">In **Value**, enter the applicable value or value range</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5daa3-217">![Правила применения MEM](images/mem07-5-applicability-rules.png)</span><span class="sxs-lookup"><span data-stu-id="5daa3-217">![MEM Applicability rules](images/mem07-5-applicability-rules.png)</span></span>

10. <span data-ttu-id="5daa3-218">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-218">Click **Next**.</span></span> <span data-ttu-id="5daa3-219">В **шаге 6 Обзор + создание**, просмотрите параметры и сведения, которые вы выбрали и ввели, а затем нажмите **кнопку Создать**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-219">In step **6 Review + create**, review the settings and information you have selected and entered, and then click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5daa3-220">![Обзор и создание MEM](images/mem08-6-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="5daa3-220">![MEM Review and create](images/mem08-6-review-create.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="5daa3-221">Правила активны и действуют в течение нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="5daa3-221">Rules are active and live within minutes.</span></span>

>[!NOTE]
> <span data-ttu-id="5daa3-222">Обработка конфликтов:</span><span class="sxs-lookup"><span data-stu-id="5daa3-222">Conflict handling:</span></span>
>
> <span data-ttu-id="5daa3-223">Если назначить устройству две разные политики ASR, то способ обработки конфликта — это правила, назначаемые разным состояниям, не существует управления конфликтами, и в результате происходит ошибка.</span><span class="sxs-lookup"><span data-stu-id="5daa3-223">If you assign a device two different ASR policies, the way conflict is handled is rules that are assigned different states, there is no conflict management in place, and the result is an error.</span></span>
>
> <span data-ttu-id="5daa3-224">Неконфликтные правила не привнося ошибку, и правило будет применяться правильно.</span><span class="sxs-lookup"><span data-stu-id="5daa3-224">Non-conflicting rules will not result in an error, and the rule will be applied correctly.</span></span> <span data-ttu-id="5daa3-225">В результате применяется первое правило и последующие правила, не конфликтующие, объединяются в политику.</span><span class="sxs-lookup"><span data-stu-id="5daa3-225">The result is that the first rule is applied, and subsequent non-conflicting rules are merged into the policy.</span></span>

## <a name="mdm"></a><span data-ttu-id="5daa3-226">MDM</span><span class="sxs-lookup"><span data-stu-id="5daa3-226">MDM</span></span>

<span data-ttu-id="5daa3-227">Используйте [поставщика служб конфигурации ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) для индивидуального включить и задать режим для каждого правила.</span><span class="sxs-lookup"><span data-stu-id="5daa3-227">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="5daa3-228">Ниже приводится пример для справки с использованием [значений GUID для правил ASR.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="5daa3-228">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="5daa3-229">Значения, которые необходимо включить (Block), отключить, предупредить или включить в режиме аудита:</span><span class="sxs-lookup"><span data-stu-id="5daa3-229">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="5daa3-230">0. Отключение (отключение правила ASR)</span><span class="sxs-lookup"><span data-stu-id="5daa3-230">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="5daa3-231">1. Блок (Включить правило ASR)</span><span class="sxs-lookup"><span data-stu-id="5daa3-231">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="5daa3-232">2. Аудит (Оцените, как правило ASR повлияет на организацию, если включено)</span><span class="sxs-lookup"><span data-stu-id="5daa3-232">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="5daa3-233">6. Предупреждение (Включить правило ASR, но разрешить конечному пользователю обойти блок).</span><span class="sxs-lookup"><span data-stu-id="5daa3-233">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="5daa3-234">Режим Warn теперь доступен для большинства правил ASR.</span><span class="sxs-lookup"><span data-stu-id="5daa3-234">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="5daa3-235">Для добавления исключений используйте поставщика служб конфигурации [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions.](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions)</span><span class="sxs-lookup"><span data-stu-id="5daa3-235">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="5daa3-236">Пример.</span><span class="sxs-lookup"><span data-stu-id="5daa3-236">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="5daa3-237">Обязательно введите значения OMA-URI без пробелов.</span><span class="sxs-lookup"><span data-stu-id="5daa3-237">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="5daa3-238">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5daa3-238">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="5daa3-239">В Microsoft Endpoint Configuration Manager перейдите в **службу Assets and Compliance**  >  **Endpoint Protection** Защитник Windows  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-239">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="5daa3-240">Выберите   >  **домашнее создание политики защиты от эксплойтов**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-240">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="5daa3-241">Введите имя и описание, выберите **сокращение поверхности атаки** и выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="5daa3-241">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="5daa3-242">Выберите правила, которые будут блокировать действия или аудит, и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-242">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="5daa3-243">Просмотрите параметры и выберите **Далее,** чтобы создать политику.</span><span class="sxs-lookup"><span data-stu-id="5daa3-243">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="5daa3-244">После создания политики **закрой**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-244">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="5daa3-245">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="5daa3-245">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="5daa3-246">Если управлять компьютерами и устройствами с помощью Intune, Configuration Manager или другой платформы управления на корпоративном уровне, программное обеспечение управления перезаписает все противоречивые параметры групповой политики при запуске.</span><span class="sxs-lookup"><span data-stu-id="5daa3-246">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="5daa3-247">Для этого на компьютере, управляющем групповыми политиками, откройте [Консоль управления групповой политикой](https://technet.microsoft.com/library/cc731212.aspx), щелкните правой кнопкой мыши нужный объект групповой политики и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-247">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="5daa3-248">В **редакторе управления групповыми политиками** перейдите к **конфигурации компьютера** и выберите **Административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-248">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="5daa3-249">Расширь **дерево, Windows компоненты антивирусная программа в Microsoft Defender**  >    >  **Exploit Guard в Microsoft Defender**  >  **атаки.**</span><span class="sxs-lookup"><span data-stu-id="5daa3-249">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="5daa3-250">Выберите **Настройка правил уменьшения поверхности атаки и** выберите **Включено.**</span><span class="sxs-lookup"><span data-stu-id="5daa3-250">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="5daa3-251">Затем можно установить отдельное состояние для каждого правила в разделе параметры.</span><span class="sxs-lookup"><span data-stu-id="5daa3-251">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="5daa3-252">Выберите **Показать...** и введите ID правила в столбце **Имя** значения и выбранное состояние в столбце **Значение** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5daa3-252">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="5daa3-253">0. Отключение (отключение правила ASR)</span><span class="sxs-lookup"><span data-stu-id="5daa3-253">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="5daa3-254">1. Блок (Включить правило ASR)</span><span class="sxs-lookup"><span data-stu-id="5daa3-254">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="5daa3-255">2. Аудит (Оцените, как правило ASR повлияет на организацию, если включено)</span><span class="sxs-lookup"><span data-stu-id="5daa3-255">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="5daa3-256">6. Предупреждение (Включить правило ASR, но разрешить конечному пользователю обойти блок)</span><span class="sxs-lookup"><span data-stu-id="5daa3-256">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="Правила ASR в групповой политике":::

5. <span data-ttu-id="5daa3-258">Чтобы исключить файлы и папки из правил ASR, выберите исключить файлы и пути из настройки правил уменьшения поверхности **Атаки** и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-258">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="5daa3-259">Выберите **Показать и** ввести каждый файл или папку в столбце Имя **значения.**</span><span class="sxs-lookup"><span data-stu-id="5daa3-259">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="5daa3-260">Введите **0** в **столбце Значение** для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="5daa3-260">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="5daa3-261">Не используйте кавычка, так как они не поддерживаются ни для столбца **value name,** ни для **столбца Value.**</span><span class="sxs-lookup"><span data-stu-id="5daa3-261">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="5daa3-262">PowerShell</span><span class="sxs-lookup"><span data-stu-id="5daa3-262">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="5daa3-263">Если управлять компьютерами и устройствами с помощью Intune, Configuration Manager или другой платформы управления на корпоративном уровне, программное обеспечение управления перезаписает все противоречивые параметры PowerShell при запуске.</span><span class="sxs-lookup"><span data-stu-id="5daa3-263">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="5daa3-264">Чтобы разрешить пользователям определять значение с помощью PowerShell, используйте параметр "User Defined" для правила в платформе управления.</span><span class="sxs-lookup"><span data-stu-id="5daa3-264">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="5daa3-265">Введите **powershell** в меню , щелкните **правой** кнопкой мыши Windows PowerShell выберите **Выполнить в качестве администратора**.</span><span class="sxs-lookup"><span data-stu-id="5daa3-265">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="5daa3-266">Введите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5daa3-266">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="5daa3-267">Чтобы включить правила ASR в режиме аудита, используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5daa3-267">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="5daa3-268">Чтобы включить правила ASR в режиме предупреждения, используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5daa3-268">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="5daa3-269">Чтобы включить злоупотребление asR Block для эксплуатируемого уязвимого подписанного драйвера, используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5daa3-269">To enable ASR Block abuse of exploited vulnerable signed drivers, use the following cmdlet:</span></span>

   ```PowerShell
   Add-MpPreference -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled
   ```

    <span data-ttu-id="5daa3-270">Чтобы отключить правила ASR, используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5daa3-270">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="5daa3-271">Необходимо указать состояние отдельно для каждого правила, но можно объединить правила и состояния в отдельном списке запятой.</span><span class="sxs-lookup"><span data-stu-id="5daa3-271">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="5daa3-272">В следующем примере будут включены первые два правила, третье правило будет отключено, а четвертое правило будет включено в режиме аудита:</span><span class="sxs-lookup"><span data-stu-id="5daa3-272">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="5daa3-273">Для добавления новых правил в существующий список можно также использовать глагол `Add-MpPreference` PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5daa3-273">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="5daa3-274">`Set-MpPreference` всегда переопишет существующий набор правил.</span><span class="sxs-lookup"><span data-stu-id="5daa3-274">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="5daa3-275">Если вы хотите добавить к существующему набору, используйте `Add-MpPreference` вместо этого.</span><span class="sxs-lookup"><span data-stu-id="5daa3-275">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="5daa3-276">Вы можете получить список правил и их текущего состояния с помощью `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="5daa3-276">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="5daa3-277">Чтобы исключить файлы и папки из правил ASR, используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5daa3-277">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="5daa3-278">Продолжайте использовать для добавления в список дополнительных файлов `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` и папок.</span><span class="sxs-lookup"><span data-stu-id="5daa3-278">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5daa3-279">Используйте `Add-MpPreference` для добавления или добавления приложений в список.</span><span class="sxs-lookup"><span data-stu-id="5daa3-279">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="5daa3-280">С помощью `Set-MpPreference` этого комлета будет переописывать существующий список.</span><span class="sxs-lookup"><span data-stu-id="5daa3-280">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5daa3-281">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="5daa3-281">Related articles</span></span>

- [<span data-ttu-id="5daa3-282">Уменьшение поверхностей атаки с помощью правил уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="5daa3-282">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="5daa3-283">Оценка уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="5daa3-283">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="5daa3-284">Сокращение направлений атак: вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="5daa3-284">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
