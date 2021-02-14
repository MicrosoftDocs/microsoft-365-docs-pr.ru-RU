---
title: Перенос старых запросов на поиск и удерживание электронных данных в Центре соответствия требованиям Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 216ec3853f1b55c7fb34de3a236f50094202bca5
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352469"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a>Перенос старых запросов на поиск и удерживание электронных данных в Центре соответствия требованиям Microsoft 365

Центр соответствия требованиям Microsoft 365 обеспечивает улучшенный опыт использования eDiscovery, в том числе: более высокую надежность, лучшую производительность и множество функций, адаптированных к бизнес-процессам eDiscovery, включая случаи организации контента по сути, обзорные наборы для просмотра контента и аналитики, чтобы помочь в отхвалении данных для проверки, таких как почти дублирующиеся группы, потоки электронной почты, анализ тем и прогнозирование кодирования.

Чтобы помочь клиентам воспользоваться преимуществами новых и улучшенных функций, в этой статье приводится базовое руководство по переносу поисковых запросов In-Place eDiscovery из Центра администрирования Exchange в Центр соответствия требованиям Microsoft 365.

> [!NOTE]
> Поскольку существует множество различных сценариев, в этой статье приводится общее руководство по переходу поиска и сведения данных к основному делу eDiscovery в Центре соответствия требованиям Microsoft 365. Использование дел eDiscovery не всегда требуется, но они добавляют дополнительный уровень безопасности, позволяя назначать разрешения для управления доступом к делам eDiscovery в организации.

## <a name="before-you-begin"></a>Перед началом работы

- Для выполнения команд PowerShell, описанных в этой статье, необходимо быть членом группы ролей "Менеджер по обнаружению электронных данных" в Центре безопасности & соответствия требованиям. Вы также должны быть членом группы ролей "Управление обнаружением" в Центре администрирования Exchange.

- В этой статье содержится руководство по созданию удержания для eDiscovery. Политика удержания будет применяться к почтовым ящикам с помощью асинхронного процесса. При создании удержания для eDiscovery необходимо создать и CaseHoldPolicy, и CaseHoldRule, иначе удержание не будет создано, а расположения контента не будут помещены на удержание.

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a>Шаг 1. Подключение к Exchange Online PowerShell и PowerShell & Центра соответствия требованиям PowerShell

Первым шагом является подключение к Exchange Online PowerShell и PowerShell в Центре & безопасности. Можно скопировать следующий сценарий, вкопировать его в окно PowerShell и запустить его. Вам будут предложены учетные данные для организации, к которую вы хотите подключиться. 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

Команды необходимо выполнить на следующих шагах в этом сеансе PowerShell.

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a>Шаг 2. Получите список поисковых запросов In-Place eDiscovery с помощью Get-MailboxSearch

После проверки подлинности вы можете получить список поисковых запросов In-Place eDiscovery, задав для этого cmdlet **Get-MailboxSearch.** Скопируйте и в paste следующую команду в PowerShell и запустите ее. Список поисковых запросов будет указан с их именами и состоянием всех In-Place.

```powershell
Get-MailboxSearch
```

Выходные данные этого cmdlet будут похожи на следующие:

![Пример Get-MailboxSearch PowerShell](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a>Шаг 3. Получите сведения о поиске In-Place eDiscovery и In-Place, которые вы хотите перенести

Опять же, вы будете использовать для получения свойств поиска с помощью cmdlet **Get-MailboxSearch.** Эти свойства можно сохранить в переменной для использования позже. В следующем примере результаты работы с cmdlet **Get-MailboxSearch** сохраняется в переменной, а затем отображаются свойства поиска.

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

Выходные данные этих двух команд будут похожи на следующие:

![Пример выходных данных PowerShell при использовании Get-MailboxSearch для отдельного поиска](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> Срок действия удержания In-Place в этом примере не ограничен (*ItemHoldPeriod: Unlimited).* Это типично для сценариев eDiscovery и юридических расследований. Если срок хранения отличается от неопределенного, причина, скорее всего, заключается в том, что удержание используется для хранения содержимого в сценарии хранения. Вместо использования для сценариев хранения в Центре безопасности и & соответствия требованиям PowerShell в Центре безопасности и соответствия требованиям рекомендуется использовать [new-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy) и [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) для хранения контента. Результат использования этих cmdlets будет аналогичен использованию **New-CaseHoldPolicy** и **New-CaseHoldRule,** но вы сможете указать период хранения и действие хранения, например удаление содержимого по истечении срока хранения. Кроме того, при использовании этих данных не требуется связывать удержания хранения с делом eDiscovery.

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a>Шаг 4. Создание дела в Центре соответствия требованиям Microsoft 365

Чтобы создать удержание для eDiscovery, необходимо создать дело eDiscovery, чтобы связать удержание с. В следующем примере создается дело eDiscovery с использованием вашего имени. Свойства нового дела будут сохранены в переменной для использования позже. Чтобы просмотреть эти свойства, после создания дела вы можете использовать `$case | FL` команду.

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![Пример запуска команды New-ComplianceCase управления](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a>Шаг 5. Создание удержания для eDiscovery

После создания дела можно создать удержание и связать его с делом, созданным на предыдущем шаге. Важно помнить, что необходимо создать как политику удержания дела, так и правило удержания дела. Если правило удержания дела не создается после создания политики удержания дела, удержание для eDiscovery не создается и содержимое не помещается на удержание.

Чтобы повторно создать удержание eDiscovery, которое необходимо перенести, запустите следующие команды. В этих примерах используются свойства из In-Place с шага 3, который нужно перенести. Первая команда создает новую политику удержания дела и сохраняет свойства в переменную. Вторая команда создает соответствующее правило удержания дела.

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![Пример использованиялетов NewCaseHoldPolicy и NewCaseHoldRule](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a>Шаг 6. Проверка удержания для eDiscovery

Чтобы убедиться, что при создании удержания не было проблем, необходимо убедиться, что состояние распространения удержания успешно. Распространение означает, что удержание применено к всем расположениям контента, указанным в параметре *ExchangeLocation* на предыдущем шаге. Для этого можно запустить cmdlet **Get-CaseHoldPolicy.** Так как свойства, сохраненные в переменной *$policy,* созданной на предыдущем шаге, не обновляются автоматически в переменной, необходимо повторно заархивировать его, чтобы убедиться в успешном распространении. Успешное распространение политик удержания дела может занять от 5 до 24 часов.

Чтобы убедиться, что удержание eDiscovery успешно распределено, запустите следующую команду.

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

Значение success **для** свойства *DistributionStatus* указывает, что удержание было успешно помещено на расположения контента. Если распространение еще не завершено, отображается значение **Pending.**

![Пример Get-CaseHoldPolicy PowerShell](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a>Шаг 7. Создание поиска

Последним шагом является повторное создание поиска, который вы определили в шаге 3, и связывать его с делом. После создания поиска его можно запустить с помощью cmdlet **Start-ComplianceSearch** или запустить позже.

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![Пример New-ComplianceSearch PowerShell](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a>Шаг 8. Проверка дела, удержания и поиска в Центре соответствия требованиям Microsoft 365

Чтобы убедиться, что все настроено правильно, перейдите в Центр соответствия требованиям Microsoft 365 по ссылке и щелкните [https://compliance.microsoft.com](https://compliance.microsoft.com) **eDiscovery > Core.**

![EDiscovery Центра соответствия требованиям Microsoft 365](../media/MigrateLegacyeDiscovery7.png)

Дело, созданное на шаге 3, перечислены на странице **основного eDiscovery.** Откройте дело и обратите внимание на удержание, созданное на шаге 4 на вкладке **"Удержания".** Вы можете щелкнуть удержание, чтобы увидеть сведения, включая количество почтовых ящиков, к которых применяется удержание, и состояние распространения.

![Операции eDiscovery в Центре соответствия требованиям Microsoft 365](../media/MigrateLegacyeDiscovery8.png)

Поиск, созданный на шаге 7, находится в списке на вкладке **"Поиск"** дела eDiscovery.

![Поиск по делу eDiscovery в Центре соответствия требованиям Microsoft 365](../media/MigrateLegacyeDiscovery9.png)

Если вы перенесли поиск In-Place eDiscovery, но не связываете его с делом eDiscovery, он будет указан на странице поиска контента в Центре соответствия требованиям Microsoft 365.

## <a name="more-information"></a>Дополнительные сведения

- Дополнительные сведения о In-Place eDiscovery & в Центре администрирования Exchange см. в:
  
  - [Обнаружение электронных данных на месте](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [Хранение на месте и хранение для судебного разбирательства](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

- Дополнительные сведения о используемых в статье cmdlets PowerShell см. в статьях:

  - [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch)
  
  - [New-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/new-compliancecase)

  - [New-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/new-caseholdpolicy)
  
  - [New-CaseHoldRule](https://docs.microsoft.com/powershell/module/exchange/new-caseholdrule)

  - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
  
  - [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

  - [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/start-compliancesearch)

- Дополнительные сведения о Центре соответствия требованиям Microsoft 365 см. в обзоре Центра соответствия требованиям [Microsoft 365.](microsoft-365-compliance-center.md)
