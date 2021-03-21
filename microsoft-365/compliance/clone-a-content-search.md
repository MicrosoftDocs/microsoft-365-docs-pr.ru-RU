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
# <a name="clone-a-content-search"></a>Клонирование поиска контента

Создание поиска контента в центре соответствия требованиям в Office 365 или Microsoft 365, который выполняет поиск по многим почтовым ящикам или сайтам SharePoint и OneDrive для бизнеса, может занять некоторое время. Указание сайтов для поиска также может быть подвержено ошибкам, если вы неправильно напечатали URL-адрес. Чтобы избежать этих проблем, можно использовать сценарий Windows PowerShell в этой статье, чтобы быстро клонировать существующий поиск контента. При клонации поиска создается новый поиск (с другим именем), содержащий те же свойства (например, расположение контента и запрос поиска), что и исходный поиск. Затем вы можете изменить новый поиск, изменив ключевой запрос или диапазон дат, и запустить его.
  
Зачем клонировать поиск контента?
  
- Чтобы сравнить результаты различных поисковых запросов по ключевым словам, которые работают в одном и том же месте контента.
    
- Чтобы уберечь вас от необходимости повторного размещения большого количества местоположений контента при создании нового поиска.
    
- Уменьшение размера результатов поиска. Например, если у вас есть поиск, который возвращает слишком много результатов для экспорта, вы можете клонировать поиск, а затем добавить условие поиска на основе диапазона дат, чтобы уменьшить количество результатов поиска.
  
## <a name="script-information"></a>Сведения о скриптах

- Для выполнения сценария, описанного в этой теме, необходимо быть членом группы ролей диспетчера электронных данных в Центре & безопасности.
    
- Сценарий включает минимальную обработку ошибок. Основная цель сценария — быстро клонировать поиск контента.
    
- Скрипт создает новый поиск контента, но не начинает его.
    
- В этом сценарии учитывается, связан ли поиск контента, который вы клонирование, с делом об обнаружении электронных обнаружений. Если поиск связан с делом, новый поиск также будет связан с тем же случаем. Если существующий поиск не связан с делом, новый поиск  будет указан на странице поиска контента в центре соответствия требованиям. 
    
- Пример сценария, представленного в этом разделе, не поддерживается ни в рамках стандартной программы поддержки Майкрософт, ни в службе. Пример сценария приводится в виде "как есть", без каких-либо гарантий. Кроме того, корпорация Microsoft отказывается от всех подразумеваемых гарантий, включая в том числе все подразумеваемые гарантии пригодности для продажи или определенной цели. Все риски, возникающие в результате использования примера сценария и документации, берет на себя пользователь. Корпорация Майкрософт, ее штатные авторы и другие лица, принимающие участие в создании, подготовке и выпуске сценариев, ни при каких обстоятельствах не несут ответственность за какой-либо ущерб (в том числе, ущерб, вызванный потерей доходов предприятия, остановкой его работы, потерей бизнес-данных и другими материальными потерями), вызванный использованием или неспособностью использовать примеры сценариев и документацию, даже если корпорации Майкрософт известно о возможности нанесения такого ущерба.
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>Шаг 1. Запуск сценария для клонирования поиска

Скрипт на этом шаге создаст новый поиск контента путем клонирования существующего. При запуске этого сценария вам будут предложены следующие сведения:
  
- **Учетные данные** пользователей . Скрипт будет использовать учетные данные для подключения к Центру & безопасности для вашей организации с Windows PowerShell. Как уже говорилось ранее, для запуска сценария необходимо быть членом группы ролей диспетчера электронных данных в центре & compCompliance. 
    
- **Имя существующего поиска** — это поиск контента, который необходимо клонировать. 
    
- **Имя** нового поиска, который будет создан. Если оставить это значение пустым, скрипт создаст имя для нового поиска, основанное на имени клонирования поиска. 
    
Клонировать поиск:
  
1. Сохраните следующий текст в Windows PowerShell скрипта с помощью суффикса .ps1; например, `CloneSearch.ps1` .
    
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

4. При запросе учетных данных введите адрес электронной почты и пароль, а затем нажмите **кнопку ОК**.
    
5. Ввод следующих сведений по запросу скрипта. Введите каждый элемент информации и нажмите кнопку **Ввод**.
    
    - Имя существующего поиска.
    
    - Имя нового поиска.
    
    Скрипт создает новый поиск контента, но не начинает его. Это дает возможность изменить и выполнить поиск на следующем шаге. Свойства нового поиска можно просмотреть, заняв кодлет **Get-ComplianceSearch** или  переехав на страницу поиска контента или поиска электронных данных в центре соответствия требованиям, в зависимости от того, связан ли новый поиск с случаем.  
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>Шаг 2. Изменить и запустить клонированный поиск в центре соответствия требованиям

После запуска скрипта для клонирования существующего поиска контента следующий шаг — перейти в центр соответствия требованиям для редактирования и запуска нового поиска. Как уже говорилось ранее, можно изменить поиск, изменив запрос поиска по ключевым словам и добавив или удалив условия поиска. Дополнительные сведения см. в указанных ниже статьях.
  
- [Поиск контента в Office 365](content-search.md)
    
- [Запросы ключевых слов и условия поиска контента](keyword-queries-and-search-conditions.md)
    
- [дела об обнаружении электронной почты](./get-started-core-ediscovery.md)