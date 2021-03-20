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
description: После настройка ключа клиента узнайте, как управлять им, восстановив ключи AKV, а также управляя разрешениями и политиками шифрования данных.
ms.openlocfilehash: 8f55667254ce7f5cbd9d4de274623ca4a3c4aa9d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909951"
---
# <a name="manage-customer-key"></a><span data-ttu-id="0042f-103">Управление ключом клиента</span><span class="sxs-lookup"><span data-stu-id="0042f-103">Manage Customer Key</span></span>

<span data-ttu-id="0042f-104">После того как вы настроите ключ клиента для Office 365, вы сможете управлять ключами, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0042f-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="0042f-105">Дополнительные данные о ключе клиента в связанных темах.</span><span class="sxs-lookup"><span data-stu-id="0042f-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="0042f-106">Восстановление ключей Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="0042f-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="0042f-107">Перед выполнением восстановления используйте возможности восстановления, предоставляемые мягким удалением.</span><span class="sxs-lookup"><span data-stu-id="0042f-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="0042f-108">Для всех ключей, используемых с ключом клиента, требуется включить мягкое удаление.</span><span class="sxs-lookup"><span data-stu-id="0042f-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="0042f-109">Мягкое удаление действует как корзина для переработки и позволяет восстанавливать до 90 дней без необходимости восстановления.</span><span class="sxs-lookup"><span data-stu-id="0042f-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="0042f-110">Восстановление должно требоваться только в экстремальных или необычных обстоятельствах, например, если ключ или хранилище ключа потеряно.</span><span class="sxs-lookup"><span data-stu-id="0042f-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="0042f-111">Если необходимо восстановить ключ для использования с ключом клиента, в Azure PowerShell выполните Restore-AzureKeyVaultKey следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0042f-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="0042f-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="0042f-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="0042f-113">Если хранилище ключей уже содержит ключ с тем же именем, операция восстановления сбой.</span><span class="sxs-lookup"><span data-stu-id="0042f-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="0042f-114">Restore-AzKeyVaultKey восстанавливает все ключевые версии и все метаданные для ключа, включая имя ключа.</span><span class="sxs-lookup"><span data-stu-id="0042f-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="0042f-115">Управление разрешениями хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="0042f-115">Manage key vault permissions</span></span>

<span data-ttu-id="0042f-116">Доступно несколько cmdlets, которые позволяют просматривать и при необходимости удалять разрешения на хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="0042f-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="0042f-117">Может потребоваться удалить разрешения, например, когда сотрудник покидает команду.</span><span class="sxs-lookup"><span data-stu-id="0042f-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="0042f-118">Для каждой из этих задач вы будете использовать Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0042f-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="0042f-119">Сведения о Azure Powershell см. в [обзоре Azure PowerShell.](/powershell/azure/)</span><span class="sxs-lookup"><span data-stu-id="0042f-119">For information about Azure Powershell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="0042f-120">Чтобы просмотреть разрешения хранилища ключей, запустите Get-AzKeyVault.</span><span class="sxs-lookup"><span data-stu-id="0042f-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="0042f-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="0042f-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="0042f-122">Чтобы удалить разрешения администратора, запустите Remove-AzKeyVaultAccessPolicy:</span><span class="sxs-lookup"><span data-stu-id="0042f-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="0042f-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="0042f-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="0042f-124">Управление политиками шифрования данных (DEP) с помощью ключа клиента</span><span class="sxs-lookup"><span data-stu-id="0042f-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="0042f-125">Ключ клиента обрабатывает dePs по-разному между различными службами.</span><span class="sxs-lookup"><span data-stu-id="0042f-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="0042f-126">Например, можно создать другое число dePs для различных служб.</span><span class="sxs-lookup"><span data-stu-id="0042f-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="0042f-127">**Exchange Online и Skype для бизнеса:** Можно создать до 50 dePs.</span><span class="sxs-lookup"><span data-stu-id="0042f-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="0042f-128">Инструкции см. в [инструкции Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business.](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)</span><span class="sxs-lookup"><span data-stu-id="0042f-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="0042f-129">**Файлы SharePoint Online, OneDrive для бизнеса и Teams:** DeP применяется к данным в одном географическом расположении, также называемом _geo_.</span><span class="sxs-lookup"><span data-stu-id="0042f-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="0042f-130">Если вы используете многофункциональный элемент Office 365, можно создать один DEP на один гео.</span><span class="sxs-lookup"><span data-stu-id="0042f-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="0042f-131">Если вы не используете multi-geo, можно создать один DEP.</span><span class="sxs-lookup"><span data-stu-id="0042f-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="0042f-132">Обычно при создании ключа клиента создается deP.</span><span class="sxs-lookup"><span data-stu-id="0042f-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="0042f-133">Инструкции см. в раздел Создание политики шифрования данных [(DEP)](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)для каждого SharePoint Online и OneDrive для бизнеса geo.</span><span class="sxs-lookup"><span data-stu-id="0042f-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="0042f-134">Просмотр dePs, созданных для Exchange Online и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0042f-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="0042f-135">Чтобы просмотреть список всех dePs, созданных для Exchange Online и Skype для бизнеса с помощью Get-DataEncryptionPolicy PowerShell, выполните эти действия.</span><span class="sxs-lookup"><span data-stu-id="0042f-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="0042f-136">С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в организации, подключите [к Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="0042f-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="0042f-137">Чтобы вернуть все dePs в организации, запустите Get-DataEncryptionPolicy без параметров.</span><span class="sxs-lookup"><span data-stu-id="0042f-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="0042f-138">Дополнительные сведения о Get-DataEncryptionPolicy см. в этой записи [в get-DataEncryptionPolicy.](/powershell/module/exchange/get-dataencryptionpolicy)</span><span class="sxs-lookup"><span data-stu-id="0042f-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="0042f-139">Назначение deP перед переносом почтового ящика в облако</span><span class="sxs-lookup"><span data-stu-id="0042f-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="0042f-140">При назначении deP Microsoft 365 шифрует содержимое почтового ящика с помощью назначенного deP во время миграции.</span><span class="sxs-lookup"><span data-stu-id="0042f-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="0042f-141">Этот процесс более эффективен, чем перенос почтового ящика, назначение deP и ожидание шифрования, которое может занять несколько часов или, возможно, дней.</span><span class="sxs-lookup"><span data-stu-id="0042f-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="0042f-142">Чтобы назначить deP почтовому ящику перед его переносом в Office 365, запустите Set-MailUser в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0042f-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="0042f-143">С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в организации, подключите [к Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="0042f-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="0042f-144">Запустите Set-MailUser.</span><span class="sxs-lookup"><span data-stu-id="0042f-144">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="0042f-145">Если *GeneralMailboxOrMailUserIdParameter* указывает почтовый ящик, а *DataEncryptionPolicyIdParameter* — это ID deP.</span><span class="sxs-lookup"><span data-stu-id="0042f-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="0042f-146">Дополнительные сведения о Set-MailUser см. в [списке Set-MailUser.](/powershell/module/exchange/set-mailuser)</span><span class="sxs-lookup"><span data-stu-id="0042f-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="0042f-147">Определение deP, назначенного почтовому ящику</span><span class="sxs-lookup"><span data-stu-id="0042f-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="0042f-148">Чтобы определить deP, назначенное почтовому ящику, используйте Get-MailboxStatistics.</span><span class="sxs-lookup"><span data-stu-id="0042f-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="0042f-149">В этом кодлете возвращается уникальный идентификатор (GUID).</span><span class="sxs-lookup"><span data-stu-id="0042f-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="0042f-150">С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в организации, подключите [к Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="0042f-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="0042f-151">Если *GeneralMailboxOrMailUserIdParameter* указывает почтовый ящик, а DataEncryptionPolicyID возвращает GUID deP.</span><span class="sxs-lookup"><span data-stu-id="0042f-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="0042f-152">Дополнительные сведения о Get-MailboxStatistics см. в [списке Get-MailboxStatistics.](/powershell/module/exchange/get-mailboxstatistics)</span><span class="sxs-lookup"><span data-stu-id="0042f-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="0042f-153">Запустите Get-DataEncryptionPolicy, чтобы узнать удобное имя deP, которому назначен почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0042f-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="0042f-154">Если *GUID* — это GUID, возвращаемая Get-MailboxStatistics на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="0042f-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="0042f-155">Убедитесь, что ключ клиента завершил шифрование</span><span class="sxs-lookup"><span data-stu-id="0042f-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="0042f-156">Если только что был свернут ключ клиента, назначен новый deP или перенесен почтовый ящик, используйте действия в этом разделе, чтобы обеспечить завершение шифрования.</span><span class="sxs-lookup"><span data-stu-id="0042f-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="0042f-157">Проверка завершения шифрования для Exchange Online и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0042f-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="0042f-158">Шифрование почтового ящика может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="0042f-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="0042f-159">Рекомендуется подождать 72 часа, прежде чем попытаться проверить шифрование после изменения deP или при первом назначении deP в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0042f-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="0042f-160">Используйте Get-MailboxStatistics, чтобы определить, зашифрован ли почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0042f-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="0042f-161">Свойство IsEncrypted возвращает значение  true, если почтовый ящик зашифрован,  а значение false, если почтовый ящик не зашифрован.</span><span class="sxs-lookup"><span data-stu-id="0042f-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="0042f-162">Время выполнения ходов почтовых ящиков зависит от размера почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="0042f-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="0042f-163">Если клиентский ключ не полностью шифрует почтовый ящик через 72 часа после назначения нового deP, обратитесь за помощью в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0042f-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, contact Microsoft support for help.</span></span> <span data-ttu-id="0042f-164">Этот New-MoveRequest больше не доступен для перемещения локальных почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="0042f-164">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="0042f-165">Дополнительные [сведения можно найти в](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) этом объявлении.</span><span class="sxs-lookup"><span data-stu-id="0042f-165">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="0042f-166">Проверка завершения шифрования для файлов SharePoint Online, OneDrive для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="0042f-166">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="0042f-167">Проверьте состояние шифрования, запуская Get-SPODataEncryptionPolicy следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0042f-167">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="0042f-168">Выход из этого комлета включает в себя:</span><span class="sxs-lookup"><span data-stu-id="0042f-168">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="0042f-169">URI основного ключа.</span><span class="sxs-lookup"><span data-stu-id="0042f-169">The URI of the primary key.</span></span>

- <span data-ttu-id="0042f-170">URI вторичного ключа.</span><span class="sxs-lookup"><span data-stu-id="0042f-170">The URI of the secondary key.</span></span>

- <span data-ttu-id="0042f-171">Состояние шифрования для гео.</span><span class="sxs-lookup"><span data-stu-id="0042f-171">The encryption status for the geo.</span></span> <span data-ttu-id="0042f-172">Возможные состояния:</span><span class="sxs-lookup"><span data-stu-id="0042f-172">Possible states include:</span></span>

  - <span data-ttu-id="0042f-173">**Незарегистрированные:** Шифрование ключа клиента еще не применено.</span><span class="sxs-lookup"><span data-stu-id="0042f-173">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="0042f-174">**Регистрация:** Шифрование ключа клиента было применено, и ваши файлы находятся в процессе шифрования.</span><span class="sxs-lookup"><span data-stu-id="0042f-174">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="0042f-175">Если ключ для георегистра регистрируется, вам также будет показана информация о том, какой процент сайтов в геополии завершен, чтобы можно было отслеживать ход шифрования.</span><span class="sxs-lookup"><span data-stu-id="0042f-175">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="0042f-176">**Зарегистрированы:** Было применено шифрование ключа клиента, и все файлы на всех сайтах были зашифрованы.</span><span class="sxs-lookup"><span data-stu-id="0042f-176">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="0042f-177">**Прокатка:** В настоящее время продолжается перекат ключей.</span><span class="sxs-lookup"><span data-stu-id="0042f-177">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="0042f-178">Если ключ для геоската катится, вам также будет показана информация о том, какой процент сайтов завершил операцию рулона ключа, чтобы можно было отслеживать ход выполнения.</span><span class="sxs-lookup"><span data-stu-id="0042f-178">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="unassign-a-dep-from-a-mailbox"></a><span data-ttu-id="0042f-179">Отогнать deP из почтового ящика</span><span class="sxs-lookup"><span data-stu-id="0042f-179">Unassign a DEP from a mailbox</span></span>

<span data-ttu-id="0042f-180">Вы отожмести deP из почтового ящика с помощью набора почтовых ящиков PowerShell и установите `DataEncryptionPolicy` параметр `$NULL` .</span><span class="sxs-lookup"><span data-stu-id="0042f-180">You unassign a DEP from a mailbox using the Set-mailbox PowerShell cmdlet and setting the `DataEncryptionPolicy` to `$NULL`.</span></span> <span data-ttu-id="0042f-181">При запуске этого cmdlet ненастоящается назначенное в настоящее время deP и повторное шифрование почтового ящика с помощью DEP, связанного с управляемыми ключами Майкрософт по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0042f-181">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft managed keys.</span></span> <span data-ttu-id="0042f-182">Нельзя отоименить deP, используемый управляемыми ключами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0042f-182">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="0042f-183">Если вы не хотите использовать управляемые ключи Майкрософт, вы можете назначить другому deP почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0042f-183">If you don't want to use Microsoft managed keys, you can assign another DEP to the mailbox.</span></span>

<span data-ttu-id="0042f-184">Чтобы отогнать deP из почтового ящика с помощью Set-Mailbox PowerShell, выполните эти действия.</span><span class="sxs-lookup"><span data-stu-id="0042f-184">To unassign the DEP from a mailbox using the Set-Mailbox PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="0042f-185">С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в организации, подключите [к Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="0042f-185">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="0042f-186">Запустите Set-Mailbox.</span><span class="sxs-lookup"><span data-stu-id="0042f-186">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="0042f-187">Отзовите ключи и запустите процесс очистки данных</span><span class="sxs-lookup"><span data-stu-id="0042f-187">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="0042f-188">Вы контролируете отзыв всех корневых ключей, включая ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="0042f-188">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="0042f-189">Ключ клиента обеспечивает контроль за аспектом планирования выхода из системы нормативных требований для вас.</span><span class="sxs-lookup"><span data-stu-id="0042f-189">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="0042f-190">Если вы решите отопустить ключи для очистки данных и выхода из службы, служба удаляет ключ доступности после завершения процесса очистки данных.</span><span class="sxs-lookup"><span data-stu-id="0042f-190">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="0042f-191">Microsoft 365 проверяет и проверяет путь очистки данных.</span><span class="sxs-lookup"><span data-stu-id="0042f-191">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="0042f-192">Дополнительные сведения см. в отчете SSAE 18 SOC 2, доступном на [портале доверия к службам.](https://servicetrust.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="0042f-192">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="0042f-193">Кроме того, Корпорация Майкрософт рекомендует следующие документы:</span><span class="sxs-lookup"><span data-stu-id="0042f-193">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="0042f-194">Руководство по оценке рисков и обеспечению соответствия требованиям для финансовых учреждений в Облаке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0042f-194">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="0042f-195">Соображения планирования выхода O365</span><span class="sxs-lookup"><span data-stu-id="0042f-195">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="0042f-196">Путь очистки данных незначительно различается между различными службами.</span><span class="sxs-lookup"><span data-stu-id="0042f-196">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="0042f-197">Отзовите ключи клиентов и ключ доступности для Exchange Online и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0042f-197">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="0042f-198">Когда вы инициируете путь очистки данных для Exchange Online и Skype для бизнеса, вы установите постоянный запрос на очистку данных в DEP.</span><span class="sxs-lookup"><span data-stu-id="0042f-198">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="0042f-199">Это навсегда удаляет зашифрованные данные в почтовых ящиках, которым назначен этот deP.</span><span class="sxs-lookup"><span data-stu-id="0042f-199">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="0042f-200">Так как вы можете запускать только комдлет PowerShell по одному deP одновременно, перед началом пути очистки данных рассмотрите возможность повторного перенанаружания единого deP для всех почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="0042f-200">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="0042f-201">Не используйте путь очистки данных для удаления подмножество почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="0042f-201">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="0042f-202">Этот процесс предназначен только для клиентов, которые выходят из службы.</span><span class="sxs-lookup"><span data-stu-id="0042f-202">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="0042f-203">Чтобы инициировать путь очистки данных, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0042f-203">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="0042f-204">Удалите разрешения на обертывание и открутку для "O365 Exchange Online" из хранилища ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="0042f-204">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="0042f-205">С помощью учетной записи работы или школы, которая имеет глобальные привилегии администратора в организации, подключите [к Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="0042f-205">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="0042f-206">Для каждого deP, который содержит почтовые ящики, которые необходимо удалить, выполните [набор-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0042f-206">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="0042f-207">Если команда не справилась с задачей, убедитесь, что вы удалили разрешения Exchange Online с обоих ключей в хранилище ключей Azure, как указано ранее в этой задаче.</span><span class="sxs-lookup"><span data-stu-id="0042f-207">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="0042f-208">После того как вы установите переключатель PermanentDataPurgeRequested с помощью Set-DataEncryptionPolicy, вы больше не сможете назначить этот deP почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="0042f-208"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="0042f-209">Обратитесь в службу поддержки Корпорации Майкрософт и запросите eDocument очистки данных.</span><span class="sxs-lookup"><span data-stu-id="0042f-209">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="0042f-210">По вашему запросу Корпорация Майкрософт отправляет вам юридический документ для подтверждения и авторизации удаления данных.</span><span class="sxs-lookup"><span data-stu-id="0042f-210">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="0042f-211">Человек в вашей организации, который зарегистрировался в качестве утвержденного в предложении FastTrack во время входной регистрации, должен подписать этот документ.</span><span class="sxs-lookup"><span data-stu-id="0042f-211">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="0042f-212">Как правило, это руководитель или другое назначенное лицо в вашей компании, которому по закону разрешено подписывать документы от имени вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0042f-212">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="0042f-213">После того как ваш представитель подписал юридический документ, верни его в Корпорацию Майкрософт (как правило, с помощью подписи eDoc).</span><span class="sxs-lookup"><span data-stu-id="0042f-213">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="0042f-214">Когда Корпорация Майкрософт получает юридический документ, Корпорация Майкрософт запускает комлеты, чтобы вызвать очистку данных, которая сначала удаляет политику, отмечает почтовые ящики для постоянного удаления, а затем удаляет ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="0042f-214">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="0042f-215">После завершения процесса очистки данных данные будут очищены, недоступны для Exchange Online и не будут восстановлены.</span><span class="sxs-lookup"><span data-stu-id="0042f-215">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="0042f-216">Отзовите ключи клиентов и ключ доступности для файлов SharePoint Online, OneDrive для бизнеса и teams</span><span class="sxs-lookup"><span data-stu-id="0042f-216">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="0042f-217">Чтобы инициировать путь очистки данных для файлов SharePoint Online, OneDrive для бизнеса и Teams, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0042f-217">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="0042f-218">Отзови доступ к хранилищем ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="0042f-218">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="0042f-219">Все администраторы хранилища ключей должны согласиться на отвод доступа.</span><span class="sxs-lookup"><span data-stu-id="0042f-219">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="0042f-220">Хранилище ключей Azure для SharePoint Online не удаляется.</span><span class="sxs-lookup"><span data-stu-id="0042f-220">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="0042f-221">Хранилища ключей могут быть общими для нескольких клиентов SharePoint Online и dePs.</span><span class="sxs-lookup"><span data-stu-id="0042f-221">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="0042f-222">Свяжитесь с Корпорацией Майкрософт, чтобы удалить ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="0042f-222">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="0042f-223">Когда вы обратитесь в Корпорацию Майкрософт, чтобы удалить ключ доступности, мы отправим вам юридический документ.</span><span class="sxs-lookup"><span data-stu-id="0042f-223">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="0042f-224">Человек в вашей организации, который зарегистрировался в качестве утвержденного в предложении FastTrack во время входной регистрации, должен подписать этот документ.</span><span class="sxs-lookup"><span data-stu-id="0042f-224">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="0042f-225">Как правило, это руководитель или другой назначенный человек в вашей компании, который имеет юридические права подписывать документы от имени организации.</span><span class="sxs-lookup"><span data-stu-id="0042f-225">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="0042f-226">Как только ваш представитель подпишет юридический документ, верни его в Microsoft (обычно с помощью подписи eDoc).</span><span class="sxs-lookup"><span data-stu-id="0042f-226">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="0042f-227">Когда Корпорация Майкрософт получает юридический документ, мы запускаем комлеты, чтобы вызвать очистку данных, которая выполняет крипто-удаление ключа клиента, ключа сайта и всех отдельных ключей каждого документа, безвозвратно нарушая иерархию ключей.</span><span class="sxs-lookup"><span data-stu-id="0042f-227">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="0042f-228">После завершения очистки данных данные будут очищены.</span><span class="sxs-lookup"><span data-stu-id="0042f-228">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0042f-229">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0042f-229">Related articles</span></span>

- [<span data-ttu-id="0042f-230">Шифрование службы с помощью ключа клиента</span><span class="sxs-lookup"><span data-stu-id="0042f-230">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="0042f-231">Узнайте о ключе доступности</span><span class="sxs-lookup"><span data-stu-id="0042f-231">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="0042f-232">Настройка ключа клиента</span><span class="sxs-lookup"><span data-stu-id="0042f-232">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="0042f-233">Смена или ротация ключа клиента или ключа доступности</span><span class="sxs-lookup"><span data-stu-id="0042f-233">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="0042f-234">Защищенное хранилище пользователя</span><span class="sxs-lookup"><span data-stu-id="0042f-234">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="0042f-235">Шифрование служб</span><span class="sxs-lookup"><span data-stu-id="0042f-235">Service Encryption</span></span>](office-365-service-encryption.md)