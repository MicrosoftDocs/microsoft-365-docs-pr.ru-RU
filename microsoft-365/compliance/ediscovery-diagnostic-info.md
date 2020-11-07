---
title: Сбор диагностических данных обнаружения электронных данных
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
description: Узнайте, как собирать диагностические данные обнаружения электронных данных для обращения в службу поддержки Майкрософт.
ms.openlocfilehash: 107309748e2f27b50be5f8e8fc76afcb693989f9
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944400"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="d7d27-103">Сбор диагностических данных обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="d7d27-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="d7d27-104">Иногда инженерам службы поддержки Майкрософт требуются определенные сведения о возникшей ошибке при открытии обращения в службу поддержки, связанной с основными обнаружениями электронных данных или расширенным обнаружением электронных данных.</span><span class="sxs-lookup"><span data-stu-id="d7d27-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="d7d27-105">В этой статье приводятся рекомендации по сбору диагностических данных, которые помогут инженерам службы поддержки исследовать и устранять проблемы.</span><span class="sxs-lookup"><span data-stu-id="d7d27-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="d7d27-106">Как правило, вам не нужно собирать эти сведения, пока не запрашивается специалист службы поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d7d27-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7d27-107">В выходных данных командлетов и диагностических данных, описанных в этой статье, могут быть конфиденциальные сведения о судебном разбирательстве или внутреннем расследовании в Организации.</span><span class="sxs-lookup"><span data-stu-id="d7d27-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="d7d27-108">Перед отправкой необработанных диагностических данных в службу поддержки Майкрософт необходимо просмотреть сведения и исправить все конфиденциальные сведения (например, имена или другие сведения о субъектах для судебного разбирательства или расследования), заменив их на `XXXXXXX` .</span><span class="sxs-lookup"><span data-stu-id="d7d27-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="d7d27-109">Использование этого метода также указывает специалисту службы поддержки Майкрософт, что информация была отредактировал.</span><span class="sxs-lookup"><span data-stu-id="d7d27-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="d7d27-110">Сбор диагностических данных для основного обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="d7d27-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="d7d27-111">Сбор диагностических данных для основного обнаружения электронных данных выполняется на основе командлетов, поэтому необходимо использовать оболочку безопасности & центра соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d7d27-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="d7d27-112">Следующие примеры PowerShell выполняют командлеты, а затем сохраняют выходные данные в указанном текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="d7d27-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="d7d27-113">В большинстве случаев поддержки вам нужно выполнить только одну из этих команд.</span><span class="sxs-lookup"><span data-stu-id="d7d27-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="d7d27-114">Чтобы выполнить следующие командлеты, [подключитесь к PowerShell </span> центра безопасности & соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="d7d27-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="d7d27-115">После подключения выполните одну или несколько из приведенных ниже команд и заменяйте заполнители фактическими именами объектов.</span><span class="sxs-lookup"><span data-stu-id="d7d27-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="d7d27-116">После просмотра созданного текстового файла и редактинг конфиденциальной информации отправьте его специалисту службы поддержки Майкрософт, работающему в вашем случае.</span><span class="sxs-lookup"><span data-stu-id="d7d27-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="d7d27-117">Кроме того, вы можете выполнить команды в этом разделе, чтобы собрать диагностические сведения для поиска и экспортов, перечисленных на странице " **Поиск контента** " в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d7d27-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="d7d27-118">Сбор сведений об операциях поиска</span><span class="sxs-lookup"><span data-stu-id="d7d27-118">Collect information about searches</span></span>

<span data-ttu-id="d7d27-119">Следующая команда собирает сведения, которые полезны при исследовании проблем с поиском контента или поиском, связанным с основным вариантом обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="d7d27-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="d7d27-120">Сбор сведений о действиях поиска</span><span class="sxs-lookup"><span data-stu-id="d7d27-120">Collect information about search actions</span></span>

<span data-ttu-id="d7d27-121">Следующая команда собирает информацию для изучения проблем с предварительным просмотром, экспортом или удалением результатов поиска контента или поиска, связанных с основным вариантом обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="d7d27-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="d7d27-122">Чтобы определить имя действия поиска, щелкните Экспорт, указанный на вкладке **экспорты** . Чтобы определить имена действий для предварительного просмотра и очистки, можно выполнить командлет **Get – ComplianceSearchAction** , чтобы отобразить список всех действий.</span><span class="sxs-lookup"><span data-stu-id="d7d27-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="d7d27-123">Формат имени действия поиска создается путем добавления `_Preview` `_Export` или `_Purge` к имени соответствующего поиска.</span><span class="sxs-lookup"><span data-stu-id="d7d27-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="d7d27-124">Сбор сведений о удержаниях обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="d7d27-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="d7d27-125">Если удержание обнаружения электронных данных, связанное с основным вариантом обнаружения электронных данных, не работает должным образом, выполните следующую команду, чтобы собрать сведения о политике удержания обращений и правиле удержания связанных с ними правил для удержания обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="d7d27-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="d7d27-126">*Имя политики удержания обращений* в следующей команде совпадает с именем удержания обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="d7d27-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="d7d27-127">Это имя можно определить на вкладках **удержания** в основном случае обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="d7d27-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="d7d27-128">Сбор всех сведений о обращениях</span><span class="sxs-lookup"><span data-stu-id="d7d27-128">Collect all case information</span></span>

<span data-ttu-id="d7d27-129">Иногда не видно, какие сведения требуются службе поддержки Майкрософт для изучения вашей проблемы.</span><span class="sxs-lookup"><span data-stu-id="d7d27-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="d7d27-130">В этом случае вы можете собрать все диагностические сведения для основного случая обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="d7d27-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="d7d27-131">*Основное имя случая обнаружения электронных* данных в следующей команде совпадает с именем варианта, отображаемого на **основной странице обнаружения электронных** данных в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d7d27-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="d7d27-132">Сбор диагностических данных для расширенного обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="d7d27-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="d7d27-133">На вкладке **Параметры** в расширенном случае обнаружения электронных данных можно быстро скопировать диагностические сведения для случая.</span><span class="sxs-lookup"><span data-stu-id="d7d27-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="d7d27-134">Диагностические сведения сохраняются в буфере обмена, поэтому их можно вставить в текстовый файл и отправить в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d7d27-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="d7d27-135">Перейдите в раздел [https://compliance.microsoft.com](https://compliance.microsoft.com/) и выберите пункт **показать все > обнаружения электронных данных > Advanced**.</span><span class="sxs-lookup"><span data-stu-id="d7d27-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="d7d27-136">Выберите вариант, а затем перейдите на вкладку **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="d7d27-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="d7d27-137">В разделе **сведения об обращении** нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="d7d27-137">Under **Case Information** , click **Select**.</span></span>

4. <span data-ttu-id="d7d27-138">В раскрывающейся странице щелкните **Копировать диагностические сведения** , чтобы скопировать сведения в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="d7d27-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="d7d27-139">Откройте текстовый файл (в Блокноте) и вставьте данные в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="d7d27-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="d7d27-140">Сохраните текстовый файл и присвойте ему имя `AeD Diagnostic Info YYYY.MM.DD` (например, `AeD Diagnostic Info 2020.11.03` ).</span><span class="sxs-lookup"><span data-stu-id="d7d27-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="d7d27-141">Проверив файл и редактинг конфиденциальную информацию, отправьте его в службу поддержки Майкрософт, которая работает в вашем случае.</span><span class="sxs-lookup"><span data-stu-id="d7d27-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>
