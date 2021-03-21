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
description: Используйте скрипт PowerShell в этой статье, чтобы быстро клонировать существующий поиск контента в центре соответствия требованиям в Office 365 или Microsoft 365.
ms.openlocfilehash: c64cec2415819dc53f30c303c241e3902f34017d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918065"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="ee8f6-103">Клонирование поиска контента</span><span class="sxs-lookup"><span data-stu-id="ee8f6-103">Clone a Content Search</span></span>

<span data-ttu-id="ee8f6-104">Создание поиска контента в центре соответствия требованиям в Office 365 или Microsoft 365, который выполняет поиск по многим почтовым ящикам или сайтам SharePoint и OneDrive для бизнеса, может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-104">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches many mailboxes or SharePoint and OneDrive for Business sites can take a while.</span></span> <span data-ttu-id="ee8f6-105">Указание сайтов для поиска также может быть подвержено ошибкам, если вы неправильно напечатали URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-105">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="ee8f6-106">Чтобы избежать этих проблем, можно использовать сценарий Windows PowerShell в этой статье, чтобы быстро клонировать существующий поиск контента.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-106">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="ee8f6-107">При клонации поиска создается новый поиск (с другим именем), содержащий те же свойства (например, расположение контента и запрос поиска), что и исходный поиск.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-107">When you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="ee8f6-108">Затем вы можете изменить новый поиск, изменив ключевой запрос или диапазон дат, и запустить его.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-108">Then you can edit the new search by changing the keyword query or the date range, and run it.</span></span>
  
<span data-ttu-id="ee8f6-109">Зачем клонировать поиск контента?</span><span class="sxs-lookup"><span data-stu-id="ee8f6-109">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="ee8f6-110">Чтобы сравнить результаты различных поисковых запросов по ключевым словам, которые работают в одном и том же месте контента.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-110">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="ee8f6-111">Чтобы уберечь вас от необходимости повторного размещения большого количества местоположений контента при создании нового поиска.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-111">To save you from having to reenter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="ee8f6-112">Уменьшение размера результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-112">To decrease the size of the search results.</span></span> <span data-ttu-id="ee8f6-113">Например, если у вас есть поиск, который возвращает слишком много результатов для экспорта, вы можете клонировать поиск, а затем добавить условие поиска на основе диапазона дат, чтобы уменьшить количество результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-113">For example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="script-information"></a><span data-ttu-id="ee8f6-114">Сведения о скриптах</span><span class="sxs-lookup"><span data-stu-id="ee8f6-114">Script information</span></span>

- <span data-ttu-id="ee8f6-115">Для выполнения сценария, описанного в этой теме, необходимо быть членом группы ролей диспетчера электронных данных в Центре & безопасности.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-115">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="ee8f6-116">Сценарий включает минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-116">The script includes minimal error handling.</span></span> <span data-ttu-id="ee8f6-117">Основная цель сценария — быстро клонировать поиск контента.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-117">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="ee8f6-118">Скрипт создает новый поиск контента, но не начинает его.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-118">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="ee8f6-119">В этом сценарии учитывается, связан ли поиск контента, который вы клонирование, с делом об обнаружении электронных обнаружений.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-119">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="ee8f6-120">Если поиск связан с делом, новый поиск также будет связан с тем же случаем.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-120">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="ee8f6-121">Если существующий поиск не связан с делом, новый поиск  будет указан на странице поиска контента в центре соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-121">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="ee8f6-122">Пример сценария, представленного в этом разделе, не поддерживается ни в рамках стандартной программы поддержки Майкрософт, ни в службе.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-122">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="ee8f6-123">Пример сценария приводится в виде "как есть", без каких-либо гарантий.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-123">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="ee8f6-124">Кроме того, корпорация Microsoft отказывается от всех подразумеваемых гарантий, включая в том числе все подразумеваемые гарантии пригодности для продажи или определенной цели.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-124">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="ee8f6-125">Все риски, возникающие в результате использования примера сценария и документации, берет на себя пользователь.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-125">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="ee8f6-126">Корпорация Майкрософт, ее штатные авторы и другие лица, принимающие участие в создании, подготовке и выпуске сценариев, ни при каких обстоятельствах не несут ответственность за какой-либо ущерб (в том числе, ущерб, вызванный потерей доходов предприятия, остановкой его работы, потерей бизнес-данных и другими материальными потерями), вызванный использованием или неспособностью использовать примеры сценариев и документацию, даже если корпорации Майкрософт известно о возможности нанесения такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-126">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="ee8f6-127">Шаг 1. Запуск сценария для клонирования поиска</span><span class="sxs-lookup"><span data-stu-id="ee8f6-127">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="ee8f6-128">Скрипт на этом шаге создаст новый поиск контента путем клонирования существующего.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-128">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="ee8f6-129">При запуске этого сценария вам будут предложены следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="ee8f6-129">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="ee8f6-130">**Учетные данные** пользователей . Скрипт будет использовать учетные данные для подключения к Центру & безопасности для вашей организации с Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-130">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your organization with Windows PowerShell.</span></span> <span data-ttu-id="ee8f6-131">Как уже говорилось ранее, для запуска сценария необходимо быть членом группы ролей диспетчера электронных данных в центре & compCompliance.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-131">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="ee8f6-132">**Имя существующего поиска** — это поиск контента, который необходимо клонировать.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-132">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="ee8f6-133">**Имя** нового поиска, который будет создан. Если оставить это значение пустым, скрипт создаст имя для нового поиска, основанное на имени клонирования поиска.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-133">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="ee8f6-134">Клонировать поиск:</span><span class="sxs-lookup"><span data-stu-id="ee8f6-134">To clone a search:</span></span>
  
1. <span data-ttu-id="ee8f6-135">Сохраните следующий текст в Windows PowerShell скрипта с помощью суффикса .ps1; например, `CloneSearch.ps1` .</span><span class="sxs-lookup"><span data-stu-id="ee8f6-135">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
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

2. <span data-ttu-id="ee8f6-136">Откройте Windows PowerShell и перейдите в папку, в которой сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-136">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="ee8f6-137">Запустите сценарий; Например:</span><span class="sxs-lookup"><span data-stu-id="ee8f6-137">Run the script; for example:</span></span>
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="ee8f6-138">При запросе учетных данных введите адрес электронной почты и пароль, а затем нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-138">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="ee8f6-139">Ввод следующих сведений по запросу скрипта.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-139">Enter following information when prompted by the script.</span></span> <span data-ttu-id="ee8f6-140">Введите каждый элемент информации и нажмите кнопку **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-140">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="ee8f6-141">Имя существующего поиска.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-141">The name of the existing search.</span></span>
    
    - <span data-ttu-id="ee8f6-142">Имя нового поиска.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-142">The name of the new search.</span></span>
    
    <span data-ttu-id="ee8f6-143">Скрипт создает новый поиск контента, но не начинает его.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-143">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="ee8f6-144">Это дает возможность изменить и выполнить поиск на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-144">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="ee8f6-145">Свойства нового поиска можно просмотреть, заняв кодлет **Get-ComplianceSearch** или  переехав на страницу поиска контента или поиска электронных данных в центре соответствия требованиям, в зависимости от того, связан ли новый поиск с случаем. </span><span class="sxs-lookup"><span data-stu-id="ee8f6-145">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="ee8f6-146">Шаг 2. Изменить и запустить клонированный поиск в центре соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="ee8f6-146">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="ee8f6-147">После запуска скрипта для клонирования существующего поиска контента следующий шаг — перейти в центр соответствия требованиям для редактирования и запуска нового поиска.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-147">After you run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="ee8f6-148">Как уже говорилось ранее, можно изменить поиск, изменив запрос поиска по ключевым словам и добавив или удалив условия поиска.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-148">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="ee8f6-149">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="ee8f6-149">For more information, see:</span></span>
  
- [<span data-ttu-id="ee8f6-150">Поиск контента в Office 365</span><span class="sxs-lookup"><span data-stu-id="ee8f6-150">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="ee8f6-151">Запросы ключевых слов и условия поиска контента</span><span class="sxs-lookup"><span data-stu-id="ee8f6-151">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="ee8f6-152">дела об обнаружении электронной почты</span><span class="sxs-lookup"><span data-stu-id="ee8f6-152">eDiscovery cases</span></span>](./get-started-core-ediscovery.md)