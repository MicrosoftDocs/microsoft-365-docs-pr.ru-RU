---
title: Перенос устаревших поисков электронных данных и их перенос в центр соответствия требованиям Microsoft 365
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
ms.openlocfilehash: ef5562aa6f5c7519d19452100b55dd4bc30d4126
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926327"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="4cd06-102">Перенос устаревших поисков электронных данных и их перенос в центр соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4cd06-102">Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="4cd06-103">Центр соответствия требованиям Microsoft 365 предоставляет улучшенный опыт использования электронных данных, в том числе: более высокую надежность, лучшую производительность и многие функции, адаптированные к рабочего процессам eDiscovery, включая случаи организации контента по материи, наборы обзоров для проверки контента и аналитики, чтобы помочь отключать данные для проверки, такие как почти дубликатная группировка, потоки электронной почты, анализ тем и прогностическое кодирование.</span><span class="sxs-lookup"><span data-stu-id="4cd06-103">The Microsoft 365 compliance center provides an improved experience for eDiscovery usage, including: higher reliability, better performance and many features tailored to eDiscovery workflows including cases to organize your content by matter, review sets to review content and analytics to help cull data for review such as near-duplicate grouping, email threading, themes analysis, and predictive coding.</span></span>

<span data-ttu-id="4cd06-104">Чтобы помочь клиентам воспользоваться новыми и улучшенными функциями, в этой статье данная статья содержит основные рекомендации по переносу поиска In-Place поиска и удерживания электронных данных из центра администрирования Exchange в центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cd06-104">To help customers take advantage of the new and improved functionality, this article provides basic guidance on how to migrate In-Place eDiscovery searches and holds from the Exchange admin center to the Microsoft 365 compliance center.</span></span>

> [!NOTE]
> <span data-ttu-id="4cd06-105">Так как существует множество различных сценариев, в этой статье содержится общее руководство по переходу поиска и содержится в основном деле об обнаружении электронных данных в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cd06-105">Because there are many different scenarios, this article provides general guidance to transition searches and holds to a core eDiscovery case in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="4cd06-106">Не всегда требуется использовать случаи получения электронных данных, но они добавляют дополнительный уровень безопасности, позволяя назначать разрешения для управления доступом к делам об обнаружении электронных данных в организации.</span><span class="sxs-lookup"><span data-stu-id="4cd06-106">Using eDiscovery cases aren't always required, but they add an extra layer of security by letting you assign permissions to control who has access to the eDiscovery cases in your organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4cd06-107">Подготовка</span><span class="sxs-lookup"><span data-stu-id="4cd06-107">Before you begin</span></span>

- <span data-ttu-id="4cd06-108">Для выполнения команд PowerShell, описанных в этой статье, необходимо быть членом группы ролей диспетчера электронных данных в Центре & безопасности.</span><span class="sxs-lookup"><span data-stu-id="4cd06-108">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the PowerShell commands described in this article.</span></span> <span data-ttu-id="4cd06-109">Вы также должны быть членом группы ролей управления обнаружением в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="4cd06-109">You also have to be a member of the Discovery Management role group in the Exchange admin center.</span></span>

- <span data-ttu-id="4cd06-110">В этой статье данная статья содержит рекомендации по созданию удержания для электронных обнаружений.</span><span class="sxs-lookup"><span data-stu-id="4cd06-110">This article provides guidance on how to create an eDiscovery hold.</span></span> <span data-ttu-id="4cd06-111">Политика удержания будет применяться к почтовым ящикам с помощью асинхронного процесса.</span><span class="sxs-lookup"><span data-stu-id="4cd06-111">The hold policy will be applied to mailboxes through an asynchronous process.</span></span> <span data-ttu-id="4cd06-112">При создании удержания для электронных обнаружений необходимо создать как CaseHoldPolicy, так и CaseHoldRule, в противном случае удержание не будет создано и расположения контента не будут помещены в удержание.</span><span class="sxs-lookup"><span data-stu-id="4cd06-112">When creating an eDiscovery hold, you must create both a CaseHoldPolicy and CaseHoldRule, otherwise the hold will not be created and content locations will not be placed on hold.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a><span data-ttu-id="4cd06-113">Шаг 1. Подключение к Exchange Online PowerShell и & Центра соответствия требованиям PowerShell</span><span class="sxs-lookup"><span data-stu-id="4cd06-113">Step 1: Connect to Exchange Online PowerShell and Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="4cd06-114">Первый шаг — подключение к Exchange Online PowerShell и службе безопасности & PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4cd06-114">The first step is to connect to Exchange Online PowerShell and Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="4cd06-115">Вы можете скопировать следующий сценарий, вклеить его в окно PowerShell и запустить его.</span><span class="sxs-lookup"><span data-stu-id="4cd06-115">You can copy the following script, paste it into a PowerShell window and then run it.</span></span> <span data-ttu-id="4cd06-116">Вам будут предложены учетные данные для организации, к которую необходимо подключиться.</span><span class="sxs-lookup"><span data-stu-id="4cd06-116">You'll be prompted for credentials for the organization that you want to connect to.</span></span> 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

<span data-ttu-id="4cd06-117">Необходимо выполнить команды в следующих действиях в этом сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4cd06-117">You need to run the commands in the following steps in this PowerShell session.</span></span>

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a><span data-ttu-id="4cd06-118">Шаг 2. Получить список поиска In-Place с помощью Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="4cd06-118">Step 2: Get a list of In-Place eDiscovery searches by using Get-MailboxSearch</span></span>

<span data-ttu-id="4cd06-119">После проверки подлинности вы можете получить список In-Place поиска по электронным данным с помощью **cmdlet Get-MailboxSearch.**</span><span class="sxs-lookup"><span data-stu-id="4cd06-119">After you've authenticated, you can get a list of In-Place eDiscovery searches by running the **Get-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="4cd06-120">Скопируйте и вклеите следующую команду в PowerShell и запустите ее.</span><span class="sxs-lookup"><span data-stu-id="4cd06-120">Copy and paste the following command into PowerShell and then run it.</span></span> <span data-ttu-id="4cd06-121">Список поисков будет указан с их именами и состоянием любого In-Place holds.</span><span class="sxs-lookup"><span data-stu-id="4cd06-121">A list of searches will be listed with their names and the status of any In-Place Holds.</span></span>

```powershell
Get-MailboxSearch
```

<span data-ttu-id="4cd06-122">Вывод cmdlet будет похож на следующий:</span><span class="sxs-lookup"><span data-stu-id="4cd06-122">The cmdlet output will be similar to the following:</span></span>

![Пример PowerShell Get-MailboxSearch](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a><span data-ttu-id="4cd06-124">Шаг 3. Сведения о поиске In-Place и In-Place, которые необходимо перенести</span><span class="sxs-lookup"><span data-stu-id="4cd06-124">Step 3: Get information about the In-Place eDiscovery searches and In-Place Holds you want to migrate</span></span>

<span data-ttu-id="4cd06-125">Снова вы будете использовать **комлет Get-MailboxSearch,** но на этот раз, чтобы получить свойства поиска.</span><span class="sxs-lookup"><span data-stu-id="4cd06-125">Again you will use the **Get-MailboxSearch** cmdlet, but this time to get the properties of the search.</span></span> <span data-ttu-id="4cd06-126">Эти свойства можно хранить в переменной для использования позже.</span><span class="sxs-lookup"><span data-stu-id="4cd06-126">You can store these properties in a variable for use later.</span></span> <span data-ttu-id="4cd06-127">В следующем примере в переменной хранится результат **комлета Get-MailboxSearch,** а затем отображаются свойства поиска.</span><span class="sxs-lookup"><span data-stu-id="4cd06-127">The following example stores the results of the **Get-MailboxSearch** cmdlet in a variable and then displays the properties of the search.</span></span>

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

<span data-ttu-id="4cd06-128">Выход этих двух команд будет похож на следующие:</span><span class="sxs-lookup"><span data-stu-id="4cd06-128">The output of these two commands will be similar to the following:</span></span>

![Пример вывода PowerShell с Get-MailboxSearch для индивидуального поиска](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> <span data-ttu-id="4cd06-130">Продолжительность удержания In-Place в этом примере неопределенная *(ItemHoldPeriod: Unlimited).*</span><span class="sxs-lookup"><span data-stu-id="4cd06-130">The duration of the In-Place Hold in this example is indefinite (*ItemHoldPeriod: Unlimited*).</span></span> <span data-ttu-id="4cd06-131">Это характерно для сценариев расследования электронных и юридических расследований.</span><span class="sxs-lookup"><span data-stu-id="4cd06-131">This is typical for eDiscovery and legal investigation scenarios.</span></span> <span data-ttu-id="4cd06-132">Если продолжительность хранения отличается от неопределенного значения, причина, скорее всего, в том, что удержание используется для сохранения контента в сценарии хранения.</span><span class="sxs-lookup"><span data-stu-id="4cd06-132">If the hold duration has is different value than indefinite, the reason is likely because the hold is being used to retain content in a retention scenario.</span></span> <span data-ttu-id="4cd06-133">Вместо использования кодлетов eDiscovery в Центре обеспечения безопасности & PowerShell для сценариев хранения рекомендуется использовать [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) и [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) для сохранения контента.</span><span class="sxs-lookup"><span data-stu-id="4cd06-133">Instead of using the eDiscovery cmdlets in Security & Compliance Center PowerShell for retention scenarios, we recommend that you use [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) and [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) to retain content.</span></span> <span data-ttu-id="4cd06-134">Результат использования этих кодлетов будет аналогичен использованию **New-CaseHoldPolicy** и **New-CaseHoldRule,** но вы сможете указать период хранения и действие хранения, например удаление контента по истечении срока хранения.</span><span class="sxs-lookup"><span data-stu-id="4cd06-134">The result of using these cmdlets will be similar to using **New-CaseHoldPolicy** and **New-CaseHoldRule**, but you'll able to specify a retention period and a retention action, such as deleting content after the retention period expires.</span></span> <span data-ttu-id="4cd06-135">Кроме того, с помощью кодлетов хранения не требуется связывать удержание хранении с случаем электронного разоружия.</span><span class="sxs-lookup"><span data-stu-id="4cd06-135">Also, using the retention cmdlets don't require you to associate the retention holds with an eDiscovery case.</span></span>

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="4cd06-136">Шаг 4. Создание дела в центре соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4cd06-136">Step 4: Create a case in the Microsoft 365 Compliance center</span></span>

<span data-ttu-id="4cd06-137">Чтобы создать удержание для электронных обнаружений, необходимо создать дело об обнаружении электронных обнаружений, чтобы связать удержание с.</span><span class="sxs-lookup"><span data-stu-id="4cd06-137">To create an eDiscovery hold, you have to create an eDiscovery case to associate the hold with.</span></span> <span data-ttu-id="4cd06-138">В следующем примере создается дело об обнаружении электронной почты с использованием имени по вашему выбору.</span><span class="sxs-lookup"><span data-stu-id="4cd06-138">The following example creates an eDiscovery case using a name of your choice.</span></span> <span data-ttu-id="4cd06-139">Свойства нового дела будут храниться в переменной для использования позже.</span><span class="sxs-lookup"><span data-stu-id="4cd06-139">We will store the properties of the new case in a variable for use later.</span></span> <span data-ttu-id="4cd06-140">Эти свойства можно просматривать, запуская `$case | FL` команду после создания дела.</span><span class="sxs-lookup"><span data-stu-id="4cd06-140">You can view those properties by running the `$case | FL` command after you create the case.</span></span>

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![Пример запуска команды New-ComplianceCase](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a><span data-ttu-id="4cd06-142">Шаг 5. Создание удержания для электронных обнаружений</span><span class="sxs-lookup"><span data-stu-id="4cd06-142">Step 5: Create the eDiscovery hold</span></span>

<span data-ttu-id="4cd06-143">После создания случая можно создать удержание и связать его с случаем, созданным на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="4cd06-143">After the case is created, you can create the hold and associate it with the case that you created in the previous step.</span></span> <span data-ttu-id="4cd06-144">Важно помнить, что необходимо создать как политику удержания кейсов, так и правило удержания кейсов.</span><span class="sxs-lookup"><span data-stu-id="4cd06-144">It's important to remember that you must create both a case hold policy and a case hold rule.</span></span> <span data-ttu-id="4cd06-145">Если правило удержания в случае не создается после создания политики удержания в случае, удержание электронных обнаружений не создается и содержимое не будет помещено в удержание.</span><span class="sxs-lookup"><span data-stu-id="4cd06-145">If the case hold rule isn't created after you created case hold policy, the eDiscovery hold will not be created and any content won't be placed on hold.</span></span>

<span data-ttu-id="4cd06-146">Запустите следующие команды, чтобы повторно создать удержание для электронных обнаружений, которое необходимо перенести.</span><span class="sxs-lookup"><span data-stu-id="4cd06-146">Run the following commands to re-create the eDiscovery hold that you want to migrate.</span></span> <span data-ttu-id="4cd06-147">В этих примерах используются свойства из In-Place удержания из шага 3, которые необходимо перенести.</span><span class="sxs-lookup"><span data-stu-id="4cd06-147">These examples use the properties from In-Place Hold from Step 3 that you want to migrate.</span></span> <span data-ttu-id="4cd06-148">Первая команда создает новую политику удержания корпусов и сохраняет свойства на переменную.</span><span class="sxs-lookup"><span data-stu-id="4cd06-148">The first command creates a new case hold policy and saves the properties to a variable.</span></span> <span data-ttu-id="4cd06-149">Вторая команда создает соответствующее правило удержания случая.</span><span class="sxs-lookup"><span data-stu-id="4cd06-149">The second command creates the corresponding case hold rule.</span></span>

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![Пример использования cmdlets NewCaseHoldPolicy и NewCaseHoldRule](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a><span data-ttu-id="4cd06-151">Шаг 6. Проверка удержания для проверки электронных обнаружений</span><span class="sxs-lookup"><span data-stu-id="4cd06-151">Step 6: Verify the eDiscovery hold</span></span>

<span data-ttu-id="4cd06-152">Чтобы убедиться, что при создании удержания не было проблем, необходимо убедиться, что состояние распределения удержания успешно.</span><span class="sxs-lookup"><span data-stu-id="4cd06-152">To make sure there were no issues in creating the hold, it's good to check that the hold distribution status is successful.</span></span> <span data-ttu-id="4cd06-153">Распространение означает, что удержание было применено во всех расположениях контента, указанных в параметре *ExchangeLocation* на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="4cd06-153">Distribution means that the hold has been applied to all the content locations specified in the *ExchangeLocation* parameter in the previous step.</span></span> <span data-ttu-id="4cd06-154">Для этого можно запустить **cmdlet Get-CaseHoldPolicy.**</span><span class="sxs-lookup"><span data-stu-id="4cd06-154">To do this, you can run the **Get-CaseHoldPolicy** cmdlet.</span></span> <span data-ttu-id="4cd06-155">Так как свойства, сохраненные в переменной *$policy,* созданной на предыдущем шаге, не обновляются автоматически в переменной, необходимо повторно перезаключить кодлет, чтобы убедиться в успешном распространении.</span><span class="sxs-lookup"><span data-stu-id="4cd06-155">Because the properties saved to the *$policy* variable that you created in the previous step aren't automatically updated in the variable, you need to rerun the cmdlet to verify that distribution is successful.</span></span> <span data-ttu-id="4cd06-156">Для успешного распространения политик удержания для дела может занять от 5 минут до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="4cd06-156">It can take between 5 minutes and 24 hours for case hold policies to be successfully distributed.</span></span>

<span data-ttu-id="4cd06-157">Запустите следующую команду, чтобы убедиться, что удержание электронной информации успешно распределено.</span><span class="sxs-lookup"><span data-stu-id="4cd06-157">Run the following command to verify that the eDiscovery hold has been successfully distributed.</span></span>

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

<span data-ttu-id="4cd06-158">Значение **Success** для свойства *DistributionStatus* указывает, что удержание было успешно размещено в расположениях контента.</span><span class="sxs-lookup"><span data-stu-id="4cd06-158">The value of **Success** for the *DistributionStatus* property indicates the hold was successfully placed on the content locations.</span></span> <span data-ttu-id="4cd06-159">Если распределение еще не завершено, отображается значение **Pending.**</span><span class="sxs-lookup"><span data-stu-id="4cd06-159">If the distribution is not yet complete, a value of **Pending** is displayed.</span></span>

![Пример PowerShell Get-CaseHoldPolicy](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a><span data-ttu-id="4cd06-161">Шаг 7. Создание поиска</span><span class="sxs-lookup"><span data-stu-id="4cd06-161">Step 7: Create the search</span></span>

<span data-ttu-id="4cd06-162">Последним шагом является повторное создание поиска, который вы определили в шаге 3, и связать его с делом.</span><span class="sxs-lookup"><span data-stu-id="4cd06-162">The last step is to re-create the search that you identified in Step 3 and associate it with the case.</span></span> <span data-ttu-id="4cd06-163">После создания поиска можно выполнить его с помощью **cmdlet Start-ComplianceSearch** или выполнить его позже.</span><span class="sxs-lookup"><span data-stu-id="4cd06-163">After you create the search, you can run it by using the **Start-ComplianceSearch** cmdlet or run at a later time.</span></span>

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![Пример PowerShell New-ComplianceSearch](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="4cd06-165">Шаг 8. Проверка случая, удержания и поиска в центре соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4cd06-165">Step 8: Verify the case, hold, and search in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="4cd06-166">Чтобы убедиться, что все настроено правильно, перейдите в центр соответствия требованиям Microsoft 365 по ссылке и нажмите [https://compliance.microsoft.com](https://compliance.microsoft.com) **кнопку > Core**.</span><span class="sxs-lookup"><span data-stu-id="4cd06-166">To make sure that everything is set up correctly, go to the Microsoft 365 compliance center at [https://compliance.microsoft.com](https://compliance.microsoft.com), and click **eDiscovery > Core**.</span></span>

![EDiscovery Центра соответствия требованиям Microsoft 365](../media/MigrateLegacyeDiscovery7.png)

<span data-ttu-id="4cd06-168">Случай, созданный в шаге 3, указан на странице **Core eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="4cd06-168">The case that you created in Step 3 is listed on the **Core eDiscovery** page.</span></span> <span data-ttu-id="4cd06-169">Откройте случай, а затем обратите внимание на удержание, созданное в шаге 4 в списке на **вкладке Удержание.** Вы можете щелкнуть удержание, чтобы увидеть сведения, в том числе количество почтовых ящиков, к которых применяется удержание, и состояние рассылки.</span><span class="sxs-lookup"><span data-stu-id="4cd06-169">Open the case and then notice the hold that you created in Step 4 in listed on the **Holds** tab. You can click the hold to see details, including the number of mailboxes the hold is applied to and the distribution status.</span></span>

![eDiscovery содержится в центре соответствия требованиям Microsoft 365](../media/MigrateLegacyeDiscovery8.png)

<span data-ttu-id="4cd06-171">Поиск, созданный в шаге 7, указан на вкладке **"Поиски"** дела об обнаружении электронных обнаружений.</span><span class="sxs-lookup"><span data-stu-id="4cd06-171">The search that you created in Step 7 is listed on the listed on the **Searches** tab of the eDiscovery case.</span></span>

![Поиск по делу об обнаружении электронных данных в центре соответствия требованиям Microsoft 365](../media/MigrateLegacyeDiscovery9.png)

<span data-ttu-id="4cd06-173">Если вы переадружаете поиск In-Place, но не связываете его с делом об обнаружении электронных данных, он будет указан на странице поиска контента в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cd06-173">If you migrate an In-Place eDiscovery search but don't associate it with an eDiscovery case, it will be listed on the Content search page in the Microsoft 365 compliance center.</span></span>

## <a name="more-information"></a><span data-ttu-id="4cd06-174">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="4cd06-174">More information</span></span>

- <span data-ttu-id="4cd06-175">Дополнительные сведения о In-Place eDiscovery & в центре администрирования Exchange см. в.</span><span class="sxs-lookup"><span data-stu-id="4cd06-175">For more information about In-Place eDiscovery & Holds in the Exchange admin center, see:</span></span>
  
  - [<span data-ttu-id="4cd06-176">Обнаружение электронных данных на месте</span><span class="sxs-lookup"><span data-stu-id="4cd06-176">In-Place eDiscovery</span></span>](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [<span data-ttu-id="4cd06-177">Хранение на месте и хранение для судебного разбирательства</span><span class="sxs-lookup"><span data-stu-id="4cd06-177">In-Place Hold and Litigation Hold</span></span>](/exchange/security-and-compliance/in-place-and-litigation-holds)

- <span data-ttu-id="4cd06-178">Дополнительные сведения о cmdlets PowerShell, используемых в статье, см. в статье:</span><span class="sxs-lookup"><span data-stu-id="4cd06-178">For more information about the PowerShell cmdlets used in the article, see:</span></span>

  - [<span data-ttu-id="4cd06-179">Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="4cd06-179">Get-MailboxSearch</span></span>](/powershell/module/exchange/get-mailboxsearch)
  
  - [<span data-ttu-id="4cd06-180">New-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="4cd06-180">New-ComplianceCase</span></span>](/powershell/module/exchange/new-compliancecase)

  - [<span data-ttu-id="4cd06-181">New-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="4cd06-181">New-CaseHoldPolicy</span></span>](/powershell/module/exchange/new-caseholdpolicy)
  
  - [<span data-ttu-id="4cd06-182">New-CaseHoldRule</span><span class="sxs-lookup"><span data-stu-id="4cd06-182">New-CaseHoldRule</span></span>](/powershell/module/exchange/new-caseholdrule)

  - [<span data-ttu-id="4cd06-183">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="4cd06-183">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
  
  - [<span data-ttu-id="4cd06-184">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="4cd06-184">New-ComplianceSearch</span></span>](/powershell/module/exchange/new-compliancesearch)

  - [<span data-ttu-id="4cd06-185">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="4cd06-185">Start-ComplianceSearch</span></span>](/powershell/module/exchange/start-compliancesearch)

- <span data-ttu-id="4cd06-186">Дополнительные сведения о центре соответствия требованиям Microsoft 365 см. в обзоре центра соответствия требованиям [Microsoft 365.](microsoft-365-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="4cd06-186">For more information about the Microsoft 365 compliance center, see [Overview of the Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>