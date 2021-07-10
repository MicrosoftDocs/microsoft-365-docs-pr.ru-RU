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
description: Сведения о сборе диагностических сведений об обнаружении электронных данных для случая поддержки Майкрософт.
ms.openlocfilehash: b2441e0b7af8a82e24a8acca9e000e954e1c8964
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362598"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="131ce-103">Сбор диагностических сведений об обнаружении электронных данных</span><span class="sxs-lookup"><span data-stu-id="131ce-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="131ce-104">Иногда инженерам службы поддержки Майкрософт требуется конкретная информация о вашей проблеме при открытии дела поддержки, связанного с core eDiscovery или Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="131ce-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="131ce-105">В этой статье содержится руководство по сбору диагностических сведений, которые помогут инженерам в расследовании и устранении проблем.</span><span class="sxs-lookup"><span data-stu-id="131ce-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="131ce-106">Как правило, вам не нужно собирать эти сведения, пока не будет предложено сделать это инженером службы поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="131ce-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="131ce-107">Результаты из смещает и диагностические сведения, описанные в этой статье, могут включать конфиденциальные сведения о судебных разбирательствах или внутренних расследованиях в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="131ce-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="131ce-108">Перед отправкой необработанных диагностических сведений в службу поддержки Майкрософт необходимо просмотреть эти сведения и отредактовать любые конфиденциальные сведения (например, имена или другие сведения о сторонами судебного разбирательства или расследования), заменив их `XXXXXXX` на .</span><span class="sxs-lookup"><span data-stu-id="131ce-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="131ce-109">Использование этого метода также указывает инженеру службы поддержки Майкрософт, что сведения были отредактировали.</span><span class="sxs-lookup"><span data-stu-id="131ce-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="131ce-110">Сбор диагностических сведений для core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="131ce-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="131ce-111">Сбор диагностических сведений для core eDiscovery основан на cmdlet, поэтому вам придется использовать центр & powerShell.</span><span class="sxs-lookup"><span data-stu-id="131ce-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="131ce-112">В следующих примерах PowerShell будут запускаться комлеты, а затем сохранять выход в заданный текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="131ce-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="131ce-113">В большинстве случаев поддержки необходимо выполнить только одну из этих команд.</span><span class="sxs-lookup"><span data-stu-id="131ce-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="131ce-114">Чтобы запустить следующие cmdlets, подключите [к безопасности & </span> Центра соответствия требованиям PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="131ce-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="131ce-115">После подключения запустите одну или несколько следующих команд и замените их фактическими именами объектов.</span><span class="sxs-lookup"><span data-stu-id="131ce-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="131ce-116">После просмотра сгенерированного текстового файла и отредактирований конфиденциальных сведений отправьте его инженеру службы поддержки Майкрософт, который работает над вашим делом.</span><span class="sxs-lookup"><span data-stu-id="131ce-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="131ce-117">Вы также можете запустить команды в этом разделе для сбора диагностических  сведений для поиска и экспорта, перечисленных на странице поиска контента в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="131ce-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="131ce-118">Сбор сведений об поисковых запросах</span><span class="sxs-lookup"><span data-stu-id="131ce-118">Collect information about searches</span></span>

<span data-ttu-id="131ce-119">Следующая команда собирает сведения, полезные при расследовании проблем с поиском контента или поиском, связанным с делом об обнаружении основных данных.</span><span class="sxs-lookup"><span data-stu-id="131ce-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="131ce-120">Сбор сведений о действиях поиска</span><span class="sxs-lookup"><span data-stu-id="131ce-120">Collect information about search actions</span></span>

<span data-ttu-id="131ce-121">Следующая команда собирает сведения для расследования проблем с предварительным просмотром, экспортом или чисткой результатов поиска контента или поиска, связанного с делом core eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="131ce-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="131ce-122">Вы можете определить имя действия поиска, щелкнув экспорт, указанный на вкладке **Экспорт.** Чтобы определить имена действий предварительного просмотра и очистки, можно запустить комдлет **Get-ComplianceSearchAction,** чтобы отобразить список всех действий.</span><span class="sxs-lookup"><span data-stu-id="131ce-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="131ce-123">Формат имени действия поиска строится с помощью приложения или имени `_Preview` `_Export` `_Purge` соответствующего поиска.</span><span class="sxs-lookup"><span data-stu-id="131ce-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="131ce-124">Сбор сведений о удерживаемой информации об обнаружении электронных данных</span><span class="sxs-lookup"><span data-stu-id="131ce-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="131ce-125">Если удержание электронных данных, связанное с случаем core eDiscovery, работает не так, как ожидалось, запустите следующую команду для сбора сведений о политике удержания случая и связанном правиле удержания кейсов для удержания электронных данных.</span><span class="sxs-lookup"><span data-stu-id="131ce-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="131ce-126">Имя *политики удержания case* в следующей команде то же самое, что и имя удержания электронных обнаружений.</span><span class="sxs-lookup"><span data-stu-id="131ce-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="131ce-127">Это имя можно определить на вкладке **"Удерживает"** в случае с core eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="131ce-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="131ce-128">Сбор всех сведений о случаях</span><span class="sxs-lookup"><span data-stu-id="131ce-128">Collect all case information</span></span>

<span data-ttu-id="131ce-129">Иногда не видно, какие сведения требуется службе поддержки Майкрософт для расследования проблемы.</span><span class="sxs-lookup"><span data-stu-id="131ce-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="131ce-130">В этой ситуации можно собрать всю информацию по диагностике для дела об обнаружении основных электронных данных.</span><span class="sxs-lookup"><span data-stu-id="131ce-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="131ce-131">Имя *случая core eDiscovery* в следующей команде такое же, как и имя случая, отображаемого на странице **Core eDiscovery** в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="131ce-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{$_|fl;"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="131ce-132">Сбор диагностических сведений для Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="131ce-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="131ce-133">Вкладка **Параметры** в Advanced eDiscovery позволяет быстро скопировать диагностические сведения для дела.</span><span class="sxs-lookup"><span data-stu-id="131ce-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="131ce-134">Диагностические сведения сохраняются в буфере обмена, чтобы можно было вклеить ее в текстовый файл и отправить в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="131ce-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="131ce-135">Перейдите [https://compliance.microsoft.com](https://compliance.microsoft.com/) к и нажмите **кнопку Показать все > eDiscovery > Advanced**.</span><span class="sxs-lookup"><span data-stu-id="131ce-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="131ce-136">Выберите случай, а затем нажмите **Параметры** вкладку.</span><span class="sxs-lookup"><span data-stu-id="131ce-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="131ce-137">В **соответствии с сведениями о случае** щелкните **Выберите**.</span><span class="sxs-lookup"><span data-stu-id="131ce-137">Under **Case Information**, click **Select**.</span></span>

4. <span data-ttu-id="131ce-138">На странице вылетов щелкните **Скопируйте диагностические сведения,** чтобы скопировать сведения в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="131ce-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="131ce-139">Откройте текстовый файл (Блокнот) и вклеите сведения в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="131ce-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="131ce-140">Сохраните текстовый файл и назовите его чем-то `AeD Diagnostic Info YYYY.MM.DD` похожим (например, `AeD Diagnostic Info 2020.11.03` ).</span><span class="sxs-lookup"><span data-stu-id="131ce-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="131ce-141">После проверки файла и отредактиста конфиденциальной информации отправьте его инженеру службы поддержки Майкрософт, который работает над вашим делом.</span><span class="sxs-lookup"><span data-stu-id="131ce-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>
