---
title: Клонирование поиска контента
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: Используйте сценарий PowerShell в этой статье, чтобы быстро клонировать существующий поиск контента в Центре соответствия требованиям в Office 365 или Microsoft 365.
ms.openlocfilehash: 9bc9329d31ae27736bdcd399c555f5d70bb9c761
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357907"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="d07e4-103">Клонирование поиска контента</span><span class="sxs-lookup"><span data-stu-id="d07e4-103">Clone a Content Search</span></span>

<span data-ttu-id="d07e4-104">Создание поиска контента в Центре соответствия требованиям в Office 365 или Microsoft 365, который выполняет поиск во многих почтовых ящиках или на сайтах SharePoint и OneDrive для бизнеса, может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="d07e4-104">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches many mailboxes or SharePoint and OneDrive for Business sites can take a while.</span></span> <span data-ttu-id="d07e4-105">Указание сайтов для поиска также может привести к ошибкам при неправильном указании URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="d07e4-105">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="d07e4-106">Чтобы избежать этих проблем, можно использовать сценарий Windows PowerShell, указанный в этой статье, для быстрого клонирования существующего поиска контента.</span><span class="sxs-lookup"><span data-stu-id="d07e4-106">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="d07e4-107">При клонации поиска создается новый поиск (с другим именем), содержащий те же свойства (например, расположения контента и поисковый запрос), что и исходный поиск.</span><span class="sxs-lookup"><span data-stu-id="d07e4-107">When you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="d07e4-108">Затем можно изменить новый поиск, изменив запрос ключевого слова или диапазон дат, и запустить его.</span><span class="sxs-lookup"><span data-stu-id="d07e4-108">Then you can edit the new search by changing the keyword query or the date range, and run it.</span></span>
  
<span data-ttu-id="d07e4-109">Зачем клонировать поиск контента?</span><span class="sxs-lookup"><span data-stu-id="d07e4-109">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="d07e4-110">Сравнение результатов различных поисковых запросов по ключевым словам, которые запускались в одном и том же местоположении контента.</span><span class="sxs-lookup"><span data-stu-id="d07e4-110">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="d07e4-111">Чтобы вам не нужно было повторно ввести большое количество местоположений контента при создании нового поиска.</span><span class="sxs-lookup"><span data-stu-id="d07e4-111">To save you from having to reenter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="d07e4-112">Чтобы уменьшить размер результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="d07e4-112">To decrease the size of the search results.</span></span> <span data-ttu-id="d07e4-113">Например, если имеется поиск, который возвращает слишком много результатов для экспорта, можно клонировать поиск, а затем добавить условие поиска на основе диапазона дат, чтобы уменьшить число результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="d07e4-113">For example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="script-information"></a><span data-ttu-id="d07e4-114">Сведения о скрипте</span><span class="sxs-lookup"><span data-stu-id="d07e4-114">Script information</span></span>

- <span data-ttu-id="d07e4-115">Чтобы запустить сценарий, описанный в этой теме, необходимо быть членом группы ролей "Руководитель службы eDiscovery" в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d07e4-115">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="d07e4-116">Сценарий включает минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="d07e4-116">The script includes minimal error handling.</span></span> <span data-ttu-id="d07e4-117">Основная цель сценария — быстро клонировать поиск контента.</span><span class="sxs-lookup"><span data-stu-id="d07e4-117">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="d07e4-118">Сценарий создает новый поиск контента, но не начинает его.</span><span class="sxs-lookup"><span data-stu-id="d07e4-118">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="d07e4-119">Этот сценарий учитывает, связан ли клонирование поиска контента с делом eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="d07e4-119">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="d07e4-120">Если поиск связан с делом, новый поиск также будет связан с тем же делом.</span><span class="sxs-lookup"><span data-stu-id="d07e4-120">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="d07e4-121">Если существующий поиск не связан с делом, новый поиск  будет указан на странице "Поиск контента" в Центре соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d07e4-121">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="d07e4-122">Пример сценария, предоставленный в этом разделе, не поддерживается ни в одной стандартной программе или службе поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d07e4-122">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="d07e4-123">Пример сценария приводится в виде "как есть", без каких-либо гарантий.</span><span class="sxs-lookup"><span data-stu-id="d07e4-123">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="d07e4-124">Кроме того, корпорация Microsoft отказывается от всех подразумеваемых гарантий, включая в том числе все подразумеваемые гарантии пригодности для продажи или определенной цели.</span><span class="sxs-lookup"><span data-stu-id="d07e4-124">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="d07e4-125">Все риски, возникающие в результате использования примера сценария и документации, берет на себя пользователь.</span><span class="sxs-lookup"><span data-stu-id="d07e4-125">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="d07e4-126">Корпорация Майкрософт, ее штатные авторы и другие лица, принимающие участие в создании, подготовке и выпуске сценариев, ни при каких обстоятельствах не несут ответственность за какой-либо ущерб (в том числе, ущерб, вызванный потерей доходов предприятия, остановкой его работы, потерей бизнес-данных и другими материальными потерями), вызванный использованием или неспособностью использовать примеры сценариев и документацию, даже если корпорации Майкрософт известно о возможности нанесения такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="d07e4-126">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="d07e4-127">Шаг 1. Запуск сценария для клонирования поиска</span><span class="sxs-lookup"><span data-stu-id="d07e4-127">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="d07e4-128">Сценарий на этом этапе создает новый поиск контента путем клонирования существующего.</span><span class="sxs-lookup"><span data-stu-id="d07e4-128">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="d07e4-129">При запуске этого сценария вам будут предложены следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d07e4-129">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="d07e4-130">**Учетные данные пользователя** — сценарий будет использовать ваши учетные данные для подключения к Центру безопасности & соответствия требованиям для вашей организации с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d07e4-130">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your organization with Windows PowerShell.</span></span> <span data-ttu-id="d07e4-131">Как было сказано ранее, для запуска сценария необходимо быть членом группы ролей "Менеджер по обнаружению электронных данных" в Центре безопасности & compCompliance Center.</span><span class="sxs-lookup"><span data-stu-id="d07e4-131">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="d07e4-132">**Имя существующего поиска —** это поиск контента, который необходимо клонировать.</span><span class="sxs-lookup"><span data-stu-id="d07e4-132">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="d07e4-133">**Имя** нового поиска, который будет создан. Если оставить это значение пустым, сценарий создаст имя нового поиска, основанное на имени клонирования поиска.</span><span class="sxs-lookup"><span data-stu-id="d07e4-133">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="d07e4-134">Клонирование поиска:</span><span class="sxs-lookup"><span data-stu-id="d07e4-134">To clone a search:</span></span>
  
1. <span data-ttu-id="d07e4-135">Сохраните следующий текст в Windows PowerShell сценария с помощью суффикса имени файла PS1; например, `CloneSearch.ps1` .</span><span class="sxs-lookup"><span data-stu-id="d07e4-135">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
  ```powershell
  # This PowerShell script clones an existing content search in the Security &amp; Compliance Center.
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. <span data-ttu-id="d07e4-136">Откройте Windows PowerShell и перейдите в папку, в которой сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="d07e4-136">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="d07e4-137">Запустите сценарий; Например:</span><span class="sxs-lookup"><span data-stu-id="d07e4-137">Run the script; for example:</span></span>
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="d07e4-138">При запросе учетных данных введите свой адрес электронной почты и пароль, а затем нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="d07e4-138">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="d07e4-139">Введите следующую информацию при запросе сценария.</span><span class="sxs-lookup"><span data-stu-id="d07e4-139">Enter following information when prompted by the script.</span></span> <span data-ttu-id="d07e4-140">Введите каждый фрагмент информации и нажмите **ввод.**</span><span class="sxs-lookup"><span data-stu-id="d07e4-140">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="d07e4-141">Имя существующего поиска.</span><span class="sxs-lookup"><span data-stu-id="d07e4-141">The name of the existing search.</span></span>
    
    - <span data-ttu-id="d07e4-142">Имя нового поиска.</span><span class="sxs-lookup"><span data-stu-id="d07e4-142">The name of the new search.</span></span>
    
    <span data-ttu-id="d07e4-143">Сценарий создает новый поиск контента, но не начинает его.</span><span class="sxs-lookup"><span data-stu-id="d07e4-143">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="d07e4-144">Это дает возможность изменить и запустить поиск на следующем этапе.</span><span class="sxs-lookup"><span data-stu-id="d07e4-144">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="d07e4-145">Вы можете просмотреть свойства нового поиска, вы можете запускать с помощью cmdlet **Get-ComplianceSearch** или на странице поиска контента или **eDiscovery** в Центре соответствия требованиям в зависимости от того, связан ли новый поиск с делом. </span><span class="sxs-lookup"><span data-stu-id="d07e4-145">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="d07e4-146">Шаг 2. Изменение и запуск клонированного поиска в Центре соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="d07e4-146">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="d07e4-147">После выполнения сценария для клонирования существующего поиска контента необходимо перейти в Центр соответствия требованиям для редактирования и запуска нового поиска.</span><span class="sxs-lookup"><span data-stu-id="d07e4-147">After you run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="d07e4-148">Как было сказано ранее, поиск можно изменить, изменив поисковый запрос по ключевым словам и добавив или удалив условия поиска.</span><span class="sxs-lookup"><span data-stu-id="d07e4-148">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="d07e4-149">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="d07e4-149">For more information, see:</span></span>
  
- [<span data-ttu-id="d07e4-150">Поиск контента в Office 365</span><span class="sxs-lookup"><span data-stu-id="d07e4-150">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="d07e4-151">Запросы ключевых слов и условия поиска контента</span><span class="sxs-lookup"><span data-stu-id="d07e4-151">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="d07e4-152">Дела eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d07e4-152">eDiscovery cases</span></span>](ediscovery-cases.md)
