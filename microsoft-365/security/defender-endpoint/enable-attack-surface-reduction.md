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
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e6f3d6da2424b2b3b6b7c1f2c9973e4046d6e27f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689176"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="c4e4a-104">Включить правила сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="c4e4a-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c4e4a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c4e4a-105">**Applies to:**</span></span>
- [<span data-ttu-id="c4e4a-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c4e4a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c4e4a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4e4a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="c4e4a-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c4e4a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c4e4a-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="c4e4a-110">[Правила уменьшения поверхности](attack-surface-reduction.md) атаки (правила ASR) помогают предотвратить действия, которые вредоносные программы часто используют для компрометации устройств и сетей.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span> <span data-ttu-id="c4e4a-111">Вы можете установить правила ASR для устройств, работающих с любыми из следующих выпусков и версий Windows:</span><span class="sxs-lookup"><span data-stu-id="c4e4a-111">You can set ASR rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="c4e4a-112">Windows 10 Pro, [версия 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="c4e4a-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="c4e4a-113">Windows 10 Enterprise, [версия 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="c4e4a-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="c4e4a-114">Windows Server, [версия 1803 (полугодовой канал)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="c4e4a-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="c4e4a-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c4e4a-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="c4e4a-116">Каждое правило ASR содержит один из четырех параметров:</span><span class="sxs-lookup"><span data-stu-id="c4e4a-116">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="c4e4a-117">**Не настроен:** отключить правило ASR</span><span class="sxs-lookup"><span data-stu-id="c4e4a-117">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="c4e4a-118">**Блок**: Включить правило ASR</span><span class="sxs-lookup"><span data-stu-id="c4e4a-118">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="c4e4a-119">**Аудит.** Оцените, как правило ASR повлияет на организацию, если включено</span><span class="sxs-lookup"><span data-stu-id="c4e4a-119">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="c4e4a-120">**Предупреждение.** Включить правило ASR, но обойти блокировку конечному пользователю</span><span class="sxs-lookup"><span data-stu-id="c4e4a-120">**Warn**: Enable the ASR rule but alow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4e4a-121">В настоящее время режим предупреждения не поддерживается для трех правил ASR при настройке правил ASR в Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="c4e4a-121">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="c4e4a-122">Дополнительные дополнительные информации см. [в том, как не](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)поддерживается режим предупреждения.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-122">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="c4e4a-123">Настоятельно рекомендуется использовать правила ASR с лицензией Windows E5 (или аналогичный SKU лицензирования), чтобы использовать расширенные возможности мониторинга и отчетности, доступные в Microsoft Defender for Endpoint (Defender for [Endpoint).](https://docs.microsoft.com/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="c4e4a-123">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="c4e4a-124">Однако для других лицензий, таких как Windows Professional или E3, которые не имеют доступа к расширенным возможностям мониторинга и отчетности, можно разработать собственные средства мониторинга и отчетности в верхней части событий, которые создаются на каждой конечной точке при запуске правил ASR (например, переадмиссии событий).</span><span class="sxs-lookup"><span data-stu-id="c4e4a-124">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="c4e4a-125">Дополнительные информацию о лицензировании Windows см. в руководстве по лицензированию [Windows 10](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) и руководстве по лицензированию томов [для Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="c4e4a-125">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="c4e4a-126">Вы можете включить правила уменьшения поверхности атаки с помощью любого из этих методов:</span><span class="sxs-lookup"><span data-stu-id="c4e4a-126">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="c4e4a-127">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c4e4a-127">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="c4e4a-128">Управление мобильными устройствами (MDM)</span><span class="sxs-lookup"><span data-stu-id="c4e4a-128">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="c4e4a-129">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c4e4a-129">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="c4e4a-130">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="c4e4a-130">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="c4e4a-131">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4e4a-131">PowerShell</span></span>](#powershell)

<span data-ttu-id="c4e4a-132">Рекомендуется управление на корпоративном уровне, например Intune или Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-132">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="c4e4a-133">Управление на уровне предприятия перезаписывает любые противоречивые параметры групповой политики или PowerShell при запуске.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-133">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="c4e4a-134">Исключение файлов и папок из правил ASR</span><span class="sxs-lookup"><span data-stu-id="c4e4a-134">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="c4e4a-135">Вы можете исключить оценку файлов и папок большинством правил уменьшения поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-135">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="c4e4a-136">Это означает, что даже если правило ASR определяет файл или папку с вредоносным поведением, оно не будет блокировать работу файла.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-136">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="c4e4a-137">Это потенциально может позволить небезопасным файлам запускать и заражать устройства.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-137">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="c4e4a-138">Вы также можете исключить запуск правил ASR на основе хеш-файлов сертификатов и файлов, разрешив указанные индикаторы файла и сертификата Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-138">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="c4e4a-139">[(См. управление индикаторами.)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="c4e4a-139">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4e4a-140">Исключение файлов или папок может серьезно уменьшить защиту, предоставляемую правилами ASR.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-140">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="c4e4a-141">Исключенные файлы будут разрешены для запуска, и отчет или событие не будут записаны.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-141">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="c4e4a-142">Если правила ASR обнаруживают файлы, которые, как вы считаете, не следует обнаруживать, сначала следует использовать режим аудита для [проверки правила.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="c4e4a-142">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>


<span data-ttu-id="c4e4a-143">Вы можете указать отдельные файлы или папки (с помощью путей папок или полностью квалифицированных имен ресурсов), но вы не можете указать правила, к которым применяются исключения.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-143">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="c4e4a-144">Исключение применяется только при старте исключенного приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-144">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="c4e4a-145">Например, если добавлено исключение для уже запущенной службы обновления, служба обновления будет продолжать запускать события до тех пор, пока служба не будет остановлена и перезапущена.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-145">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="c4e4a-146">Правила ASR поддерживают переменные среды и подкарды.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-146">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="c4e4a-147">Сведения об использовании подмастерьев см. в материалах [Use wildcards in the file name and folder path or extension exclusion lists.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="c4e4a-147">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="c4e4a-148">Следующие процедуры включения правил ASR включают инструкции по исключению файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-148">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="c4e4a-149">Intune</span><span class="sxs-lookup"><span data-stu-id="c4e4a-149">Intune</span></span>

1. <span data-ttu-id="c4e4a-150">Выберите **профили**  >  **конфигурации устройств.**</span><span class="sxs-lookup"><span data-stu-id="c4e4a-150">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="c4e4a-151">Выберите существующий профиль защиты конечной точки или создайте новый.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-151">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="c4e4a-152">Чтобы создать новый, выберите **Создать профиль** и ввести сведения для этого профиля.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-152">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="c4e4a-153">Для **типа профиля** выберите защиту **конечных точек.**</span><span class="sxs-lookup"><span data-stu-id="c4e4a-153">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="c4e4a-154">Если вы выбрали существующий профиль, выберите **свойства** и выберите **Параметры.**</span><span class="sxs-lookup"><span data-stu-id="c4e4a-154">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="c4e4a-155">В области **защиты конечных** точек выберите Защитник Windows **Exploit Guard**, а затем выберите **сокращение поверхности атаки.**</span><span class="sxs-lookup"><span data-stu-id="c4e4a-155">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="c4e4a-156">Выберите нужный параметр для каждого правила ASR.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-156">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="c4e4a-157">В **соответствии с исключениями для** уменьшения поверхности атаки введите отдельные файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-157">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="c4e4a-158">Вы также можете выбрать **Импорт для** импорта CSV-файла, который содержит файлы и папки, чтобы исключить из правил ASR.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-158">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="c4e4a-159">Каждая строка в CSV-файле должна быть отформатирована следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c4e4a-159">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="c4e4a-160">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="c4e4a-160">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="c4e4a-161">Выберите **ОК** на трех стемнах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-161">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="c4e4a-162">Затем выберите **Создать,** если вы создаете новый файл защиты конечной точки или **сохраните,** если вы редактируете существующий.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-162">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="c4e4a-163">MDM</span><span class="sxs-lookup"><span data-stu-id="c4e4a-163">MDM</span></span>

<span data-ttu-id="c4e4a-164">Используйте [поставщика служб конфигурации ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) для индивидуального включить и задать режим для каждого правила.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-164">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="c4e4a-165">Ниже приводится пример для справки с использованием [значений GUID для правил ASR.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="c4e4a-165">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="c4e4a-166">Значения, которые необходимо включить (Block), отключить, предупредить или включить в режиме аудита:</span><span class="sxs-lookup"><span data-stu-id="c4e4a-166">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="c4e4a-167">0. Отключение (отключение правила ASR)</span><span class="sxs-lookup"><span data-stu-id="c4e4a-167">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="c4e4a-168">1. Блок (Включить правило ASR)</span><span class="sxs-lookup"><span data-stu-id="c4e4a-168">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="c4e4a-169">2. Аудит (Оцените, как правило ASR повлияет на организацию, если включено)</span><span class="sxs-lookup"><span data-stu-id="c4e4a-169">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="c4e4a-170">6. Предупреждение (Включить правило ASR, но разрешить конечному пользователю обойти блок)</span><span class="sxs-lookup"><span data-stu-id="c4e4a-170">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

<span data-ttu-id="c4e4a-171">Для добавления исключений используйте поставщика служб конфигурации [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions)</span><span class="sxs-lookup"><span data-stu-id="c4e4a-171">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="c4e4a-172">Пример.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-172">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="c4e4a-173">Обязательно введите значения OMA-URI без пробелов.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-173">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="c4e4a-174">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c4e4a-174">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="c4e4a-175">В Microsoft Endpoint Configuration Manager перейдите в **службу Assets and**  >  **Compliance Endpoint Protection** Защитник Windows Exploit  >  **Guard.**</span><span class="sxs-lookup"><span data-stu-id="c4e4a-175">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="c4e4a-176">Выберите   >  **домашнее создание политики защиты от эксплойтов**.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-176">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="c4e4a-177">Введите имя и описание, выберите **сокращение поверхности атаки** и выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="c4e4a-177">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="c4e4a-178">Выберите правила, которые будут блокировать действия или аудит, и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-178">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="c4e4a-179">Просмотрите параметры и выберите **Далее,** чтобы создать политику.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-179">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="c4e4a-180">После создания политики **закрой**.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-180">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="c4e4a-181">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="c4e4a-181">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="c4e4a-182">Если управлять компьютерами и устройствами с помощью Intune, Configuration Manager или другой платформы управления на корпоративном уровне, программное обеспечение управления перезаписает все противоречивые параметры групповой политики при запуске.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-182">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="c4e4a-183">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](https://technet.microsoft.com/library/cc731212.aspx)кнопкой мыши объект групповой политики, который необходимо настроить, и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-183">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="c4e4a-184">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="c4e4a-184">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="c4e4a-185">Расширь дерево до **компонентов**  >  **Windows, антивирус Microsoft Defender** Microsoft Defender Exploit Guard  >    >  **Attack.**</span><span class="sxs-lookup"><span data-stu-id="c4e4a-185">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="c4e4a-186">Выберите **Настройка правил уменьшения поверхности атаки и** выберите **Включено.**</span><span class="sxs-lookup"><span data-stu-id="c4e4a-186">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="c4e4a-187">Затем можно установить отдельное состояние для каждого правила в разделе параметры.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-187">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="c4e4a-188">Выберите **Показать...** и введите ID правила в столбце **Имя** значения и выбранное состояние в столбце **Значение** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c4e4a-188">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="c4e4a-189">0. Отключение (отключение правила ASR)</span><span class="sxs-lookup"><span data-stu-id="c4e4a-189">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="c4e4a-190">1. Блок (Включить правило ASR)</span><span class="sxs-lookup"><span data-stu-id="c4e4a-190">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="c4e4a-191">2. Аудит (Оцените, как правило ASR повлияет на организацию, если включено)</span><span class="sxs-lookup"><span data-stu-id="c4e4a-191">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="c4e4a-192">6. Предупреждение (Включить правило ASR, но разрешить конечному пользователю обойти блок)</span><span class="sxs-lookup"><span data-stu-id="c4e4a-192">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="Правила ASR в групповой политике":::

5. <span data-ttu-id="c4e4a-194">Чтобы исключить файлы и папки из правил ASR, выберите исключить файлы и пути из настройки правил уменьшения поверхности **Атаки** и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-194">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="c4e4a-195">Выберите **Показать и** ввести каждый файл или папку в столбце Имя **значения.**</span><span class="sxs-lookup"><span data-stu-id="c4e4a-195">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="c4e4a-196">Введите **0** в **столбце Значение** для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-196">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="c4e4a-197">Не используйте кавычка, так как они не поддерживаются ни для столбца **value name,** ни для **столбца Value.**</span><span class="sxs-lookup"><span data-stu-id="c4e4a-197">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="c4e4a-198">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4e4a-198">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="c4e4a-199">Если управлять компьютерами и устройствами с помощью Intune, Configuration Manager или другой платформы управления на корпоративном уровне, программное обеспечение управления перезаписает все противоречивые параметры PowerShell при запуске.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-199">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="c4e4a-200">Чтобы разрешить пользователям определять значение с помощью PowerShell, используйте параметр "User Defined" для правила в платформе управления.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-200">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="c4e4a-201">Введите **powershell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-201">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="c4e4a-202">Введите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c4e4a-202">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="c4e4a-203">Чтобы включить правила ASR в режиме аудита, используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c4e4a-203">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="c4e4a-204">Чтобы включить правила ASR в режиме предупреждения, используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c4e4a-204">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="c4e4a-205">Чтобы отключить правила ASR, используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c4e4a-205">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="c4e4a-206">Необходимо указать состояние отдельно для каждого правила, но можно объединить правила и состояния в отдельном списке запятой.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-206">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="c4e4a-207">В следующем примере будут включены первые два правила, третье правило будет отключено, а четвертое правило будет включено в режиме аудита:</span><span class="sxs-lookup"><span data-stu-id="c4e4a-207">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="c4e4a-208">Для добавления новых правил в существующий список можно также использовать глагол `Add-MpPreference` PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-208">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="c4e4a-209">`Set-MpPreference` всегда переопишет существующий набор правил.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-209">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="c4e4a-210">Если вы хотите добавить к существующему набору, используйте `Add-MpPreference` вместо этого.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-210">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="c4e4a-211">Вы можете получить список правил и их текущего состояния с помощью `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="c4e4a-211">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="c4e4a-212">Чтобы исключить файлы и папки из правил ASR, используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c4e4a-212">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="c4e4a-213">Продолжайте использовать для добавления в список дополнительных файлов `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` и папок.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-213">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c4e4a-214">Используйте `Add-MpPreference` для добавления или добавления приложений в список.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-214">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="c4e4a-215">С помощью `Set-MpPreference` этого комлета будет переописывать существующий список.</span><span class="sxs-lookup"><span data-stu-id="c4e4a-215">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c4e4a-216">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c4e4a-216">Related articles</span></span>

- [<span data-ttu-id="c4e4a-217">Уменьшение поверхностей атаки с помощью правил уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="c4e4a-217">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="c4e4a-218">Оценка уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="c4e4a-218">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="c4e4a-219">Сокращение направлений атак: вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="c4e4a-219">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
