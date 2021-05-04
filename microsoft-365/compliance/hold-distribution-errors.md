---
title: Устранение ошибок удержания электронных данных
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Устранение ошибок, связанных с юридическими хранениями, применяемыми к хранителям и источникам данных, не связанным с хранением, в Core eDiscovery.
ms.openlocfilehash: 3bd417f2eb6bfb8de8d4b5ccaeb48e6ae1c888eb
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860390"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a><span data-ttu-id="8174f-103">Устранение ошибок удержания электронных данных</span><span class="sxs-lookup"><span data-stu-id="8174f-103">Troubleshoot eDiscovery hold errors</span></span>

<span data-ttu-id="8174f-104">В этой статье обсуждаются распространенные проблемы, которые могут возникать с помощью удерживаемого электронных обнаружений, и их устранение.</span><span class="sxs-lookup"><span data-stu-id="8174f-104">This article discusses common issues that may occur with eDiscovery holds and how to resolve them.</span></span> <span data-ttu-id="8174f-105">В статье также содержатся рекомендации по смягчению или предотвращению этих проблем.</span><span class="sxs-lookup"><span data-stu-id="8174f-105">The article also includes recommended practices to help you mitigate or avoid these issues.</span></span>

## <a name="recommended-practices"></a><span data-ttu-id="8174f-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="8174f-106">Recommended practices</span></span>

<span data-ttu-id="8174f-107">Чтобы уменьшить количество ошибок, связанных с удерживаемой электронной тайной, рекомендуется использовать следующие методы:</span><span class="sxs-lookup"><span data-stu-id="8174f-107">To reduce the number of errors related to eDiscovery holds, we recommend the following practices:</span></span>

- <span data-ttu-id="8174f-108">Если распределение удержания еще не завершено, с состоянием либо, либо , подождите, пока распределение удержания не будет завершено, прежде чем делать `On (Pending)` `Off (Pending)` какие-либо дополнительные обновления.</span><span class="sxs-lookup"><span data-stu-id="8174f-108">If a hold distribution is still pending, with a status of either `On (Pending)` or `Off (Pending)`, wait until the hold distribution is complete before you make any further updates.</span></span>

- <span data-ttu-id="8174f-109">Объединяйте обновления с удержанием электронных обнаружений в одном массовом запросе вместо многократного обновления политики удержания для каждой транзакции.</span><span class="sxs-lookup"><span data-stu-id="8174f-109">Merge your updates to an eDiscovery hold in a single bulk request rather than updating the hold policy repeatedly for each transaction.</span></span> <span data-ttu-id="8174f-110">Например, чтобы добавить несколько почтовых ящиков пользователей в существующую политику удержания с помощью командлета [Set-CaseHoldPolicy,](/powershell/module/exchange/set-caseholdpolicy) запустите команду (или добавьте в скрипт в качестве блока кода), чтобы она запускалась только один раз, чтобы добавить несколько пользователей.</span><span class="sxs-lookup"><span data-stu-id="8174f-110">For example, to add multiple user mailboxes to an existing hold policy using the [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet, run the command (or add as a code block to a script) so that it runs only once to add multiple users.</span></span>

  <span data-ttu-id="8174f-111">**Правильный вариант**</span><span class="sxs-lookup"><span data-stu-id="8174f-111">**Correct**</span></span>

    ```powershell
    Set-CaseHoldPolicy -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   <span data-ttu-id="8174f-112">**Неправильный вариант**</span><span class="sxs-lookup"><span data-stu-id="8174f-112">**Incorrect**</span></span>

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -AddExchangeLocation $user
    }
    ```

   <span data-ttu-id="8174f-113">В предыдущем неправильном примере для выполнения задачи для выполнения задачи будет запускаться пять раз.</span><span class="sxs-lookup"><span data-stu-id="8174f-113">In the previous incorrect example, the cmdlet is run five separate times to complete the task.</span></span> <span data-ttu-id="8174f-114">Дополнительные сведения о рекомендуемых практиках добавления пользователей в политику удержания см. в [разделе Дополнительные сведения.](#more-information)</span><span class="sxs-lookup"><span data-stu-id="8174f-114">For more information about the recommended practices for adding users to a hold policy, see the [More information](#more-information) section.</span></span>

- <span data-ttu-id="8174f-115">Прежде чем обращаться в службу поддержки Майкрософт по поводу проблем с удержанием электронных данных, выполните действия в разделе [Ошибка/проблема.](#errorissue-holds-dont-sync) В разделе Удержание не синхронизируйтесь, чтобы повторить распространение удержания.</span><span class="sxs-lookup"><span data-stu-id="8174f-115">Before contacting Microsoft Support about eDiscovery hold issues, follow the steps in the [Error/issue: Holds don't sync](#errorissue-holds-dont-sync) section to retry the hold distribution.</span></span> <span data-ttu-id="8174f-116">Этот процесс часто устраняет временные проблемы, включая внутренние ошибки сервера.</span><span class="sxs-lookup"><span data-stu-id="8174f-116">This process often resolves temporary issues including, internal server errors.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="8174f-117">Ошибка/проблема. Не синхронизируются удерживаемая</span><span class="sxs-lookup"><span data-stu-id="8174f-117">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="8174f-118">Если вы видите одно из следующих сообщений об ошибке при удержании хранителей и источников данных, используйте шаги по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="8174f-118">If you see one the following error messages when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="8174f-119">Ресурсы. Развертывание политики может затметь больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="8174f-119">Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="8174f-120">На обновление состояния окончательного развертывания может потребоваться дополнительно 2 часа, поэтому проверьте это в течение нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="8174f-120">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

> <span data-ttu-id="8174f-121">Политика не может быть развернута в источнике контента из-за Office 365 центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="8174f-121">Policy cannot be deployed to the content source due to a temporary Office 365 datacenter issue.</span></span> <span data-ttu-id="8174f-122">Текущая политика не применяется к любому контенту в источнике, поэтому от заблокированного развертывания никакого влияния не будет.</span><span class="sxs-lookup"><span data-stu-id="8174f-122">The current policy is not applied to any content in the source, so there's no impact from the blocked deployment.</span></span> <span data-ttu-id="8174f-123">Чтобы устранить эту проблему, попробуйте перенаправить политику.</span><span class="sxs-lookup"><span data-stu-id="8174f-123">To fix this issue, please try redeploying the policy.</span></span>

> <span data-ttu-id="8174f-124">К сожалению, мы не смогли выполнить запрашиваемое изменение политики из-за преходящей ошибки внутреннего сервера.</span><span class="sxs-lookup"><span data-stu-id="8174f-124">Sorry, we could not perform the requested changes to policy due to a transient internal server error.</span></span> <span data-ttu-id="8174f-125">Попробуйте еще раз через 30 минут.</span><span class="sxs-lookup"><span data-stu-id="8174f-125">Please try again in 30 minutes.</span></span>

### <a name="resolution"></a><span data-ttu-id="8174f-126">Решение</span><span class="sxs-lookup"><span data-stu-id="8174f-126">Resolution</span></span>

1. <span data-ttu-id="8174f-127">Подключение службу безопасности & Центра соответствия требованиям [PowerShell](/powershell/exchange/connect-to-scc-powershell) и запустите следующую команду для удержания электронных данных:</span><span class="sxs-lookup"><span data-stu-id="8174f-127">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command for an eDiscovery hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. <span data-ttu-id="8174f-128">Изучите значение *параметра DistributionDetail.*</span><span class="sxs-lookup"><span data-stu-id="8174f-128">Examine the value in the *DistributionDetail* parameter.</span></span> <span data-ttu-id="8174f-129">И посмотрите на ошибки, такие как следующие:</span><span class="sxs-lookup"><span data-stu-id="8174f-129">Look for errors like the following:</span></span>

   > <span data-ttu-id="8174f-130">Ошибка. Ресурсы. Развертывание политики проходит дольше, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="8174f-130">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="8174f-131">На обновление состояния окончательного развертывания может потребоваться дополнительно 2 часа, поэтому проверьте это в течение нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="8174f-131">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

3. <span data-ttu-id="8174f-132">Попробуйте запускать команду **Set-CaseHoldPolicy -RetryDistribution** в политике удержания, о чем идет речь; Например:</span><span class="sxs-lookup"><span data-stu-id="8174f-132">Try running the **Set-CaseHoldPolicy -RetryDistribution** command on the hold policy in question; for example:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="more-information"></a><span data-ttu-id="8174f-133">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="8174f-133">More information</span></span>

- <span data-ttu-id="8174f-134">Руководство по обновлению политик удержания для нескольких пользователей в разделе "Рекомендуемые практики" приводит к тому, что система блокирует одновременные обновления в политику удержания.</span><span class="sxs-lookup"><span data-stu-id="8174f-134">The guidance about updating hold policies for multiple users in the "Recommended practices" section results from the fact that the system blocks simultaneous updates to a hold policy.</span></span> <span data-ttu-id="8174f-135">Это означает, что если обновленная политика удержания применяется к новым расположениям контента и политика удержания находится в состоянии ожидания, дополнительные расположения контента не могут быть добавлены в политику удержания.</span><span class="sxs-lookup"><span data-stu-id="8174f-135">That means when an updated hold policy is applied to new content locations and the hold policy is in a pending state, additional content locations can't be added to the hold policy.</span></span> <span data-ttu-id="8174f-136">Вот некоторые моменты, которые необходимо помнить, чтобы помочь вам устранить эту проблему:</span><span class="sxs-lookup"><span data-stu-id="8174f-136">Here are some things to keep in mind to help you mitigate this issue:</span></span>
  
  - <span data-ttu-id="8174f-137">Каждый раз, когда обновляется удержание, оно немедленно переходит в состояние ожидания.</span><span class="sxs-lookup"><span data-stu-id="8174f-137">Every time a hold updated is updated, it immediately goes into a pending state.</span></span> <span data-ttu-id="8174f-138">Состояние состояния ожидания означает, что удержание применяется к расположениям контента.</span><span class="sxs-lookup"><span data-stu-id="8174f-138">The pending state status means the hold is being applied to content locations.</span></span>
  
  - <span data-ttu-id="8174f-139">Если у вас есть сценарий, который выполняет цикл и добавляет расположения в политику по одному (аналогично неправильному примеру, показанного в разделе "Рекомендуемые практики"), первое расположение контента (например, почтовый ящик пользователя) запускает процесс синхронизации, который вызывает ожидаемое состояние.</span><span class="sxs-lookup"><span data-stu-id="8174f-139">If you have a script that runs a loop and adds locations to policy one by one (similar to the incorrect example shown in the "Recommended practices" section), the first content location (for example, a user mailbox) initiates the sync process that triggers the pending state.</span></span> <span data-ttu-id="8174f-140">Это означает, что другие пользователи, добавленные в политику в последующих циклах, могут привести к ошибке.</span><span class="sxs-lookup"><span data-stu-id="8174f-140">That means the other users that are added to the policy in subsequent loops result in an error.</span></span>
  
  - <span data-ttu-id="8174f-141">Если ваша организация использует скрипт, который выполняет цикл обновления расположения контента для политики удержания, необходимо обновить сценарий, чтобы он обновлял расположения в одной объемной операции (как показано в правильном примере в разделе "Рекомендуемые практики").</span><span class="sxs-lookup"><span data-stu-id="8174f-141">If your organization is using a script that runs a loop to update the content locations for a hold policy, you must update the script so that it updates locations in a single bulk operation (as shown in the correct example in the "Recommended practices" section).</span></span>
