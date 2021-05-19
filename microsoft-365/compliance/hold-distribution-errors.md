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
ms.openlocfilehash: b101bf92c6a304262b3886a4ce0280f427a4a847
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538475"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a><span data-ttu-id="44207-103">Устранение ошибок удержания электронных данных</span><span class="sxs-lookup"><span data-stu-id="44207-103">Troubleshoot eDiscovery hold errors</span></span>

<span data-ttu-id="44207-104">В этой статье обсуждаются распространенные проблемы, которые могут возникать с помощью удерживаемого электронных обнаружений, и их устранение.</span><span class="sxs-lookup"><span data-stu-id="44207-104">This article discusses common issues that may occur with eDiscovery holds and how to resolve them.</span></span> <span data-ttu-id="44207-105">В статье также содержатся рекомендации по смягчению или предотвращению этих проблем.</span><span class="sxs-lookup"><span data-stu-id="44207-105">The article also includes recommended practices to help you mitigate or avoid these issues.</span></span>

## <a name="recommended-practices"></a><span data-ttu-id="44207-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="44207-106">Recommended practices</span></span>

<span data-ttu-id="44207-107">Чтобы уменьшить количество ошибок, связанных с удерживаемой электронной тайной, рекомендуется использовать следующие методы:</span><span class="sxs-lookup"><span data-stu-id="44207-107">To reduce the number of errors related to eDiscovery holds, we recommend the following practices:</span></span>

- <span data-ttu-id="44207-108">Если распределение удержания еще не завершено, с состоянием либо, либо , подождите, пока распределение удержания не будет завершено, прежде чем делать `On (Pending)` `Off (Pending)` какие-либо дополнительные обновления.</span><span class="sxs-lookup"><span data-stu-id="44207-108">If a hold distribution is still pending, with a status of either `On (Pending)` or `Off (Pending)`, wait until the hold distribution is complete before you make any further updates.</span></span>

- <span data-ttu-id="44207-109">Проверьте, не ожидается ли политика удержания перед тем, как внести в нее какие-либо дополнительные обновления.</span><span class="sxs-lookup"><span data-stu-id="44207-109">Check whether a hold policy is pending before you make any further updates to it.</span></span> <span data-ttu-id="44207-110">Запустите следующие команды или сохраните их в скрипте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44207-110">Run the following commands or save them to a PowerShell script.</span></span>

    ```powershell
    $status = Get-CaseHoldPolicy -Identity <policyname> 
    if($status.DistributionStatus -ne "Pending"){
        # policy no longer pending
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user1
    }else{
        # policy still pending
        Write-Host "Hold policy still pending."
    }
   ```

- <span data-ttu-id="44207-111">Объединяйте обновления с удержанием электронных обнаружений в одном массовом запросе вместо многократного обновления политики удержания для каждой транзакции.</span><span class="sxs-lookup"><span data-stu-id="44207-111">Merge your updates to an eDiscovery hold in a single bulk request rather than updating the hold policy repeatedly for each transaction.</span></span> <span data-ttu-id="44207-112">Например, чтобы добавить несколько почтовых ящиков пользователей в существующую политику удержания с помощью командлета [Set-CaseHoldPolicy,](/powershell/module/exchange/set-caseholdpolicy) запустите команду (или добавьте в скрипт в качестве блока кода), чтобы она запускалась только один раз, чтобы добавить несколько пользователей.</span><span class="sxs-lookup"><span data-stu-id="44207-112">For example, to add multiple user mailboxes to an existing hold policy using the [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet, run the command (or add as a code block to a script) so that it runs only once to add multiple users.</span></span>

  <span data-ttu-id="44207-113">**Правильный вариант**</span><span class="sxs-lookup"><span data-stu-id="44207-113">**Correct**</span></span>

    ```powershell
    Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   <span data-ttu-id="44207-114">**Неправильный вариант**</span><span class="sxs-lookup"><span data-stu-id="44207-114">**Incorrect**</span></span>

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user
    }
    ```

   <span data-ttu-id="44207-115">В предыдущем неправильном примере для выполнения задачи для выполнения задачи будет запускаться пять раз.</span><span class="sxs-lookup"><span data-stu-id="44207-115">In the previous incorrect example, the cmdlet is run five separate times to complete the task.</span></span> <span data-ttu-id="44207-116">Дополнительные сведения о рекомендуемых практиках добавления пользователей в политику удержания см. в [разделе Дополнительные сведения.](#more-information)</span><span class="sxs-lookup"><span data-stu-id="44207-116">For more information about the recommended practices for adding users to a hold policy, see the [More information](#more-information) section.</span></span>

- <span data-ttu-id="44207-117">Прежде чем обращаться в службу поддержки Майкрософт по поводу проблем с удержанием электронных данных, выполните действия в разделе [Ошибка/проблема.](#errorissue-holds-dont-sync) В разделе Удержание не синхронизируйтесь, чтобы повторить распространение удержания.</span><span class="sxs-lookup"><span data-stu-id="44207-117">Before contacting Microsoft Support about eDiscovery hold issues, follow the steps in the [Error/issue: Holds don't sync](#errorissue-holds-dont-sync) section to retry the hold distribution.</span></span> <span data-ttu-id="44207-118">Этот процесс часто устраняет временные проблемы, включая внутренние ошибки сервера.</span><span class="sxs-lookup"><span data-stu-id="44207-118">This process often resolves temporary issues including, internal server errors.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="44207-119">Ошибка/проблема. Не синхронизируются удерживаемая</span><span class="sxs-lookup"><span data-stu-id="44207-119">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="44207-120">Если вы видите одно из следующих сообщений об ошибке при удержании хранителей и источников данных, используйте шаги по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="44207-120">If you see one the following error messages when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="44207-121">Ресурсы. Развертывание политики может затметь больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="44207-121">Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="44207-122">На обновление состояния окончательного развертывания может потребоваться дополнительно 2 часа, поэтому проверьте это в течение нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="44207-122">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

> <span data-ttu-id="44207-123">Политика не может быть развернута в источнике контента из-за Office 365 центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="44207-123">Policy cannot be deployed to the content source due to a temporary Office 365 datacenter issue.</span></span> <span data-ttu-id="44207-124">Текущая политика не применяется к любому контенту в источнике, поэтому от заблокированного развертывания никакого влияния не будет.</span><span class="sxs-lookup"><span data-stu-id="44207-124">The current policy is not applied to any content in the source, so there's no impact from the blocked deployment.</span></span> <span data-ttu-id="44207-125">Чтобы устранить эту проблему, попробуйте перенаправить политику.</span><span class="sxs-lookup"><span data-stu-id="44207-125">To fix this issue, please try redeploying the policy.</span></span>

> <span data-ttu-id="44207-126">К сожалению, мы не смогли выполнить запрашиваемое изменение политики из-за преходящей ошибки внутреннего сервера.</span><span class="sxs-lookup"><span data-stu-id="44207-126">Sorry, we could not perform the requested changes to policy due to a transient internal server error.</span></span> <span data-ttu-id="44207-127">Попробуйте еще раз через 30 минут.</span><span class="sxs-lookup"><span data-stu-id="44207-127">Please try again in 30 minutes.</span></span>

### <a name="resolution"></a><span data-ttu-id="44207-128">Решение</span><span class="sxs-lookup"><span data-stu-id="44207-128">Resolution</span></span>

1. <span data-ttu-id="44207-129">Подключение службу безопасности & Центра соответствия требованиям [PowerShell](/powershell/exchange/connect-to-scc-powershell) и запустите следующую команду для удержания электронных данных:</span><span class="sxs-lookup"><span data-stu-id="44207-129">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command for an eDiscovery hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. <span data-ttu-id="44207-130">Изучите значение *параметра DistributionDetail.*</span><span class="sxs-lookup"><span data-stu-id="44207-130">Examine the value in the *DistributionDetail* parameter.</span></span> <span data-ttu-id="44207-131">И посмотрите на ошибки, такие как следующие:</span><span class="sxs-lookup"><span data-stu-id="44207-131">Look for errors like the following:</span></span>

   > <span data-ttu-id="44207-132">Ошибка. Ресурсы. Развертывание политики проходит дольше, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="44207-132">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="44207-133">На обновление состояния окончательного развертывания может потребоваться дополнительно 2 часа, поэтому проверьте это в течение нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="44207-133">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

3. <span data-ttu-id="44207-134">Попробуйте запускать команду **Set-CaseHoldPolicy -RetryDistribution** в политике удержания, о чем идет речь; Например:</span><span class="sxs-lookup"><span data-stu-id="44207-134">Try running the **Set-CaseHoldPolicy -RetryDistribution** command on the hold policy in question; for example:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="error-the-sharepoint-site-is-read-only-or-not-accessible"></a><span data-ttu-id="44207-135">Ошибка: SharePoint является доступным только для чтения или недоступным</span><span class="sxs-lookup"><span data-stu-id="44207-135">Error: The SharePoint site is read-only or not accessible</span></span>

<span data-ttu-id="44207-136">Если вы видите следующее сообщение об ошибке при удержании хранителей и источников данных, это означает, что глобальный администратор [или](/sharepoint/sharepoint-admin-role) администратор SharePoint организации заблокировали сайт.</span><span class="sxs-lookup"><span data-stu-id="44207-136">If you see the following error message when putting custodians and data sources on hold, it means that your organization's [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) has locked the site.</span></span> <span data-ttu-id="44207-137">Заблокированный сайт блокирует возможность размещения удержания на сайте.</span><span class="sxs-lookup"><span data-stu-id="44207-137">A locked site blocks eDiscovery from placing a hold on the site.</span></span>

> <span data-ttu-id="44207-138">Сайт SharePoint только для чтения или не доступен.</span><span class="sxs-lookup"><span data-stu-id="44207-138">The SharePoint site is read-only or not accessible.</span></span> <span data-ttu-id="44207-139">Обратитесь к администратору сайта, чтобы сделать сайт понятным, а затем перенаправление этой политики.</span><span class="sxs-lookup"><span data-stu-id="44207-139">Please contact the site administrator to make the site writable, and then redeploy this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="44207-140">Решение</span><span class="sxs-lookup"><span data-stu-id="44207-140">Resolution</span></span>

<span data-ttu-id="44207-141">Разблокировать сайт (или попросить администратора разблокировать его) для решения этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="44207-141">Unlock the site (or ask an admin to unlock it) to resolve this issue.</span></span> <span data-ttu-id="44207-142">Дополнительные информацию о том, как изменить состояние блокировки для сайта, см. в [сайте Lock and unlock sites.](/sharepoint/manage-lock-status)</span><span class="sxs-lookup"><span data-stu-id="44207-142">To learn more about how to change the lock state for a site, see [Lock and unlock sites](/sharepoint/manage-lock-status).</span></span>

## <a name="error-the-mailbox-or-sharepoint-site-may-not-exist"></a><span data-ttu-id="44207-143">Ошибка. Почтовый ящик или SharePoint может не существовать</span><span class="sxs-lookup"><span data-stu-id="44207-143">Error: The mailbox or SharePoint site may not exist</span></span>

<span data-ttu-id="44207-144">Если вы видите следующее сообщение об ошибке при удержании хранителей и источников данных, используйте шаги по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="44207-144">If you see the following error message when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="44207-145">Почтовый ящик или SharePoint может не существовать.</span><span class="sxs-lookup"><span data-stu-id="44207-145">The mailbox or SharePoint site may not exist.</span></span>  <span data-ttu-id="44207-146">Если это неправильно, обратитесь в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="44207-146">If this is incorrect, please contact Microsoft support.</span></span>  <span data-ttu-id="44207-147">В противном случае удалите его из этой политики.</span><span class="sxs-lookup"><span data-stu-id="44207-147">Otherwise, please remove it from this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="44207-148">Решение</span><span class="sxs-lookup"><span data-stu-id="44207-148">Resolution</span></span>

- <span data-ttu-id="44207-149">Запустите почтовый ящик [Get-Mailbox](/powershell/module/exchange/get-mailbox) в Exchange Online PowerShell, чтобы проверить, существует ли почтовый ящик пользователя в организации.</span><span class="sxs-lookup"><span data-stu-id="44207-149">Run the [Get-Mailbox](/powershell/module/exchange/get-mailbox) in Exchange Online PowerShell to check if the user mailbox exists in your organization.</span></span>

- <span data-ttu-id="44207-150">Запустите [комлет Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) в SharePoint PowerShell, чтобы проверить, существует ли сайт в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="44207-150">Run the [Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) cmdlet in SharePoint Online PowerShell to check if the site exists in your organization.</span></span>

- <span data-ttu-id="44207-151">Проверьте, изменился ли URL-адрес сайта.</span><span class="sxs-lookup"><span data-stu-id="44207-151">Check to see if the site URL has changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="44207-152">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="44207-152">More information</span></span>

<span data-ttu-id="44207-153">Руководство по обновлению политик удержания для нескольких пользователей в разделе "Рекомендуемые практики" приводит к тому, что система блокирует одновременные обновления в политику удержания.</span><span class="sxs-lookup"><span data-stu-id="44207-153">The guidance about updating hold policies for multiple users in the "Recommended practices" section results from the fact that the system blocks simultaneous updates to a hold policy.</span></span> <span data-ttu-id="44207-154">Это означает, что если обновленная политика удержания применяется к новым расположениям контента и политика удержания находится в состоянии ожидания, дополнительные расположения контента не могут быть добавлены в политику удержания.</span><span class="sxs-lookup"><span data-stu-id="44207-154">That means when an updated hold policy is applied to new content locations and the hold policy is in a pending state, additional content locations can't be added to the hold policy.</span></span> <span data-ttu-id="44207-155">Вот некоторые моменты, которые необходимо помнить, чтобы помочь вам устранить эту проблему:</span><span class="sxs-lookup"><span data-stu-id="44207-155">Here are some things to keep in mind to help you mitigate this issue:</span></span>
  
- <span data-ttu-id="44207-156">Каждый раз, когда обновляется удержание, оно немедленно переходит в состояние ожидания.</span><span class="sxs-lookup"><span data-stu-id="44207-156">Every time a hold updated is updated, it immediately goes into a pending state.</span></span> <span data-ttu-id="44207-157">Состояние состояния ожидания означает, что удержание применяется к расположениям контента.</span><span class="sxs-lookup"><span data-stu-id="44207-157">The pending state status means the hold is being applied to content locations.</span></span>
  
- <span data-ttu-id="44207-158">Если у вас есть сценарий, который выполняет цикл и добавляет расположения в политику по одному (аналогично неправильному примеру, показанного в разделе "Рекомендуемые практики"), первое расположение контента (например, почтовый ящик пользователя) запускает процесс синхронизации, который вызывает ожидаемое состояние.</span><span class="sxs-lookup"><span data-stu-id="44207-158">If you have a script that runs a loop and adds locations to policy one by one (similar to the incorrect example shown in the "Recommended practices" section), the first content location (for example, a user mailbox) initiates the sync process that triggers the pending state.</span></span> <span data-ttu-id="44207-159">Это означает, что другие пользователи, добавленные в политику в последующих циклах, могут привести к ошибке.</span><span class="sxs-lookup"><span data-stu-id="44207-159">That means the other users that are added to the policy in subsequent loops result in an error.</span></span>
  
- <span data-ttu-id="44207-160">Если ваша организация использует скрипт, который выполняет цикл обновления расположения контента для политики удержания, необходимо обновить сценарий, чтобы он обновлял расположения в одной объемной операции (как показано в правильном примере в разделе "Рекомендуемые практики").</span><span class="sxs-lookup"><span data-stu-id="44207-160">If your organization is using a script that runs a loop to update the content locations for a hold policy, you must update the script so that it updates locations in a single bulk operation (as shown in the correct example in the "Recommended practices" section).</span></span>
