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
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="8c050-102">Перенос старых запросов на поиск и удерживание электронных данных в Центре соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8c050-102">Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="8c050-103">Центр соответствия требованиям Microsoft 365 обеспечивает улучшенный опыт использования eDiscovery, в том числе: более высокую надежность, лучшую производительность и множество функций, адаптированных к бизнес-процессам eDiscovery, включая случаи организации контента по сути, обзорные наборы для просмотра контента и аналитики, чтобы помочь в отхвалении данных для проверки, таких как почти дублирующиеся группы, потоки электронной почты, анализ тем и прогнозирование кодирования.</span><span class="sxs-lookup"><span data-stu-id="8c050-103">The Microsoft 365 compliance center provides an improved experience for eDiscovery usage, including: higher reliability, better performance and many features tailored to eDiscovery workflows including cases to organize your content by matter, review sets to review content and analytics to help cull data for review such as near-duplicate grouping, email threading, themes analysis, and predictive coding.</span></span>

<span data-ttu-id="8c050-104">Чтобы помочь клиентам воспользоваться преимуществами новых и улучшенных функций, в этой статье приводится базовое руководство по переносу поисковых запросов In-Place eDiscovery из Центра администрирования Exchange в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c050-104">To help customers take advantage of the new and improved functionality, this article provides basic guidance on how to migrate In-Place eDiscovery searches and holds from the Exchange admin center to the Microsoft 365 compliance center.</span></span>

> [!NOTE]
> <span data-ttu-id="8c050-105">Поскольку существует множество различных сценариев, в этой статье приводится общее руководство по переходу поиска и сведения данных к основному делу eDiscovery в Центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c050-105">Because there are many different scenarios, this article provides general guidance to transition searches and holds to a core eDiscovery case in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="8c050-106">Использование дел eDiscovery не всегда требуется, но они добавляют дополнительный уровень безопасности, позволяя назначать разрешения для управления доступом к делам eDiscovery в организации.</span><span class="sxs-lookup"><span data-stu-id="8c050-106">Using eDiscovery cases aren't always required, but they add an extra layer of security by letting you assign permissions to control who has access to the eDiscovery cases in your organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8c050-107">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="8c050-107">Before you begin</span></span>

- <span data-ttu-id="8c050-108">Для выполнения команд PowerShell, описанных в этой статье, необходимо быть членом группы ролей "Менеджер по обнаружению электронных данных" в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="8c050-108">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the PowerShell commands described in this article.</span></span> <span data-ttu-id="8c050-109">Вы также должны быть членом группы ролей "Управление обнаружением" в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="8c050-109">You also have to be a member of the Discovery Management role group in the Exchange admin center.</span></span>

- <span data-ttu-id="8c050-110">В этой статье содержится руководство по созданию удержания для eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="8c050-110">This article provides guidance on how to create an eDiscovery hold.</span></span> <span data-ttu-id="8c050-111">Политика удержания будет применяться к почтовым ящикам с помощью асинхронного процесса.</span><span class="sxs-lookup"><span data-stu-id="8c050-111">The hold policy will be applied to mailboxes through an asynchronous process.</span></span> <span data-ttu-id="8c050-112">При создании удержания для eDiscovery необходимо создать и CaseHoldPolicy, и CaseHoldRule, иначе удержание не будет создано, а расположения контента не будут помещены на удержание.</span><span class="sxs-lookup"><span data-stu-id="8c050-112">When creating an eDiscovery hold, you must create both a CaseHoldPolicy and CaseHoldRule, otherwise the hold will not be created and content locations will not be placed on hold.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a><span data-ttu-id="8c050-113">Шаг 1. Подключение к Exchange Online PowerShell и PowerShell & Центра соответствия требованиям PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c050-113">Step 1: Connect to Exchange Online PowerShell and Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="8c050-114">Первым шагом является подключение к Exchange Online PowerShell и PowerShell в Центре & безопасности.</span><span class="sxs-lookup"><span data-stu-id="8c050-114">The first step is to connect to Exchange Online PowerShell and Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="8c050-115">Можно скопировать следующий сценарий, вкопировать его в окно PowerShell и запустить его.</span><span class="sxs-lookup"><span data-stu-id="8c050-115">You can copy the following script, paste it into a PowerShell window and then run it.</span></span> <span data-ttu-id="8c050-116">Вам будут предложены учетные данные для организации, к которую вы хотите подключиться.</span><span class="sxs-lookup"><span data-stu-id="8c050-116">You'll be prompted for credentials for the organization that you want to connect to.</span></span> 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

<span data-ttu-id="8c050-117">Команды необходимо выполнить на следующих шагах в этом сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c050-117">You need to run the commands in the following steps in this PowerShell session.</span></span>

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a><span data-ttu-id="8c050-118">Шаг 2. Получите список поисковых запросов In-Place eDiscovery с помощью Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="8c050-118">Step 2: Get a list of In-Place eDiscovery searches by using Get-MailboxSearch</span></span>

<span data-ttu-id="8c050-119">После проверки подлинности вы можете получить список поисковых запросов In-Place eDiscovery, задав для этого cmdlet **Get-MailboxSearch.**</span><span class="sxs-lookup"><span data-stu-id="8c050-119">After you've authenticated, you can get a list of In-Place eDiscovery searches by running the **Get-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="8c050-120">Скопируйте и в paste следующую команду в PowerShell и запустите ее.</span><span class="sxs-lookup"><span data-stu-id="8c050-120">Copy and paste the following command into PowerShell and then run it.</span></span> <span data-ttu-id="8c050-121">Список поисковых запросов будет указан с их именами и состоянием всех In-Place.</span><span class="sxs-lookup"><span data-stu-id="8c050-121">A list of searches will be listed with their names and the status of any In-Place Holds.</span></span>

```powershell
Get-MailboxSearch
```

<span data-ttu-id="8c050-122">Выходные данные этого cmdlet будут похожи на следующие:</span><span class="sxs-lookup"><span data-stu-id="8c050-122">The cmdlet output will be similar to the following:</span></span>

![Пример Get-MailboxSearch PowerShell](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a><span data-ttu-id="8c050-124">Шаг 3. Получите сведения о поиске In-Place eDiscovery и In-Place, которые вы хотите перенести</span><span class="sxs-lookup"><span data-stu-id="8c050-124">Step 3: Get information about the In-Place eDiscovery searches and In-Place Holds you want to migrate</span></span>

<span data-ttu-id="8c050-125">Опять же, вы будете использовать для получения свойств поиска с помощью cmdlet **Get-MailboxSearch.**</span><span class="sxs-lookup"><span data-stu-id="8c050-125">Again you will use the **Get-MailboxSearch** cmdlet, but this time to get the properties of the search.</span></span> <span data-ttu-id="8c050-126">Эти свойства можно сохранить в переменной для использования позже.</span><span class="sxs-lookup"><span data-stu-id="8c050-126">You can store these properties in a variable for use later.</span></span> <span data-ttu-id="8c050-127">В следующем примере результаты работы с cmdlet **Get-MailboxSearch** сохраняется в переменной, а затем отображаются свойства поиска.</span><span class="sxs-lookup"><span data-stu-id="8c050-127">The following example stores the results of the **Get-MailboxSearch** cmdlet in a variable and then displays the properties of the search.</span></span>

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

<span data-ttu-id="8c050-128">Выходные данные этих двух команд будут похожи на следующие:</span><span class="sxs-lookup"><span data-stu-id="8c050-128">The output of these two commands will be similar to the following:</span></span>

![Пример выходных данных PowerShell при использовании Get-MailboxSearch для отдельного поиска](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> <span data-ttu-id="8c050-130">Срок действия удержания In-Place в этом примере не ограничен (*ItemHoldPeriod: Unlimited).*</span><span class="sxs-lookup"><span data-stu-id="8c050-130">The duration of the In-Place Hold in this example is indefinite (*ItemHoldPeriod: Unlimited*).</span></span> <span data-ttu-id="8c050-131">Это типично для сценариев eDiscovery и юридических расследований.</span><span class="sxs-lookup"><span data-stu-id="8c050-131">This is typical for eDiscovery and legal investigation scenarios.</span></span> <span data-ttu-id="8c050-132">Если срок хранения отличается от неопределенного, причина, скорее всего, заключается в том, что удержание используется для хранения содержимого в сценарии хранения.</span><span class="sxs-lookup"><span data-stu-id="8c050-132">If the hold duration has is different value than indefinite, the reason is likely because the hold is being used to retain content in a retention scenario.</span></span> <span data-ttu-id="8c050-133">Вместо использования для сценариев хранения в Центре безопасности и & соответствия требованиям PowerShell в Центре безопасности и соответствия требованиям рекомендуется использовать [new-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy) и [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) для хранения контента.</span><span class="sxs-lookup"><span data-stu-id="8c050-133">Instead of using the eDiscovery cmdlets in Security & Compliance Center PowerShell for retention scenarios, we recommend that you use [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy) and [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) to retain content.</span></span> <span data-ttu-id="8c050-134">Результат использования этих cmdlets будет аналогичен использованию **New-CaseHoldPolicy** и **New-CaseHoldRule,** но вы сможете указать период хранения и действие хранения, например удаление содержимого по истечении срока хранения.</span><span class="sxs-lookup"><span data-stu-id="8c050-134">The result of using these cmdlets will be similar to using **New-CaseHoldPolicy** and **New-CaseHoldRule**, but you'll able to specify a retention period and a retention action, such as deleting content after the retention period expires.</span></span> <span data-ttu-id="8c050-135">Кроме того, при использовании этих данных не требуется связывать удержания хранения с делом eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="8c050-135">Also, using the retention cmdlets don't require you to associate the retention holds with an eDiscovery case.</span></span>

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="8c050-136">Шаг 4. Создание дела в Центре соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8c050-136">Step 4: Create a case in the Microsoft 365 Compliance center</span></span>

<span data-ttu-id="8c050-137">Чтобы создать удержание для eDiscovery, необходимо создать дело eDiscovery, чтобы связать удержание с.</span><span class="sxs-lookup"><span data-stu-id="8c050-137">To create an eDiscovery hold, you have to create an eDiscovery case to associate the hold with.</span></span> <span data-ttu-id="8c050-138">В следующем примере создается дело eDiscovery с использованием вашего имени.</span><span class="sxs-lookup"><span data-stu-id="8c050-138">The following example creates an eDiscovery case using a name of your choice.</span></span> <span data-ttu-id="8c050-139">Свойства нового дела будут сохранены в переменной для использования позже.</span><span class="sxs-lookup"><span data-stu-id="8c050-139">We will store the properties of the new case in a variable for use later.</span></span> <span data-ttu-id="8c050-140">Чтобы просмотреть эти свойства, после создания дела вы можете использовать `$case | FL` команду.</span><span class="sxs-lookup"><span data-stu-id="8c050-140">You can view those properties by running the `$case | FL` command after you create the case.</span></span>

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![Пример запуска команды New-ComplianceCase управления](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a><span data-ttu-id="8c050-142">Шаг 5. Создание удержания для eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8c050-142">Step 5: Create the eDiscovery hold</span></span>

<span data-ttu-id="8c050-143">После создания дела можно создать удержание и связать его с делом, созданным на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="8c050-143">After the case is created, you can create the hold and associate it with the case that you created in the previous step.</span></span> <span data-ttu-id="8c050-144">Важно помнить, что необходимо создать как политику удержания дела, так и правило удержания дела.</span><span class="sxs-lookup"><span data-stu-id="8c050-144">It's important to remember that you must create both a case hold policy and a case hold rule.</span></span> <span data-ttu-id="8c050-145">Если правило удержания дела не создается после создания политики удержания дела, удержание для eDiscovery не создается и содержимое не помещается на удержание.</span><span class="sxs-lookup"><span data-stu-id="8c050-145">If the case hold rule isn't created after you created case hold policy, the eDiscovery hold will not be created and any content won't be placed on hold.</span></span>

<span data-ttu-id="8c050-146">Чтобы повторно создать удержание eDiscovery, которое необходимо перенести, запустите следующие команды.</span><span class="sxs-lookup"><span data-stu-id="8c050-146">Run the following commands to re-create the eDiscovery hold that you want to migrate.</span></span> <span data-ttu-id="8c050-147">В этих примерах используются свойства из In-Place с шага 3, который нужно перенести.</span><span class="sxs-lookup"><span data-stu-id="8c050-147">These examples use the properties from In-Place Hold from Step 3 that you want to migrate.</span></span> <span data-ttu-id="8c050-148">Первая команда создает новую политику удержания дела и сохраняет свойства в переменную.</span><span class="sxs-lookup"><span data-stu-id="8c050-148">The first command creates a new case hold policy and saves the properties to a variable.</span></span> <span data-ttu-id="8c050-149">Вторая команда создает соответствующее правило удержания дела.</span><span class="sxs-lookup"><span data-stu-id="8c050-149">The second command creates the corresponding case hold rule.</span></span>

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![Пример использованиялетов NewCaseHoldPolicy и NewCaseHoldRule](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a><span data-ttu-id="8c050-151">Шаг 6. Проверка удержания для eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8c050-151">Step 6: Verify the eDiscovery hold</span></span>

<span data-ttu-id="8c050-152">Чтобы убедиться, что при создании удержания не было проблем, необходимо убедиться, что состояние распространения удержания успешно.</span><span class="sxs-lookup"><span data-stu-id="8c050-152">To make sure there were no issues in creating the hold, it's good to check that the hold distribution status is successful.</span></span> <span data-ttu-id="8c050-153">Распространение означает, что удержание применено к всем расположениям контента, указанным в параметре *ExchangeLocation* на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="8c050-153">Distribution means that the hold has been applied to all the content locations specified in the *ExchangeLocation* parameter in the previous step.</span></span> <span data-ttu-id="8c050-154">Для этого можно запустить cmdlet **Get-CaseHoldPolicy.**</span><span class="sxs-lookup"><span data-stu-id="8c050-154">To do this, you can run the **Get-CaseHoldPolicy** cmdlet.</span></span> <span data-ttu-id="8c050-155">Так как свойства, сохраненные в переменной *$policy,* созданной на предыдущем шаге, не обновляются автоматически в переменной, необходимо повторно заархивировать его, чтобы убедиться в успешном распространении.</span><span class="sxs-lookup"><span data-stu-id="8c050-155">Because the properties saved to the *$policy* variable that you created in the previous step aren't automatically updated in the variable, you need to rerun the cmdlet to verify that distribution is successful.</span></span> <span data-ttu-id="8c050-156">Успешное распространение политик удержания дела может занять от 5 до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="8c050-156">It can take between 5 minutes and 24 hours for case hold policies to be successfully distributed.</span></span>

<span data-ttu-id="8c050-157">Чтобы убедиться, что удержание eDiscovery успешно распределено, запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="8c050-157">Run the following command to verify that the eDiscovery hold has been successfully distributed.</span></span>

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

<span data-ttu-id="8c050-158">Значение success **для** свойства *DistributionStatus* указывает, что удержание было успешно помещено на расположения контента.</span><span class="sxs-lookup"><span data-stu-id="8c050-158">The value of **Success** for the *DistributionStatus* property indicates the hold was successfully placed on the content locations.</span></span> <span data-ttu-id="8c050-159">Если распространение еще не завершено, отображается значение **Pending.**</span><span class="sxs-lookup"><span data-stu-id="8c050-159">If the distribution is not yet complete, a value of **Pending** is displayed.</span></span>

![Пример Get-CaseHoldPolicy PowerShell](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a><span data-ttu-id="8c050-161">Шаг 7. Создание поиска</span><span class="sxs-lookup"><span data-stu-id="8c050-161">Step 7: Create the search</span></span>

<span data-ttu-id="8c050-162">Последним шагом является повторное создание поиска, который вы определили в шаге 3, и связывать его с делом.</span><span class="sxs-lookup"><span data-stu-id="8c050-162">The last step is to re-create the search that you identified in Step 3 and associate it with the case.</span></span> <span data-ttu-id="8c050-163">После создания поиска его можно запустить с помощью cmdlet **Start-ComplianceSearch** или запустить позже.</span><span class="sxs-lookup"><span data-stu-id="8c050-163">After you create the search, you can run it by using the **Start-ComplianceSearch** cmdlet or run at a later time.</span></span>

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![Пример New-ComplianceSearch PowerShell](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="8c050-165">Шаг 8. Проверка дела, удержания и поиска в Центре соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8c050-165">Step 8: Verify the case, hold, and search in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="8c050-166">Чтобы убедиться, что все настроено правильно, перейдите в Центр соответствия требованиям Microsoft 365 по ссылке и щелкните [https://compliance.microsoft.com](https://compliance.microsoft.com) **eDiscovery > Core.**</span><span class="sxs-lookup"><span data-stu-id="8c050-166">To make sure that everything is set up correctly, go to the Microsoft 365 compliance center at [https://compliance.microsoft.com](https://compliance.microsoft.com), and click **eDiscovery > Core**.</span></span>

![EDiscovery Центра соответствия требованиям Microsoft 365](../media/MigrateLegacyeDiscovery7.png)

<span data-ttu-id="8c050-168">Дело, созданное на шаге 3, перечислены на странице **основного eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="8c050-168">The case that you created in Step 3 is listed on the **Core eDiscovery** page.</span></span> <span data-ttu-id="8c050-169">Откройте дело и обратите внимание на удержание, созданное на шаге 4 на вкладке **"Удержания".** Вы можете щелкнуть удержание, чтобы увидеть сведения, включая количество почтовых ящиков, к которых применяется удержание, и состояние распространения.</span><span class="sxs-lookup"><span data-stu-id="8c050-169">Open the case and then notice the hold that you created in Step 4 in listed on the **Holds** tab. You can click the hold to see details, including the number of mailboxes the hold is applied to and the distribution status.</span></span>

![Операции eDiscovery в Центре соответствия требованиям Microsoft 365](../media/MigrateLegacyeDiscovery8.png)

<span data-ttu-id="8c050-171">Поиск, созданный на шаге 7, находится в списке на вкладке **"Поиск"** дела eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="8c050-171">The search that you created in Step 7 is listed on the listed on the **Searches** tab of the eDiscovery case.</span></span>

![Поиск по делу eDiscovery в Центре соответствия требованиям Microsoft 365](../media/MigrateLegacyeDiscovery9.png)

<span data-ttu-id="8c050-173">Если вы перенесли поиск In-Place eDiscovery, но не связываете его с делом eDiscovery, он будет указан на странице поиска контента в Центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c050-173">If you migrate an In-Place eDiscovery search but don't associate it with an eDiscovery case, it will be listed on the Content search page in the Microsoft 365 compliance center.</span></span>

## <a name="more-information"></a><span data-ttu-id="8c050-174">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="8c050-174">More information</span></span>

- <span data-ttu-id="8c050-175">Дополнительные сведения о In-Place eDiscovery & в Центре администрирования Exchange см. в:</span><span class="sxs-lookup"><span data-stu-id="8c050-175">For more information about In-Place eDiscovery & Holds in the Exchange admin center, see:</span></span>
  
  - [<span data-ttu-id="8c050-176">Обнаружение электронных данных на месте</span><span class="sxs-lookup"><span data-stu-id="8c050-176">In-Place eDiscovery</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [<span data-ttu-id="8c050-177">Хранение на месте и хранение для судебного разбирательства</span><span class="sxs-lookup"><span data-stu-id="8c050-177">In-Place Hold and Litigation Hold</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

- <span data-ttu-id="8c050-178">Дополнительные сведения о используемых в статье cmdlets PowerShell см. в статьях:</span><span class="sxs-lookup"><span data-stu-id="8c050-178">For more information about the PowerShell cmdlets used in the article, see:</span></span>

  - [<span data-ttu-id="8c050-179">Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="8c050-179">Get-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch)
  
  - [<span data-ttu-id="8c050-180">New-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="8c050-180">New-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancecase)

  - [<span data-ttu-id="8c050-181">New-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="8c050-181">New-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-caseholdpolicy)
  
  - [<span data-ttu-id="8c050-182">New-CaseHoldRule</span><span class="sxs-lookup"><span data-stu-id="8c050-182">New-CaseHoldRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-caseholdrule)

  - [<span data-ttu-id="8c050-183">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="8c050-183">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
  
  - [<span data-ttu-id="8c050-184">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="8c050-184">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

  - [<span data-ttu-id="8c050-185">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="8c050-185">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/start-compliancesearch)

- <span data-ttu-id="8c050-186">Дополнительные сведения о Центре соответствия требованиям Microsoft 365 см. в обзоре Центра соответствия требованиям [Microsoft 365.](microsoft-365-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="8c050-186">For more information about the Microsoft 365 compliance center, see [Overview of the Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>
