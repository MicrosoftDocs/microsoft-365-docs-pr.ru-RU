---
title: Клонирование поиска контента
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: С помощью сценария Windows PowerShell в этой статье можно быстро клонировать существующий поиск контента в центре соответствия требованиям в Office 365 или Microsoft 365. При клонировании поиска создается новый поиск (с новым именем), содержащий те же свойства, что и исходный Поиск. Затем можно изменить новый поиск (изменив запрос ключевых слов или диапазон дат), а затем запустить его.
ms.openlocfilehash: 25aa5d6a1ba19f697a6ccf474e055faf6a19d6bd
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "38687512"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="a9018-105">Клонирование поиска контента</span><span class="sxs-lookup"><span data-stu-id="a9018-105">Clone a Content Search</span></span>

<span data-ttu-id="a9018-106">Создание поиска контента в центре соответствия требованиям в Office 365 или Microsoft 365, который выполняет поиск в большом объеме почтовых ящиков или на сайтах SharePoint и OneDrive для бизнеса, может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="a9018-106">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches a lot of mailboxes or SharePoint and OneDrive for Business sites can take awhile.</span></span> <span data-ttu-id="a9018-107">Указание сайтов для поиска также может привести к ошибкам при ошибочном вводе URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="a9018-107">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="a9018-108">Чтобы избежать этих проблем, можно использовать сценарий Windows PowerShell, описанный в этой статье, для быстрой клонирования существующего поиска контента.</span><span class="sxs-lookup"><span data-stu-id="a9018-108">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="a9018-109">При клонировании поиска создается новый поиск (с другим именем), содержащий те же свойства (такие как расположения контента и поисковый запрос), что и в исходном поиске.</span><span class="sxs-lookup"><span data-stu-id="a9018-109">When a you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="a9018-110">После этого вы можете изменить новый поиск (изменив запрос ключевых слов или диапазон дат) и запуская его.</span><span class="sxs-lookup"><span data-stu-id="a9018-110">Then you can edit the new search (by changing the keyword query or the date range) and run it.</span></span>
  
<span data-ttu-id="a9018-111">Зачем выполнять поиск по клону контента?</span><span class="sxs-lookup"><span data-stu-id="a9018-111">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="a9018-112">Чтобы сравнить результаты разных запросов поиска ключевых слов, выполните одно и то же расположение контента.</span><span class="sxs-lookup"><span data-stu-id="a9018-112">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="a9018-113">Для сохранения необходимости повторного ввода большого количества расположений контента при создании нового поиска.</span><span class="sxs-lookup"><span data-stu-id="a9018-113">To save you from having to re-enter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="a9018-114">Для уменьшения размера результатов поиска; Например, если у вас есть поиск, возвращающий слишком много результатов для экспорта, можно клонировать Поиск, а затем добавить условие поиска на основе диапазона дат, чтобы уменьшить количество результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="a9018-114">To decrease the size of the search results; for example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="a9018-115">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="a9018-115">Before you begin</span></span>

- <span data-ttu-id="a9018-116">Для запуска сценария, описанного в этом разделе, необходимо быть членом группы ролей "Диспетчер обнаружения электронных данных" в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a9018-116">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="a9018-117">Сценарий включает в себя минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="a9018-117">The script includes minimal error handling.</span></span> <span data-ttu-id="a9018-118">Основной целью сценария является быстрая клонирование поиска контента.</span><span class="sxs-lookup"><span data-stu-id="a9018-118">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="a9018-119">Сценарий создает новый поиск контента, но не запускает его.</span><span class="sxs-lookup"><span data-stu-id="a9018-119">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="a9018-120">В этом сценарии учитывается, связан ли составной контент, для которого выполняется клонирование, с вариантом обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="a9018-120">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="a9018-121">Если поиск связан с обращением, новый поиск также будет связан с тем же случаем.</span><span class="sxs-lookup"><span data-stu-id="a9018-121">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="a9018-122">Если существующий Поиск не связан с обращением, новый поиск будет указан на странице " **Поиск контента** " в центре соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a9018-122">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="a9018-123">Пример сценария, представленный в этом разделе, не поддерживается ни в одной из стандартных программ или услуг поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a9018-123">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="a9018-124">Пример сценария предоставляется без каких-либо гарантий.</span><span class="sxs-lookup"><span data-stu-id="a9018-124">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="a9018-125">Кроме того, корпорация Майкрософт отказывается от всех косвенных гарантий товарного качества.</span><span class="sxs-lookup"><span data-stu-id="a9018-125">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="a9018-126">Весь риск, возникающий из примера использования или производительности примера сценария и документации, остается без вас.</span><span class="sxs-lookup"><span data-stu-id="a9018-126">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="a9018-127">Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации сценариев, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров сценариев или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="a9018-127">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="a9018-128">Шаг 1: запуск скрипта для клонирования поиска</span><span class="sxs-lookup"><span data-stu-id="a9018-128">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="a9018-129">Скрипт на этом шаге создаст новый поиск контента, выполнив клонирование существующего контента.</span><span class="sxs-lookup"><span data-stu-id="a9018-129">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="a9018-130">При выполнении этого сценария будут выведены следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a9018-130">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="a9018-131">**Ваши учетные данные пользователя** — сценарий будет использовать ваши учетные данные для подключения к центру безопасности & соответствия требованиям для вашей организации Office 365 с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9018-131">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your Office 365 organization with Windows PowerShell.</span></span> <span data-ttu-id="a9018-132">Как было сказано ранее, для запуска скрипта необходимо быть членом группы ролей "Диспетчер обнаружения электронных данных" в центре безопасности & Компкомплианце.</span><span class="sxs-lookup"><span data-stu-id="a9018-132">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="a9018-133">**Имя существующего поиска** — это поиск контента, который необходимо клонировать.</span><span class="sxs-lookup"><span data-stu-id="a9018-133">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="a9018-134">**Имя нового поиска, который будет создан** — если оставить это значение пустым, сценарий создаст имя для нового поиска, основанное на имени клонированного запроса.</span><span class="sxs-lookup"><span data-stu-id="a9018-134">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="a9018-135">Для клонирования поиска:</span><span class="sxs-lookup"><span data-stu-id="a9018-135">To clone a search:</span></span>
  
1. <span data-ttu-id="a9018-136">Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `CloneSearch.ps1`.</span><span class="sxs-lookup"><span data-stu-id="a9018-136">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
  ```powershell
  # This PowerShell script clones an existing Content Search in the Office 365 security and compliance center.
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

2. <span data-ttu-id="a9018-137">Откройте Windows PowerShell и перейдите к папке, в которой вы сохранили сценарий.</span><span class="sxs-lookup"><span data-stu-id="a9018-137">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="a9018-138">Запуск скрипта; Например:</span><span class="sxs-lookup"><span data-stu-id="a9018-138">Run the script; for example:</span></span>
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="a9018-139">При запросе учетных данных введите свой адрес электронной почты и пароль, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a9018-139">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="a9018-140">Введите следующие сведения, когда запрашивается сценарий.</span><span class="sxs-lookup"><span data-stu-id="a9018-140">Enter following information when prompted by the script.</span></span> <span data-ttu-id="a9018-141">Введите все данные и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="a9018-141">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="a9018-142">Имя существующего поиска.</span><span class="sxs-lookup"><span data-stu-id="a9018-142">The name of the existing search.</span></span>
    
    - <span data-ttu-id="a9018-143">Имя нового поиска.</span><span class="sxs-lookup"><span data-stu-id="a9018-143">The name of the new search.</span></span>
    
    <span data-ttu-id="a9018-144">Сценарий создает новый поиск контента, но не запускает его.</span><span class="sxs-lookup"><span data-stu-id="a9018-144">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="a9018-145">Это дает возможность изменить и запустить поиск на следующем этапе.</span><span class="sxs-lookup"><span data-stu-id="a9018-145">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="a9018-146">Свойства нового поиска можно просмотреть, выполнив командлет **Get-ComplianceSearch** или перейдя на страницу **Поиск контента** или **Обнаружение электронных** данных в центре соответствия требованиям в зависимости от того, связан ли новый поиск с обращением.</span><span class="sxs-lookup"><span data-stu-id="a9018-146">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether or not the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="a9018-147">Шаг 2: изменение и выполнение клонированного поиска в центре соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a9018-147">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="a9018-148">После выполнения сценария для клонирования существующего поиска контента необходимо перейти в центр соответствия требованиям, чтобы изменить и выполнить новый поиск.</span><span class="sxs-lookup"><span data-stu-id="a9018-148">After the you've run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="a9018-149">Как было сказано ранее, вы можете изменить поиск, изменив запрос поиска ключевых слов и добавив или удалив условия поиска.</span><span class="sxs-lookup"><span data-stu-id="a9018-149">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="a9018-150">Подробнее:</span><span class="sxs-lookup"><span data-stu-id="a9018-150">For more information, see:</span></span>
  
- [<span data-ttu-id="a9018-151">Поиск контента в Office 365</span><span class="sxs-lookup"><span data-stu-id="a9018-151">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="a9018-152">Запросы ключевых слов и условия поиска контента</span><span class="sxs-lookup"><span data-stu-id="a9018-152">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="a9018-153">случаи обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="a9018-153">eDiscovery cases</span></span>](ediscovery-cases.md)
