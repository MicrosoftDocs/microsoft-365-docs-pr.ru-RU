---
title: Миграция поиска электронных данных прежних версий и удержаний в центре соответствия требованиям Microsoft 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: eacbb5577c070ce463ad8e17ba6d0d19a1d8736c
ms.sourcegitcommit: af7950d9674f0eab3aee03f9afccff9ca2f4709a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971405"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a>Миграция поиска электронных данных прежних версий и удержаний в центре соответствия требованиям Microsoft 365

Центр соответствия требованиям Microsoft 365 обеспечивает улучшенное взаимодействие с обнаружением электронных данных, в том числе: повышенная надежность, повышенная производительность и многие функции, связанные с рабочими процессами обнаружения электронных данных, в том числе делами для упорядочения контента, а также для просмотра наборов Просмотрите контент и аналитику, чтобы помочь в отборе данных для пересмотра, таких как почти повторяющиеся группы, почтовые потоки, анализ тем и прогнозирование кода.

Чтобы помочь пользователям использовать новые и улучшенные функции, в этой статье представлены основные рекомендации по переносу поисковых запросов с обнаружением электронных данных на месте и удержанию из центра администрирования Exchange в центр соответствия требованиям Microsoft 365.

> [!NOTE]
> Так как существует множество различных сценариев, в этой статье представлены общие рекомендации по переходу на поиск и удержанию в базовом варианте обнаружения электронных данных в центре соответствия требованиям Microsoft 365. Не всегда требуется использовать случаи обнаружения электронных данных, но они добавляют дополнительный уровень безопасности, позволяя назначать разрешения для управления доступом пользователей к делам обнаружения электронных данных в Организации.

## <a name="before-you-begin"></a>Подготовка

- Для запуска команд PowerShell, описанных в этой статье, необходимо быть членом группы ролей "Диспетчер обнаружения электронных данных" в центре безопасности & соответствия требованиям Office 365. Вы также должны быть членом группы ролей "Управление обнаружением" в центре администрирования Exchange.

- В этой статье приводятся рекомендации по созданию удержания обнаружения электронных данных. Политика удержания будет применяться к почтовым ящикам с помощью асинхронного процесса. При создании удержания для обнаружения электронных данных необходимо создать как Caseholdpolicy позволяет, так и Caseholdrule позволяет, в противном случае удержание не будет создано, а расположения контента не появятся на удержании.

## <a name="step-1-connect-to-exchange-online-powershell-and-office-365-security--compliance-center-powershell"></a>Шаг 1: подключение к Exchange Online PowerShell и Office 365 Security &, PowerShell, центр соответствия требованиям

Первым этапом является подключение к Exchange Online PowerShell и Office 365 Security & с помощью PowerShell центра соответствия требованиям. Вы можете скопировать следующий сценарий, вставить его в окно PowerShell и запустить его. Вам будет предложено ввести учетные данные для Организации, к которой вы хотите подключиться. 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session -AllowClobber -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

В этом сеансе PowerShell необходимо выполнить указанные ниже действия.

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a>Шаг 2: получение списка поисковых запросов при обнаружении электронных данных на месте с помощью Get – MailboxSearch

После проверки подлинности можно получить список поисковых запросов с обнаружением электронных данных на месте, выполнив командлет **Get – MailboxSearch** . Скопируйте и вставьте следующую команду в PowerShell, а затем запустите ее. Список операций поиска будет отображаться с их именами и состоянием удержания на месте.

```powershell
Get-MailboxSearch
```

Выходные данные командлета будут выглядеть следующим образом:

![Пример PowerShell Get — MailboxSearch](media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a>Шаг 3: получение сведений об поисках с обнаружением электронных данных на месте и удержаниях на месте, которые требуется перенести

Опять же, вы будете использовать командлет **Get – MailboxSearch** , но на этот раз — для получения свойств поиска. Эти свойства можно хранить в переменной для последующего использования. В следующем примере показано, как сохранить результаты командлета **Get – MailboxSearch** в переменной, а затем отобразить свойства поиска.

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

Выходные данные этих двух команд будут выглядеть следующим образом:

![Пример выходных данных PowerShell с использованием командлета Get – MailboxSearch для отдельного поиска](media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> Продолжительность удержания на месте в данном примере является неопределенной (*ItemHoldPeriod: Unlimited*). Это типично для сценариев обнаружения электронных данных и судебного разбирательства. Если длительность удержания отличается от значения неопределенности, причина, скорее всего, заключается в том, что удержание используется для хранения контента в сценарии хранения. Вместо использования командлетов обнаружения электронных данных в Office 365 Security & центра соответствия требованиям PowerShell для сценариев хранения мы рекомендуем использовать командлеты [New – HoldCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-holdcompliancepolicy) и [New – HoldComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-holdcompliancerule) для хранения контента. Результат использования этих командлетов аналогичен использованию командлетов **New – caseholdpolicy позволяет** и **New – caseholdrule позволяет**, но вы можете указать срок хранения и действие хранения, такие как удаление контента после истечения срока хранения. Кроме того, использование командлетов хранения не требует, чтобы привязать удержание к случаю обнаружения электронных данных.

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a>Шаг 4: создание дела в центре соответствия требованиям Microsoft 365

Чтобы создать удержание для обнаружения электронных данных, необходимо создать сценарий обнаружения электронных данных для связи с удержанием. В следующем примере показано, как создать вариант обнаружения электронных данных с помощью имени. Мы будем хранить свойства нового случая в переменной для дальнейшего использования. Вы можете просмотреть эти свойства, выполнив `$case | FL` команду после создания дела.

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```

![Пример выполнения команды New – ComplianceCase](media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a>Шаг 5: Создание удержания обнаружения электронных данных

После создания обращения можно создать удержание и связать его с обращением, созданным на предыдущем шаге. Важно помнить о том, что необходимо создать как политику удержания, так и правило удержания дел. Если правило удержания не создается после создания политики удержания, то удержание для обнаружения электронных данных не будет создано и содержимое не будет включено в удержание.

Выполните следующие команды, чтобы повторно создать удержание для обнаружения электронных данных, которое требуется перенести. В этих примерах используются свойства из шага 3, которые нужно перенести, из раздела "удержание на месте".

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
$rule = New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![Пример использования командлетов Невкасехолдполици и Невкасехолдруле](media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a>Шаг 6: Проверка удержания обнаружения электронных данных

Чтобы убедиться в отсутствии проблем с созданием удержания, убедитесь, что состояние распределения для удержания прошло успешно. Распределение означает, что удержание применено ко всем расположениям контента, указанным в параметре *ExchangeLocation* на предыдущем шаге. Для этого можно выполнить командлет **Get – caseholdpolicy позволяет** . Так как свойства, сохраненные в переменной *$Policy* , созданной на предыдущем шаге, не обновляются автоматически в переменной, необходимо повторно выполнить командлет, чтобы убедиться в успешности распространения. Для успешного распространения политик удержания на случай может потребоваться от 5 минут до 24 часов.

Выполните следующую команду, чтобы убедиться, что удержание обнаружения электронных данных успешно распространено.

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

Значение **Success** для свойства *дистрибутионстатус* указывает на то, что удержание успешно размещено в расположениях контента. Если распределение еще не завершено, отображается значение **Ожидание** .

![Пример PowerShell Get — Caseholdpolicy позволяет](media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a>Шаг 7: создание поиска

Последний шаг — повторное создание поиска, который вы определили на шаге 3, и свяжите его с обращением. После создания поиска вы можете запустить его с помощью командлета **Start – ComplianceSearch** или выполнить позже.

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![Пример PowerShell New — ComplianceSearch](media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a>Шаг 8: Проверка регистра, удержания и поиска в центре соответствия требованиям Microsoft 365

Чтобы убедиться, что все настроено правильно, перейдите в центр [https://compliance.microsoft.com](https://compliance.microsoft.com)соответствия требованиям Microsoft 365 и выберите **ядро > обнаружения электронных**данных.

![Обнаружение электронных данных в центре соответствия требованиям Microsoft 365](media/MigrateLegacyeDiscovery7.png)

Дело, созданное на шаге 3, отображается на основной странице **обнаружения электронных** данных. Откройте обращение и обратите внимание на удержание, созданное на шаге 4 в списке на вкладке **удержания** . Вы можете щелкнуть удержание, чтобы просмотреть подробные сведения, в том числе количество почтовых ящиков, к которым применяется удержание, а также состояние распространения.

![Обнаружение электронных данных в центре соответствия требованиям Microsoft 365](media/MigrateLegacyeDiscovery8.png)

Поиск, созданный на шаге 7, указан в списке на вкладке " **поиски** " в варианте обнаружения электронных данных.

![Поиск дел обнаружения электронных данных в центре соответствия требованиям Microsoft 365](media/MigrateLegacyeDiscovery9.png)

Если вы переносите Поиск с обнаружением электронных данных на месте, но не связываете его с вариантом обнаружения электронных данных, он будет указан на странице "поиск контента" в центре соответствия требованиям Microsoft 365.

## <a name="more-information"></a>Дополнительные сведения

- Дополнительные сведения о & обнаружения электронных данных на месте в центре администрирования Exchange приведены в следующих статьях:
  
  - [Обнаружение электронных данных на месте](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [Хранение на месте и хранение для судебного разбирательства](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

- Дополнительные сведения о командлетах PowerShell, используемых в этой статье, приведены в статье:

  - [Get — MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch)
  
  - [New — ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-compliancecase)

  - [New — Caseholdpolicy позволяет](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-caseholdpolicy)
  
  - [New — Caseholdrule позволяет](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-caseholdrule)

  - [Get — Caseholdpolicy позволяет](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)
  
  - [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)

  - [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)

- Для получения дополнительных сведений о центре соответствия требованиям Microsoft 365, ознакомьтесь со статьей [Обзор центра соответствия требованиям microsoft 365](microsoft-365-compliance-center.md).
