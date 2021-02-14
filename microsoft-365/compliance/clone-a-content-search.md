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
# <a name="clone-a-content-search"></a>Клонирование поиска контента

Создание поиска контента в Центре соответствия требованиям в Office 365 или Microsoft 365, который выполняет поиск во многих почтовых ящиках или на сайтах SharePoint и OneDrive для бизнеса, может занять некоторое время. Указание сайтов для поиска также может привести к ошибкам при неправильном указании URL-адреса. Чтобы избежать этих проблем, можно использовать сценарий Windows PowerShell, указанный в этой статье, для быстрого клонирования существующего поиска контента. При клонации поиска создается новый поиск (с другим именем), содержащий те же свойства (например, расположения контента и поисковый запрос), что и исходный поиск. Затем можно изменить новый поиск, изменив запрос ключевого слова или диапазон дат, и запустить его.
  
Зачем клонировать поиск контента?
  
- Сравнение результатов различных поисковых запросов по ключевым словам, которые запускались в одном и том же местоположении контента.
    
- Чтобы вам не нужно было повторно ввести большое количество местоположений контента при создании нового поиска.
    
- Чтобы уменьшить размер результатов поиска. Например, если имеется поиск, который возвращает слишком много результатов для экспорта, можно клонировать поиск, а затем добавить условие поиска на основе диапазона дат, чтобы уменьшить число результатов поиска.
  
## <a name="script-information"></a>Сведения о скрипте

- Чтобы запустить сценарий, описанный в этой теме, необходимо быть членом группы ролей "Руководитель службы eDiscovery" в Центре безопасности & соответствия требованиям.
    
- Сценарий включает минимальную обработку ошибок. Основная цель сценария — быстро клонировать поиск контента.
    
- Сценарий создает новый поиск контента, но не начинает его.
    
- Этот сценарий учитывает, связан ли клонирование поиска контента с делом eDiscovery. Если поиск связан с делом, новый поиск также будет связан с тем же делом. Если существующий поиск не связан с делом, новый поиск  будет указан на странице "Поиск контента" в Центре соответствия требованиям. 
    
- Пример сценария, предоставленный в этом разделе, не поддерживается ни в одной стандартной программе или службе поддержки Майкрософт. Пример сценария приводится в виде "как есть", без каких-либо гарантий. Кроме того, корпорация Microsoft отказывается от всех подразумеваемых гарантий, включая в том числе все подразумеваемые гарантии пригодности для продажи или определенной цели. Все риски, возникающие в результате использования примера сценария и документации, берет на себя пользователь. Корпорация Майкрософт, ее штатные авторы и другие лица, принимающие участие в создании, подготовке и выпуске сценариев, ни при каких обстоятельствах не несут ответственность за какой-либо ущерб (в том числе, ущерб, вызванный потерей доходов предприятия, остановкой его работы, потерей бизнес-данных и другими материальными потерями), вызванный использованием или неспособностью использовать примеры сценариев и документацию, даже если корпорации Майкрософт известно о возможности нанесения такого ущерба.
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>Шаг 1. Запуск сценария для клонирования поиска

Сценарий на этом этапе создает новый поиск контента путем клонирования существующего. При запуске этого сценария вам будут предложены следующие сведения:
  
- **Учетные данные пользователя** — сценарий будет использовать ваши учетные данные для подключения к Центру безопасности & соответствия требованиям для вашей организации с помощью Windows PowerShell. Как было сказано ранее, для запуска сценария необходимо быть членом группы ролей "Менеджер по обнаружению электронных данных" в Центре безопасности & compCompliance Center. 
    
- **Имя существующего поиска —** это поиск контента, который необходимо клонировать. 
    
- **Имя** нового поиска, который будет создан. Если оставить это значение пустым, сценарий создаст имя нового поиска, основанное на имени клонирования поиска. 
    
Клонирование поиска:
  
1. Сохраните следующий текст в Windows PowerShell сценария с помощью суффикса имени файла PS1; например, `CloneSearch.ps1` .
    
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

2. Откройте Windows PowerShell и перейдите в папку, в которой сохранен сценарий.
    
3. Запустите сценарий; Например:
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. При запросе учетных данных введите свой адрес электронной почты и пароль, а затем нажмите кнопку **"ОК".**
    
5. Введите следующую информацию при запросе сценария. Введите каждый фрагмент информации и нажмите **ввод.**
    
    - Имя существующего поиска.
    
    - Имя нового поиска.
    
    Сценарий создает новый поиск контента, но не начинает его. Это дает возможность изменить и запустить поиск на следующем этапе. Вы можете просмотреть свойства нового поиска, вы можете запускать с помощью cmdlet **Get-ComplianceSearch** или на странице поиска контента или **eDiscovery** в Центре соответствия требованиям в зависимости от того, связан ли новый поиск с делом.  
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>Шаг 2. Изменение и запуск клонированного поиска в Центре соответствия требованиям

После выполнения сценария для клонирования существующего поиска контента необходимо перейти в Центр соответствия требованиям для редактирования и запуска нового поиска. Как было сказано ранее, поиск можно изменить, изменив поисковый запрос по ключевым словам и добавив или удалив условия поиска. Дополнительные сведения см. в указанных ниже статьях.
  
- [Поиск контента в Office 365](content-search.md)
    
- [Запросы ключевых слов и условия поиска контента](keyword-queries-and-search-conditions.md)
    
- [Дела eDiscovery](ediscovery-cases.md)
