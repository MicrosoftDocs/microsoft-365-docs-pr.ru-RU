---
title: Сбор диагностических сведений об обнаружении электронных данных
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Сведения о том, как собирать диагностические сведения об обнаружении электронных данных для дела службы поддержки Майкрософт.
ms.openlocfilehash: 107309748e2f27b50be5f8e8fc76afcb693989f9
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944400"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="24014-103">Сбор диагностических сведений об обнаружении электронных данных</span><span class="sxs-lookup"><span data-stu-id="24014-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="24014-104">Иногда инженерам службы поддержки Майкрософт требуется определенная информация о вашей проблеме при открытии дела поддержки, связанного с core eDiscovery или Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="24014-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="24014-105">В этой статье содержится руководство по сбору диагностических сведений, которые помогут инженерам службы поддержки изучить и устранить проблемы.</span><span class="sxs-lookup"><span data-stu-id="24014-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="24014-106">Как правило, вам не нужно собирать эти сведения, пока не будет предложено сделать это от инженера службы поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="24014-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24014-107">Выходные данные, которые содержатся в этих данных, могут включать конфиденциальную информацию о судебных разбирательствах или внутренних расследованиях в организации.</span><span class="sxs-lookup"><span data-stu-id="24014-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="24014-108">Перед отправкой необработанных диагностических сведений в службу поддержки Майкрософт необходимо просмотреть эти сведения и отредакциовать любую конфиденциальную информацию (например, имена или другую информацию о лицах для судебного разбирательства или расследования), заменив их на `XXXXXXX` .</span><span class="sxs-lookup"><span data-stu-id="24014-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="24014-109">Использование этого метода также указывает инженеру службы поддержки Майкрософт, что сведения были отредактировали.</span><span class="sxs-lookup"><span data-stu-id="24014-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="24014-110">Сбор диагностических сведений для core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="24014-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="24014-111">Сбор диагностической информации для Core eDiscovery основан на использовании & PowerShell в Центре безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="24014-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="24014-112">В следующих примерах PowerShell будут запускаться и сохраняться выходные данные в указанном текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="24014-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="24014-113">В большинстве случаев необходимо выполнить только одну из этих команд.</span><span class="sxs-lookup"><span data-stu-id="24014-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="24014-114">Чтобы выполнить следующие cmdlets, подключите [к PowerShell </span> ](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)Центра & безопасности.</span><span class="sxs-lookup"><span data-stu-id="24014-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="24014-115">После подключения запустите одну или несколько из следующих команд и замените их фактическими именами объектов.</span><span class="sxs-lookup"><span data-stu-id="24014-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="24014-116">После просмотра сгенерированного текстового файла и отредактки конфиденциальных сведений отправьте его инженеру службы поддержки Майкрософт, который работает над вашим делом.</span><span class="sxs-lookup"><span data-stu-id="24014-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="24014-117">Вы также можете выполнить команды, указанные в этом разделе, для  сбора диагностических сведений об поисковых запросах и экспорте, перечисленных на странице "Поиск контента" в Центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24014-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="24014-118">Сбор сведений о поиске</span><span class="sxs-lookup"><span data-stu-id="24014-118">Collect information about searches</span></span>

<span data-ttu-id="24014-119">Следующая команда собирает сведения, полезные при расследовании проблем с поиском контента или поиском, связанным с основным делом eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="24014-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="24014-120">Сбор сведений о действиях поиска</span><span class="sxs-lookup"><span data-stu-id="24014-120">Collect information about search actions</span></span>

<span data-ttu-id="24014-121">Следующая команда собирает сведения, чтобы исследовать проблемы с предварительным просмотром, экспортом или сгружение результатов поиска контента или поиска, связанного с основным делом eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="24014-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="24014-122">Вы можете определить имя действия поиска, щелкнув экспорт, указанный на вкладке **"Экспорт".** Чтобы определить имена действий предварительного просмотра и очистки, вы можете выполнить для отображения списка всех действий с его целью выполнить выполнение слета **Get-ComplianceSearchAction.**</span><span class="sxs-lookup"><span data-stu-id="24014-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="24014-123">Формат имени действия поиска составляется с помощью приложения или имени `_Preview` `_Export` `_Purge` соответствующего поиска.</span><span class="sxs-lookup"><span data-stu-id="24014-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="24014-124">Сбор сведений об обнаружении электронных данных</span><span class="sxs-lookup"><span data-stu-id="24014-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="24014-125">Если удержание eDiscovery, связанное с основным делом eDiscovery, не работает должным образом, запустите следующую команду, чтобы собрать сведения о политике удержания дела и связанном с ним правиле удержания дела для удержания eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="24014-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="24014-126">Имя *политики удержания дела* в следующей команде такое же, как имя удержания eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="24014-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="24014-127">Это имя можно идентифицировать на вкладке **"Содержит"** в случае core eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="24014-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="24014-128">Сбор всех сведений о делах</span><span class="sxs-lookup"><span data-stu-id="24014-128">Collect all case information</span></span>

<span data-ttu-id="24014-129">Иногда не очевидно, какие сведения требуются службе поддержки Майкрософт для изучения вашей проблемы.</span><span class="sxs-lookup"><span data-stu-id="24014-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="24014-130">В этой ситуации можно собрать все диагностические сведения для основного дела eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="24014-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="24014-131">Имя основного дела *eDiscovery* в следующей команде такое же, как имя дела, которое отображается на странице Core **eDiscovery** в Центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24014-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="24014-132">Сбор диагностических сведений для Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="24014-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="24014-133">Вкладка **"Параметры"** в случае Advanced eDiscovery позволяет быстро скопировать диагностические сведения для дела.</span><span class="sxs-lookup"><span data-stu-id="24014-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="24014-134">Диагностические сведения сохраняются в буфер обмена, чтобы вы могли в paste it to a text file and send to Microsoft Support.</span><span class="sxs-lookup"><span data-stu-id="24014-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="24014-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click Show all > **eDiscovery > Advanced**.</span><span class="sxs-lookup"><span data-stu-id="24014-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="24014-136">Выберите дело и щелкните вкладку **"Параметры".**</span><span class="sxs-lookup"><span data-stu-id="24014-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="24014-137">В **области "Сведения о деле"** нажмите **кнопку "Выбрать".**</span><span class="sxs-lookup"><span data-stu-id="24014-137">Under **Case Information**, click **Select**.</span></span>

4. <span data-ttu-id="24014-138">На странице "Flyout" щелкните **"Копировать диагностические сведения",** чтобы скопировать эти сведения в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="24014-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="24014-139">Откройте текстовый файл (в Блокноте) и в paste the information in the text file.</span><span class="sxs-lookup"><span data-stu-id="24014-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="24014-140">Сохраните текстовый файл и назовите его как-то `AeD Diagnostic Info YYYY.MM.DD` вроде (например, `AeD Diagnostic Info 2020.11.03` ).</span><span class="sxs-lookup"><span data-stu-id="24014-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="24014-141">После просмотра файла и отредактки конфиденциальных сведений отправьте его инженеру службы поддержки Майкрософт, который работает над вашим делом.</span><span class="sxs-lookup"><span data-stu-id="24014-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>
