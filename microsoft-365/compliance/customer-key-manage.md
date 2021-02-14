---
title: Управление ключом клиента
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: После того как вы настроите ключ клиента, узнайте, как управлять им, восстанавливая ключи AKV, а также управляя разрешениями и политиками шифрования данных.
ms.openlocfilehash: de85edd5c53fc2b76be4361575e1a85655c0f297
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547089"
---
# <a name="manage-customer-key"></a><span data-ttu-id="3f4e1-103">Управление ключом клиента</span><span class="sxs-lookup"><span data-stu-id="3f4e1-103">Manage Customer Key</span></span>

<span data-ttu-id="3f4e1-104">После того как вы настроите ключ клиента для Office 365, вы сможете управлять ключами, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="3f4e1-105">Узнайте больше о ключе клиента в соответствующих темах.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="3f4e1-106">Восстановление ключей Хранилища ключей Azure</span><span class="sxs-lookup"><span data-stu-id="3f4e1-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="3f4e1-107">Перед выполнением восстановления используйте возможности восстановления, предоставляемые функцией мягкого удаления.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="3f4e1-108">Все ключи, используемые с ключом клиента, должны быть включены для мягкого удаления.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="3f4e1-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="3f4e1-110">Восстановление необходимо только в крайних или необычных обстоятельствах, например, если ключ или хранилище ключей потеряно.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="3f4e1-111">Если необходимо восстановить ключ для использования с ключом клиента, в Azure PowerShell выполните Restore-AzureKeyVaultKey следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3f4e1-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="3f4e1-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="3f4e1-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="3f4e1-113">Если хранилище ключей уже содержит ключ с таким же именем, операция восстановления не будет работать.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="3f4e1-114">Restore-AzKeyVaultKey восстановления всех ключевых версий и всех метаданных ключа, включая имя ключа.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="3f4e1-115">Управление разрешениями хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="3f4e1-115">Manage key vault permissions</span></span>

<span data-ttu-id="3f4e1-116">Доступно несколько cmdlets, которые позволяют просматривать и при необходимости удалять разрешения хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="3f4e1-117">Может потребоваться удалить разрешения, например, когда сотрудник покидает команду.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="3f4e1-118">Для каждой из этих задач используется Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="3f4e1-119">Сведения о Azure Powershell см. в [обзоре Azure PowerShell.](https://docs.microsoft.com/powershell/azure/)</span><span class="sxs-lookup"><span data-stu-id="3f4e1-119">For information about Azure Powershell, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span></span>

<span data-ttu-id="3f4e1-120">Чтобы просмотреть разрешения хранилища ключей, запустите Get-AzKeyVault управления.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="3f4e1-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="3f4e1-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="3f4e1-122">Чтобы удалить разрешения администратора, запустите Remove-AzKeyVaultAccessPolicy:</span><span class="sxs-lookup"><span data-stu-id="3f4e1-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="3f4e1-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="3f4e1-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="3f4e1-124">Управление политиками шифрования данных (DEP) с помощью ключа клиента</span><span class="sxs-lookup"><span data-stu-id="3f4e1-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="3f4e1-125">Ключ клиента обрабатывает DEP по-разному между различными службами.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="3f4e1-126">Например, можно создать разное количество DEP для различных служб.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="3f4e1-127">**Exchange Online и Skype для бизнеса:** Можно создать до 50 DEP.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="3f4e1-128">Инструкции см. в инструкциях по созданию политики шифрования данных [(DEP)](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)для использования с Exchange Online и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="3f4e1-129">**Файлы SharePoint Online, OneDrive для бизнеса и Teams:** DEP применяется к данным в одном географическом расположении, также называемом _географической областью._</span><span class="sxs-lookup"><span data-stu-id="3f4e1-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="3f4e1-130">Если вы используете функцию Office 365 с несколькими географическими службами, вы можете создать одну DEP для каждого географического.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="3f4e1-131">Если вы не используете multi-geo, вы можете создать один DEP.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="3f4e1-132">Как правило, deP создается при создании ключа клиента.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="3f4e1-133">Инструкции см. в инструкциях по созданию политики шифрования данных [(DEP)](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)для каждого географического центра SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="3f4e1-134">Просмотр DEP, созданных для Exchange Online и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3f4e1-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="3f4e1-135">Чтобы просмотреть список всех DEP, созданных для Exchange Online и Skype для бизнеса с помощью Get-DataEncryptionPolicy PowerShell, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="3f4e1-136">Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, подключите [к Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3f4e1-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3f4e1-137">Чтобы вернуть все DEP в организации, запустите Get-DataEncryptionPolicy без параметров.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="3f4e1-138">Дополнительные сведения о Get-DataEncryptionPolicy см. в записи [Get-DataEncryptionPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy)</span><span class="sxs-lookup"><span data-stu-id="3f4e1-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="3f4e1-139">Назначение DEP перед переносом почтового ящика в облако</span><span class="sxs-lookup"><span data-stu-id="3f4e1-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="3f4e1-140">При назначении DEP Microsoft 365 шифрует содержимое почтового ящика с помощью назначенного DEP во время миграции.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="3f4e1-141">Этот процесс более эффективен, чем перенос почтового ящика, назначение DEP и ожидание шифрования, которое может занять несколько часов или, возможно, дней.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="3f4e1-142">Чтобы назначить deP почтовому ящику перед его переносом в Office 365, запустите Set-MailUser в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3f4e1-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="3f4e1-143">Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, подключите [к Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3f4e1-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3f4e1-144">Запустите Set-MailUser управления.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-144">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="3f4e1-145">Где *GeneralMailboxOrMailUserIdParameter* указывает почтовый ящик, а *DataEncryptionPolicyIdParameter* — это ИД DEP.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="3f4e1-146">Дополнительные сведения о Set-MailUser см. в [сообщении Set-MailUser.](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)</span><span class="sxs-lookup"><span data-stu-id="3f4e1-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="3f4e1-147">Определение DEP, назначенного почтовому ящику</span><span class="sxs-lookup"><span data-stu-id="3f4e1-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="3f4e1-148">Чтобы определить DEP, назначенное почтовому ящику, используйте Get-MailboxStatistics управления.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="3f4e1-149">Он возвращает уникальный идентификатор (GUID).</span><span class="sxs-lookup"><span data-stu-id="3f4e1-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="3f4e1-150">Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, подключите [к Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3f4e1-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="3f4e1-151">Где *GeneralMailboxOrMailUserIdParameter* указывает почтовый ящик, а DataEncryptionPolicyID возвращает GUID DEP.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="3f4e1-152">Дополнительные сведения о Get-MailboxStatistics см. в [get-MailboxStatistics.](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics)</span><span class="sxs-lookup"><span data-stu-id="3f4e1-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="3f4e1-153">Запустите Get-DataEncryptionPolicy, чтобы узнать имя DEP, которому назначен почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="3f4e1-154">Где *GUID* — это GUID, возвращенный Get-MailboxStatistics на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="3f4e1-155">Проверка того, что шифрование ключа клиента завершено</span><span class="sxs-lookup"><span data-stu-id="3f4e1-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="3f4e1-156">Выполните действия, которые необходимо выполнить в этом разделе, чтобы убедиться, что шифрование завершено, независимо от того, только что был свернут ключ клиента, назначен новый DEP или перенесен почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="3f4e1-157">Проверка завершения шифрования для Exchange Online и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3f4e1-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="3f4e1-158">Шифрование почтового ящика может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="3f4e1-159">Рекомендуется подождать 72 часа, прежде чем пытаться проверить шифрование после изменения DEP или при первом назначении DEP почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="3f4e1-160">Используйте Get-MailboxStatistics, чтобы определить, зашифрован ли почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="3f4e1-161">Свойство IsEncrypted возвращает значение **true,** если почтовый ящик зашифрован, и значение **false,** если почтовый ящик не зашифрован.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="3f4e1-162">Время завершения перемещения почтового ящика зависит от размера почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="3f4e1-163">Если ключ клиента не зашифровыл почтовый ящик полностью через 72 часа после назначения нового DEP, обратитесь за помощью в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, contact Microsoft support for help.</span></span> <span data-ttu-id="3f4e1-164">Этот New-MoveRequest больше не доступен для локального перемещения почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-164">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="3f4e1-165">Дополнительные [сведения можно найти в этом](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) объявлении.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-165">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="3f4e1-166">Проверка завершения шифрования файлов SharePoint Online, OneDrive для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="3f4e1-166">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="3f4e1-167">Проверьте состояние шифрования, задав Get-SPODataEncryptionPolicy следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3f4e1-167">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="3f4e1-168">Выходные данные этого cmdlet включают:</span><span class="sxs-lookup"><span data-stu-id="3f4e1-168">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="3f4e1-169">URI первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-169">The URI of the primary key.</span></span>

- <span data-ttu-id="3f4e1-170">URI дополнительного ключа.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-170">The URI of the secondary key.</span></span>

- <span data-ttu-id="3f4e1-171">Состояние шифрования для географического положения.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-171">The encryption status for the geo.</span></span> <span data-ttu-id="3f4e1-172">Возможные состояния:</span><span class="sxs-lookup"><span data-stu-id="3f4e1-172">Possible states include:</span></span>

  - <span data-ttu-id="3f4e1-173">**Unregistered:** Шифрование ключа клиента еще не применено.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-173">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="3f4e1-174">**Регистрация:** Шифрование ключа клиента применено, и ваши файлы находятся в процессе шифрования.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-174">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="3f4e1-175">Если регистрируется ключ для географического объекта, вы также увидите сведения о том, какой процент сайтов в географическом отношении завершен, чтобы можно было отслеживать ход шифрования.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-175">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="3f4e1-176">**Зарегистрировано:** Шифрование ключа клиента применено, и все файлы на всех сайтах были зашифрованы.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-176">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="3f4e1-177">**Катящийся:** В настоящее время идет перекат ключа.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-177">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="3f4e1-178">Если ключ для геооблигации скатился, вы также увидите сведения о том, какой процент сайтов выполнил операцию переката ключей, чтобы можно было отслеживать ход выполнения.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-178">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="unassign-a-dep-from-a-mailbox"></a><span data-ttu-id="3f4e1-179">Unassign a DEP from a mailbox</span><span class="sxs-lookup"><span data-stu-id="3f4e1-179">Unassign a DEP from a mailbox</span></span>

<span data-ttu-id="3f4e1-180">Вы отогнание DEP из почтового ящика с помощью параметра Set-mailbox PowerShell и установка `DataEncryptionPolicy` параметра `$NULL` ..</span><span class="sxs-lookup"><span data-stu-id="3f4e1-180">You unassign a DEP from a mailbox using the Set-mailbox PowerShell cmdlet and setting the `DataEncryptionPolicy` to `$NULL`.</span></span> <span data-ttu-id="3f4e1-181">При запуске этого cmdlet списываются назначенная в данный момент DEP и повторно шифруется почтовый ящик с помощью DEP, связанного с управляемыми ключами Майкрософт по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-181">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft managed keys.</span></span> <span data-ttu-id="3f4e1-182">Вы не можете отоименовать DEP, используемую управляемыми ключами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-182">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="3f4e1-183">Если вы не хотите использовать управляемые ключи Майкрософт, вы можете назначить другому DEP почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-183">If you don't want to use Microsoft managed keys, you can assign another DEP to the mailbox.</span></span>

<span data-ttu-id="3f4e1-184">Чтобы отоименовать DEP из почтового ящика с помощью Set-Mailbox PowerShell, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-184">To unassign the DEP from a mailbox using the Set-Mailbox PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="3f4e1-185">Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, подключите [к Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3f4e1-185">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3f4e1-186">Запустите Set-Mailbox управления.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-186">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="3f4e1-187">Отозовите ключи и запустите процесс очистки данных</span><span class="sxs-lookup"><span data-stu-id="3f4e1-187">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="3f4e1-188">Вы управляете отзывом всех корневых ключей, включая ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-188">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="3f4e1-189">Ключ клиента обеспечивает контроль за аспектом планирования выхода нормативных требований.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-189">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="3f4e1-190">Если вы решите отопустить ключи для очистки данных и выхода из службы, служба удалит ключ доступности после завершения процесса очистки данных.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-190">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="3f4e1-191">Microsoft 365 проводит аудит и проверяет путь очистки данных.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-191">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="3f4e1-192">Дополнительные сведения см. в отчете SSAE 18 SOC 2, доступном на [портале Service Trust Portal.](https://servicetrust.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="3f4e1-192">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="3f4e1-193">Кроме того, корпорация Майкрософт рекомендует следующие документы:</span><span class="sxs-lookup"><span data-stu-id="3f4e1-193">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="3f4e1-194">Руководство по оценке рисков и обеспечению соответствия требованиям для финансовых учреждений в Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="3f4e1-194">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="3f4e1-195">Вопросы планирования выхода из O365</span><span class="sxs-lookup"><span data-stu-id="3f4e1-195">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="3f4e1-196">Путь очистки данных немного отличается в разных службах.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-196">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="3f4e1-197">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3f4e1-197">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="3f4e1-198">Когда вы инициируете путь очистки данных для Exchange Online и Skype для бизнеса, вы можете настроить постоянный запрос на очистку данных в DEP.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-198">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="3f4e1-199">Это окончательно удаляет зашифрованные данные в почтовых ящиках, которым назначена deP.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-199">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="3f4e1-200">Так как вы можете одновременно запускать только один cmdlet PowerShell для одного DEP, рассмотрите возможность перенамерования одного DEP для всех почтовых ящиков, прежде чем инициировать путь очистки данных.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-200">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="3f4e1-201">Не используйте путь очистки данных для удаления подмножество почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-201">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="3f4e1-202">Этот процесс предназначен только для клиентов, которые выходят из службы.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-202">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="3f4e1-203">Чтобы инициировать путь очистки данных, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3f4e1-203">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="3f4e1-204">Удалите разрешения на перенос и удаление для "O365 Exchange Online" из хранилищ Ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-204">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="3f4e1-205">Используя учетную запись для работы или учебного заведения с привилегиями глобального администратора в вашей организации, подключите [к Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3f4e1-205">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="3f4e1-206">Для каждого DEP, содержаного почтовые ящики, [](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) которые требуется удалить, выполните этот запуск следующим образом.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-206">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="3f4e1-207">Если команда не удалась, убедитесь, что вы удалили разрешения Exchange Online из обоих ключей в Azure Key Vault, как указано ранее в этой задаче.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-207">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="3f4e1-208">После того как вы настроите переключатель PermanentDataPurgeRequested с помощью Set-DataEncryptionPolicy, вы больше не сможете назначить этот DEP почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-208"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="3f4e1-209">Обратитесь в службу поддержки Майкрософт и запросите очистку данных eDocument.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-209">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="3f4e1-210">По вашему запросу корпорация Майкрософт отправляет вам юридический документ для подтверждения и авторизации удаления данных.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-210">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="3f4e1-211">Человек в вашей организации, который зарегистрировался в качестве утвержденного в предложении FastTrack во время входной регистрации, должен подписать этот документ.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-211">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="3f4e1-212">Как правило, это руководитель или другой назначенный человек в вашей компании, который имеет юридические полномочия подписывать документы от имени вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-212">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="3f4e1-213">После того как ваш представитель подписает юридический документ, верните его в корпорацию Майкрософт (обычно с помощью подписи eDoc).</span><span class="sxs-lookup"><span data-stu-id="3f4e1-213">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="3f4e1-214">Когда корпорация Майкрософт получит юридический документ, корпорация Майкрософт запускает для запуска очистки данных, которая сначала удаляет политику, пометит почтовые ящики для постоянного удаления, а затем удалит ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-214">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="3f4e1-215">После завершения процесса очистки данных данные будут очищены, недоступны для Exchange Online и не будут восстановлены.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-215">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="3f4e1-216">Отозовите ключи клиента и ключ доступности для файлов SharePoint Online, OneDrive для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="3f4e1-216">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="3f4e1-217">Чтобы инициировать путь очистки данных для файлов SharePoint Online, OneDrive для бизнеса и Teams, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3f4e1-217">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="3f4e1-218">Отозовет доступ к хранилищу Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-218">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="3f4e1-219">Все администраторы хранилища ключей должны согласиться на отопуск доступа.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-219">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="3f4e1-220">Хранилище Azure Key Vault для SharePoint Online не удаляется.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-220">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="3f4e1-221">Хранилища ключей могут совместно использовать несколько клиентов SharePoint Online и DEP.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-221">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="3f4e1-222">Обратитесь в корпорацию Майкрософт, чтобы удалить ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-222">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="3f4e1-223">Когда вы обратитесь в корпорацию Майкрософт, чтобы удалить ключ доступности, мы отправим вам юридический документ.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-223">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="3f4e1-224">Человек в вашей организации, который зарегистрировался в качестве утвержденного в предложении FastTrack во время входной регистрации, должен подписать этот документ.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-224">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="3f4e1-225">Как правило, это руководитель или другой назначенный человек в вашей компании, который имеет юридические полномочия подписывать документы от имени вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-225">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="3f4e1-226">После того как ваш представитель подпишет юридический документ, верните его в корпорацию Майкрософт (обычно с помощью подписи eDoc).</span><span class="sxs-lookup"><span data-stu-id="3f4e1-226">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="3f4e1-227">Когда корпорация Майкрософт получит юридический документ, мы запускаем с его запуском очистку данных, которая выполняет криптографической очистку ключа клиента, ключа сайта и всех отдельных ключей для каждого документа, что безвозвратно разрывает иерархию ключей.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-227">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="3f4e1-228">После завершения работы с данными для очистки данные будут очищены.</span><span class="sxs-lookup"><span data-stu-id="3f4e1-228">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3f4e1-229">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3f4e1-229">Related articles</span></span>

- [<span data-ttu-id="3f4e1-230">Шифрование службы с помощью ключа клиента</span><span class="sxs-lookup"><span data-stu-id="3f4e1-230">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="3f4e1-231">Узнайте о ключе доступности</span><span class="sxs-lookup"><span data-stu-id="3f4e1-231">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="3f4e1-232">Настройка ключа клиента</span><span class="sxs-lookup"><span data-stu-id="3f4e1-232">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="3f4e1-233">Смена или ротация ключа клиента или ключа доступности</span><span class="sxs-lookup"><span data-stu-id="3f4e1-233">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="3f4e1-234">Защищенное хранилище пользователя</span><span class="sxs-lookup"><span data-stu-id="3f4e1-234">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="3f4e1-235">Шифрование службы</span><span class="sxs-lookup"><span data-stu-id="3f4e1-235">Service Encryption</span></span>](office-365-service-encryption.md)
