---
title: Клонирование поиска контента
f1.keywords:
- NOCSH
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
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: С помощью сценария Windows PowerShell в этой статье можно быстро клонировать существующий поиск контента в центре соответствия требованиям в Office 365 или Microsoft 365.
ms.openlocfilehash: 013a3cd04b665e1da800638a2335adb034878a4a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035651"
---
# <a name="clone-a-content-search"></a>Клонирование поиска контента

Создание поиска контента в центре соответствия требованиям в Office 365 или Microsoft 365, который выполняет поиск во многих почтовых ящиках или SharePoint и OneDrive для бизнеса, может занять некоторое время. Указание сайтов для поиска также может привести к ошибкам при ошибочном вводе URL-адреса. Чтобы избежать этих проблем, можно использовать сценарий Windows PowerShell, описанный в этой статье, для быстрой клонирования существующего поиска контента. При клонировании поиска создается новый поиск (с другим именем), содержащий те же свойства (такие как расположения контента и поисковый запрос), что и в исходном поиске. Затем вы можете изменить новый поиск, изменив запрос ключевого слова или диапазон дат и запуская его.
  
Зачем выполнять поиск по клону контента?
  
- Чтобы сравнить результаты разных запросов поиска ключевых слов, выполните одно и то же расположение контента.
    
- Для сохранения необходимости повторного ввода большого количества расположений контента при создании нового поиска.
    
- Для уменьшения размера результатов поиска. Например, если у вас есть поиск, возвращающий слишком много результатов для экспорта, можно клонировать Поиск, а затем добавить условие поиска на основе диапазона дат, чтобы уменьшить количество результатов поиска.
  
## <a name="before-you-begin"></a>Подготовка

- Для запуска сценария, описанного в этом разделе, необходимо быть членом группы ролей "Диспетчер обнаружения электронных данных" в центре безопасности & соответствия требованиям.
    
- Сценарий включает в себя минимальную обработку ошибок. Основной целью сценария является быстрая клонирование поиска контента.
    
- Сценарий создает новый поиск контента, но не запускает его.
    
- В этом сценарии учитывается, связан ли составной контент, для которого выполняется клонирование, с вариантом обнаружения электронных данных. Если поиск связан с обращением, новый поиск также будет связан с тем же случаем. Если существующий Поиск не связан с обращением, новый поиск будет указан на странице " **Поиск контента** " в центре соответствия требованиям. 
    
- Пример сценария, представленный в этом разделе, не поддерживается ни в одной из стандартных программ или услуг поддержки Майкрософт. Пример сценария предоставляется без каких-либо гарантий. Кроме того, корпорация Майкрософт отказывается от всех косвенных гарантий товарного качества. Весь риск, возникающий из примера использования или производительности примера сценария и документации, остается без вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации сценариев, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров сценариев или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>Шаг 1: запуск скрипта для клонирования поиска

Скрипт на этом шаге создаст новый поиск контента, выполнив клонирование существующего контента. При выполнении этого сценария будут выведены следующие сведения:
  
- **Ваши учетные данные пользователя** — сценарий будет использовать ваши учетные данные для подключения к центру безопасности & соответствия требованиям для вашей организации с помощью Windows PowerShell. Как было сказано ранее, для запуска скрипта необходимо быть членом группы ролей "Диспетчер обнаружения электронных данных" в центре безопасности & Компкомплианце. 
    
- **Имя существующего поиска** — это поиск контента, который необходимо клонировать. 
    
- **Имя нового поиска, который будет создан** — если оставить это значение пустым, сценарий создаст имя для нового поиска, основанное на имени клонированного запроса. 
    
Для клонирования поиска:
  
1. Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `CloneSearch.ps1`.
    
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

2. Откройте Windows PowerShell и перейдите к папке, в которой вы сохранили сценарий.
    
3. Запуск скрипта; Например:
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. При запросе учетных данных введите свой адрес электронной почты и пароль, а затем нажмите кнопку **ОК**.
    
5. Введите следующие сведения, когда запрашивается сценарий. Введите все данные и нажмите клавишу **Ввод**.
    
    - Имя существующего поиска.
    
    - Имя нового поиска.
    
    Сценарий создает новый поиск контента, но не запускает его. Это дает возможность изменить и запустить поиск на следующем этапе. Свойства нового поиска можно просмотреть, выполнив командлет **Get-ComplianceSearch** или перейдя на страницу **Поиск контента** или **Обнаружение электронных** данных в центре соответствия требованиям в зависимости от того, связан ли новый поиск с обращением. 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>Шаг 2: изменение и выполнение клонированного поиска в центре соответствия требованиям

После выполнения скрипта для клонирования существующего поиска контента необходимо перейти в центр соответствия требованиям, чтобы изменить и выполнить новый поиск. Как было сказано ранее, вы можете изменить поиск, изменив запрос поиска ключевых слов и добавив или удалив условия поиска. Дополнительные сведения см. в указанных ниже статьях.
  
- [Поиск контента в Office 365](content-search.md)
    
- [Запросы ключевых слов и условия поиска контента](keyword-queries-and-search-conditions.md)
    
- [случаи обнаружения электронных данных](ediscovery-cases.md)
